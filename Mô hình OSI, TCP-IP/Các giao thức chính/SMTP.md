# Mục lục

[Giao thức SMTP là gì?](#smtp)

[Máy chủ SMTP là gì?](#maychu)

[Cách thức hoạt động của dịch vụ SMTP](#hoatdong)

[Lợi ích của SMTP](#loiich)

# Giao thức SMTP

<a name="smtp"></a>
## Giao thức SMTP là gì?
### Khái niệm
SMTP (Simple Mail Transfer Protocol) là giao thức chuẩn TCP/IP truyền tải thư điện tử đơn giản hóa. Giao thức này có nhiệm vụ thiết lập kênh kết nối giữa mail client và mail server, và thiết lập kênh liên lạc giữa mail server gửi và mail server nhận.

<p align="center">
  <img width="600" height="300" src="https://user-images.githubusercontent.com/111716161/186106242-77edeab8-bb40-4412-bfba-c7bd165c8f5b.png">
</p>

Việc gửi email được giao thức SMTP thực hiện thông qua TCP hoặc IP. Vì vậy, người dùng có thể an tâm về khả năng bảo mật và tính tiện lợi. 

Sử dụng giao thức SMTP giúp người dùng nâng cao hiệu suất làm việc. Bởi chúng hỗ trợ việc gửi lượng lớn thư điện tử chỉ trong thời gian ngắn. Nhờ thế, người dùng tiết kiệm rất nhiều thời gian và công sức so với việc gửi thư thủ công.

Chưa dừng tại đó, giao thức SMTP còn cho phép gửi tệp tin đính kèm với khả năng lưu trữ dung lượng lớn. Do đó, nó càng mang đến sự thuận tiện hơn cho người dùng trong môi trường doanh nghiệp cần trao đổi dữ liệu.

### Lịch sử hình thành
Vào khoảng thời gian đầu 1980, giao thức SMTP đã bắt đầu được khá nhiều doanh nghiệp nước ngoài sử dụng rộng rãi. Mặc dù thời gian đầu thì hệ thống SMTP khá đơn giản, nó chỉ là ứng dụng trong hệ thống UUCP mà thôi.

UUPC là hệ thống sao chép dữ liệu của máy Unix sang máy Unix khác, nó giúp hệ thống này trao đổi thư điện tử dễ dàng hơn so với các thiết bị khác cùng thời điểm đó.

Hiện nay thì SMTP đã trở thành một giao thức độc lập và hoạt động vô cùng tốt nếu như thiết bị gửi hoặc nhận Email có kết nối Internet liên tục là được.

SMTP hiện nay có thể được xem là một giao thức khá hoàn hảo và nó gần giống với Email. Tất cả công việc của SMTP đều cần thông qua Email và nó có sự liên quan mật thiết tới Email.

<a name="maychu"></a>
## Máy chủ SMTP là gì?
Máy chủ SMTP là dịch vụ cho phép gửi thư với số lượng lớn và tốc độ nhanh. Tất nhiên, nó sẽ không giới hạn như một số ứng dụng gửi thư miễn phí là Gmail hay hộp thư đi kèm hosting. SMTP server sử dụng giao thức TCP hoặc IP để thực hiện việc gửi email.

Thông thường, giao thức SMTP dùng internet port 25 (TCP) để hoạt động. Tuy nhiên, tại Châu Âu, có một phương thức được sử dụng phổ biến để thay thế cho SMTP là X.400. 

Ngoài ra, hiện nay cũng có khá nhiều máy chủ email hỗ trợ các giao thức truyền tải thư mở rộng và đơn giản là ESMTP. Đây là giao thức hỗ trợ người dùng gửi tập tin đa phương tiện qua email.

<a name="hoatdong"></a>
## Cách thức hoạt động của dịch vụ SMTP 
Phương thức hoạt động của SMTP được diễn giải theo các bước sau:
- Đầu tiên, thông báo việc gửi email được chuyển đến một máy chủ SMTP đã chỉ định.
- Tiếp đến, máy chủ SMTP sẽ dựa vào tên miền của email nhận mà tiến hành liên lạc với một máy chủ DNS. Sau đó, DNS server bắt đầu tìm kiếm và phản hồi về host name của máy chủ SMTP đích cho tên miền của email nhận. 
- Trong trường hợp tên người nhận trùng khớp với một trong các tài khoản người dùng trong máy chủ đích, hệ thống sẽ chuyển thông báo email gốc đến máy chủ này. Cuối cùng, người nhận lấy thông báo bằng chương trình gửi và nhận email (ví dụ Outlook).
- Nếu máy chủ SMTP đầu tiên không liên lạc và không thể trực tiếp trao đổi thông tin với máy chủ đích, thì giao thức SMTP sẽ chuyển thông báo qua một hoặc nhiều máy chủ SMTP trung gian. Trong đó, một máy chủ trung gian tiến hành nhận thông báo gốc rồi gửi đến máy chủ đích. Hoặc có khi nó lại chuyển thông báo đó đến một server trung gian khác. Quá trình này được thực hiện nhiều lần, và liên tục cho đến khi thông báo được chuyển đến máy chủ đích hoặc hết thời gian lưu trữ.

<a name="loiich"></a>
## Lợi ích của SMTP
Giao thức SMTP mang lại cho người dùng 3 lợi ích chính:
- Tăng tỷ lệ gửi email thành công cao hơn.
- Người dùng không cần cài đặt máy chủ nếu dùng hosting VPS.
- Hầu hết email của người dùng gửi đều được hệ thống mail server của người nhận đánh dấu an toàn. Vì thế, số lượng email bị chuyển vào thư mục Junk, Spam giảm đáng kể.
