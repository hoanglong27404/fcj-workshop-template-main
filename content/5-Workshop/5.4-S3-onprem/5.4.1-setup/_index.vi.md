---
title : "Thiết lập Script"
date: 2025-10-13
weight : 1
chapter : false
pre : " <b> 5.4.1. </b> "
---

## Bước 1: Điều hướng đến thư mục
Điều hướng đến thư mục scripts nơi chứa seeding script:

```bash
cd backend/scripts
```

## Bước 2: Cài đặt dependencies
Script sử dụng AWS SDK v3. Cài đặt các gói cần thiết:

```bash
npm install
```

Lệnh này sẽ cài đặt tất cả dependencies được định nghĩa trong file package.json, bao gồm:

- @aws-sdk/client-cognito-identity-provider - Cho các thao tác Cognito
- @aws-sdk/client-dynamodb - Cho các thao tác DynamoDB
- dotenv - Cho quản lý biến môi trường
- Các dependencies cần thiết khác

Đảm bảo bạn đang ở trong thư mục backend/scripts trước khi chạy npm install.

Chờ quá trình cài đặt hoàn thành thành công trước khi tiếp tục bước tiếp theo.