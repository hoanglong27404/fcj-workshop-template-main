---
title: "Bản đề xuất"
date: 2025-10-13
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# FindNest

## Nền Tảng AI AWS Serverless cho Tìm Kiếm Nhà Trọ Thông Minh

### 1. Tóm tắt điều hành

Nền tảng FindNest tận dụng khả năng hiểu biết AI và kiến trúc AWS Serverless để biến đổi việc tìm kiếm chỗ ở thành trải nghiệm thông minh, có ngữ cảnh. Bằng cách kết hợp Amazon Bedrock để xử lý ngôn ngữ tự nhiên và Amazon Location Service để phân tích không gian, nó cho phép người dùng tìm phòng bằng các truy vấn tự nhiên như "phòng giá rẻ gần Thủ Đức có phòng gym và khu vực an toàn."

Hệ thống (Frontend: React hosted trên Amplify, Backend: AWS Lambda + API Gateway) lưu trữ dữ liệu trong DynamoDB, xử lý xác thực qua Cognito, và làm phong phú danh sách với những hiểu biết ngữ cảnh như mật độ thức ăn, tiện ích gần đó, và chỉ số an toàn. Thông báo và xác thực OTP được xử lý qua Amazon SNS. Toàn bộ nền tảng hoạt động dưới AWS Free Tier với chi phí ước tính ~$0.5/tháng.

### 3. Kiến trúc giải pháp

Nền tảng sử dụng thiết kế AWS Serverless modular với làm phong phú AI và dữ liệu ngữ cảnh động.

| Thành phần            | Dịch vụ / Công nghệ        |
| --------------------- | -------------------------- |
| Frontend Hosting      | AWS Amplify (React SPA)    |
| API Backend           | AWS Lambda + API Gateway   |
| Database              | DynamoDB                   |
| File Storage          | S3                         |
| User Management       | Cognito                    |
| Notifications         | Amazon SNS                 |
| Map & Location        | Amazon Location Service    |
| Recommendation Engine | Amazon Bedrock + Lambda Logic |

![Kiến trúc FindNest](/images/2-Proposal/AWSProject.png)

#### Dịch vụ AWS sử dụng

- **AWS Lambda**: Thực thi logic backend bao gồm xử lý AI và truy vấn tìm kiếm.
- **Amazon API Gateway**: Cung cấp các endpoint RESTful cho yêu cầu client.
- **Amazon DynamoDB**: Lưu trữ hồ sơ người dùng, danh sách và dữ liệu ngữ cảnh được làm phong phú.
- **Amazon S3**: Lưu trữ hình ảnh phòng và file tĩnh frontend.
- **AWS Amplify**: Lưu trữ và quản lý triển khai frontend.
- **Amazon Cognito**: Quản lý luồng xác thực và phân quyền.
- **Amazon SNS**: Gửi mã OTP và thông báo người dùng.
- **Amazon Location Service**: Lấy POI xung quanh, tuyến đường và ngữ cảnh an toàn.
- **Amazon Bedrock**: Diễn giải tìm kiếm ngôn ngữ tự nhiên và thực hiện xếp hạng ngữ nghĩa.

#### Thiết kế thành phần

- **Ứng dụng Frontend**: React SPA hosted trên Amplify cho trải nghiệm người dùng responsive, động.
- **Lớp API**: Ứng dụng Express triển khai trên Lambda qua API Gateway xử lý tìm kiếm AI, danh sách và làm phong phú.
- **Cơ sở dữ liệu**: Bảng DynamoDB cho danh sách, người dùng và lịch sử tìm kiếm.
- **Lưu trữ**: S3 bucket lưu trữ hình ảnh; đọc công khai qua signed URLs.
- **Công cụ gợi ý**: Bedrock diễn giải truy vấn người dùng và xếp hạng danh sách.
- **Tích hợp bản đồ**: Amazon Location Service cung cấp vị trí ngữ cảnh và trực quan hóa POI.
- **Hệ thống thông báo**: SNS gửi OTP và cảnh báo cho danh sách mới.
- **Quản lý người dùng**: Cognito xử lý đăng ký, đăng nhập và token bảo mật.

### 4. Triển khai kỹ thuật

#### Phương pháp Recommendation Engine

- **Giai đoạn MVP**: Bedrock diễn giải truy vấn người dùng → Bộ lọc DynamoDB + Làm phong phú Location Service.
- **Giai đoạn mở rộng**: Công việc làm phong phú liên tục để tính toán chỉ số ngữ cảnh (food_density, safety_score, comfort_index).
- **Giai đoạn nâng cao**: Học thích ứng — lưu trữ phản hồi người dùng để tinh chỉnh phản hồi prompt Bedrock.

#### Yêu cầu kỹ thuật

- **Frontend**: React + Amplify UI với thanh tìm kiếm tích hợp AI và bản đồ vị trí.
- **Backend**: Ứng dụng Lambda Node.js sử dụng AWS SDK cho Bedrock, DynamoDB và Location.
- **Cơ sở dữ liệu**: Bảng DynamoDB cho người dùng, danh sách và lịch sử tìm kiếm.
- **Lưu trữ**: S3 buckets cho lưu trữ file.
- **Xác thực**: Luồng đăng nhập Cognito + SNS OTP.

### 5. Lộ trình & Mốc triển khai

**Lộ trình dự án**

- **Tuần 1-2**: Thiết kế kiến trúc AWS và thiết lập môi trường phát triển.
- **Tuần 3-4**: Phát triển giao diện frontend và triển khai các endpoint API.
- **Tuần 5**: Xây dựng và tích hợp công cụ AI Recommendation (MVP rule-based).
- **Tuần 6**: Kiểm thử, sửa lỗi và chuẩn bị demo.
- **Sau triển khai**: Theo dõi chi phí và hiệu năng, thu thập phản hồi người dùng để cải tiến.

### 6. Ước tính ngân sách

#### Chi phí hạ tầng

| Thành phần           | Dịch vụ                    | Chi phí ước tính |
| -------------------- | -------------------------- | ---------------- |
| Lambda + API Gateway | Backend                    | $0.22/tháng      |
| DynamoDB             | Database                   | $0.10/tháng      |
| S3                   | Storage                    | $0.20/tháng      |
| Cognito + SNS        | Authentication + OTP       | $0.13/tháng      |
| Bedrock              | AI Processing              | $7.5/tháng       |
| Location Service     | Map & Geospatial Data      | $3.30/tháng      |
| **Tổng**             |                            | **~$24.32/tháng** |

**Lưu ý**: Tất cả dịch vụ hoạt động dưới giới hạn sử dụng Free Tier trong giai đoạn MVP với chi phí vận hành tối thiểu.

### 7. Đánh giá rủi ro

#### Ma trận rủi ro

- **Bedrock diễn giải sai**: Ảnh hưởng trung bình, xác suất trung bình.
- **Lambda tăng chi phí đột biến (Scaling)**: Ảnh hưởng thấp, xác suất trung bình.
- **Dữ liệu ngữ cảnh không đầy đủ**: Ảnh hưởng trung bình, xác suất thấp.

#### Chiến lược giảm thiểu

- **Prompt Engineering**: Tối ưu đầu vào Bedrock và fallback về bộ lọc đơn giản.
- **Caching**: Cache kết quả Location và AI cho các truy vấn thường xuyên.

#### Kế hoạch dự phòng

- **Giới hạn Bedrock**: Fallback về logic lọc chỉ DynamoDB.
- **Vấn đề timeout**: Chia công việc làm phong phú thành các batch Lambda nhỏ hơn.
- **Tải API cao**: Scale API Gateway với throttling sử dụng.

### 8. Kết quả kỳ vọng

#### Cải tiến kỹ thuật

- **Tìm kiếm ngôn ngữ tự nhiên được hỗ trợ AI** qua Bedrock.
- **Làm phong phú ngữ cảnh tự động** sử dụng Location Service.
- **Hạ tầng có thể mở rộng, chi phí thấp** được hỗ trợ bởi AWS Serverless stack.

#### Giá trị dài hạn

- **Học liên tục**: Cải thiện prompt Bedrock với phản hồi người dùng.
- **Nhận thức ngữ cảnh thông minh**: Xây dựng hồ sơ động cho khu vực và thói quen người dùng.
- **Nền tảng có thể mở rộng**: Sẵn sàng tích hợp với Amazon Personalize hoặc fine-tuning Bedrock.
- **Hiệu quả chi phí**: Hoàn toàn serverless với bảo trì tối thiểu và không có server cố định.
