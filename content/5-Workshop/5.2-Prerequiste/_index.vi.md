---
title : "Điều kiện tiên quyết"
date: 2025-10-13
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

## Quyền IAM

Để triển khai FindNest Backend stack một cách an toàn, tuân thủ nguyên tắc least privilege, hãy thêm JSON policy sau vào IAM User của bạn.

Policy này tập trung nghiêm ngặt vào các dịch vụ được định nghĩa trong CDK code của bạn (DynamoDB, Cognito, Location, v.v.)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "FindnestDeploymentPermissions",
      "Effect": "Allow",
      "Action": [
        "cloudformation:*",
        "s3:*",
        "iam:*",
        "lambda:*",
        "apigateway:*",
        "dynamodb:*",
        "cognito-idp:*",
        "cognito-identity:*",
        "geo:*",
        "sns:*",
        "bedrock:*",
        "cloudwatch:*",
        "logs:*",
        "ssm:GetParameter",
        "sts:AssumeRole"
      ],
      "Resource": "*"
    }
  ]
}
```

## Cung cấp tài nguyên (CDK Bootstrap)

Trong lab này, chúng ta sẽ sử dụng **vùng N. Virginia (us-east-1)**. Để chuẩn bị môi trường workshop, chúng ta cần cung cấp các tài nguyên CDK Bootstrap. Quá trình này tạo ra một S3 Bucket để lưu trữ Lambda code và CloudFormation templates của bạn.

### 1. Cài đặt Dependencies

Đảm bảo bạn đã cài đặt các công cụ cốt lõi trên máy local:

```bash
npm install -g aws-cdk
```

### 2. Bootstrap môi trường

Chạy lệnh sau trong terminal để triển khai bootstrap stack. Chấp nhận tất cả các mặc định.

```bash
cdk bootstrap aws://<YOUR-ACCOUNT-ID>/us-east-1
```

*(Thay thế `<YOUR-ACCOUNT-ID>` bằng AWS Account ID 12 chữ số của bạn)*

Đợi CloudFormation stack **CDKToolkit** đạt trạng thái **CREATE_COMPLETE**. 1 S3 Bucket đã được tạo để lưu trữ assets. Môi trường hiện đã sẵn sàng cho triển khai serverless.