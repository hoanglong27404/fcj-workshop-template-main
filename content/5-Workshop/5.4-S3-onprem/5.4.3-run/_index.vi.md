---
title : "Chạy Script"
date: 2025-10-13
weight : 3
chapter : false
pre : " <b> 5.4.3. </b> "
---

Bây giờ, thực thi script. Nó có tính tương tác, vì vậy sẽ hỏi bạn các thông tin chi tiết.

## Thực thi script

```bash
node seed-admin.js
```

## Hướng dẫn Tương tác
Script sẽ nhắc bạn nhập các thông tin sau:

- **Username**: Nhập username (ví dụ: superadmin)
- **Password**: Nhập mật khẩu mạnh (tối thiểu 8 ký tự, chữ hoa, chữ thường, số, ký tự đặc biệt)
- **Email**: Nhập địa chỉ email hợp lệ
- **Full Name**: Nhập tên hiển thị
- **Confirm**: Gõ yes để tiếp tục

## Kết quả Mong đợi
Nếu mọi thứ được cấu hình đúng, bạn sẽ thấy output tương tự như sau:

```
* Environment variables loaded:
   Region: us-east-1
   User Pool ID: us-east-1_xxxxxx
   User Profiles Table: UserProfiles

📝 Creating admin user in Cognito...
   * User created with ID: xxxx-xxxx-xxxx
🔑 Setting permanent password...
   * Password set
👑 Adding user to Admins group...
   * Added to Admins group
📝 Creating admin profile in DynamoDB...
   * Profile created

═══════════════════════════════════════════════
* ADMIN USER CREATED SUCCESSFULLY!
═══════════════════════════════════════════════
Save the credentials! You'll need the username and password to log in to the system.
```

Nếu bạn gặp lỗi:

- Kiểm tra file .env có các giá trị đúng
- Xác minh AWS credentials đã được cấu hình (aws configure)
- Đảm bảo bạn có các quyền IAM cần thiết
- Đảm bảo CDK stack đã được deploy thành công

## Script thực hiện gì
Script thực hiện các thao tác sau:

- Tạo user trong Cognito User Pool với username và password được cung cấp
- Đặt password là vĩnh viễn (không cần thay đổi khi đăng nhập lần đầu)
- Thêm user vào nhóm "Admins" để có quyền nâng cao
- Tạo bản ghi profile trong DynamoDB với thông tin user