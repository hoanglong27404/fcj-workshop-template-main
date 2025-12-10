---
title : "Giới thiệu"
date: 2025-10-13
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

## Kiến trúc Serverless

Kiến trúc Serverless cho phép bạn xây dựng và chạy ứng dụng và dịch vụ mà không cần nghĩ về máy chủ. Nó loại bỏ các tác vụ quản lý hạ tầng như cung cấp máy chủ, vá lỗi, bảo trì hệ điều hành và cung cấp dung lượng. Kiến trúc dựa trên AWS Lambda cho tính toán, Amazon API Gateway cho quản lý API và Amazon DynamoDB cho lưu trữ dữ liệu. Tài nguyên tính toán chạy trong Lambda được kích hoạt bởi các sự kiện từ API Gateway và tự động mở rộng quy mô.

## Tổng quan workshop

Trong workshop này, bạn sẽ triển khai **FindNest Backend** sử dụng AWS CDK.

- **"Backend Logic"** được xử lý bởi AWS Lambda chạy code Node.js/Express. Nó đóng vai trò là "bộ não" của ứng dụng, xử lý logic nghiệp vụ chỉ khi được kích hoạt.

- **"Data & Storage"** sử dụng Amazon DynamoDB cho lưu trữ dữ liệu NoSQL hiệu suất cao (Listings, Users) và Amazon S3 để lưu trữ hình ảnh do người dùng tải lên một cách an toàn.

- **Amazon API Gateway** hoạt động như điểm vào an toàn cho tất cả các yêu cầu từ client.

![Kiến trúc FindNest](/images/5-Workshop/5.1-Workshop-overview/AWSProject.png)