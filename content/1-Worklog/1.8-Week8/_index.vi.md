---
title: "Worklog Tuần 8"
date: 2025-10-13
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu Tuần 8:

* Thiết kế và phát triển giao diện Bản đồ cho ứng dụng tìm kiếm phòng trọ
* Hiểu và tích hợp Swagger API để lấy dữ liệu phòng
* Hiển thị các marker phòng trên bản đồ với thông tin chi tiết
* Thực hành xử lý dữ liệu API và hiển thị trên bản đồ

### Công việc thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | -------- | ------------ | --------------- | ------------------ |
| 2 | Nghiên cứu Swagger API: đọc tài liệu, hiểu cấu trúc API, kiểm tra endpoints để lấy danh sách phòng. Ghi chép endpoints, tham số và định dạng response. | 2/11/2025 | 3/11/2025 | Tài liệu Swagger |
| 3 | Thiết kế giao diện Bản đồ: tạo HTML/CSS cơ bản cho bản đồ, sidebar thông tin, bộ lọc tìm kiếm. Sử dụng framework/library (React, Vue, hoặc vanilla JS). | 3/11/2025 | 4/11/2025 | Google Maps API, Leaflet docs |
| 4 | Tích hợp thư viện Bản đồ: sử dụng Google Maps hoặc Leaflet, hiển thị bản đồ cơ bản, triển khai zoom/pan. Kiểm tra các tính năng tương tác. | 4/11/2025 | 5/11/2025 | Google Maps API Guide |
| 5 | Lấy dữ liệu từ Swagger API: viết code fetch/axios để gọi API, xử lý response, hiển thị marker phòng trên bản đồ với số phòng và giá. | 5/11/2025 | 6/11/2025 | Swagger Endpoints |
| 6 | Tổng kết: kiểm tra logic API, test hiển thị marker, tối ưu hóa hiệu suất. Ghi chép các vấn đề gặp phải và giải pháp. | 6/11/2025 | 7/11/2025 | Ghi chú cá nhân |

---

### Kết quả đạt được Tuần 8:

#### Tích hợp Swagger API:

* Hiểu cấu trúc API và các endpoints cần thiết
* Viết thành công code để lấy dữ liệu từ Swagger
* Xử lý error handling và kiểm tra tính hợp lệ của response

#### Giao diện Bản đồ:

* Thiết kế layout giao diện Bản đồ với HTML/CSS
* Tích hợp thành công thư viện Bản đồ
* Hiển thị marker phòng với thông tin cơ bản

#### Phát triển Frontend:

* Xử lý dữ liệu API và hiển thị trên bản đồ
* Triển khai zoom, pan và click marker để xem chi tiết
* Tối ưu hóa hiệu suất khi tải nhiều marker

#### Giải quyết vấn đề:

* Giải quyết các vấn đề CORS và API timeout
* Debug logic hiển thị marker
* Ghi chép các phương pháp tốt nhất cho phát triển frontend

#### Kết luận:

Tuần này hoàn thành giao diện Bản đồ frontend với tích hợp Swagger API. Giao diện Bản đồ giờ đã có thể hiển thị phòng và cho phép người dùng tương tác cơ bản.


