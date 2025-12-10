---
title : "Deploy Stack"
date: 2025-10-13
weight : 3 
chapter : false
pre : " <b> 5.3.3. </b> "
---

Bây giờ, hãy biến thiết kế này thành hiện thực.

## Bước 1: Synthesize
Chạy lệnh synthesize để tạo CloudFormation template:

```bash
cdk synth
```

Lệnh này tạo CloudFormation template trong thư mục cdk.out. Nếu không có lỗi màu đỏ nào xuất hiện, bạn có thể tiếp tục.

Quá trình synthesize chuyển đổi mã CDK (TypeScript) thành CloudFormation template (JSON/YAML).

## Bước 2: Deploy
Deploy stack lên AWS:

```bash
cdk deploy --require-approval never
```

Flag --require-approval never bỏ qua prompt xác nhận cho các thay đổi IAM.

Quá trình deployment sẽ mất khoảng 5-10 phút để cung cấp tất cả tài nguyên.

Trong quá trình deployment, bạn sẽ thấy:

- Tiến trình tạo CloudFormation stack
- Các tài nguyên riêng lẻ được tạo (DynamoDB tables, Lambda functions, API Gateway, v.v.)
- Cập nhật trạng thái cho từng tài nguyên

Chờ deployment hoàn thành thành công trước khi tiếp tục bước tiếp theo.