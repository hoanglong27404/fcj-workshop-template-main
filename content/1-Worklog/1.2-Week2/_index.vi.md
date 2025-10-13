---
title: "Worklog Tuần 2"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2

- Thiết lập Hybrid DNS với Route 53 Resolver (giới thiệu, kiến trúc, các thành phần).
- Thực hành: tạo Key Pair, khởi tạo CloudFormation template, cấu hình Security Group.
- Kết nối RDGW, thiết lập DNS, tạo Outbound/Inbound Endpoints và Resolver Rules.
- Dọn dẹp tài nguyên sau khi hoàn tất lab.

### Các công việc cần triển khai trong tuần này

<!-- markdownlint-disable MD033 -->

| Thứ | Công việc                                                                                                                                                                                                                                                                                                               | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                                    |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 2   | Thiết lập Hybrid DNS với Route 53 Resolver:<br>- Generate Key Pair<br>+ Initialize CloudFormation Template<br>+ Configure Security Group<br>- Connect to RDGW<br>- Set up DNS<br>+ Create Route 53 Outbound Endpoint<br>+ Create Route 53 Resolver Rules<br>+ Create Route 53 Inbound Endpoints<br>- Clean up resources | 15/09/2025   | 15/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | Ôn tập lại các kiến thức đã học (Hybrid DNS, RDGW, DNS, Endpoints/Rules)                                                                                                                                                                                                                                                | 16/09/2025   | 16/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | Set up VPC peering:<br>- Set up VPC peering (Introduction)<br>+ Initialize CloudFormation Templates<br>+ Create Security group<br>- Create EC2 instance<br>- Update Network ACL (NACLs)<br>+ Create a peering connection<br>+ Configure Route tables<br>- Enable Cross-Peer DNS                                         | 17/09/2025   | 17/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | Set up AWS Transit Gateway:<br>- Set up AWS Transit Gateway (Introduction)<br>+ Create Transit Gateway<br>+ Create Transit Gateway Attachments<br>- Create Transit Gateway Route Tables<br>- Add Transit Gateway Routes to VPC Route Tables                                                                             | 18/09/2025   | 18/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | Tìm giải pháp lên ý tưởng cho project                                                                                                                                                                                                                                                                                   | 19/09/2025   | 19/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |

<!-- markdownlint-enable MD033 -->

### Kết quả đạt được tuần 2

#### Đã làm được gì

- Thiết lập Hybrid DNS lab để mô phỏng kết nối trường đại học với AWS
- Cấu hình VPC Peering để kết nối môi trường dev và staging
- Triển khai Transit Gateway để quản lý nhiều VPC trong project lớn
- Thực hành CloudFormation để tự động hóa deployment infrastructure
- Lên kế hoạch cho đồ án cuối kỳ sử dụng kiến thức AWS đã học
