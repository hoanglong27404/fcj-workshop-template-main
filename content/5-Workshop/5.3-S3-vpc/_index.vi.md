---
title : "Deploy Backend"
date: 2025-10-13
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

## Giới thiệu về Infrastructure as Code (IaC)

Thay vì nhấp chuột thủ công qua AWS Console ("ClickOps"), chúng ta sử dụng **AWS CDK** để định nghĩa toàn bộ infrastructure. Trong file `cdk/lib/backend-stack.ts`, chúng ta đã thiết kế một hệ thống Serverless hoàn chỉnh.

Khi bạn chạy lệnh `cdk deploy`, CDK synthesize mã này thành CloudFormation Template, và AWS tự động cung cấp các tài nguyên tương ứng.

## Kiến trúc

![FindNest Architecture](/images/5-Workshop/5.1-Workshop-overview/AWSProject.png)

## Nội dung

1. [Phân Tích Kiến Trúc Chi Tiết](5.3.1-architecture/) - Hướng dẫn mã chi tiết của tất cả tài nguyên AWS
2. [Cài Đặt Dependencies](5.3.2-dependencies/) - Thiết lập môi trường phát triển
3. [Deploy Stack](5.3.3-deploy/) - Chạy lệnh CDK để cung cấp infrastructure
4. [Kết Quả & Outputs](5.3.4-results/) - Hiểu deployment outputs và các bước tiếp theo