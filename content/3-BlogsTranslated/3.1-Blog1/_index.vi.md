---
title: "Hỗ trợ Web Application Firewall cho AWS Amplify"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Hỗ trợ Web Application Firewall cho các Website được lưu trữ trên AWS Amplify

**Tác giả:** Sébastien Stormacq  
**Xuất bản:** 26 tháng 3, 2025  
**Danh mục:** Thông báo, AWS Amplify, AWS WAF, Nổi bật, Front-End Web & Mobile, Ra mắt, Tin tức, Bảo mật, Danh tính & Tuân thủ

## Giới thiệu

Hôm nay, chúng tôi thông báo về việc tích hợp AWS WAF (Web Application Firewall) với AWS Amplify Hosting. Các chủ sở hữu ứng dụng web luôn nỗ lực bảo vệ ứng dụng của họ khỏi các mối đe dọa khác nhau.

## Vấn đề trước đây

Trước đây, nếu bạn muốn triển khai hệ thống bảo mật mạnh mẽ cho các ứng dụng Amplify Hosted, bạn cần:

- Tạo kiến trúc sử dụng Amazon CloudFront với bảo vệ AWS WAF
- Thực hiện các bước cấu hình phức tạp bổ sung
- Yêu cầu chuyên môn kỹ thuật cao
- Tăng chi phí quản lý đáng kể

## Giải pháp mới: Tích hợp AWS WAF với Amplify

Bây giờ, bạn có thể gắn trực tiếp tường lửa ứng dụng web vào ứng dụng AWS Amplify của mình thông qua:

- Tích hợp một cú nhấp chuột trong bảng điều khiển Amplify, hoặc
- Sử dụng Infrastructure as Code (IaC)

Tích hợp này cho phép bạn:

- Truy cập tất cả các tính năng AWS WAF
- Sử dụng các quy tắc được quản lý trước
- Tạo quy tắc tùy chỉnh dựa trên nhu cầu ứng dụng cụ thể của bạn
- Bảo vệ chống lại các lỗ hổng web phổ biến:
  - SQL injection
  - Cross-site scripting (XSS)

## Chiến lược bảo mật mạnh mẽ

### 1. Bảo vệ DDoS

Bạn có thể tận dụng các quy tắc dựa trên tỷ lệ của AWS WAF để:

- Giới hạn tỷ lệ yêu cầu từ các địa chỉ IP
- Bảo vệ chống lại các cuộc tấn công từ chối dịch vụ phân tán (DDoS)

### 2. Chặn địa lý

- Hạn chế truy cập vào ứng dụng của bạn từ các quốc gia cụ thể
- Đặc biệt hữu ích nếu dịch vụ của bạn nhắm đến các khu vực địa lý cụ thể

## Bốn loại bảo vệ được cung cấp bởi Amplify

### 1. Bảo vệ Firewall được Amplify khuyến nghị

- Bảo vệ chống lại các lỗ hổng phổ biến nhất được tìm thấy trong ứng dụng web
- Chặn địa chỉ IP từ các mối đe dọa tiềm ẩn dựa trên thông tin tình báo mối đe dọa nội bộ của Amazon
- Bảo vệ chống lại các tác nhân độc hại khám phá lỗ hổng ứng dụng

### 2. Hạn chế truy cập vào amplifyapp.com

- Hạn chế truy cập vào domain amplifyapp.com mặc định được tạo bởi Amplify
- Hữu ích khi bạn thêm domain tùy chỉnh
- Ngăn bot và công cụ tìm kiếm thu thập thông tin domain

### 3. Bảo vệ địa chỉ IP

- Hạn chế lưu lượng web bằng cách cho phép hoặc chặn yêu cầu từ các dải IP được chỉ định

### 4. Bảo vệ địa lý

- Hạn chế truy cập dựa trên các quốc gia cụ thể

## Cách thiết lập

Thiết lập bảo vệ AWS WAF cho ứng dụng Amplify của bạn rất đơn giản:

1. Từ bảng điều khiển Amplify, điều hướng đến cài đặt ứng dụng
2. Chọn tab Firewall
3. Chọn các quy tắc được xác định trước mà bạn muốn áp dụng

### Tạo Web Access Control List (ACL)

Các biện pháp bảo vệ được kích hoạt thông qua bảng điều khiển Amplify sẽ tạo một Web Access Control List (ACL) cơ bản trong tài khoản AWS của bạn.

**Đối với các bộ quy tắc chi tiết hơn:** Sử dụng trình tạo quy tắc trong bảng điều khiển AWS WAF.

### Thời gian kích hoạt

Sau vài phút, các quy tắc sẽ được liên kết với ứng dụng của bạn và AWS WAF sẽ bắt đầu chặn các yêu cầu đáng ngờ.

## Kiểm tra AWS WAF hoạt động

### Cách mô phỏng một cuộc tấn công

Bạn có thể mô phỏng một cuộc tấn công và giám sát nó bằng chức năng yêu cầu kiểm tra của AWS WAF.

**Ví dụ:** Gửi yêu cầu với giá trị header User-Agent trống → Điều này sẽ kích hoạt quy tắc chặn trong AWS WAF.

#### Bước 1: Gửi yêu cầu hợp lệ

Đầu tiên, gửi một yêu cầu hợp lệ đến ứng dụng của bạn.

**Kết quả:** Máy chủ trả về phản hồi HTTP 200 (OK)

#### Bước 2: Gửi yêu cầu không hợp lệ

Sau đó, gửi yêu cầu không có giá trị nào liên kết với header HTTP User-Agent.

**Kết quả:** Máy chủ trả về phản hồi HTTP 403 (Forbidden)

## Giám sát và tối ưu hóa

AWS WAF cung cấp khả năng hiển thị các mẫu yêu cầu, giúp bạn:

- Tinh chỉnh cài đặt bảo mật theo thời gian
- Phân tích xu hướng lưu lượng
- Cải thiện quy tắc bảo mật khi cần thiết

Bạn có thể truy cập nhật ký thông qua:

- Bảng điều khiển Amplify Hosting, hoặc
- Bảng điều khiển AWS WAF

## Tính khả dụng

- Có sẵn trong tất cả các vùng AWS nơi Amplify Hosting hoạt động
- Tích hợp này là một phần của tài nguyên toàn cầu của AWS WAF (tương tự như Amazon CloudFront)
- **Lưu ý:** Web ACL có thể được gắn vào nhiều ứng dụng Amplify Hosting, nhưng chúng phải ở cùng một vùng

## Mô hình giá cả

Giá cả cho tích hợp này tuân theo mô hình giá cả AWS WAF tiêu chuẩn:

### Chi phí AWS WAF:

Bạn trả tiền cho các tài nguyên AWS WAF mà bạn sử dụng dựa trên:

- Số lượng ACL
- Số lượng quy tắc
- Số lượng yêu cầu web

### Chi phí bổ sung từ AWS Amplify:

- **$15/tháng** khi bạn gắn tường lửa ứng dụng web vào ứng dụng của mình
- Chi phí này được tính theo giờ

## Lợi ích chính

Tính năng mới này mang các tính năng bảo mật cấp doanh nghiệp đến tất cả khách hàng Amplify Hosting, từ:

- Các nhà phát triển cá nhân
- Đến các doanh nghiệp lớn

Bây giờ bạn có thể:

- Xây dựng ứng dụng web
- Lưu trữ ứng dụng web
- Bảo vệ ứng dụng web

Tất cả trong cùng một dịch vụ, giảm:

- Độ phức tạp kiến trúc
- Chi phí quản lý bảo mật

## Kết luận

Tích hợp AWS WAF với Amplify Hosting là một bước tiến quan trọng trong việc đơn giản hóa bảo mật ứng dụng web. Với khả năng thiết lập các biện pháp bảo vệ mạnh mẽ chỉ bằng một cú nhấp chuột, các nhà phát triển có thể tập trung vào việc xây dựng ứng dụng của họ mà không phải lo lắng về độ phức tạp của bảo mật.

## Tài liệu tham khảo và tìm hiểu thêm

- [Tài liệu tích hợp AWS WAF cho Amplify](https://docs.aws.amazon.com/amplify/)
- [Thử trực tiếp trong bảng điều khiển Amplify](https://console.aws.amazon.com/amplify/)
- [Tài liệu AWS WAF](https://docs.aws.amazon.com/waf/)

## Về tác giả: Sébastien Stormacq

Seb đã viết code từ khi lần đầu tiên chạm vào Commodore 64 vào giữa những năm tám mươi. Anh ấy truyền cảm hứng cho các nhà phát triển khai thác sức mạnh của AWS Cloud, sử dụng sự kết hợp bí mật của:

- Đam mê
- Nhiệt tình
- Ủng hộ khách hàng
- Tò mò
- Sáng tạo

Sở thích của anh ấy: Kiến trúc phần mềm, công cụ phát triển và điện toán di động.

**Mẹo chuyên nghiệp:** Nếu bạn muốn bán cho anh ấy thứ gì đó, hãy đảm bảo nó có API.

Theo dõi @sebsto trên: Bluesky, X, Mastodon và hơn thế nữa.