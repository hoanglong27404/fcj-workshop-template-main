---
title: "Từ Máy ảo đến Kubernetes đến Serverless"
date: 2025-10-13
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# Từ Máy ảo đến Kubernetes đến Serverless: Cách Dacadoo tiết kiệm 78% chi phí Cloud

**Tác giả:** Andreas Gehrig, Kevin Nash, Philippe Wanner  
**Xuất bản:** 26 tháng 3, 2025  
**Danh mục:** Amazon API Gateway, Amazon DynamoDB, Amazon Route 53, Amazon Simple Storage Service (S3), Kiến trúc, Quản lý Tài chính AWS Cloud, AWS Lambda, AWS WAF, Migration, Serverless, Tư duy Lãnh đạo

## Giới thiệu

Dacadoo là một công ty công nghệ toàn cầu có trụ sở tại Thụy Sĩ, chuyên về các giải pháp cho:

- **Tương tác sức khỏe số**
- **Định lượng rủi ro sức khỏe**

Sản phẩm của họ bao gồm nền tảng SaaS dựa trên:

- **Khoa học hành vi**
- **Trí tuệ nhân tạo (AI)**
- **Gamification**

Để giúp người dùng cuối cải thiện kết quả sức khỏe của họ.

## Hành trình hiện đại hóa

Công ty khởi xướng hành trình hiện đại hóa API để:

- Định lượng dữ liệu sức khỏe và lối sống
- Cung cấp công cụ đánh giá rủi ro
- Tính toán xác suất tử vong và bệnh tật dựa trên dữ liệu nghiên cứu khoa học

Để chuyển đổi các dịch vụ API dựa trên VM thành giải pháp tính toán điểm sức khỏe và rủi ro toàn cầu với khôi phục thảm họa, dacadoo đã chọn Amazon Web Services (AWS).

## Kết quả đạt được

Kết quả:

* **Giảm 78% chi phí**  
* **Thời gian bảo trì hạ tầng dưới 1 giờ/năm**  
* **Triển khai nhiều hạ tầng AWS mà không mở rộng đội SRE**  
* **Mức độ tự động hóa cao và tư duy agile**

## Bối cảnh: Ba giai đoạn tiến hóa

Kiến trúc giải pháp tiến hóa qua ba giai đoạn:

**Giai đoạn 1:** Ươm tạo với Máy ảo  
- Máy ảo đơn lẻ on-premises với khôi phục thảm họa (DR) tại Thụy Sĩ

**Giai đoạn 2:** Toàn cầu và có thể mở rộng  
- Nhiều cụm Kubernetes trên toàn cầu

**Giai đoạn 3:** Xuất sắc vận hành  
- Hoàn toàn serverless với dự phòng địa lý trên AWS

## Giai đoạn 1: Ươm tạo với Máy ảo

### Kiến trúc ban đầu

Sau nhiều năm nghiên cứu và phát triển khoa học, dịch vụ được ra mắt, chạy trên:

- Một máy ảo on-premises đơn lẻ
- Sử dụng công nghệ hypervisor để cung cấp khả năng khôi phục thảm họa (DR)

Ứng dụng phục vụ:
- Yêu cầu API
- Cơ sở dữ liệu NoSQL
- Tất cả chạy trên cùng một máy chủ

### Thách thức

| Vấn đề | Chi tiết |
|--------|----------|
| Tính khả dụng cao | Không có HA, yêu cầu khôi phục thủ công |
| Triển khai phần mềm | Thủ công qua SSH |
| Bảo trì OS | Quy trình thủ công |
| Mức độ tự động hóa | Rất thấp |
| Sao lưu dữ liệu | Chỉ VM snapshots |
| Giám sát | Thủ công, không tự động |
| Kiểm thử | Chỉ trên máy trạm phát triển |

### Hạn chế chính

- API chỉ có sẵn tại Thụy Sĩ
- Bảo trì được thực hiện thủ công
- Triển khai phần mềm được xử lý thủ công
- Không có khả năng mở rộng toàn cầu
- Vấn đề quản lý nhân sự

## Giai đoạn 2: Toàn cầu và có thể mở rộng với Kubernetes

### Quyết định chiến lược

Dacadoo đã đưa ra quyết định đầu tư chiến lược vào:

- **Kubernetes** để quản lý workloads được container hóa
- **Quản lý toàn cầu** ở quy mô lớn

### Triển khai toàn cầu

Do khách hàng phân tán địa lý và yêu cầu độ trễ thấp:

**Ba cụm Kubernetes được triển khai:**
- Mỗi cụm ở một lục địa khác nhau
- Cơ sở dữ liệu NoSQL được lưu trữ gần workloads
- Giảm độ trễ dịch vụ và nỗ lực migration

### Tối ưu hóa vận hành

**Cơ sở dữ liệu NoSQL:**
- Tích hợp như dịch vụ SaaS
- Giảm thiểu bảo trì vận hành

**Giám sát:**
- Tập trung với Datadog

**Cung cấp hạ tầng:**
- Độc quyền với Terraform
- Bao gồm: cụm Kubernetes, cơ sở dữ liệu NoSQL, tích hợp GitLab & Datadog

**CI/CD:**
- Sử dụng GitLab CI/CD
- Triển khai đến nhiều môi trường và cụm
- Hệ thống siêu quy mô hành tinh

### So sánh: VM vs Kubernetes

| Tiêu chí | Máy ảo | Kubernetes |
|----------|--------|------------|
| Khả năng mở rộng | Thấp | Cao |
| Tính khả dụng | Cố gắng tốt nhất | 99.95% |
| Chi phí hạ tầng | Thấp | Cao |
| Nỗ lực bảo trì | Cao | Trung bình |

### Thách thức

**Chi phí cao:**
- Ba cụm Kubernetes khu vực
- Ba môi trường
- Tổng cộng: 27 node cụm

**Chi phí bổ sung:**
- Quản lý các instance cơ sở dữ liệu NoSQL SaaS cho mỗi cụm

**Độ phức tạp:**
- Quy trình CI/CD đa cụm đa môi trường
- Nỗ lực vận hành đáng kể để duy trì hạ tầng
- Cần cập nhật liên tục các thành phần Kubernetes

## Giai đoạn 3: Xuất sắc vận hành với Serverless

### Tại sao chuyển sang Serverless?

Kiến trúc dựa trên Kubernetes đáp ứng yêu cầu, nhưng:

- Một số tính năng API backlog cần sự liên kết tốt hơn
- Kiến trúc cần liên kết với công nghệ mới nhất
- Cần tối ưu hóa các phương pháp tốt nhất

Đây là thời điểm phù hợp để:
- Có cái nhìn toàn diện về kiến trúc hạ tầng và phần mềm
- Tái cấu trúc giải pháp với công nghệ mới nhất của AWS

### Yêu cầu giải pháp

Yêu cầu cho việc tái cấu trúc:

* **Duy trì chức năng API**

* **Hạn chế xử lý dữ liệu ở các khu vực được chọn** (tuân thủ luật bảo vệ dữ liệu địa phương)

* **Tránh chu kỳ vá lỗi hàng tuần** - chỉ sử dụng dịch vụ serverless được quản lý

* **Giảm chi phí** - chọn dịch vụ với mô hình định giá pay-as-you-go

* **Ủy thác xác thực cho dịch vụ chuyên dụng**

* **Sử dụng web framework đã được thiết lập với hệ sinh thái rộng**

### Tái cấu trúc ứng dụng

**Dịch vụ API bao gồm:**
- Developer Portal (Cổng thông tin nhà phát triển)
- API tính toán điểm sức khỏe và rủi ro

**Cơ sở dữ liệu chỉ cần:**
- API keys
- Tham số thuật toán
- Quotas
- Thống kê sử dụng

### Cơ sở dữ liệu phân tán

**Dữ liệu sức khỏe:**
- Được xử lý theo khu vực bởi lớp tính toán
- KHÔNG được lưu trữ (chỉ xử lý tạm thời)
- Mở cơ hội cho cơ sở dữ liệu phân tán

**Amazon DynamoDB Global Tables:**
- Lựa chọn hoàn hảo cho giải pháp này
- Ghi: Phân tán đến tất cả các khu vực được kết nối
- Đọc: Được thực hiện cục bộ
- Độ trễ thấp - đáp ứng SLA của Dacadoo

### Thành phần kiến trúc

**Developer Portal:**
- Giao diện người dùng web
- Tài liệu API
- Quản lý API key
- AWS Lambda - tự động mở rộng, trả tiền theo yêu cầu

**Health and Risk API:**
- Thuật toán được triển khai bằng C (mô phỏng ngắn)
- Yêu cầu tính toán chuyên sâu
- REST API được bao bọc trong Python FastAPI
- AWS Lambda - lựa chọn xuất sắc

## Kiến trúc Serverless chi tiết

### Luồng yêu cầu

**Yêu cầu HTTP:**
- Được định tuyến qua Amazon API Gateway
- Được bảo vệ bởi AWS WAF (chống lại yêu cầu độc hại)
- Được chuyển tiếp đến các hàm AWS Lambda

**Tài nguyên tĩnh:**
- Được phục vụ từ Amazon S3
- Qua API Gateway
- CloudFront không cần thiết (giảm độ phức tạp)

### Định tuyến DNS toàn cầu

**Amazon Route 53 - Định tuyến dựa trên độ trễ:**
- Chuyển hướng truy vấn DNS đến endpoint có độ trễ thấp nhất
- Cung cấp HA khu vực cho người dùng API
- Không yêu cầu vị trí xử lý dữ liệu cụ thể
- Người dùng có thể gọi endpoints cụ thể theo khu vực (nếu cần tuân thủ quy định)

### Xác thực và ủy quyền

**Ủy quyền API:**
- Dựa trên HTTP headers
- Được triển khai trong ứng dụng
- Dữ liệu được lưu trữ trong Amazon DynamoDB

## Infrastructure as Code với Pulumi

### Lựa chọn công cụ

Đội SRE thành thạo Python, đã chọn Pulumi:

**Ưu điểm:**

* **Kiểm soát luồng ngôn ngữ lập trình** - lập trình ngôn ngữ  
* **Khả năng cấu hình mạnh mẽ**  
* **Hỗ trợ đa cloud**

### Pipeline CI/CD

**GitLab CI:**
- Biên dịch thư viện thuật toán
- Kiểm thử ứng dụng FastAPI
- Đóng gói mọi thứ

**Triển khai:**
- Chỉ là cập nhật AWS Lambda
- Quy trình đơn giản và đáng tin cậy

### Nâng cao kỹ năng

**Chuyển đổi:**
- Từ cách tiếp cận dựa trên cấu hình
- Đến thiết kế cơ sở mã hạ tầng
- Sử dụng lập trình hướng đối tượng Python

**Kết quả:**
- SRE phát triển kỹ năng kỹ thuật phần mềm
- Đầu tư vào hiện đại hóa đội ngũ
- Văn hóa GitOps tập trung vào năng suất

## So sánh toàn diện

| Tiêu chí | Máy ảo | Kubernetes | Serverless |
|----------|--------|------------|------------|
| Khả năng mở rộng | Thấp | Cao | Rất cao |
| Tính khả dụng | Cố gắng tốt nhất | 99.95% | 99.999%* |
| Chi phí hạ tầng | Thấp | Cao | Thấp |
| Nỗ lực bảo trì | Cao | Trung bình | Rất thấp |

*Với dự phòng toàn cầu nâng tính khả dụng lên 99.999% trong khi giữ chi phí thấp.

## Kết quả cuối cùng

### Chi phí & Hiệu suất

* **Giảm 78% chi phí**

* **Thời gian bảo trì dưới 1 giờ/năm**

* **99.999% tính khả dụng toàn cầu**

* **Tự động hóa hoàn toàn**

### Lợi ích chiến lược

* **Triển khai nhiều hạ tầng AWS mà không mở rộng đội SRE**

* **Đơn giản hóa độ phức tạp quản lý hạ tầng**

* **Tăng cường tính linh hoạt và tự động hóa**

* **Duy trì đội SRE tinh gọn**

* **Giữ chi phí hạ tầng cạnh tranh**

## Kết luận

Migration từ máy ảo → Kubernetes → AWS Lambda chứng minh:

**Sự tiến hóa của kỹ thuật cloud hướng tới:**

📈 **Hiệu quả**  
📈 **Khả năng mở rộng nâng cao**

**Mỗi bước trong hành trình:**

⬇️ **Giảm thiểu độ phức tạp quản lý hạ tầng**  
⬆️ **Tăng cường tính linh hoạt và tự động hóa**

**Kết quả cho Dacadoo:**

✨ **Tăng trưởng nền tảng mạnh mẽ**  
✨ **Nâng cao kỹ năng cho kỹ sư**  
✨ **Duy trì đội SRE tinh gọn**  
✨ **Cấu trúc chi phí cạnh tranh**

### Bắt đầu

Bắt đầu với giải pháp serverless AWS của riêng bạn!

## Về các tác giả

### Andreas Gehrig
**Vị trí:** Senior Cloud Architect tại Dacadoo, Zurich, Thụy Sĩ

**Background:** Kỹ thuật phần mềm

**Chuyên môn:** Tận dụng công nghệ AWS để thiết kế và xây dựng giải pháp cloud-native cho ứng dụng và phân tích

### Kevin Nash
**Vị trí:** Senior Solutions Architect tại Amazon Web Services (AWS), Thụy Sĩ

**Background:** Hệ thống phân tán

**Chuyên môn:** Xây dựng giải pháp cho khách hàng, hỗ trợ migration cloud của khách hàng

### Philippe Wanner
**Vị trí:** Senior Expert Solutions Architect tại AWS

**Chuyên môn:** Thúc đẩy các phương pháp tối ưu hóa cho migration và hiện đại hóa

**Tập trung hiện tại:** Các lĩnh vực đa ngành bao gồm:
- Hệ thống phân tán
- Kiến trúc serverless
- Chuyển đổi kinh doanh