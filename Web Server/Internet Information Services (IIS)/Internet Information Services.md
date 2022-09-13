[Internet Information Services (IIS)](#iis)

[So sánh IIS và Apache](#sosanh)
<a name="iis"></a>
# Internet Information Services (IIS)

Internet Information Services (IIS) được đính kèm với các phiên bản của Windows, là các dịch vụ dành cho máy chủ chạy trên nền hệ điều hành Windows nhằm cung cấp và phân tán các thông tin lên mạng, nó bao gồm nhiều dịch vụ khác nhau như Web Server, FTP Server...

Nó có thể được sử dụng để xuất bản nội dung của các trang Web lên Internet/Intranet bằng việc sử dụng “Phương thức chuyển giao siêu văn bản“ – Hypertext Transport Protocol (HTTP).

## Nhiệm vụ, hoạt động và tính năng

Nhiệm vụ của IIS là tiếp nhận yêu cầu của máy trạm và đáp ứng lại yêu cầu đó bằng cách gửi về máy trạm những thông tin mà máy trạm yêu cầu.

Bạn có thể sử dụng IIS để:

- Xuất bản một Website của bạn trên Internet
- Tạo các giao dịch thương mại điện tử trên Internet (hiện các catalog và nhận được các đơn đặt hàng từ nguời tiêu dùng)
- Chia sẻ file dữ liệu thông qua giao thức FTP.
- Cho phép người ở xa có thể truy xuất database của bạn (gọi là Database remote access).Và rất nhiều khả năng khác …

IIS sử dụng các giao thức mạng phổ biến là HTTP và FTP (File Transfer Protocol) để tiếp nhận yêu cầu và truyền tải thông tin trên mạng với các định dạng khác nhau.

Một trong những dịch vụ phổ biến nhất của IIS mà chúng ta quan tâm trong giáo trình này là dịch vụ WWW (World Wide Web), nói tắt là dịch vụ Web.

Dịch vụ Web sử dụng giao thức HTTP để tiếp nhận yêu cầu (Requests) của trình duyệt Web (Web browser) dưới dạng một địa chỉ URL (Uniform Resource Locator) của một trang Web và IIS phản hồi lại các yêu cầu bằng cách gửi về cho Web browser nội dung của trang Web tương ứng.

Một trong những tính năng được sử dụng nhiều nhất của IIS là tạo một ứng dụng web bằng ASP.NET. Bên cạnh đó, IIS hoàn toàn có thể chạy được với các trang web viết bằng các ngôn ngữ khác như PHP, Perl,…

IIS hỗ trợ một số loại xác thực như Basic access authentication, Digest access authentication, Windows Authentication, Certificate authentication,…; các tính năng bảo mật khác bao gồm hỗ trợ SSL/TLS, Server Name Indication (SNI), thiết lập bảo mật cho máy chủ FTP,…

Với thiết kế dạng module, việc mở, tắt và cài đặt một số tính năng để đáp ứng nhu cầu của người sử dụng cũng như tối ưu hiệu năng và bảo mật cho web server được đáp ứng.

### 1. IIS Manager

IIS Manager là một giao diện đồ hoạ được thiết kế để quản trị IIS Server. Nó quản lý tài nguyên các file, directory, và các thiết lập cho các ứng dụng như về security, performance và các tính năng khác.

### 2. Audit Policy

Cần thiết lập Audit Policy trên IIS Server trong môi trường làm việc đảm bảo toàn bộ thông tin của người dùng khi log vào hệ thống sẽ đều được ghi lại. Tất cả những dữ liệu được truy cập đều được log lại.

### 3. User Rights Assignments

Cần thiết lập “Deny access to this computer from the network”, với thiết lập này sẽ quyết định những users nào bị cấm truy cập tới IIS Server từ mạng. Thiết lập này sẽ cấm một số các giao thức mạng, bao gồm:
- Server Message Block (SMB).
- NetBIOS.
- Common Internet File System (CIFS)
- Hypertext Transfer Protocol (HTTP)
- Component Object Model Plus (COM+).

Với thiết lập này tài khoản người dùng sẽ bị hạn chế và đảm bảo tính bảo mật cao hơn dưới đây là những người dùng cần phải thiết lập:
- ANONOYMOUS LOGON,
- Built-in Administrator, Suport_388945a0,
- Guest và toàn bộ người dùng không thuộc các tài khoản có sẵn.

Tất cả những thiết lập trên đều được thực hiện trong User Rights Assignments.

### 4. Event Log

Cần thiết lập trên IIS Servers lưu lại toàn bộ các sự kiện theo một thể thống nhất với các tham số tuỳ vào yêu cầu, nhưng có hai yêu cầu cần ghi lại đó là:
- Ghi lại quá trình đăng nhập hệ thống.
- Ghi lại những đối tượng được truy cập (kể cả lỗi hay không có lỗi xảy ra trong quá trình đăng nhập).

### 5. SYSTEM Services
Cần phải thiết lập những dịch vụ sau trong Microsoft Windows Server ở chế độ automatically:
- HTTP SSL.

HTTP SSL được kích hoạt trong IIS Servers để thực hiện Secure Sockets Layer (SSL). SSL là một chuẩn để thiết lập bảo mật khi truyền những thông tin nhạy cảm. Nếu HTTP SSL bị tắt thì IIS Servers sẽ không làm việc với SSL. Dẫn tới một số dịch vụ khác phụ thuộc vào nó bị ảnh hưởng.

- IIS Admin Service.

IIS Admin Service cho phép quản trị các thành phần trong IIS như FTP, Application Pools, Web Sites, Web Service Extensions và cả NNTP và SMTP. IIS Admin Service cần phải hoạt động để cung cấp Web, FTP, NNTP và SMTP. Nếu dịch vụ này bị tắt, IIS sẽ không thể cấu hình , tất cả những yêu cầu cho tới dịch vụ Web đều bị ngưng trệ.

- World Wide Web Publishing Service.

Dịch vụ này cung cấp kết nối và quản trị Website qua IIS Snap-in. Dịch vụ này buộc phải chạy trên IIS Server để cung cấp kết nối Web và quản trị trên IIS Manager.

### 6. Web Service Extensions

Khi kích hoạt toàn bộ các Web Service Extensions chắc chắn một điều nó sẽ có khả năng tương thích và hỗ trợ cao nhất cho các ứng dụng, tuy nhiên nó cũng tạo ra các nguy cơ về bảo mật. Để hạn chế nguy cơ bảo mật cần phải hiểu các Extensions và chỉ những Extensions nào cần thiết thì mới kích hoạt nó trên IIS Server mà thôi.

### 7. Thiết lập vùng an toàn

Nên chuyển tất cả tập tin và thư mục của website vào vùng an toàn nhằm ngăn chặn việc tấn công và nếu có vấn đề gì xảy ra có thể restore lại một cách dễ dàng. Ngoài ra bạn có thể bảo mật thư mục góc bằng cách hạn chế truy cập theo NTFS và một số cơ chế bảo khác.

### 8. IIS Web Site Permissions

IIS có khả năng thiết lập Web site permissions để quyết định cho phép hay cấm những hành động nào truy cập vào website. Web site permissions có thể thực hiện để bảo mật website trên IIS Server. Dưới đây là chi tiết các quyền có thể gán trong Web Site Permissions:
- Read: Chỉ được xem các nội dung và các thuộc tính của các thư mục hoặc tập tin. Đây là thiết lập mặc định.
- Write: Có khả năng thay đổi nội dung và thuộc tính của các thư mục hoặc tập tin.
- Script Source Access: Có thể xem các thông tin và phụ thuộc vào Read, Write.
- Directory browing: Có thể xem danh sách các tập tin.
- Log Visits: Toàn bộ log ghi lại quá trình truy cập của người dùng vào web site
- Index this Resource: Cho phép Indexing Service có khả năng index resource.
- Excuted: Thực thi script, có những tuỳ chọn cho từng users:
  - None: Không cho chạy các script trên server. 
  - Scripts only: Chỉ cho phép các scripts chạy trên server. 
  - Scripts and executables: Cho phép cả script và executables.

### 9. Thực hiện bảo mật IIS Server bằng IPSec

Internet Protocol Security (IPSec) Filters có thể cung cấp khả năng tối ưu hưu hoá bảo mật máy chủ ở mức độ rất cao và là một mức độ bảo mật cần thiết trên các máy chủ.

### 10. Một số tiêu chí khi triển khai
Để bảo vệ cho máy chủ IIS cần thực hiện một số biện pháp sau:
- Nên sử dụng các giao thức mã hóa như SSL hoặc TLS nhằm mã hóa các kết nối an toàn.
- Cần thiết lập các thuộc tính trong Audit Policy trên máy chủ IIS trong môi trường làm việc đảm bảo toàn bộ thông tin của người dùng khi đăng nhập vào hệ thống sẽ đều được ghi lại. Tất cả những dữ liệu khi truy cập đều được ghi lại nhật ký.
- Cần thiết lập “Deny access to this computer from the network”, với thiết lập này sẽ quyết định những tài khoản nào bị cấm truy cập tới máy chủ IIS từ mạng và các tài khoản người dùng sẽ bị hạn chế và đảm bảo tính bảo mật cao hơn. - - Sau đây là những tài khoản người dùng cần phải thiết lập chế độ cấm nêu trên: ANONYMOUS LOGON, Built-in Administrator và Guest.
- Nên tắt tất cả chi tiết thông báo lỗi mà có khả năng đưa ra quá nhiều thông tin. Việc đưa ra quá chi tiết các thông báo lỗi sẽ dẫn đến việc các tin tặc có thể lợi dụng để tìm hiểu thông tin về hệ thống.
- Nên cài đặt thư mục gốc của ứng dụng web trên phân vùng đĩa có định dạng NTFS, bởi vì khả năng kiểm soát quyền truy cập trên hệ thống tập tin với phân vùng định dạng NTFS mạnh hơn so với các định dạng FAT, FAT32. Khi đã cài đặt thư mục gốc trên phân vùng NTFS thì cũng phải thiết lập quyền truy cập thấp nhất cho thư mục gốc này, tránh trường hợp thư mục gốc của ứng dụng web được mặc định là Everyone: Full Control.
- Trong IIS có rất nhiều thành phần (module) bổ trợ. Nên gỡ bỏ những thành phần không cần thiết ra khỏi IIS được cài đặt, vì những thành phần này khi bị lỗi có khả năng dẫn đến IIS bị tấn công và chiếm quyền kiểm soát một cách gián tiếp.
- Nên cài đặt URLScan để bổ sung thêm nhiều tính năng bảo mật cho IIS.

<a name="sosanh"></a>
# So sánh IIS với Apache

Máy chủ web Apache rất phổ biến nó miễn phí. Điều này rất thuận lợi cho những người chỉ đang cố gắng xuất bản trên web và vẫn không chắc chắn về nó. Apache được sử dụng rộng rãi nhất trong một giải pháp máy chủ web miễn phí được gọi là LAMP (Linux / Apache / MySQL / PHP) là một bộ sưu tập của phần mềm nguồn mở hoàn toàn có thể giải quyết tất cả nhu cầu xuất bản trên web của bạn từ hệ điều hành xuống ngôn ngữ kịch bản. Ngoài việc tự do, cộng đồng mã nguồn mở cũng là một nguồn hỗ trợ tốt cho những người dùng có thời gian và kiên nhẫn để yêu cầu các câu trả lời.

IIS là từ Microsoft và do đó nó sẽ chỉ chạy trên hệ điều hành Microsoft Windows, cần phải mua Windows để sử dụng nó. Lợi thế rõ ràng khi chạy IIS là hầu hết mọi người đã quen thuộc với hệ điều hành Windows và IIS sẽ dễ dàng hơn nhiều để tìm hiểu cho người dùng Windows. IIS cũng đi kèm với sự hỗ trợ của .NET Framework được phát hành bởi Microsoft; trên thực tế, kịch bản ASPX chỉ dành cho IIS. Hỗ trợ cho IIS được cung cấp bởi Microsoft là một đảm bảo rằng bạn sẽ có câu trả lời cho vấn đề của bạn trực tiếp từ các nhà sản xuất mình.

- IIS được đi kèm với Windows còn Apache là một mã nguồn mở miễn phí.
- IIS dành cho Windows còn Apache dành cho tất cả các hệ điều hành như macOS, UNIX và Linux.
- IIS tích hợp với các dịch vụ của Microsoft như .NET và ASPX.
- IIS có khả năng xử lý các vấn đề từ bộ phận trợ giúp còn Apache dựa vào cộng đồng.
- IIS bảo mật an toàn hơn Apache.
- IIS với các công nghệ hiện đại có sự tương thích cao hơn so với Apache.

