---
title: "Worklog Tuần 9"
date: 2025-10-13
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu Tuần 9:

* Phát triển giao diện Admin để quản lý phòng
* Tạo chức năng CRUD (Create, Read, Update, Delete) cho phòng
* Lấy API từ Swagger để lấy/thêm/sửa/xóa dữ liệu phòng
* Xây dựng admin dashboard với danh sách phòng và form quản lý

### Công việc thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | -------- | ------------ | --------------- | ------------------ |
| 2 | Thiết kế layout Admin Dashboard: tạo header, sidebar navigation, khu vực nội dung chính. Sử dụng UI framework (Bootstrap, Material UI, Tailwind). | 9/11/2025 | 10/11/2025 | Tài liệu UI Framework |
| 3 | Xây dựng chức năng READ: hiển thị danh sách phòng từ API, tạo bảng với phân trang, sắp xếp, lọc. Lấy từ Swagger endpoint. | 10/11/2025 | 11/11/2025 | Tài liệu Swagger API |
| 4 | Xây dựng chức năng CREATE & UPDATE: tạo form thêm/sửa phòng, kiểm tra dữ liệu đầu vào, gửi lên API. | 11/11/2025 | 12/11/2025 | Thư viện Form Validation |
| 5 | Xây dựng chức năng DELETE: thêm nút xóa, hộp thoại xác nhận, gọi delete API. Làm mới danh sách sau khi xóa. | 12/11/2025 | 13/11/2025 | Tài liệu Swagger API |
| 6 | Tổng kết: kiểm tra toàn bộ quy trình CRUD, kiểm tra xử lý lỗi, ghi chép bugs nếu có. Tối ưu hóa code và UI/UX. | 13/11/2025 | 14/11/2025 | Ghi chú cá nhân |

---

### Kết quả đạt được Tuần 9:

#### Thiết kế Admin Dashboard:

* Thiết kế layout admin responsive và thân thiện với người dùng
* Xây dựng sidebar navigation và header
* Cấu hình routing cho các trang admin

#### Chức năng CRUD:

* Hiển thị danh sách phòng với phân trang, sắp xếp, lọc
* Tạo form thêm phòng mới với kiểm tra dữ liệu
* Xây dựng form chỉnh sửa thông tin phòng
* Triển khai xóa phòng với xác nhận

#### Tích hợp API:

* Viết code fetch cho tất cả các CRUD endpoints từ Swagger
* Xử lý các response và lỗi từ API
* Làm mới giao diện sau mỗi thao tác

#### Tối ưu hóa UX:

* Thêm loading indicators cho các lần gọi API
* Hiển thị thông báo thành công/lỗi
* Tối ưu hóa hiển thị bảng và kiểm tra form

#### Kết luận:

Tuần này hoàn thành giao diện Admin với đầy đủ chức năng CRUD. Quản trị viên giờ đã có thể quản lý phòng hiệu quả thông qua giao diện web.


