---
title : "Dọn dẹp Tài nguyên"
date: 2025-10-13
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

## Tại sao việc dọn dẹp lại quan trọng?

Trong môi trường Cloud, bạn trả tiền cho những gì bạn cung cấp. Mặc dù các dịch vụ Serverless như Lambda và DynamoDB (On-Demand) có Free Tier hào phóng hoặc chi phí idle thấp, các tài nguyên khác có thể phát sinh phí theo thời gian:

- **S3 Storage**: Bạn trả tiền cho dữ liệu được lưu trữ trong buckets
- **Amazon Location Service**: Lưu trữ Place Indexes hoặc sử dụng Maps
- **CloudWatch Logs**: Dữ liệu log được lưu trữ

Để tránh hóa đơn bất ngờ, luôn dọn dẹp môi trường của bạn sau khi hoàn thành workshop.

## Nội dung

1. [Hủy Stack](5.6.1-destroy/)
2. [Xác minh Xóa Tài nguyên](5.6.2-verify/)
3. [Kết luận Workshop](5.6.3-conclusion/)