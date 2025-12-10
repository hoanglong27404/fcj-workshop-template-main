---
title : "Cấu hình Environment"
date: 2025-10-13
weight : 2
chapter : false
pre : " <b> 5.4.2. </b> "
---

Script (seed-admin.js) tìm kiếm các biến môi trường cụ thể để kết nối với tài nguyên AWS của bạn. Bạn cần tạo file .env với các giá trị từ CDK Deployment Output.

## Tạo file .env
Tạo file có tên .env trong thư mục backend/scripts với nội dung sau:

```bash
# Nội dung file .env
REGION=us-east-1
USER_POOL_ID=<Paste_Value_From_CDK_Output>
USER_PROFILES_TABLE_NAME=UserProfiles
```

## Giải thích Biến Môi trường

| Biến | Mô tả | Nơi tìm |
|------|-------|---------|
| REGION | AWS region nơi tài nguyên được deploy | us-east-1 (hoặc ap-southeast-1 nếu bạn đã thay đổi) |
| USER_POOL_ID | Định danh Cognito User Pool | Sao chép giá trị BackendStack.UserPoolId từ terminal sau khi cdk deploy |
| USER_PROFILES_TABLE_NAME | Tên bảng DynamoDB cho user profiles | Trong mã CDK, chúng ta đặt tên bảng là UserProfiles. Nếu bạn đã thay đổi, kiểm tra DynamoDB Console để biết tên chính xác |

## Ví dụ Cấu hình

```bash
# Ví dụ file .env
REGION=us-east-1
USER_POOL_ID=us-east-1_AbCdEfGh
USER_PROFILES_TABLE_NAME=UserProfiles
```

Đảm bảo thay thế `<Paste_Value_From_CDK_Output>` bằng giá trị thực tế từ CDK deployment outputs của bạn!

Bạn có thể tìm CDK outputs bằng cách cuộn lên trong terminal hoặc chạy lại cdk deploy (nó sẽ không redeploy nếu không có gì thay đổi).