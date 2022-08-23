# Mục lục

[Khái niệm](#khainiem)

[Sơ đồ hoạt động](#sodo)

[Các thành phần chính](#thanhphan)
  [1. Uniform Resource Locator (URL)](#url)
  
  [2. HTTP – Requests](#requests)
  
  [3. HTTP – Responses](#responses)

# Giao thức HTTP 

<a name="khainiem"><a/>
## Khái niệm
HyperText Transfer Protocol – Giao thức truyền tải siêu văn bản: là một trong các giao thức chuẩn về mạng Internet, được dùng để liên hệ thông tin giữa máy cung cấp dịch vụ (Web server) và máy sử dụng dịch vụ (Web client).

Là giao thức Client/Server dùng cho World Wide Web – WWW.

HTTP là một giao thức ứng dụng của bộ giao thức TCP/IP (các giao thức nền tảng cho Internet).

HTTP lần đầu được giới thiệu vào những năm 90. Cho đến ngày nay, nó không ngừng được mở rộng và chiếm một vị trí rất quan trọng trong thế giới Internet. HTTP được coi như là một giao thức ứng dụng của bộ các giao thức nền tảng cho Internet TCP/IP. Nó cũng có thể được gửi thông qua kết nối TCP được mã hóa TLS.

<a name="sodo"></a>
## Sơ đồ hoạt động của HTTP
HTTP hoạt động dựa trên mô hình Client – Server.

Trong mô hình client – server, các máy tính của người dùng sẽ đóng vai trò làm máy khách (Client). Sau một thao tác nào đó của người dùng, các máy khách sẽ gửi yêu cầu đến máy chủ (Server) và chờ đợi câu trả lời từ những máy chủ này.

HTTP là một stateless protocol. Hay nói cách khác, request hiện tại không biết những gì đã hoàn thành trong request trước đó.

HTTP cho phép tạo các yêu cầu gửi và nhận các kiểu dữ liệu, do đó cho phép xây dựng hệ thống độc lập với dữ liệu được truyển giao.
 
<a name="thanhphan"></a>
## Các thành phần chính của HTTP

<a name="url"><a/>
### 1. Uniform Resource Locator (URL)
