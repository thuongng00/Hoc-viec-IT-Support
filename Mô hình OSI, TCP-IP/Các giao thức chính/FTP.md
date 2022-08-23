# Mục lục

[Giao thức FTP là gì?](#ftplagi)

[Mô hình hoạt động của giao thức FTP](#mohinh)

[Phương thức truyền dữ liệu với FTP](#phuongthuc)

[Kênh dữ liệu trong FTP](#kenhdulieu)

[Dữ liệu trong FTP](#dulieu)

[Cách xây dựng một máy chủ FTP đơn giản](#cachxaydung)

# Giao thức FTP

<a name="ftplagi"></a>
## Giao thức FTP là gì?
FTP được viết tắt từ File Transfer Protocol được hiểu là giao thức chuyển nhượng tập tin. Đây là một giao thức truyền tải tập tin từ một máy tính đến máy tính khác, thường là một máy tính cá nhân và server thông qua một mạng TCP hoặc mạng Internet.
  
Tại giao thức FTP, bạn có quyền quản lý toàn bộ các dữ liệu dạng tập tin và thư mục có trên host ngoại trừ database. Tất cả các gói host bạn mua có hỗ trợ control panel cPanel, DirectAdmin… đều hỗ trợ sẵn FTP qua cổng kết nối 21 (21 là cổng mặc định, cổng này có thể thay đổi nếu nhà cung cấp Hosting đổi port).

Thông qua giao thức FTP, người dùng có thể tải dữ liệu như hình ảnh, văn bản, các tập tin media (nhạc, video)… từ máy tính của mình lên máy chủ đang đặt ở một nơi khác hoặc tải các tập tin có trên máy chủ về máy tính cá nhân.

<p align="center">
  <img src="https://www.totolink.vn/public/uploads/img_article/giaothucftplaginhungdieubanchuabietvegiaothucftp-1.png">
</p>

<a name="mohinh"></a>
## Mô hình hoạt động của giao thức FTP
Giao thức FTP hoạt động dựa trên mô hình cơ bản của việc truyền và nhận dữ liệu từ máy Client đến máy Server. Quá trình truyền nhận dữ liệu giữa máy Client và Server lại được tạo nên từ 2 tiến trình TCP logic là Control Connection và Data Connection.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/186089478-a059e4e8-ebf1-470c-912c-7f4fc5cdb9c0.png"/>
</p>

- Control Connection: Đây là phiên làm việc TCP logic đầu tiên được tạo ra khi quá trình truyền dữ liệu bắt đầu. Tuy nhiên, tiến trình này chỉ kiểm soát các thông tin điều khiển đi qua nó, ví dụ như các tập lệnh. Quá trình này sẽ được duy trì trong suốt quá trình phiên làm việc diễn ra.

- Data Connection: Khác với tiến trình Control Connection, Data Connection là một kết nối dữ liệu TCP được tạo ra với mục đích chuyên biệt là truyền tải dữ liệu giữa máy Client và máy Server. Kết nối sẽ tự động ngắt khi quá trình truyền tải dữ liệu hoàn tất.

<a name="phuongthuc"></a>
## Phương thức truyền dữ liệu với FTP

Có 3 phương thức truyền dữ liệu là stream mode, block mode, và compressed mode.

### Stream mode
Phương thức này hoạt động dựa vào tính tin cậy trong việc truyền dữ liệu trên giao thức TCP.
- Dữ liệu truyền đi liên tiếp dưới dạng các byte không cấu trúc.
- Thiết bị gửi chỉ đơn thuần đẩy luồng dữ liệu qua kết nối TCP tới phía nhận.
- Không có trường tiêu đề nhất định
- Không có cấu trúc dạng Header, nên việc báo hiệu kết thúc file sẽ đơn giản được thực hiện khi thiết bị gửi ngắt kênh kết nối dữ liệu khi đã truyền dữ liệu xong.

Phương thức này được sử dụng nhiều nhất trong 3 phương thức trong triển khai FTP thực tế. Do:
- Là phương thức mặc định và đơn giản nhất.
- Là phương thức phổ biến nhất, vì nó xử lí các file chỉ đơn thuần là xử lí dòng byte, mà không cần để ý tới nội dung.
- Không tốn 1 lượng byte “overload” nào để thông báo Header.

### Block mode
Phương thức truyền dữ liệu mang tính quy chuẩn hơn.

Dữ liệu được chia thành nhiều khối nhỏ và đóng gói thành các FTP block.

Mỗi block có 1 trường Header 3 byte: báo hiệu độ dài, và chứa thông tin về các khối dữ liệu đang được gửi.

Một thuật toán đặc biệt được sử dụng để kiểm tra các dữ liệu đã truyền đi. Và để phát hiện, khởi tạo lại đối với 1 phiên truyền dữ liệu đã bị ngắt kết nối.

### Compressed mode
Phương thức truyền dữ liệu sử dụng 1 kỹ thuật nén đơn giản, là “run-lenght encoding (mã hóa chiều dài)” – có tác dụng phát hiện và xử lí các đoạn lặp trong dữ liệu được truyền đi để giảm chiều dài của toàn bộ thông điệp.

Thông tin sau khi được nén, sẽ được xử lí như Block mode, với trường Header.

Trong thực tế, việc nén dữ liệu thường được thực hiện ở chỗ khác, làm cho phương thức Compressed mode trở nên không cần thiết.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/186089680-94f93ca7-00cf-4cc2-b9a3-714fa9071467.png"/>
</p>

<a name="kenhdulieu"></a>
## Kênh dữ liệu trong FTP

Kênh dữ liệu được tạo ra giữa Server – PI và User – PI, được sử dụng trong quá trình thiết lập kết nối và chứng thực được duy trì trong suốt phiên kết nối FTP. Các lệnh và các hồi đáp được trao đổi giữa bộ phận PI qua kênh điều khiển, nhưng dữ liệu thì không.

Khi muốn truyền dữ liệu giữa các server và client thì phải tạo ra một kênh dữ liệu. Kênh dữ liệu này sẽ kết nối bộ phận User – DTP và Server DTP. Kết nối này rất cần thiết đối với việc truyền dữ liệu ngầm cũng như truyền file trực tiếp.

Để tạo ra kênh dữ liệu, FTP sử dụng 2 phương thức khác nhau: Normal (Active) Data Connections (mặc định) và Passive Data Connections.

### Normal (Active) Data Connections
Phương thức này còn hay được gọi là kết nối kênh dữ liệu ở dạng chủ động. Phía Server – DTP tạo kênh dữ liệu bằng cách mở một cổng kết nối tới User DTP. Server sử dụng cổng đặc biệt được dành riêng cho kết nối dữ liệu là cổng số 20.

Trên máy Client, cổng mặc định được sử dụng chính là cổng được sử dụng để kết nối điều khiển, nhưng Server sẽ thường chọn mỗi cổng khác nhau cho mỗi chuyển giao.

### Passive Data Connections
Phương thức này là một phương thức tạo kết nối bị động.
- Server sẽ chấp nhận 1 yêu cầu kết nối dữ liệu được khởi tạo từ Client.
- Server sẽ trả lời lại phía Client với địa chỉ IP cũng như địa chỉ cổng mà Server sẽ sử dụng.
- Sau đó phía Server-DTP lắng nghe trên cổng này một kết nối TCP đến từ User-DTP.
- Theo mặc định, phía Client sẽ sử dụng cùng cổng mà nó sử dụng cho Control Connection như trong trường hợp chủ động. Tuy nhiên, trong phương pháp này, Client cũng có thể chọn sử dụng một cổng khác cho Data Connection nếu cần thiết.

<a name="dulieu"></a>
## Dữ liệu trong FTP
Các tập tin trong giao thức FTP được coi như một tập hợp các byte. FTP không quan tâm nội dung tập tin, sẽ chỉ đơn giản là di chuyển các tệp tin, các byte cùng 1 thời điểm, từ nơi này sang nơi khác.
### FTP Data Types
Phần đầu tiên của thông tin có thể được đưa ra về tập tin là kiểu dữ liệu của nó. Có 4 kiểu dữ liệu khác nhau được quy định trong chuẩn của FTP.
- ASCII: file văn bản ASCII.
- EBCDIC: tương tự ASCII, nhưng sử dụng kiểu kí tự EBCDIC do IBM đặt.
- Image: Các tập tin không có cấu trúc nội bộ chính thức.
- Local: Kiểu dữ liệu này được sử dụng để xử lí các tập tin có thể lưu trữ dữ liệu trong byte logic. Cách xác định loại này cùng với cách dữ liệu có cấu trúc cho phép dữ liệu được lưu trữ trên hệ thống đích một cách phù hợp với đại diện local của nó.
### FTP Format Control
3 tùy chọn trong FTP Format Control:
- Non Print : Đây là tùy chọn mặc định, cho biết không có định dạng dọc
- Telnet Format : Tệp sử dụng các kí tự điều khiển định dạng dọc, như được chỉ định trong giao thức Telnet
- Carriage Control/FORTRAN : Tệp sử dụng kí tự điều khiển được định dạng đưa ra làm kí tự đầu tiên của mỗi dòng, như được xác định cho ngôn ngữ lập trình FORTRAN.
### FTP Data Structures
Ngoài việc xác định một loại dữ liệu tệp tin, ta cũng có thể xác định cấu trúc tệp tin theo 3 cách:
- File Structure: là 1 luồng byte liền kề không có cấu trúc bên trong. Đây là cách mặc định và được sử dụng cho hầu hết các loại tệp.
- Record Structure: bao gồm một tập hợp các bản ghi, mỗi bản ghi được phân định bằng đánh dấu end-of-record.
- Page Structure: chứa 1 trang dữ liệu được lập chỉ mục đặc biệt. Cấu trúc này không được sử dụng phổ biến. Nó được tạo ra cho 1 máy tính cổ xưa được sử dụng trong ARPAnet đời đầu.

<a name="cachxaydung"></a>
## Cách xây dựng một máy chủ FTP đơn giản
Trước đây, việc xây dựng một máy chủ FTP khá phức tạp và tốn kém đối với mọi người. Nhất là các doanh nghiệp chưa có riêng cho mình một phòng server và những hộ gia đình có nhu cầu sử dụng nhưng ngại thực hiện vì chi phí tốn kém. Nhưng giờ đây, việc xây dựng một máy chủ FTP để truyền và nhận dữ liệu trở nên hoàn toàn dễ dàng khi được tích hợp sẵn trên các Router.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/186090097-5f8312c4-a122-46eb-9fd2-0f5f02c5f08f.png"/>
</p>

Các doanh nghiệp hay hộ gia đình chỉ cần sở hữu một thiết bị Router có tích hợp tính năng FTP. Sau đó, đầu tư thêm 1 bộ nhớ ngoài như USB hoặc ổ cứng với dung lượng thích hợp với nhu cầu cần sử dụng. Kết nối bộ nhớ với Router và cài đặt các thông số cần thiết theo hướng dẫn từ nhà sản xuất. Vậy là một máy chủ FTP đã được dựng thành công.
