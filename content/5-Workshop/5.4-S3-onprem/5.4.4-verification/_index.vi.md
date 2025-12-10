---
title : "Xác minh"
date: 2025-10-13
weight : 4
chapter : false
pre : " <b> 5.4.4. </b> "
---

Hãy đảm bảo user tồn tại trong cả dịch vụ Authentication và Database.

## A. Kiểm tra Cognito (Authentication)
1. Vào Amazon Cognito Console
2. Chọn User Pool **FindNestUsers**
3. Vào tab **Users**
4. Bạn sẽ thấy superadmin với trạng thái **Confirmed**.

Nhấp vào user và xác minh họ có trong nhóm **Admins**.

User phải có:
- **Status**: CONFIRMED (không phải FORCE_CHANGE_PASSWORD)
- **Group membership**: Admins

## B. Kiểm tra DynamoDB (Data)
1. Vào DynamoDB Console
2. Chọn bảng **UserProfiles**
3. Nhấp **Explore table items**
4. Tìm kiếm item có userId khớp với ID từ script output.

Bạn sẽ thấy dữ liệu profile với `userType: "admin"`.

## Danh sách Xác minh
Xác nhận những điều sau trước khi tiếp tục:

- User tồn tại trong Cognito User Pool với trạng thái CONFIRMED
- User là thành viên của nhóm Admins
- User profile tồn tại trong bảng DynamoDB UserProfiles
- Profile có userType được đặt thành "admin"
- Tất cả thuộc tính user (email, fullName) được điền đúng

## Bước Tiếp theo
Bây giờ bạn đã sẵn sàng đăng nhập và kiểm tra hệ thống!

Tài khoản Super Admin của bạn đã sẵn sàng sử dụng. Bây giờ bạn có thể xác thực với API bằng các thông tin đăng nhập này.

Giữ thông tin đăng nhập admin an toàn. Cân nhắc sử dụng AWS Secrets Manager cho môi trường production.