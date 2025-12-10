---
title : "Nhật ký Tuần 13"
date: 2025-10-13
weight : 13
chapter : false
pre : " <b> 1.13. </b> "
---

## Mục tiêu Tuần 13
- Hoàn thành và sửa tính năng AI Search (semantic search) trong dự án FindNest
- Thực hiện kiểm tra end-to-end từ frontend → API Gateway → Lambda → Bedrock/DynamoDB
- Cải thiện prompts, xử lý lỗi và tối ưu hiệu suất phản hồi

## Các nhiệm vụ được lên kế hoạch trong tuần

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày kết thúc | Ghi chú |
|------|----------|--------------|---------------|---------|
| T2 | Thử nghiệm các prompt khác nhau để cải thiện semantic search | 01/12/2025 | 01/12/2025 | So sánh few-shot vs minimal prompts |
| T3 | Debug Lambda search handler và validate Bedrock requests | 02/12/2025 | 02/12/2025 | Sửa định dạng input cho Bedrock |
| T4 | Thêm input validation và fallback logic | 03/12/2025 | 03/12/2025 | Ngăn chặn trả về kết quả nhiễu |
| T5 | Tối ưu DynamoDB queries và thêm temporary caching | 04/12/2025 | 04/12/2025 | Sử dụng TTL và in-memory cache trong Lambda |
| T6 | Integration testing với FE, thu thập feedback, sửa UI edgecases | 05/12/2025 | 05/12/2025 | Căn chỉnh request/response schema |

## Kết quả Tuần 13
- AI Search hiện trả về kết quả phù hợp hơn với truy vấn của người dùng; độ liên quan semantic được cải thiện đáng kể
- Độ trễ giảm ~30% cho các truy vấn phổ biến nhờ temporary Lambda caching và tối ưu DynamoDB query
- Lỗi phân tích input đã được xử lý; frontend hiện nhận được mã lỗi rõ ràng cho các request không đúng định dạng
- Tích hợp end-to-end (FE → API Gateway → Lambda → Bedrock/DynamoDB) ổn định trong môi trường dev/staging