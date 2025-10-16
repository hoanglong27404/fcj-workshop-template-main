---
title: "Worklog Tuần 4"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu Tuần 4: Tối ưu hóa Hệ thống

Tuần này tập trung vào việc áp dụng AWS Well-Architected Framework để tối ưu hóa toàn diện hệ thống trên 5 trụ cột chính:
-   **Vận hành Xuất sắc (Operational Excellence)**: Tự động hóa vận hành, giám sát chủ động và xây dựng quy trình xử lý sự cố hiệu quả.
-   **Bảo mật (Security)**: Xây dựng kiến trúc bảo mật theo nguyên tắc zero-trust, đảm bảo tuân thủ (compliance) và bảo vệ hệ thống trước các mối đe dọa.
-   **Độ tin cậy (Reliability)**: Đảm bảo tính sẵn sàng cao (high availability), xây dựng kế hoạch khôi phục sau thảm họa (disaster recovery) và tăng cường khả năng chịu lỗi.
-   **Hiệu năng (Performance)**: Nâng cao hiệu năng thông qua co giãn tự động, kỹ thuật caching, và tối ưu hóa tài nguyên trên các dịch vụ container và lưu trữ.
-   **Tối ưu hóa Chi phí (Cost Optimization)**: Lựa chọn đúng kích thước tài nguyên (right-sizing), sử dụng các gói tiết kiệm và áp dụng các công cụ phân tích chi tiêu chi tiết.

---
### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                                                                                                                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                              |
|:----:| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |:------------:|:---------------:| ----------------------------------------------------------------------------------------------------------------------------------------------- |
|  2   | **Vận hành Xuất sắc**:<br>- Tự động hóa tác vụ (tắt máy chủ, gửi thông báo Slack) bằng AWS Lambda<br>- Xây dựng hệ thống giám sát với CloudWatch và Grafana<br>- Quản lý tài nguyên và phân quyền truy cập EC2 dựa trên Tags<br>- Tự động hóa quản lý và vận hành với AWS Systems Manager<br>- Triển khai hạ tầng dưới dạng mã (IaC) với AWS CloudFormation | 29/09/2025   | 29/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  3   | **Bảo mật**:<br>- Thiết lập đăng nhập một lần (SSO) cho toàn tổ chức<br>- Giới hạn quyền hạn tối đa của người dùng với IAM Permission Boundary<br>- Kiểm tra các tiêu chuẩn bảo mật với AWS Security Hub<br>- Bảo vệ ứng dụng web và API bằng AWS WAF<br>- Quản lý khóa mã hóa tập trung với AWS KMS | 30/09/2025   | 30/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  4   | **Độ tin cậy**:<br>- Xây dựng chiến lược sao lưu và phục hồi hệ thống với AWS Backup<br>- Kết nối trực tiếp giữa các VPC bằng VPC Peering<br>- Quản lý kết nối mạng tập trung qua AWS Transit Gateway để tăng tính ổn định                                                                   | 01/10/2025   | 01/10/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  5   | **Hiệu năng**:<br>- Container hóa ứng dụng với Docker và triển khai trên Amazon ECS<br>- Xây dựng quy trình CI/CD tự động với AWS CodePipeline<br>- Lưu trữ file không giới hạn với AWS File Storage Gateway<br>- Triển khai hệ thống file chia sẻ cho Windows với Amazon FSx<br>- Xây dựng Data Lake và thiết kế kiến trúc nâng cao với DynamoDB | 02/10/2025   | 02/10/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  6   | **Tối ưu hóa Chi phí**:<br>- Tối ưu chi phí qua Savings Plans và Reserved Instances<br>- Lựa chọn cấu hình EC2 phù hợp (Right-Sizing)<br>- Trực quan hóa chi phí sử dụng dịch vụ AWS<br>- Phân tích chi phí chuyên sâu bằng AWS Glue và Amazon Athena<br>- Tổng kết và củng cố 5 trụ cột của Well-Architected Framework | 03/10/2025   | 03/10/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |

---
### Kết quả đạt được

#### Những gì đã hoàn thành

-   **Tự động hóa vận hành và giám sát**: Hoàn thiện quy trình tự động tắt máy chủ, xây dựng dashboard giám sát hiệu năng với CloudWatch/Grafana, và quản lý tài nguyên tập trung bằng Tags.
-   **Tăng cường bảo mật toàn diện**: Thiết lập thành công SSO, áp dụng IAM Permission Boundary để kiểm soát quyền chặt chẽ, triển khai tường lửa ứng dụng web (WAF) và quản lý khóa mã hóa với KMS.
-   **Nâng cao độ tin cậy của hệ thống**: Xây dựng kế hoạch backup tự động với AWS Backup, cấu hình VPC Peering và Transit Gateway để đảm bảo kết nối mạng luôn ổn định và sẵn sàng.
-   **Tối ưu hóa hiệu năng ứng dụng**: Triển khai ứng dụng container hóa qua Docker/ECS, tự động hóa quy trình CI/CD với CodePipeline, và thiết kế kiến trúc dữ liệu hiệu năng cao với DynamoDB và Data Lake.
-   **Quản lý và tối ưu chi phí hiệu quả**: Áp dụng thành công Savings Plans/Reserved Instances, thực hiện right-sizing cho EC2, và sử dụng Glue/Athena để phân tích chi phí ở mức độ sâu.

***