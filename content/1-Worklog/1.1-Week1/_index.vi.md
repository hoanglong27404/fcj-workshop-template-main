---
title: "Worklog Tuần 1"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1

- Khởi tạo và bảo vệ tài khoản AWS đầu tiên:
  - Tạo tài khoản AWS mới, bật MFA cho Root user
  - Tạo nhóm/quyền Administrator, tạo tài khoản quản trị
  - Hỗ trợ xác thực tài khoản khi cần
  - Làm quen và cấu hình AWS Management Console
- Quản lý chi phí với AWS Budgets:
  - Tạo Cost Budget, Usage Budget, Reservation Budget, Savings Plans Budget
  - Thiết lập cảnh báo và quy trình dọn dẹp tài nguyên
- Tổng quan AWS Support (kênh hỗ trợ và phạm vi dịch vụ)
- Quản trị truy cập với IAM: User, Group, Role, Switch Role
- Kiến thức mạng với VPC:
  - Giới thiệu VPC, khác biệt Security Group và Network ACL
  - Chuẩn bị môi trường, triển khai EC2
  - Dọn dẹp tài nguyên sau khi lab

### Các công việc cần triển khai trong tuần này

<!-- markdownlint-disable MD033 -->

| Thứ | Công việc                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                                    |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 2   | Tạo tài khoản AWS mới:<br>- Bật MFA cho Root<br>+ Tạo nhóm/quyền Administrator<br>+ Tạo tài khoản quản trị<br>- Làm quen và cấu hình Console                      | 08/09/2025   | 08/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | Thiết lập AWS Budgets:<br>- Cost Budget<br>+ Usage Budget<br>+ Reservation Budget<br>+ Savings Plans Budget<br>- Cấu hình cảnh báo<br>- Rà soát quy trình dọn dẹp | 09/09/2025   | 09/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | IAM:<br>- Tạo User, Group<br>+ Gán policy<br>+ Tạo Role<br>- Thực hành Switch Role<br>- Áp dụng nguyên tắc least privilege                                        | 10/09/2025   | 10/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | VPC:<br>- Tổng quan<br>+ So sánh Security Group vs NACL<br>- Chuẩn bị môi trường mạng cho lab                                                                     | 11/09/2025   | 11/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | EC2:<br>- Triển khai EC2 trong subnet<br>+ Cấu hình Security Group<br>- Dọn dẹp tài nguyên                                                                        | 12/09/2025   | 12/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |

<!-- markdownlint-enable MD033 -->

### Kết quả đạt được tuần 1

#### Đã làm được gì

- Tạo tài khoản AWS với tín dụng miễn phí $100 và thiết lập bảo mật MFA
- Tạo IAM user riêng để tránh dùng Root account trong thực hành
- Thiết lập budget $50/tháng với cảnh báo tự động để kiểm soát chi phí học tập
- Nắm vững cách phân quyền IAM và thực hành Switch Role giữa các môi trường
- Hiểu kiến trúc VPC cơ bản và cách bảo vệ tài nguyên bằng Security Group
- Triển khai EC2 instance đầu tiên và SSH vào server thành công
