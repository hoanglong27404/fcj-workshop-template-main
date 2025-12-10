---
title : "Cài Đặt Dependencies"
date: 2025-10-13
weight : 2 
chapter : false
pre : " <b> 5.3.2. </b> "
---

Hệ thống bao gồm hai phần mã nguồn cần cài đặt dependencies.

## Bước 1: Cài đặt cho Backend
Điều hướng đến thư mục backend Lambda và cài đặt các gói Node.js cần thiết:

```bash
cd backend/src/lambda
npm install
```

Lệnh này sẽ cài đặt tất cả dependencies được định nghĩa trong file package.json cho Lambda function.

## Bước 2: Cài đặt cho CDK
Quay lại thư mục gốc CDK và cài đặt CDK dependencies:

```bash
# Quay lại thư mục gốc CDK
cd ../../../cdk
npm install
```

Lệnh này cài đặt các thư viện AWS CDK và constructs cần thiết để synthesize và deploy infrastructure.

Đảm bảo bạn đã cài đặt Node.js và npm trên máy trước khi chạy các lệnh này.