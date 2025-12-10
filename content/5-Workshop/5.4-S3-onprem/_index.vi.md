---
title : "Seeding Data"
date: 2025-10-13
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

## Tại sao cần seed data?

Hạ tầng của bạn đã sẵn sàng, nhưng cơ sở dữ liệu vẫn trống. Bạn cần một tài khoản "Super Admin" để quản lý hệ thống.

Chúng ta sẽ chạy một script Node.js kết nối trực tiếp với AWS để:

- Tạo User trong Cognito User Pool
- Thêm user đó vào Admins Group
- Tạo profile tương ứng trong bảng DynamoDB UserProfiles

## Nội dung

1. [Thiết lập Script](5.4.1-setup/)
2. [Cấu hình Environment](5.4.2-configure/)
3. [Chạy Script](5.4.3-run/)
4. [Xác minh](5.4.4-verification/)