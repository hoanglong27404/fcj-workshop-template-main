---
title: "Worklog Tuần 7"
date: 2025-10-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu Tuần 7:

* Tìm hiểu về Amazon Cognito - dịch vụ quản lý danh tính và xác thực người dùng
* Thực hành tạo User Pools và cấu hình xác thực
* Tìm hiểu về Amazon Location Service - dịch vụ định vị và bản đồ
* Tích hợp Cognito với ứng dụng và Location Service

### Công việc thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | -------- | ------------ | --------------- | ------------------ |
| 2 | Học các khái niệm cơ bản về Cognito: User Pools vs Identity Pools, luồng xác thực và các trường hợp sử dụng. Tạo một User Pool đơn giản với chính sách mật khẩu. | 26/10/2025 | 27/10/2025 | <https://docs.aws.amazon.com/cognito/latest/developerguide/user-pools.html> |
| 3 | Cấu hình Cognito User Pool: thêm người dùng, thiết lập xác minh email, xác thực đa yếu tố (MFA) và khôi phục mật khẩu. | 27/10/2025 | 28/10/2025 | <https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-lambda-custom-message.html> |
| 4 | Tìm hiểu Amazon Location Service: tạo tài nguyên bản đồ, sử dụng tìm kiếm địa điểm và tính toán tuyến đường. Kiểm tra các API cơ bản. | 28/10/2025 | 29/10/2025 | <https://docs.aws.amazon.com/location/latest/developerguide/what-is.html> |
| 5 | Tích hợp Cognito với Location Service: cấu hình IAM roles để cho phép người dùng Cognito truy cập tài nguyên Location Service. Kiểm tra quy trình end-to-end. | 29/10/2025 | 30/10/2025 | <https://docs.aws.amazon.com/cognito/latest/developerguide/iam-roles.html> |
| 6 | Tổng kết: xem xét cấu hình bảo mật cho cả Cognito và Location Service, kiểm tra CloudWatch logs và dọn dẹp tài nguyên. Ghi chép các bước quan trọng. | 30/10/2025 | 1/11/2025 | Ghi chú cá nhân |

---

### Kết quả đạt được Tuần 7:

#### Cognito User Pool:

* Tạo thành công User Pool với các cấu hình bảo mật
* Thêm người dùng và cấu hình xác thực (xác minh email, MFA)
* Hiểu về luồng xác thực và JWT tokens

#### Cognito Identity Pool:

* Học cách cấp quyền tạm thời cho người dùng chưa xác thực
* Cấu hình IAM roles cho Cognito identities

#### Location Service:

* Tạo tài nguyên bản đồ và kiểm tra APIs
* Sử dụng tìm kiếm địa điểm và tính toán tuyến đường
* Hiểu về mô hình định giá

#### Tích hợp:

* Tích hợp thành công xác thực Cognito với tài nguyên Location Service
* Cấu hình IAM policies cho quyền truy cập người dùng
* Xác minh quy trình end-to-end

#### Kết luận:

Tuần này đề cập đến quản lý danh tính AWS và các dịch vụ định vị. Kết hợp Cognito với Location Service cho phép xây dựng các ứng dụng nhận biết vị trí với xác thực người dùng an toàn.


