---
title : "Kết Quả & Outputs"
date: 2025-10-13
weight : 4 
chapter : false
pre : " <b> 5.3.4. </b> "
---

Sau khi deployment thành công, terminal sẽ hiển thị phần Outputs màu xanh. Đây là các tham số quan trọng để kết nối Frontend với Backend.

## Stack Outputs
VUI LÒNG SAO CHÉP VÀ LƯU CÁC GIÁ TRỊ NÀY:

```
BackendStack

Outputs:
BackendStack.ApiUrl = https://xyz123.execute-api.us-east-1.amazonaws.com/prod/
BackendStack.UserPoolId = us-east-1_AbCdEfGh
BackendStack.UserPoolClientId = 1a2b3c4d5e6f7g8h9i0j
BackendStack.IdentityPoolId = us-east-1:12345678-abcd-1234-abcd-1234567890ab
BackendStack.ImagesBucket = findnest-images-123456789012
BackendStack.MapName = FindNestMap-123456789012
BackendStack.PlaceIndexName = FindNestPlacesV3-123456789012
BackendStack.RouteCalculatorName = FindNestRoutesV3-123456789012
BackendStack.Region = us-east-1

MonitoringStack

Outputs:
MonitoringStack.AlertTopicArn = arn:aws:sns:us-east-1:123456789012:BoardingHouseAlerts
MonitoringStack.DashboardUrl = https://us-east-1.console.aws.amazon.com/cloudwatch/home?region=us-east-1#dashboards:name=SmartBoardingHouse-Monitoring
```

## Giải Thích Tham Số Output

| Tham số | Mô tả | Sử dụng |
|---------|-------|---------|
| ApiUrl | Endpoint cho Backend API | Được Frontend sử dụng để thực hiện API calls |
| UserPoolId | Định danh Cognito User Pool | Sử dụng cho xác thực người dùng (Login/Register) |
| UserPoolClientId | Định danh Cognito App Client | Sử dụng cho xác thực người dùng (Login/Register) |
| IdentityPoolId | Định danh Cognito Identity Pool | Sử dụng để hiển thị bản đồ trên Frontend |
| ImagesBucket | Tên S3 bucket cho hình ảnh | Sử dụng để lưu trữ và truy xuất hình ảnh phòng |
| MapName | Tên bản đồ Location Service | Sử dụng để hiển thị bản đồ trên ứng dụng Frontend |
| PlaceIndexName | Place index Location Service | Sử dụng cho geocoding và chức năng tìm kiếm |
| RouteCalculatorName | Route calculator Location Service | Sử dụng để tính toán tuyến đường giữa các vị trí |
| Region | AWS region | Region nơi tài nguyên được deploy |
| AlertTopicArn | SNS Topic ARN cho cảnh báo | Đăng ký topic này để nhận cảnh báo hệ thống |
| DashboardUrl | URL CloudWatch Dashboard | Truy cập dashboard giám sát để xem metrics hệ thống |

## Bước Tiếp Theo
Lưu các outputs này ở nơi an toàn. Bạn sẽ cần chúng để cấu hình ứng dụng Frontend trong phần tiếp theo.

Bạn cũng có thể lấy lại các outputs này sau bằng cách chạy lại cdk deploy hoặc kiểm tra CloudFormation stack outputs trong AWS Console.

## Chúc Mừng
Bạn đã triển khai thành công hệ thống Backend Serverless hiện đại, tích hợp với:

- AI (Amazon Bedrock với Claude 3)
- Bản đồ Số (Amazon Location Service)
- Quyền bảo mật nghiêm ngặt (IAM)
- Cơ sở dữ liệu có thể mở rộng (DynamoDB)
- Xác thực người dùng (Cognito)
- RESTful API (API Gateway + Lambda)
- Giám sát toàn diện (CloudWatch Dashboard & Alarms)
- Cảnh báo thời gian thực (SNS Notifications)