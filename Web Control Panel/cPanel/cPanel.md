# cPanel

**cPanel** là web hosting control panel (công cụ quản trị web hosting) trên nền tảng Linux phổ biến nhất hiện nay. cPanel có giao diện đơn giản, linh hoạt, giúp người dùng quản lý tất cả các dịch vụ của web hosting một cách dễ dàng.

Web Hosting Manager viết tắt là WHM. Đây là hệ thống cho phép quản lý đơn giản để bạn kiểm soát tất cả những gì trên web server. Giao diện của nó thường dễ dùng, cung cấp nhiều tiện ích với chức năng web server. WHM quản lý Server, quản lý DNS tên miền, quản lý khách hàng, quản lý đơn hàng,…

![image](https://user-images.githubusercontent.com/111716161/193789116-6269f544-a8c0-4ce0-b31c-c737753b7310.png)

Công cụ quản trị web hosting này có giao diện thân thiện với người dùng và hoạt động trên hệ thống phân cấp ba lớp như sau:

- Hosting Company (Nhà cung cấp dịch vụ Hosting).
- Reseller.
- End User (Người dùng cuối).

Hosting Company và Reseller sử dụng giao diện tương tự có tên là Web Host Manager – Trình quản lý máy chủ web (WHM) trong đó Hosting Company có quyền quản trị cao nhất và có thể hạn chế quyền truy cập vào một số tính năng nhất định trong Reseller WHM.

End user có quyền truy cập trực tiếp vào cPanel interface nơi họ có thể thực hiện một loạt các tác vụ cho trang web của mình.

Ngoài ra, cPanel cũng có khả năng cho phép các nhà cung cấp bên thứ 3 tích hợp dịch vụ của họ vào để khách hàng có thể sử dụng dịch vụ ngay trong giao diện cPanel.

![image](https://user-images.githubusercontent.com/111716161/193789243-4daa59a9-1a0f-4c9e-999b-9ebbca6cf8c9.png)

Công cụ quản trị web hosting này có thể sử dụng trên máy chủ vật lý (Server) hoặc máy chủ riêng ảo (VPS) sử dụng hệ điều hành CentOS, RedHat Enterprise Linux, CloudLinux hoặc FreeBSD.

cPanel hỗ trợ Apache , MySQL và PHP cũng như các giao thức email phổ biến bao gồm POP3, IMAP và SMTP. End user sẽ sử dụng hosting cPanel bằng cách truy cập qua cổng 2083.

# Các chức năng chính của cPanel

## 1. Quản lý tập tin 

- File Manager (Trình quản lý File) – Truy cập và quản lý File nhanh chóng (tạo, chỉnh sửa, xóa) mà không cần FTP.
- Disk Usage (Tình trạng sử dụng ổ cứng) – Các giao diện đồ họa thể hiện tình trạng sử dụng ổ cứng để hiểu và quản lý ổ cứng tốt hơn.
- FTP Connections (Kết nối FTP) – Cung cấp tổng quan về các phiên kết nối FTP.
- BackUp and Backup Wizard: sao lưu các tập tin trên web hosting dễ dàng.
- Images (Hình ảnh) – Tính năng này cho phép người dùng thay đổi kích thước, chuyển đổi và xem hình ảnh.
- Web Disk – Cho phép quản trị viên web xem không gian ổ cứng như trên PC và quản lý không gian ổ cứng (chỉnh sửa, di chuyển, upload và download file).
- Anonymous FTP (FTP ẩn danh) – Hữu ích cho việc cung cấp các file để tải xuống công khai.
- Directory Privacy (Thư mục bảo mật) – Thư mục được bảo vệ bằng mật khẩu để bảo mật tốt hơn.
- FTP Accounts (Tài khoản FTP) – Quản lý tài khoản FTP dễ dàng.

## 2. Quản lý cơ sở dữ liệu

- PHPMyAdmin – Giao diện của bên thứ ba để quản trị cơ sở dữ liệu. Hữu ích khi sử dụng cơ sở dữ liệu MySQL.
- Remote MySQL – Cho phép cơ sở dữ liệu được truy cập từ xa, ví dụ từ các ứng dụng khác trên các máy chủ khác.
MySQL – Cơ sở dữ liệu mạnh mẽ để chạy các ứng dụng dựa trên web của bạn.
- PostgreSQL Databases (Cơ sở dữ liệu PostgreSQL) – Cơ sở dữ liệu phổ biến thay thế cho MySQL.
- MySQL Database Wizard – Dễ dàng tạo và quản lý Cơ sở dữ liệu MySQL của bạn.
- PostgreSQL Database Wizard (Trình hướng dẫn cơ sở dữ liệu PostgreSQL) – Dễ dàng tạo và quản lý Cơ sở dữ liệu PostgreSQL của bạn.

## 3. Quản lý tên miền

- Site Publisher (Nhà xuất bản Trang web) – Tạo sự hiện diện trang web cơ bản hoặc trang giữ để chuẩn bị cho một trang web mới.
- Aliases (Bí danh) – Chuyển hướng tên miền đến các trang web khác nhau.
- Advanced & Simple Zone Editors (Trình chỉnh sửa zone nâng cao & đơn giản) – Quản lý các khía cạnh khác nhau của DNS của tên miền, chẳng hạn như A record và CNAME record.
- Addon Domains (Tên miền Addon) – Giảm chi phí bằng cách thêm tên miền và tạo trang web và địa chỉ email mới cho mỗi tên miền mà không cần phải mua lưu trữ mới cho mỗi tên miền.
Redirects (Chuyển hướng) – Thiết lập chuyển hướng từ một trang cụ thể sang một trang khác.
- Subdomains (Tên miền con) – Được sử dụng để tạo các phần phụ của trang web cho mục đích cụ thể như blog của công ty hoặc cơ sở tri thức.

## 4. Tính năng Email

- Email Accounts (Tài khoản email) – Thiết lập và quản lý tất cả các khía cạnh của tài khoản email một cách nhanh chóng và dễ dàng.
- Autoresponders (Trả lời tự động) – Hữu ích cho việc gửi trả lời tự động đến các email nhận được.
- Track Delivery (Theo dõi giao hàng) – Theo dõi các email được gửi.
- Authentication (Xác thực) – Gửi email an toàn đã được xác thực.
- Archive (Lưu trữ) – Lưu email nhận và gửi trong một khoảng thời gian xác định.
- Calendars and Contacts (Lịch và Danh bạ) – Luôn cập nhật với giao diện lịch và danh bạ.
- Forwarders (Chuyển tiếp) – Thiết lập chuyển tiếp email cho các địa chỉ email cụ thể.
- Default Address (Địa chỉ mặc định) – Bất kỳ email nào nhận được địa chỉ không chính xác đều được gửi đến địa chỉ mặc định.
- Global Filters (Bộ lọc toàn cầu) – Thiết lập bộ lọc email.
Encryption (Mã hóa) – Tạo “Khóa công khai” để liên lạc qua email an toàn.
- Configure Greylisting (Định cấu hình Greylning) – Một biện pháp ngăn chặn thư rác cơ bản.
- MX Entry (Mục nhập MX) – Định tuyến lại email đến đến một máy chủ khác.
- Mailing Lists (Danh sách gửi thư) – Tạo một email và gửi cho nhiều người nhận.
- Email Filters (Bộ lọc email) – Hữu ích cho việc chuyển hướng email, ngăn chặn thư rác hoặc chuyển email đến các ứng dụng (ví dụ như bộ phận trợ giúp).
- Apache SpamAssassin – Ứng dụng chống thư rác.
BoxTrapper – Ngăn chặn các email không xác định đánh vào hộp thư đến của bạn.

## 5. Thống kê số liệu và phân tích

- Visitors (Khách truy cập) – Một bản ghi đầy đủ về khách truy cập trong file log Apache.
- Raw Access (File log nguyên bản) – Phiên bản nén của nhật ký khách truy cập máy chủ của bạn.
- Webalizer – Công cụ phân tích khách truy cập trang web.
Errors (Lỗi) – Tập hợp đầy đủ các lỗi gần đây nhất trên trang web của bạn. Để bạn có thể giải quyết mọi vấn đề.
- AWStats – Công cụ của bên thứ 3 để trực quan hóa khách truy cập vào trang web của bạn.
- Webalizer FTP – Công cụ đo lường để hiển thị khách truy cập FTP vào trang web của bạn.
- Bandwidth (Băng thông) – Hiển thị mức sử dụng băng thông.
Analog Stats (Số liệu thống kê) – Chế độ xem đơn giản của các lượt truy cập trang web.
- Metrics Editor (Trình chỉnh sửa số liệu) – Chọn Số liệu để chạy trên các miền.

## 6. Tính năng bảo mật

- SSH Access – Secure (Truy cập SSH – Kết nối an toàn) – Được xác thực đến máy chủ thông qua Dòng lệnh.
- Hotlink Protection (Bảo vệ Hotlink) – Ngăn chặn hành vi trộm cắp băng thông. Khi nội dung được nhúng trên một trang web khác.
- ModSecurity Domain Manager – Kích hoạt hoặc vô hiệu hóa ModSecurity.
- IP Blocker (Trình chặn IP) – Quyết định nếu bạn muốn chặn một số IP nhất định truy cập trang web của bạn.
- Leech Protection – Hạn chế số lần đăng nhập.
- Two-Factor Authentication (Xác thực hai yếu tố) – Cải thiện bảo mật đăng nhập.
- SSL/TLS – Bảo mật nâng cao bằng cách quản lý SSL/TLS và Yêu cầu chứng chỉ.
- Security Policy (Chính sách bảo mật) – Đặt câu hỏi xác minh quyền truy cập từ các IP không xác định.
- SSL/TLS Wizard (Hướng dẫn thiết lập SSL/TLS) – Tự động hóa quy trình cung cấp SSL.

## 7. Các ứng dụng phần mềm

- PHP – Kiểm tra cấu hình PHP của máy chủ.
- RubyGems – Quản lý Ruby.
- Optimize Website (Tối ưu hóa trang web) – Tối ưu thời gian phản hồi của Web Server Apache.
- PHP Pear Packages – Gói PEAR để bạn có thể chạy chúng trong PHP.
- Ruby On Rails – Triển khai các ứng dụng Ruby On Rails.
MultiPHP Manager (Trình quản lý MultiPHP) – Lựa chọn nhiều phiên bản PHP khác nhau cho từng website.
- PERL Modules (Mô-đun PERL) – Tạo mô-đun PERL để bạn có thể tạo các tác vụ PERL.
- Site Software (Phần mềm Trang web) – Thêm phần mềm bổ sung như Bảng thương mại điện tử và Bảng tin.
- MultiPHP INI Editor (Trình soạn thảo MultiPHP INI) – Quản lý cấu hình PHP của nhiều phiên bản khác nhau.

## 8. Các cài đặt nâng cao
- Indexes (Chỉ mục) – Tùy chỉnh trang Chỉ mục Apache mặc định.
- MIME Types (Các loại MIME) – Đặt hướng dẫn để xử lý các phần mở rộng tệp khác nhau, ví dụ: .html, .htm.
- CRON Jobs – Tự động hóa các nhiệm vụ lặp đi lặp lại vào thời gian đã lên lịch. Ví dụ: tạo hóa đơn vào 12:00 hàng ngày.
- Error Pages (Trang lỗi) – Định cấu hình cách các trang lỗi xuất hiện cho khách truy cập của bạn.
- Virus Scanner – Rà quét các mối đe dọa, phần mềm độc hại.
Track DNS (Theo dõi DNS) – Kiểm tra cài đặt DNS bằng cách truy tìm tuyến đường từ PC đến máy chủ.
- Apache Handlers (Trình xử lý Apache) – các lựa chọn xử lý của Apache.
- API Shell – Được sử dụng để chạy các lệnh gọi API cPanel.

## 9. Các tùy chọn người dùng

- User Preferences (Tùy chọn người dùng) – Đặt tùy chọn người dùng.
- User Manager (Trình quản lý người dùng) – Đặt và chỉnh sửa quyền và quyền của người dùng.

# Ưu, nhược điểm của cPanel

### Ưu điểm

- Dễ sử dụng và ổn định cho người dùng.
- cPanel không có vấn đề gì về thời gian.
- Công nghệ tiên tiến và tính bảo mật cao.
- Hỗ trợ toàn cầu và vô cùng thân thiện với người dùng.
- Chạy được trên nền tảng máy tính và di động.

### Nhược điểm

- cPanel có nhiều tính năng không cần thiết.
- Dễ làm thay đổi các thông số quan trọng.
- Một số host vẫn chạy bản cPanel cũ.
- Tốn kém hơn cho người sử dụng.
