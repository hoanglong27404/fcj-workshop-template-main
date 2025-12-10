---
title : "Phân Tích Kiến Trúc Chi Tiết"
date: 2025-10-13
weight : 1 
chapter : false
pre : " <b> 5.3.1. </b> "
---

Hãy cùng tìm hiểu mã nguồn BackendStack để hiểu cách hệ thống hoạt động. Dưới đây là các đoạn mã chi tiết cho từng tài nguyên.

## 1. Cơ sở dữ liệu (Amazon DynamoDB)
Chúng ta khởi tạo 6 bảng DynamoDB sử dụng chế độ PAY_PER_REQUEST (On-Demand) để tối ưu chi phí và khả năng mở rộng.

```typescript
// 1. Bảng Listings (Cho thuê phòng)
const listingsTable = new dynamodb.Table(this, "ListingsTable", {
  tableName: "BoardingHouseListings",
  partitionKey: { name: "listingId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});

// 2. Bảng Hồ sơ người dùng
const userProfilesTable = new dynamodb.Table(this, "UserProfilesTable", {
  tableName: "UserProfiles",
  partitionKey: { name: "userId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});

// 3. Bảng OTP (Xác minh điện thoại) - Tự động xóa sau 5 phút (TTL)
const otpTable = new dynamodb.Table(this, "OTPVerifications", {
  tableName: "OTPVerifications",
  partitionKey: {
    name: "phoneNumber",
    type: dynamodb.AttributeType.STRING,
  },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  timeToLiveAttribute: "ttl", // Cấu hình TTL
  removalPolicy: RemovalPolicy.DESTROY,
});

// 4. Bảng Yêu thích - Bao gồm Sort Key để tra cứu nhanh theo người dùng
const favoritesTable = new dynamodb.Table(this, "FavoritesTable", {
  tableName: "UserFavorites",
  partitionKey: { name: "userId", type: dynamodb.AttributeType.STRING },
  sortKey: { name: "listingId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});

// 5. Bảng Yêu cầu hỗ trợ
const supportRequestsTable = new dynamodb.Table(this, "SupportRequestsTable", {
  tableName: "SupportRequests",
  partitionKey: {
    name: "requestId",
    type: dynamodb.AttributeType.STRING,
  },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  removalPolicy: RemovalPolicy.DESTROY,
});

// 6. Bảng Thông báo - Bao gồm TTL
const notificationsTable = new dynamodb.Table(this, "NotificationsTable", {
  tableName: "Notifications",
  partitionKey: { name: "userId", type: dynamodb.AttributeType.STRING },
  sortKey: { name: "notificationId", type: dynamodb.AttributeType.STRING },
  billingMode: dynamodb.BillingMode.PAY_PER_REQUEST,
  timeToLiveAttribute: "ttl",
  removalPolicy: RemovalPolicy.DESTROY,
});
```

## 2. Lưu trữ (Amazon S3)
Tạo S3 Bucket để lưu trữ hình ảnh phòng, được cấu hình với bảo mật chặn truy cập công khai và tự động xóa khi stack bị hủy.

```typescript
const imagesBucket = new s3.Bucket(this, "BoardingHouseImages", {
  bucketName: `findnest-images-${cdk.Aws.ACCOUNT_ID}`, // Tên bucket duy nhất
  removalPolicy: RemovalPolicy.DESTROY,
  autoDeleteObjects: true,
  blockPublicAccess: s3.BlockPublicAccess.BLOCK_ALL, // Riêng tư theo mặc định
});
```

## 3. Xác thực (Amazon Cognito)
Chúng ta cấu hình User Pool để quản lý người dùng và Identity Pool để cấp quyền truy cập trực tiếp Frontend vào tài nguyên AWS.

```typescript
// Tạo User Pool
const userPool = new cognito.UserPool(this, "UserPool", {
  userPoolName: "FindNestUsers",
  selfSignUpEnabled: false, // Người dùng được tạo qua API (Backend trigger)
  signInAliases: {
    phone: true, // Người dùng sử dụng Số điện thoại
    username: true, // Admin sử dụng Username
  },
  autoVerify: { phone: true },
  standardAttributes: {
    email: { required: false, mutable: true },
    phoneNumber: { required: false, mutable: true },
  },
  passwordPolicy: {
    minLength: 8,
    requireLowercase: true,
    requireUppercase: true,
    requireDigits: true,
    requireSymbols: true,
  },
  accountRecovery: cognito.AccountRecovery.PHONE_ONLY_WITHOUT_MFA,
  removalPolicy: RemovalPolicy.DESTROY,
});

// Tạo Client App
const userPoolClient = userPool.addClient("UserPoolClient", {
  authFlows: {
    userPassword: true,
    adminUserPassword: true, // Sử dụng cho Backend auth flow
    custom: true,
  },
});

// Nhóm người dùng
const usersGroup = new cognito.CfnUserPoolGroup(this, "UsersGroup", {
  userPoolId: userPool.userPoolId,
  groupName: "Users",
});

const landlordsGroup = new cognito.CfnUserPoolGroup(this, "LandlordsGroup", {
  userPoolId: userPool.userPoolId,
  groupName: "Landlords",
});

const adminsGroup = new cognito.CfnUserPoolGroup(this, "AdminsGroup", {
  userPoolId: userPool.userPoolId,
  groupName: "Admins",
});

// Identity Pool cho Frontend
const identityPool = new cognito.CfnIdentityPool(this, "IdentityPool", {
  identityPoolName: "FindNestMapAccess",
  allowUnauthenticatedIdentities: true, // Cho phép khách xem bản đồ
  cognitoIdentityProviders: [
    {
      clientId: userPoolClient.userPoolClientId,
      providerName: userPool.userPoolProviderName,
    },
  ],
});
```

## 4. Dịch vụ Vị trí (Bản đồ & Geocoding)
Khởi tạo tài nguyên Location Service sử dụng nhà cung cấp dữ liệu Here để có phạm vi POI tốt hơn tại Việt Nam.

```typescript
const placeIndex = new location.CfnPlaceIndex(this, "PlaceIndex", {
  indexName: `FindNestPlacesV3-${cdk.Aws.ACCOUNT_ID}`,
  dataSource: "Here", // Phạm vi POI tốt hơn cho châu Á (Việt Nam)
  dataSourceConfiguration: {
    intendedUse: "Storage", // Cho phép lưu trữ và truy vấn dữ liệu POI
  },
});

const map = new location.CfnMap(this, "Map", {
  mapName: `FindNestMap-${cdk.Aws.ACCOUNT_ID}`,
  configuration: { style: "VectorEsriStreets" },
});

const routeCalculator = new location.CfnRouteCalculator(
  this,
  "RouteCalculator",
  {
    calculatorName: `FindNestRoutesV3-${cdk.Aws.ACCOUNT_ID}`,
    dataSource: "Here",
  }
);
```

## 5. Tính toán (AWS Lambda Monolith)
Cấu hình Lambda Function chứa toàn bộ logic Backend, bao gồm việc tiêm biến môi trường đầy đủ.

```typescript
const apiLambda = new lambda.Function(this, "ApiLambda", {
  functionName: "FindNestApi",
  runtime: lambda.Runtime.NODEJS_20_X,
  handler: "index.handler",
  code: lambda.Code.fromAsset(path.join(__dirname, "../../backend/src/lambda")),
  timeout: cdk.Duration.seconds(30),
  logGroup: logGroup,
  environment: {
    // Biến môi trường kết nối tài nguyên
    LISTINGS_TABLE_NAME: listingsTable.tableName,
    USER_PROFILES_TABLE_NAME: userProfilesTable.tableName,
    OTP_TABLE_NAME: otpTable.tableName,
    FAVORITES_TABLE_NAME: favoritesTable.tableName,
    SUPPORT_REQUESTS_TABLE_NAME: supportRequestsTable.tableName,
    NOTIFICATIONS_TABLE_NAME: notificationsTable.tableName,
    IMAGES_BUCKET_NAME: imagesBucket.bucketName,
    USER_POOL_ID: userPool.userPoolId,
    USER_POOL_CLIENT_ID: userPoolClient.userPoolClientId,
    PLACE_INDEX_NAME: placeIndex.indexName,
    MAP_NAME: map.mapName,
    ROUTE_CALCULATOR_NAME: routeCalculator.calculatorName,
    BEDROCK_MODEL_ID: "anthropic.claude-3-sonnet-20240229-v1:0",
    REGION: cdk.Aws.REGION,
  },
});
```

## 6. Quyền hạn (Kiểm soát truy cập chi tiết)
Chúng ta cấp Quyền hạn Chi tiết cho Lambda Function. Đây là danh sách đầy đủ các quyền được cấp:

### A. Quyền Đọc/Ghi vào Database và S3:

```typescript
listingsTable.grantReadWriteData(apiLambda);
userProfilesTable.grantReadWriteData(apiLambda);
otpTable.grantReadWriteData(apiLambda);
favoritesTable.grantReadWriteData(apiLambda);
supportRequestsTable.grantReadWriteData(apiLambda);
notificationsTable.grantReadWriteData(apiLambda);
imagesBucket.grantReadWrite(apiLambda);
```

### B. Quản lý người dùng trong Cognito (Toàn quyền Admin):

```typescript
apiLambda.addToRolePolicy(
  new iam.PolicyStatement({
    actions: [
      "cognito-idp:AdminCreateUser",
      "cognito-idp:AdminSetUserPassword",
      "cognito-idp:AdminInitiateAuth",
      "cognito-idp:AdminGetUser",
      "cognito-idp:AdminAddUserToGroup",
      "cognito-idp:AdminRemoveUserFromGroup",
      "cognito-idp:AdminListGroupsForUser",
      "cognito-idp:AdminUpdateUserAttributes",
      "cognito-idp:AdminEnableUser",
      "cognito-idp:AdminDisableUser",
      "cognito-idp:AdminDeleteUser",
      "cognito-idp:ListUsers",
      "cognito-idp:GlobalSignOut",
    ],
    resources: [userPool.userPoolArn],
  })
);
```

### C. Tích hợp với các dịch vụ khác (SNS, Bedrock, Location):

```typescript
// Gửi SMS (OTP)
apiLambda.addToRolePolicy(
  new iam.PolicyStatement({
    actions: ["sns:Publish"],
    resources: ["*"],
  })
);

// Gọi AI (Claude 3)
apiLambda.addToRolePolicy(
  new iam.PolicyStatement({
    actions: ["bedrock:InvokeModel"],
    resources: ["arn:aws:bedrock:*::foundation-model/anthropic.claude-3-*"],
  })
);

// Truy cập Location Service
apiLambda.addToRolePolicy(
  new iam.PolicyStatement({
    actions: [
      "geo:SearchPlaceIndexForText",
      "geo:GetPlace",
      "geo:CalculateRoute",
      "geo:SearchPlaceIndexForPosition",
    ],
    resources: [placeIndex.attrArn, routeCalculator.attrArn],
  })
);
```

## 7. API Gateway (REST API)
Tạo Endpoint công khai để client gọi Lambda function.

```typescript
const api = new apigateway.LambdaRestApi(this, "BoardingHouseApi", {
  handler: apiLambda,
  proxy: true,
  deployOptions: {
    stageName: "prod",
    throttlingBurstLimit: 100,
    throttlingRateLimit: 50,
  },
  defaultCorsPreflightOptions: {
    allowOrigins: apigateway.Cors.ALL_ORIGINS,
    allowMethods: apigateway.Cors.ALL_METHODS,
    allowHeaders: ["Content-Type", "Authorization"],
  },
  restApiName: "FindNestAPI",
});
```

## 8. Giám sát & Quan sát (CloudWatch)
Chúng ta triển khai giám sát toàn diện với CloudWatch Dashboard, Alarms và SNS Notifications.

### A. SNS Alert Topic:

```typescript
const alertTopic = new sns.Topic(this, "AlertTopic", {
  topicName: "BoardingHouseAlerts",
  displayName: "Smart Boarding House Alerts",
});

alertTopic.addSubscription(
  new snsSubscriptions.EmailSubscription("admin@smartboardinghouse.com")
);
```

### B. CloudWatch Alarms:

```typescript
// Lambda Error Alarm
const lambdaErrorAlarm = new cloudwatch.Alarm(this, "LambdaErrorAlarm", {
  alarmName: "BoardingHouse-Lambda-Errors",
  metric: new cloudwatch.Metric({
    namespace: "AWS/Lambda",
    metricName: "Errors",
    dimensionsMap: { FunctionName: lambdaFunctionName },
    statistic: "Sum",
  }),
  threshold: 5,
  evaluationPeriods: 2,
});
```

### Tính năng Dashboard:

- Metrics Lambda: Invocations, Errors, Throttles, Duration, Concurrency
- Metrics API Gateway: Requests, Latency (Avg & P99), 4XX/5XX Errors
- Metrics DynamoDB: Read/Write Capacity, User Errors per table
- Metrics Bedrock AI: Token Usage (Input/Output), Invocations, Latency
- Tóm tắt Sức khỏe Hệ thống: Error Rates, Response Time, Total Requests (24h)
- Cảnh báo Tự động: Thông báo email qua SNS khi vượt ngưỡng