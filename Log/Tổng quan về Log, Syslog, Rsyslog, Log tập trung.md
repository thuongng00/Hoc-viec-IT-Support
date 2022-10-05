[Log](#log)

[Syslog](#sys)

[Rsyslog](#rsys)

[Log tập trung](#logtt)

<a name="log"></a>
# Log

**Log** ghi lại liên tục các thông báo về hoạt động của cả hệ thống hoặc của các dịch vụ được triển khai trên hệ thống và file tương ứng. 

Log file thường là các file văn bản thông thường dưới dạng “clear text” tức là bạn có thể dễ dàng đọc được nó, vì thế có thể sử dụng các trình soạn thảo văn bản (vi, vim, nano…) hoặc các trình xem văn bản thông thường (cat, tailf, head…) là có thể xem được file log.

Các file log có thể nói cho bạn bất cứ thứ gì bạn cần biết, để giải quyết các rắc rối mà bạn gặp phải miễn là bạn biết ứng dụng nào. Mỗi ứng dụng được cài đặt trên hệ thống có cơ chế tạo log file riêng của mình để bất cứ khi nào bạn cần thông tin cụ thể thì các log file là nơi tốt nhất để tìm.

### Một vòng đời của Log

Bao gồm 5 bước chính:

![image](https://user-images.githubusercontent.com/111716161/193981732-e46a1632-55f2-4ca9-ac5d-6563f15e9590.png)

- Đầu tiên log sẽ được ghi lại tại chính máy local sau đó nó sẽ được vận chuyển sang máy chủ quản lý log.
- Người quản trị mạng sẽ từ những bản ghi đó mà tiến hành phân tích, từ đó có thể giám sát được hoạt động của các máy client.
- Qua bước phân tích này mà người quản trị có thể phát hiện các hoạt động, hành vi xâm nhập không được phép.
- Sau khi phân tích, dữ liệu log sẽ được lưu trữ để sử dụng lại nếu cần.
- Bước cuối cùng là xóa, thường những tập tin log không cần thiết có thể được xóa bởi người quản trị nhằm giảm bớt lượng thông tin log không cần thiết.

### Công dụng của Log

- Phân tích nguyên nhân khi có sự cố xảy ra.
- Giúp cho việc khắc phục sự cố nhanh hơn khi hệ thống gặp vấn đề.
- Giúp cho việc phát hiện, dự đoán một vấn đề có thể xảy ra đối với hệ thống.
- Khi xử lý log, thường quản trị viên có thể sử dụng 1 trong 2 phương pháp, đó là: xử lý log trên local và xử lý log tập trung.
- Log trên Local: chỉ lưu lại bản thân Server, dùng command find, tail... để xem log.

Các tập tin log được đặt trong thư mục /var/log. Bất kỳ ứng dụng khác mà sau này bạn có thể cài đặt trên hệ thống của bạn có thể sẽ tạo tập tin log của chúng tại /var/log. Dùng lệnh ls -l /var/log để xem nội dung của thư mục này.

## Ý nghĩa một số file log thông dụng có mặc định trên /var/log

`/var/log/messages` – Chứa dữ liệu log của hầu hết các thông báo hệ thống nói chung, bao gồm cả các thông báo trong quá trình khởi động hệ thống.

`/var/log/cron` – Chứa dữ liệu log của cron deamon. Bắt đầu và dừng cron cũng như cronjob thất bại.

`/var/log/maillog` hoặc `/var/log/mail.log` – Thông tin log từ các máy chủ mail chạy trên máy chủ.

`/var/log/wtmp` – Chứa tất cả các đăng nhập và đăng xuất lịch sử.

`/var/log/btmp` – Thông tin đăng nhập không thành công

`/var/run/utmp` – Thông tin log trạng thái đăng nhập hiện tại của mỗi người dùng.

`/var/log/dmesg` – Thư mục này có chứa thông điệp rất quan trọng về kernel ring buffer. Lệnh dmesg có thể được sử dụng để xem các tin nhắn của tập tin này.

`/var/log/secure` – Thông điệp an ninh liên quan sẽ được lưu trữ ở đây. Điều này bao gồm thông điệp từ SSH daemon, mật khẩu thất bại, người dùng không tồn tại...

## Một số log thường gặp

### Log SSH: /var/log/secure

```
tailf /var/log/secure | grep ssh 
```

![image](https://user-images.githubusercontent.com/111716161/193736363-f2100b99-9276-4c78-a180-96f3c462031c.png)

### Access log Apache:

```
tailf /var/log/httpd/access_log
```

![image](https://user-images.githubusercontent.com/111716161/193736781-b537144c-20e6-444e-b694-4b22a98c68a6.png)

### Error log Apache:

```
tailf error_log
```

### Log ghi lại những lần đăng nhập thành công:

```
last -f /var/log/wtmp

utmpdump /var/log/wtmp
```

![image](https://user-images.githubusercontent.com/111716161/193737102-3aa9f97a-d2e7-461b-85a2-c1958a659362.png)

![image](https://user-images.githubusercontent.com/111716161/193737172-7b45ccf5-0ee5-4bfa-bd8c-43d189a2ab6d.png)

### Log ghi lại những lần đăng nhập thất bại:

```
lastb -f /var/log/btmp | more
```

![image](https://user-images.githubusercontent.com/111716161/193737227-c4347354-c23c-45d6-accb-c754d8c77d02.png)

<a name="sys"></a>
# Syslog

![image](https://user-images.githubusercontent.com/111716161/193737331-554713c2-fd88-40d4-b1b6-6f360a17853c.png)

**Syslog** là một giao thức client/server là giao thức dùng để chuyển log và thông điệp đến máy nhận log. Máy nhận log thường được gọi là syslogd, syslog daemon hoặc syslog server. Syslog có thể gửi qua UDP hoặc TCP. Các dữ liệu được gửi dạng cleartext. Syslog dùng port 514.

Syslog được phát triển năm 1980 bởi Eric Allman, nó là một phần của dự án Sendmail, và ban đầu chỉ được sử dụng duy nhất cho Sendmail. Nó đã thể hiện giá trị của mình và các ứng dụng khác cũng bắt đầu sử dụng nó. Syslog hiện nay trở thành giải pháp khai thác log tiêu chuẩn trên Unix-Linux cũng như trên hàng loạt các hệ điều hành khác và thường được tìm thấy trong các thiết bị mạng như router Trong năm 2009, Internet Engineering Task Forec (IETF) đưa ra chuẩn syslog trong RFC 5424.

Trong chuẩn syslog, mỗi thông báo đều được dán nhãn và được gán các mức độ nghiêm trọng khác nhau. Các loại phần mềm sau có thể sinh ra thông báo: auth, authPriv, daemon, cron, ftp, dhcp, kern, mail, syslog, user,… Với các mức độ nghiêm trọng từ cao nhất trở xuống Emergency, Alert, Critical, Error, Warning, Notice, Info, and Debug.

## Mục đích của Syslog

Syslong được sử dụng như một tiêu chuẩn, chuyển tiếp và thu thập log được sử dụng trên một phiên bản Linux. 

Syslog xác định mức độ nghiêm trọng (severity levels) cũng như mức độ cơ sở (facility levels) giúp người dùng hiểu rõ hơn về nhật ký được sinh ra trên máy tính của họ. 

Log (nhật ký) có thể được phân tích và hiển thị trên các máy chủ được gọi là máy chủ Syslog.

Giao thức Syslog có những yếu tố sau:
- Defining an architecture (xác định kiến trúc): Syslog là một giao thức, nó là một phần của kiến trúc mạng hoàn chỉnh với nhiều máy khách và máy chủ. 
- Message format (định dạng tin nhắn): Syslog xác định cách định dạng tin nhắn. Điều này rõ ràng cần phải được chuẩn hóa vì các bản ghi thường được phân tích cú pháp và lưu trữ vào các công cụ lưu trữ khác nhau. Do đó chúng ta cần xác định những gì một máy khách syslog có thể tạo ra và những gì một máy chủ syslog có thể nhận được. 
- Specifying reliability (chỉ định độ tin cậy): Syslog cần xác định cách xử lý các tin nhắn không thể gửi được. Là một phần của TCP/IP, syslog rõ ràng sẽ bị thay đổi trên giao thức mạng cơ bản (TCP hoặc UDP) để lựa chọn. 
- Dealing with authentication or message authenticity (xử lý xác thực hoặc xác thực thư): syslog cần một cách đáng tin cậy để đảm bảo rằng máy khách và máy chủ đang nói chuyện một cách an toàn và tin nhắn nhận được không bị thay đổi.

## Định dạng tin nhắn Syslog

Định dạng nhật ký hệ thống được chia thành ba phần, độ dài một thông báo không được vượt quá 1024 bytes:

- PRI : chi tiết các mức độ ưu tiên của tin nhắn (từ tin nhắn gỡ lỗi (debug) đến trường hợp khẩn cấp) cũng như các mức độ cơ sở (mail, auth, kernel).
- Header: bao gồm hai trường là TIMESTAMP và HOSTNAME, tên máy chủ là tên máy gửi nhật ký.
- MSG: phần này chứa thông tin thực tế về sự kiện đã xảy ra. Nó cũng được chia thành trường TAG và trường CONTENT.

Chuyển tiếp nhật ký hệ thống (syslog forwarding) bao gồm gửi log máy khách đến một máy chủ từ xa để chúng được tập trung hóa, giúp phân tích log dễ dàng hơn.

Hầu hết thời gian, quản trị viên hệ thống không giám sát một máy duy nhất, nhưng họ phải giám sát hàng chục máy, tại chỗ và ngoài trang web.

Kết quả là, việc gửi nhật ký đến một máy ở xa, được gọi là máy chủ ghi log tập trung, sử dụng các giao thức truyền thông khác nhau như UDP hoặc TCP.

<a name="rsys"></a>
# Rsyslog

**Rsyslog** – “The rocket-fast system for log processing” được bắt đầu phát triển từ năm 2004 bởi Rainer Gerhards. 

Rsyslog là một phần mềm mã nguồn mở sử dụng trên Linux dùng để chuyển tiếp các log message đến một địa chỉ trên mạng (log receiver, log server). Nó thực hiện giao thức syslog cơ bản, đặc biệt là sử dụng TCP cho việc truyền tải log từ client tới server. 

Hiện nay rsyslog là phần mềm được cài đặt sẵn trên hầu hết hệ thống Unix và các bản phân phối của Linux như : Fedora, openSUSE, Debian, Ubuntu, Red Hat Enterprise Linux, FreeBSD…

![image](https://user-images.githubusercontent.com/111716161/193751690-67a60458-f71f-4524-8d4f-af206a510514.png)

Nếu bạn đang sử dụng một bản phân phối Linux hiện đại (như máy Ubuntu, CentOS hoặc RHEL), máy chủ syslog mặc định được sử dụng là rsyslog.

Rsyslog là một sự phát triển của syslog, cung cấp các khả năng như các mô đun có thể cấu hình, được liên kết với nhiều mục tiêu khác nhau (ví dụ chuyển tiếp nhật ký Apache đến một máy chủ từ xa).

Rsyslog cũng cung cấp tính năng lọc riêng cũng như tạo khuôn mẫu để định dạng dữ liệu sang định dạng tùy chỉnh.

## Modules Rsyslog

Rsyslog có thiết kế kiểu mô-đun. Điều này cho phép chức năng được tải động từ các mô-đun, cũng có thể được viết bởi bất kỳ bên thứ ba nào. Bản thân Rsyslog cung cấp tất cả các chức năng không cốt lõi như các mô-đun. Do đó, ngày càng có nhiều mô-đun. Có 6 modules cơ bản:

1. Output Modules
2. Input Modules
3. Parser Modules
4. Message Modification Modules
5. String Generator Modules
6. Library Modules

## Tìm hiểu file cấu hình rsyslog

```
egrep -v "^#|^$|^*#" /etc/rsyslog.conf
```

![image](https://user-images.githubusercontent.com/111716161/193753992-17e90dd7-f73c-4ad5-a26c-2f404e895ebd.png)

Cấu hình trên được chia ra làm 2 trường: 
- Trường 1: Seletor.

Trường Seletor chỉ ra nguồn tạo ra log và mức cảnh báo của log đó. Trong trường seletor có 2 thành phần và được tách nhau bằng dấu `.`.

![image](https://user-images.githubusercontent.com/111716161/193754247-764acfdb-dd0a-4722-88c1-9baa6f15ec4f.png)

- Trường 2: Trường Action.

Trường Action là trường để chỉ ra nơi lưu log của tiến trình đó. Có 2 loại là lưu tại file trong localhost hoặc gửi đến IP của máy chủ log. 

![image](https://user-images.githubusercontent.com/111716161/193754419-80531910-6565-4020-8c6c-60e855bbd0f3.png)

***Ý nghĩa các dòng lệnh***

```
mail.info         /var/log/maillog
```

Khi đó lúc này bản tin log sẽ mail lại với mức cảnh báo từ info trở lên. Cụ thể là mức notice,warn,… nếu bạn chỉ muốn nó log lại mail với mức là info bạn phải sử dụng như sau: `mail.=info /var/log/maillog`


```
mail.* 
```

Lúc này kí tự * đại diên cho các mức cảnh báo. Lúc này nó sẽ lưu hết các level của mail vào trong thư mục. Tượng tự khi đặt *. thì lúc này nó sẽ log lại tất cả các tiến trình của hệ thống vào một file. Nếu bạn muốn log lại tiến trình của mail ngoại trừ mức info bạn có thể dùng kí tự “!”

```
*.info;mail.none;authpriv.none;cron.none                /var/log/messages
```

Lúc này tất các log từ info của tiến trình hệ thống sẽ được lưu vào trong file log messages nhưng đối với các log của mail, authpriv và cron sẽ không lưu vào trong messages. Đó là ý nghĩa của dòng mail.none;authpriv.none;cron.none

<a name="logtt"></a>
# Log tập trung

![image](https://user-images.githubusercontent.com/111716161/193752159-fbefb738-abb8-4901-a4f8-da11a1833d9e.png)

**Log tâp trung** là quá trình tập trung, thu thập, phân tích… các log cần thiết từ nhiều nguồn khác nhau về một nơi an toàn để thuận lợi cho việc phân tích, theo dõi hệ thống.

## Lý do phải sử dụng log tập trung

### Do có nhiều nguồn sinh log.
- Có nhiều nguồn sinh ra log, log nằm trên nhiều máy chủ khác nhau nên khó quản lý.
- Nội dung log không đồng nhất (Giả sử log từ nguồn 1 có có ghi thông tin về ip mà không ghi thông tin về user name đăng nhập mà log từ nguồn 2 lại có) -> khó khăn trong việc kết hợp các log với nhau để xử lý vấn đề gặp phải.
- Định dạng log cũng không đồng nhất -> khó khăn trong việc chuẩn hóa.

### Đảm bảo tính toàn vẹn, bí mật, sẵn sàng của log.
- Do có nhiều các rootkit được thiết kế để xóa bỏ logs.
- Do log mới được ghi đè lên log cũ -> Log phải được lưu trữ ở một nơi an toàn và phải có kênh truyền đủ đảm bảo tính an toàn và sẵn sàng sử dụng để phân tích hệ thống.

## Ưu, nhược điểm của log tập trung

### Ưu điểm

- Giúp quản trị viên có cái nhìn chi tiết về hệ thống -> có định hướng tốt hơn về hướng giải quyết.
- Mọi hoạt động của hệ thống được ghi lại và lưu trữ ở một nơi an toàn (log server) -> đảm bảo tính toàn vẹn phục vụ cho quá trình phân tích điều tra các cuộc tấn công vào hệ thống.
- Log tập trung kết hợp với các ứng dụng thu thập và phân tích log khác nữa giúp cho việc phân tích log trở nên thuận lợi hơn -> giảm thiểu nguồn nhân lực.

### Nhược điểm

- Nguy cơ quá tải máy chủ syslog của mình: với cấu trúc này, bạn đang đẩy các bản ghi đến một máy chủ từ xa. Hậu quả là, nếu một máy bị tấn công và bắt đầu gửi hàng ngàn log messages, có nguy cơ làm quá tải máy chủ log.
- Nếu máy chủ nhật ký bị hỏng, bạn sẽ mất khả năng xem tất cả các nhật ký được gửi bởi khách hàng. Hơn nữa, nếu máy chủ ngừng hoạt động, máy khách sẽ bắt đầu lưu trữ thư cục bộ cho đến khi máy chủ khả dụng trở lại, do đó không gian đĩa ở phía máy khách sẽ dần bị đầy.


