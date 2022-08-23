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
  
![http-02](https://user-images.githubusercontent.com/111716161/186067978-1ff23cd1-a33c-4f5f-96bf-04c9b4700134.png)

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
  
Một URL được sử dụng để xác định duy nhất một tài nguyên trên Web và có cấu trúc như sau:
```
protocol://hostname:port/path-and-file-name
```
Trong một URL có 4 thành phần:
- Protocol: giao thức tầng ứng dụng được sử dụng bởi client và server.
- Hostname: tên DNS domain.
- Port: Cổng TCP để server lắng nghe request từ client.
- Path-and-file-name: Tên và vị trí của tài nguyên yêu cầu.

  <a name="requests"><a/>
### 2. HTTP – Requests
HTTP Request Method: Là phương thức để chỉ ra hành động mong muốn được thực hiện trên tài nguyên đã xác định.

Cấu trúc của một HTTP Request:
```
Request-line = Phương thức + URI–Request + Phiên bản HTTP.
```
Giao thức HTTP định nghĩa một tập các giao thức GET, POST, HEAD, PUT … Client có thể sử dụng một trong các phương thức đó để gửi request lên server.

Có thể có hoặc không các trường header.

Một dòng trống để đánh dấu sự kết thúc của các trường Header.

Request Header Fields: Các trường header cho phép client truyền thông tin bổ sung về yêu cầu, và về chính client, đến server. Một số trường: Accept-Charset, Accept-Encoding, Accept-Language, Authorization, Expect, From, Host,…

Khi request đến server, server sẽ thực hiện một trong 3 hành động sau:
- Server phân tích request nhận được, maps yêu cầu vào một chương trình trên server, thực thi chương trình và trả lại kết quả của chương trình đó.
- Server phân tích request nhận được, maps yêu cầu với tập tin trong tập tài liệu của server, và trả lại tập tin yêu cầu cho client.
- Request từ client không thể đáp ứng, server trả lại thông báo lỗi.
Giao thức HTTP định nghĩa một tập các phương thức request, client có thể sử dụng một trong các phương thức này để tạo request tới HTTP server, dưới đây liệt kê một số phương thức phổ biến: delete, get, post, put.
    
<p align="center">
  <img src ="https://user-images.githubusercontent.com/111716161/186068294-9256d038-b326-48d5-9790-bd2fd1607b3d.png"/>
    </p>
    
<a name="responses"><a/>
### 3. HTTP – Responses
  
Cấu trúc của một HTTP response:
```
Status-line = Phiên bản HTTP + Mã trạng thái + Trạng thái.
```
Có thể có hoặc không có các trường header.

Một dòng trống để đánh dấu sự kết thúc của các trường header.

Tùy chọn một thông điệp.

Mã trạng thái: Thông báo về kết quả khi nhận được yêu cầu và xử lí bên server cho client.
          
<p align="center">
  <img src ="https://user-images.githubusercontent.com/111716161/186068600-0a9634d2-b4ed-486b-b4fe-74d2d67155be.png"/>
    </p>
