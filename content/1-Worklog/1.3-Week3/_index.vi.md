---
title: "Worklog Tuần 3"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu Tuần 3

Tuần này tập trung vào việc nắm vững các dịch vụ cốt lõi của AWS, từ máy ảo đến cơ sở dữ liệu và tự động hóa. Các mục tiêu chính bao gồm:
-   **Nghiên cứu chuyên sâu về Amazon EC2**: Khám phá cách triển khai và quản lý các máy ảo Windows và Linux, xây dựng Amazon Machine Image (AMI) tùy chỉnh, quản lý ổ cứng Elastic Block Store (EBS), và thiết lập các chính sách quản lý chi phí.
-   **Bảo mật và Môi trường phát triển**: Nắm vững cách sử dụng IAM Role để cấp quyền an toàn và làm quen với môi trường phát triển tích hợp trên đám mây AWS Cloud9.
-   **Giải pháp lưu trữ với Amazon S3**: Triển khai website tĩnh trên S3, cấu hình sao lưu dữ liệu đa vùng (multi-region replication) và quản lý phiên bản (versioning) cho các đối tượng.
-   **Quản lý Cơ sở dữ liệu**: Học cách tạo và quản lý cơ sở dữ liệu quan hệ với Amazon RDS, đồng thời tìm hiểu cách tối ưu hóa chi phí cho các ứng dụng nhỏ bằng Amazon Lightsail.
-   **Tự động hóa và Giám sát**: Thiết lập hệ thống tự động co giãn tài nguyên với EC2 Autoscaling, theo dõi hiệu suất hệ thống bằng Amazon CloudWatch, và cấu hình DNS lai với Route 53.

---
### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                                                                                                                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                              |
|:----:| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |:------------:|:---------------:| ----------------------------------------------------------------------------------------------------------------------------------------------- |
|  2   | **Khám phá Dịch vụ Amazon EC2**:<br>- Triển khai máy ảo: Windows Server 2022 & Amazon Linux<br>- Tùy chỉnh cấu hình máy ảo<br>- Quản lý EBS: Tạo và quản lý snapshots<br>- Xây dựng & khởi chạy máy ảo từ AMI tùy chỉnh<br>- Khôi phục truy cập: Windows (Systems Manager) & Linux (User Data)<br>- Cấu hình giao diện đồ họa (GUI) cho Ubuntu<br>- Lưu trữ và quản lý người dùng<br>- Quản trị chi phí: Giới hạn theo Region, loại và dòng máy ảo | 22/09/2025   | 22/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  3   | **IAM, Cloud9 & Amazon S3**:<br>- Tìm hiểu và áp dụng IAM Role<br>- Làm quen với môi trường phát triển AWS Cloud9<br>- Cấu hình S3 cho website tĩnh: Bật truy cập công khai, kiểm tra website<br>- Tăng tốc độ tải trang trên S3<br>- Bật tính năng quản lý phiên bản (Versioning)<br>- Sao chép đối tượng đa vùng (Multi-Region Replication) | 23/09/2025   | 23/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  4   | **Amazon RDS & Lightsail**:<br>- Tạo và quản lý cơ sở dữ liệu trên Amazon RDS<br>- Tối ưu hóa chi phí tính toán với Amazon Lightsail cho các dự án nhỏ                                                                                                                                                 | 24/09/2025   | 24/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  5   | **Tự động hóa & Giám sát**:<br>- Tự động hóa co giãn ứng dụng với EC2 Autoscaling<br>- Xây dựng hệ thống giám sát hiệu năng với Amazon CloudWatch<br>- Thiết lập hệ thống DNS lai tích hợp giữa on-premises và VPC với Route 53                                                                        | 25/09/2025   | 25/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  6   | **Tổng kết và Ôn tập**:<br>- Hệ thống hóa lại kiến thức từ Tuần 1<br>- Củng cố hiểu biết về IAM, VPC, EC2, S3, RDS<br>- Rà soát các kỹ năng thực hành đã học                                                                                                                                             | 26/09/2025   | 26/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |

---
### Kết quả đạt được

#### Những gì đã hoàn thành

-   **Thành thạo EC2**: Triển khai và quản lý thành công nhiều loại máy ảo EC2, bao gồm Windows Server 2022 và các bản phân phối Linux, cũng như tạo AMI tùy chỉnh và quản lý EBS.
-   **Bảo mật & Phát triển**: Nắm vững cấu hình IAM Role và sử dụng AWS Cloud9 để phát triển ứng dụng trực tiếp trên đám mây.
-   **Giải pháp Lưu trữ S3**: Xây dựng thành công một website tĩnh trên Amazon S3 với đầy đủ tính năng truy cập công khai, quản lý phiên bản và sao chép dữ liệu đa vùng.
-   **Quản lý Dữ liệu**: Tạo và vận hành cơ sở dữ liệu trên Amazon RDS; sử dụng Lightsail để tối ưu hóa chi phí cho các ứng dụng nhỏ.
-   **Hệ thống Tự động hóa**: Thiết lập thành công các hệ thống tự động hóa quan trọng như EC2 Autoscaling, giám sát với CloudWatch và DNS lai với Route 53.
-   **Ứng dụng thực tế**: Triển khai các ứng dụng thực tế như XAMPP trên Windows và Node.js trên Linux để củng cố kỹ năng.
-   **Quản trị và Tổng kết**: Áp dụng các chính sách quản trị chi phí và hoàn thành việc tổng kết kiến thức toàn diện sau 3 tuần.
