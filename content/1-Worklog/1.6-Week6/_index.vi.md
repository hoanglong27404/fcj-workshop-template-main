---
title: "Worklog Tuần 6"
date: 2025-10-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu Tuần 6:

* Nâng cao kiến thức về Identity and Access Management (IAM) với các khái niệm nâng cao
* Tìm hiểu về Amazon DynamoDB - dịch vụ cơ sở dữ liệu NoSQL được quản lý hoàn toàn
* Thực hành tạo, cấu hình và quản lý bảng DynamoDB
* Hiểu về mô hình định giá và các phương pháp tốt nhất của DynamoDB

### Công việc thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | -------- | ------------ | --------------- | ------------------ |
| 2 | Ôn tập các khái niệm IAM nâng cao: logic đánh giá policy, resource-based policies và permission boundaries. Thực hành viết các policy phức tạp hơn. | 20/10/2025 | 21/10/2025 | <https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html> |
| 3 | Học các khái niệm cơ bản về DynamoDB: tables, items, attributes, primary keys (partition key & sort key). Tạo một bảng đơn giản với chế độ on-demand billing. | 21/10/2025 | 22/10/2025 | <https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html> |
| 4 | Thực hành các thao tác CRUD trên DynamoDB: insert, query, update và delete items. Sử dụng AWS Console và AWS CLI. | 22/10/2025 | 23/10/2025 | <https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/WorkingWithItems.html> |
| 5 | Tìm hiểu về các chỉ mục DynamoDB (Global Secondary Indexes - GSI, Local Secondary Indexes - LSI) và cách sử dụng chúng để tối ưu hóa truy vấn. Tạo và kiểm tra một GSI. | 23/10/2025 | 25/10/2025 | <https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html> |
| 6 | Tổng kết: xem xét các IAM policies cho quyền truy cập DynamoDB, kiểm tra các chỉ số CloudWatch và dọn dẹp các tài nguyên không cần thiết. Ghi chép các bước quan trọng. | 24/10/2025 | 25/10/2025 | Ghi chú cá nhân |

---

### Kết quả đạt được Tuần 6:

#### IAM Nâng cao:

* Hiểu sâu hơn về logic đánh giá policy và resource-based policies
* Viết thành công các policy phức tạp để kiểm soát quyền truy cập DynamoDB

#### Kiến thức cơ bản về DynamoDB:

* Tạo và cấu hình thành công bảng DynamoDB
* Hiểu về các khái niệm key schema và các loại attribute
* Thực hành so sánh on-demand billing với provisioned throughput

#### Các thao tác CRUD:

* Thực hiện thành công các thao tác insert, query, update và delete
* Sử dụng AWS Console và AWS CLI để quản lý dữ liệu
* Xác minh thời gian phản hồi và các chỉ số hiệu suất

#### Indexing & Tối ưu hóa:

* Tạo Global Secondary Index để tối ưu hóa truy vấn
* Hiểu khi nào nên sử dụng GSI so với LSI
* Kiểm tra các chỉ số hiệu suất truy vấn

#### Kết luận:

Tuần này cung cấp nền tảng vững chắc về DynamoDB - một dịch vụ NoSQL có khả năng mở rộng cao. Kết hợp với IAM giúp kiểm soát quyền truy cập một cách an toàn và hiệu quả.


