# Mục lục

[Khái niệm](#khainiem)

[Đặc điểm](#dacdiem)

[Sơ đồ hoạt động](#sodo)

[Các thành phần chính](#thanhphan)

  [1. Uniform Resource Locator (URL)](#url)
  
  [2. HTTP – Requests](#requests)
  
  [3. HTTP – Responses](#responses)

[Cấu trúc của một gói tin HTTP](#cautruc)

# Giao thức HTTP 

<a name="khainiem"><a/>
## Khái niệm
HyperText Transfer Protocol – Giao thức truyền tải siêu văn bản: là một trong các giao thức chuẩn về mạng Internet, được dùng để liên hệ thông tin giữa máy cung cấp dịch vụ (Web server) và máy sử dụng dịch vụ (Web client).

Là giao thức Client/Server dùng cho World Wide Web – WWW.

HTTP là một giao thức ứng dụng của bộ giao thức TCP/IP (các giao thức nền tảng cho Internet).

HTTP lần đầu được giới thiệu vào những năm 90. Cho đến ngày nay, nó không ngừng được mở rộng và chiếm một vị trí rất quan trọng trong thế giới Internet. HTTP được coi như là một giao thức ứng dụng của bộ các giao thức nền tảng cho Internet TCP/IP. Nó cũng có thể được gửi thông qua kết nối TCP được mã hóa TLS.
  
![http-02](https://user-images.githubusercontent.com/111716161/186067978-1ff23cd1-a33c-4f5f-96bf-04c9b4700134.png)
  
<a name="dacdiem"><a/>
## Đặc điểm
  
**HTTP có thiết kế đơn giản** 
  
Đơn giản chính là đáp án nổi bật nhất cho câu hỏi đặc điểm của giao thức HTTP là gì. Thật vậy, mục đích xuất hiện của HTTP là tạo ra một công cụ thật thân thiện, có thể được sử dụng dễ dàng bởi mọi đối tượng. Các HTTP message đều có cấu tạo rất đơn giản để những người mới sử dụng cũng có thể đọc hiểu được.

**HTTP có khả năng mở rộng**
  
HTTP sở hữu tính linh hoạt rất cao. Nó không có bất kỳ một giới hạn nào về sự nâng cấp và mở rộng. Thậm chí, chỉ cần bằng một thỏa thuận thống nhất giữa client và server là một tính năng mới của HTTP đã được hình thành.

**HTTP là stateless – Giao thức HTTP là gì**
  
Bởi mọi phản hồi của HTTP là độc lập nên người dùng không thể tạo sự liên kết thông tin giữa các phản hồi được. Điều này có thể sẽ trở thành một nhược điểm đối với những trường hợp người dùng cần có các tương tác mạch lạc và bổ trợ cho nhau, ví dụ như shopping cart trên các trang thương mại điện tử.

Để khắc phục vấn đề này, HTTP cho phép mở rộng tự do các header. Trong đó, người dùng có thể tự tạo cho mình session trên mỗi request nhằm mục đích chia sẻ các ngữ cảnh hoặc trạng thái giữa các request với nhau. Sở dĩ trường hợp này có thể thực hiện được vì bản thân HTTP là stateless.
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
Giao thức HTTP định nghĩa một tập các phương thức request, client có thể sử dụng một trong các phương thức này để tạo request tới HTTP server, dưới đây liệt kê một số phương thức phổ biến: delete, get, post, put, options, head.
    
<p align="center">
  <img src ="https://user-images.githubusercontent.com/111716161/186068294-9256d038-b326-48d5-9790-bd2fd1607b3d.png"/>
    </p>
    
 - GET : GET được sử dụng để lấy thông tin từ Server.

 Khi bạn truy câp một trang web từ trình duyệt thông qua URL thì bạn đang thực hiện một GET request trên URL đó để lấy dữ liệu.

 - POST : Một yêu cầu POST được sử dụng để gửi dữ liệu tới Server.

 Khi bạn nhập mật khẩu và password trong một trang web nào đó và nhấp Login, thì lúc này bạn đang gửi dữ liệu của bạn đến máy chủ của trang web đó thông qua phương thức POST.

 - PUT : Phương thức này được dùng với ý nghĩa là bạn đang thay đổi, cập nhật lại nội dung của một nguồn dữ liệu nào đó.

 Ví dụ bạn muốn cập nhật thông tin Profile trong trang Sociss Class, sau khi điền thông tin, bạn nhấp vào Save, thì lúc này mình đang gửi một PUT request tới Server để cập nhật lại thông tin cho các bạn.

 - DELETE : Phương thức này sử dụng với ý nghĩa bạn muốn xóa một tài nguyên nào đó.

 Ví dụ bạn muốn xóa một bình luận của bạn, thì bạn sẽ gửi một DELETE request kèm theo ID của bình luận đó tới Server, lúc này Server sẽ nhận ra là bạn đang muốn xóa sản phẩm với ID đó và thực hiện yêu cầu của bạn.

 - OPTIONS : Phương thức này thường được gửi đến Server trước mỗi Request POST, PUT, GET , DELETE ở trên để kiếm tra xem Server chấp nhận những yêu cầu loại nào.

 Ví dụ với Sociss Class, mình không bao giờ chấp nhận bất cứ yêu Cầu DELETE nào cho khóa học từ client cả, để tránh ai đó xóa khóa học trái phép.

 Lúc này nếu bạn gửi yêu cầu DELETE thì yêu cầu OPTIONS sẽ được gửi đầu tiên để kiểm tra mình cho phép những Request Methods nào, khi trả về kết quả thì không có DELETE trong đó. Lúc này trình duyệt sẽ báo lỗi là Server không chấp nhận DELETE request và từ chối yêu cầu.

 - HEAD : Phương thức này chỉ lấy về phần Header của tài nguyên không có phần thân (Body) , thường dùng để kiểm tra thông tin của tài nguyên đó , ứng dụng nhiều trong việc Caching của trình duyệt.
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
Các kiểu mã trạng thái:
- 1xx: Thông tin (100 -> 101)

VD: 100 (Continue), …
- 2xx: Thành công (200 -> 206)

VD: 200 (OK), 201 (CREATED), …
- 3xx: Sự điều hướng lại (300 -> 307)

VD: 305 (USE PROXY), …
- 4xx: Lỗi phía Client (400 -> 417)

VD: 403 (FORBIDDEN), 404 (NOT FOUND), …
- 5xx: Lỗi phía Server (500 -> 505)

VD: 500 (INTERNAL SERVER ERROR)

  <a name="cautruc"><a/>
## Cấu trúc của một gói tin HTTP
 Cấu trúc một gói tin HTTP bao gồm các thành phần sau.

Request Line : Chứa Request method và đường dẫn URL của tài nguyên đích.
Header: Chứa các thông tin của thiết bị thực hiện Request này.
Body : Phần thân chứa dữ liệu của Request.
 Ví dụ :

GET / HTTP/1.1

 Accept: */*

 Accept-Language: en-us

 Accept-Encoding: gzip, deflate

 User-Agent: Mozilla/4.0 (compatible; MSIE 5.5; Windows NT 5.0)

 Host: www.nhanhoa.com.vn

 Connection: Keep-Alive
    
    
