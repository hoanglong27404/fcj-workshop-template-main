---
title: "Workshop"
date: 2025-10-13
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Xây dựng Serverless Backend với AWS CDK

## Tổng quan

Trong workshop này, bạn sẽ xây dựng một **Serverless Backend hoàn chỉnh cho ứng dụng FindNest** - một nền tảng cho thuê nhà trọ. Bạn sẽ sử dụng **AWS CDK (Cloud Development Kit)** để định nghĩa và triển khai hạ tầng dưới dạng code.

### Bạn sẽ học cách:

* **Triển khai hạ tầng serverless** sử dụng AWS CDK với TypeScript  
* **Xây dựng RESTful APIs** với API Gateway và Lambda  
* **Triển khai xác thực** với Amazon Cognito  
* **Lưu trữ dữ liệu trong DynamoDB** với mô hình dữ liệu phù hợp  
* **Tích hợp khả năng AI** với Amazon Bedrock (Claude 3)  
* **Thêm chức năng bản đồ** với Amazon Location Service  
* **Áp dụng các phương pháp bảo mật tốt nhất** với IAM policies  
* **Quản lý vòng đời hạ tầng** (triển khai và dọn dẹp)

## Kiến trúc

Bạn sẽ triển khai một kiến trúc serverless hiện đại bao gồm:

- **API Gateway** - Các endpoint RESTful API
- **AWS Lambda** - Serverless compute (Node.js)
- **Amazon DynamoDB** - Cơ sở dữ liệu NoSQL (7 bảng)
- **Amazon Cognito** - Xác thực và ủy quyền người dùng
- **Amazon S3** - Lưu trữ hình ảnh
- **Amazon Location Service** - Bản đồ và geocoding
- **Amazon Bedrock** - AI/ML với Claude 3
- **Amazon SNS** - Thông báo SMS
- **CloudWatch Logs** - Giám sát và logging

## Nội dung

1. [Tổng quan Workshop](5.1-Workshop-overview/)
2. [Điều kiện tiên quyết](5.2-Prerequiste/)
3. [Triển khai Backend](5.3-S3-vpc/)
4. [Seeding Data](5.4-S3-onprem/)
5. [Xác thực Hệ thống](5.5-Policy/)
6. [Dọn dẹp tài nguyên](5.6-Cleanup/)