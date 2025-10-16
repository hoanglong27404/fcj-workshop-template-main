---
title: "Worklog Tuần 2"
date: 2025-10-13
weight: 2 
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu Tuần 2

Tuần này tập trung vào việc thiết lập kết nối lai (hybrid connectivity) giữa hệ thống tại chỗ (on-premises) và AWS. Các mục tiêu chính bao gồm:
-   **Thiết lập Hybrid DNS**: Sử dụng Route 53 Resolver để cho phép máy chủ on-premises phân giải các truy vấn DNS cho dịch vụ trên AWS và ngược lại.
-   **Thiết lập VPC Peering**: Tạo kết nối mạng trực tiếp giữa hai VPC (Dev và Staging) để chúng có thể giao tiếp bằng địa chỉ IP riêng.
-   **Triển khai AWS Transit Gateway**: Xây dựng một hub trung tâm để đơn giản hóa việc kết nối mạng và định tuyến giữa nhiều VPC và mạng on-premises.
-   **Tự động hóa với CloudFormation**: Thực hành hạ tầng dưới dạng mã (Infrastructure-as-Code) bằng cách sử dụng template CloudFormation để tự động hóa việc cấp phát tài nguyên.
-   **Lên kế hoạch cho dự án cuối kỳ**: Brainstorm và phác thảo kiến trúc cho dự án cuối kỳ, áp dụng các kiến thức đã học trong tuần.

---
### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                                                                                                                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                              |
|:----:| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |:------------:|:---------------:| ----------------------------------------------------------------------------------------------------------------------------------------------- |
|  2   | **Cấu hình Hybrid DNS với Route 53 Resolver**:<br>- Tạo Key Pair<br>- Khởi tạo CloudFormation Template<br>- Cấu hình Security Group<br>- Kết nối RDGW<br>- Cấu hình DNS<br>  + Tạo Outbound Endpoint<br>  + Tạo Resolver Rules<br>  + Tạo Inbound Endpoint<br>- Dọn dẹp tài nguyên                       | 15/09/2025   | 15/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  3   | **Ôn tập kiến thức**:<br>- Hybrid DNS<br>- RDGW<br>- Route 53 Endpoints<br>- Resolver Rules                                                                                                                                                                                                              | 16/09/2025   | 16/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  4   | **Cấu hình VPC Peering**:<br>- Giới thiệu Peering<br>- Khởi tạo CloudFormation Template<br>- Tạo Security Group & EC2 instance<br>- Cập nhật Network ACLs<br>  + Thiết lập kết nối Peering<br>  + Cập nhật Route Tables<br>- Bật tính năng Cross-Peer DNS                                                | 17/09/2025   | 17/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  5   | **Triển khai AWS Transit Gateway**:<br>- Tạo Transit Gateway<br>- Tạo Attachments cho từng VPC<br>- Cấu hình Route Tables cho Transit Gateway<br>- Thêm Routes vào Route Tables của VPC                                                                                                                  | 18/09/2025   | 18/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
|  6   | **Lên ý tưởng dự án cuối kỳ**:<br>- Nghiên cứu các giải pháp tiềm năng<br>- Brainstorm và phát triển ý tưởng cốt lõi<br>- Phác thảo kiến trúc sơ bộ                                                                                                                                                      | 19/09/2025   | 19/09/2025      | <https://cloudjourney.awsstudygroup.com/><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |

---
### Kết quả đạt được

#### Những gì đã hoàn thành

-   Mô phỏng thành công kết nối **Hybrid DNS** giữa môi trường on-premises và AWS.
-   Triển khai **VPC Peering** để liên kết môi trường Phát triển (Dev) và Staging, cho phép giao tiếp an toàn và riêng tư.
-   Triển khai **AWS Transit Gateway** đóng vai trò là một hub trung tâm để quản lý lưu lượng mạng giữa nhiều VPC.
-   Thực hành hạ tầng dưới dạng mã (IaC) bằng cách tự động hóa việc triển khai tài nguyên với **AWS CloudFormation**.
-   Xây dựng ý tưởng và kiến trúc cụ thể cho dự án cuối kỳ dựa trên kinh nghiệm thực tế với các dịch vụ mạng của AWS.

#### Tóm tắt kiến trúc

-   **Kết nối đa vùng (Multi-region)**: Thiết lập kết nối giữa Dev VPC ở `us-east-1` và Prod VPC ở `ap-southeast-1` thông qua Transit Gateway.
-   **Phân giải DNS lai (Hybrid DNS)**: Cấu hình hệ thống để một domain tại chỗ (`app.company.local`) có thể phân giải thành công một domain được lưu trữ trên AWS (`analytics.aws.company.com`).