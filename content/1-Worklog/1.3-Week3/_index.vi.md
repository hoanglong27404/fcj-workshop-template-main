---
title: "Worklog Tuần 3"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3

- Tìm hiểu sâu về EC2: Windows/Linux instances, AMI, EBS, cost governance.
- Nắm vững IAM Role và làm quen với AWS Cloud9 development environment.
- Triển khai Amazon S3 cho static website hosting và multi-region replication.
- Tạo và quản lý database với Amazon RDS và tối ưu chi phí với Lightsail.
- Thiết lập hệ thống tự động: Autoscaling, CloudWatch monitoring, hybrid DNS với Route53.

### Các công việc cần triển khai trong tuần này

<!-- markdownlint-disable MD033 -->

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 2   | Tìm hiểu sâu về EC2:<br>- Khởi tạo Windows Instance (Tạo & Kết nối Microsoft Windows Server 2022)<br>+ Khởi tạo Linux Instance (Tạo & Kết nối Amazon Linux)<br>+ Kiến thức cơ bản EC2 (Sửa đổi cấu hình Instance)<br>- Tạo và Quản lý EBS Snapshots<br>- Xây dựng Custom AMI & Khởi chạy từ Custom AMI<br>+ Khôi phục truy cập (Windows qua Systems Manager, Linux qua User Data)<br>+ Cấu hình GUI Desktop cho Ubuntu 22.04<br>- Triển khai EBS Volume Archiving<br>+ Deploy ứng dụng AWS User Management (Linux & Windows)<br>- Quản trị Chi phí & Sử dụng (Hạn chế theo Region/Instance Family/Type) | 22/09/2025   | 22/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | IAM Role & AWS Cloud9 & Amazon S3:<br>- Tìm hiểu IAM Role (AWS IAM)<br>+ Làm quen với AWS Cloud9<br>+ Amazon S3: Enable Static website<br>- Configure public access block<br>- Configure public object<br>+ Test website<br>+ Tăng tốc Static website host trên S3<br>- Bucket Versioning<br>- Move Object<br>+ Replication Object multi Region                                                                                                                                                                                                                                                         | 23/09/2025   | 23/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | Amazon RDS & Amazon Lightsail:<br>- Tạo cơ sở dữ liệu trên Amazon Relational Database Service (Amazon RDS)<br>+ Tối ưu hóa chi phí tính toán với Amazon Lightsail                                                                                                                                                                                                                                                                                                                                                                                                                                       | 24/09/2025   | 24/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | EC2 Autoscaling & CloudWatch & Route53:<br>- Tự động hóa mở rộng ứng dụng với Amazon EC2 Autoscaling<br>+ Tạo hệ thống giám sát với Amazon CloudWatch<br>- Thiết lập hệ thống hybrid DNS tích hợp giữa Local và Amazon VPC với Amazon Route53                                                                                                                                                                                                                                                                                                                                                           | 25/09/2025   | 25/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | Ôn tập tổng hợp:<br>- Ôn tập lại toàn bộ các phần đã làm từ tuần 1<br>+ Củng cố kiến thức về IAM, VPC, EC2, S3, RDS<br>- Ôn tập các kỹ năng thực hành đã học                                                                                                                                                                                                                                                                                                                                                                                                                                            | 26/09/2025   | 26/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |

<!-- markdownlint-enable MD033 -->

### Kết quả đạt được tuần 3

#### Đã làm được gì

- Triển khai EC2 toàn diện: Windows Server 2022, Linux instances, custom AMI, EBS management
- Nắm vững IAM Role và thực hành AWS Cloud9 cho development
- Thiết lập Amazon S3: static website hosting, public access, versioning, multi-region replication
- Tạo và quản lý Amazon RDS database; tối ưu chi phí với Lightsail
- Triển khai hệ thống tự động: EC2 Autoscaling, CloudWatch monitoring, hybrid DNS với Route53
- Deploy ứng dụng thực tế: XAMPP trên Windows, Node.js trên Linux
- Thiết lập cost governance và ôn tập tổng hợp kiến thức 3 tuần
