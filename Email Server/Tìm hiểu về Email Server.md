# Emial Server

Email Server hay Mail Server là một  máy chủ thư điện tử dùng để gửi và nhận thư điện tử (Email). Là giải pháp Email chuyên nghiệp để giao tiếp thư tín nội bộ, trao đổi thư tín với khách hàng và đối tác bên ngoài cần yêu cầu sự ổn định, liên tục với tốc độ nhanh đồng thời đảm bảo an toàn dữ liệu, khả năng khôi phục dữ liệu cao…

Các Email Server thực chất là một Server vật lý hoặc là một Server đám mây được cấu hình để biến thành một cỗ máy gửi và nhận thư điện tử. Nó cũng có đầy đủ các thông số như một Server bình thường như Ram, CPU, dung lượng lưu trữ,… ngoài ra, nó còn có các thông số khác liên quan đến yếu tố Email như Số lượng tài khoản  Email, số lượng Email fowarder, Mail list,…

Ngoài ra, Email Server còn có các tính năng mà một dịch vụ Email miễn phí dành cho cá nhân không thể có được như : Quản lý Email ra-vào của nhân viên, tích hợp với các phần mềm như Outlook, nền tảng webmail, khả năng sao lưu dữ liệu và đặc biệt hơn là nó có IP riêng để chống lại các vấn đề như virus, spam mail, mail bị vào blacklist… điều mà các dịch vụ Email share host phải bó tay.

# Lợi ích khi sử dụng Email Server

Ngày này tình trang spam mail, email chứa phần mềm độc hại ảnh hưởng đến an toàn và bảo mật dữ liệu cho các doanh nghiệp. Vì vậy, an toàn dữ liệu là vấn đề các doanh nghiệp quan tâm hàng đầu.

![image](https://user-images.githubusercontent.com/111716161/190990470-49735f61-71df-4c0f-a50a-5b9e4beb4188.png)

Email Server được đánh giá cao hơn các máy chủ khác bởi những lợi ích nó mang lại:

- Tạo email theo tên miền doanh nghiệp tăng sự uy tín và chuyên nghiệp trong hoạt động trao đổi sử dụng email.
- Độ an toàn bảo mật cao, cung cấp nhiều tính năng mà email doanh nghiệp cần.
- Sử dụng mail cho công việc mọi lúc mọi nơi trên mọi thiết bị, đồng bộ hóa dữ liệu nhanh chóng.
- Tùy chỉnh, cấu hình các tính năng cho User.
- Ngăn chặn spam và virus cực kỳ hiệu quả.
- Dữ liệu của bạn được bảo mật an toàn tuyệt đối, không gian lưu trữ riêng rộng lớn.
- Tính bảo mật cao nhờ trang bị giao thức SSL.
- Sử dụng IP riêng nên sẽ chống được việc vô cớ bị vào black list.
- Hỗ trợ tính năng Fowarder Email để cài đặt Email Offline.

# Cách thức hoạt động của Email Server và một số thuật ngữ

![image](https://user-images.githubusercontent.com/111716161/190990648-3f2e0e09-bc07-4519-a834-1e4fbdffd2cb.png)

1. Outgoing Mail Server

Outgoing Mail Server hay Mail Server gửi đi sử dụng giao thức SMTP (Simple Mail Transfer Protocol). Đây là giao thức dịch chuyển mail đơn giản được dùng để liên lạc với server từ xa. Đồng thời cho phép gửi nhiều thư cùng một lúc tới các server khác nhau.

2. Incoming Mail Server 
Giao thức này hay còn được biết đến dưới 2 hình thức:

- POP3 (Post Office Protocol phiên bản 3): chuyển email tới lưu ở máy tính chứa Mail Client, thường là nội bộ máy tính của người dùng thông qua một ứng dụng email như Outlook, Mac Mail, Windows Mail…
- IMAP (Internet Message Access Protocol) là phương thức phức tạp hơn cho phép nhiều client cùng lúc kết nối tới một Mailbox. Email từ Mailbox sẽ được sao chép tới máy client và bản gốc của Email vẫn sẽ được lưu trên Mail Server.

3. TLS Mail Server
TLS là bảo mật tầng truyền tải (Transport Layer Security). TLS hoạt động cùng với tầng ổ bảo mật SHL (Secure Sockets Layer). Mục đích chính cung cấp phương thức vận chuyển mã hoá cho đăng nhập được chứng thực của SASL.

4. SASL Mail Server 
SASL là lớp xác thực và bảo mật đơn giản (Simple Authentication and Security Layer). Để xác thực người dùng. SASL thực hiện xác thực, sau đó TLS cung cấp vận chuyển mã hoá dữ liệu xác thực.

5. Webmail
Webmail là email trên nền website. Một số Webmail mà các bạn có thường thấy như Hotmail, gmail, yahoo mail. Webmail cho phép người dùng truy cập email bất cứ lúc nào.

6. SMTP-IN Queue 
Trước khi phân tán thư đến các Local queue hoặc Remote Queue. Giao thức SMTP sẽ làm một thao tác sao lưu toàn bộ thư điện tử gửi đi từ email server của doanh nghiệp ở SMTP-IN Queue. Nói cách khác, SMTP-IN Queue chính là kho lưu trữ thông tin thư từ trước khi được gửi đi.

7. Local Queue
Sau khi tiếp nhận thông tin thư từ, hệ thống sẽ tự động điều phối phân loại và xếp thư từ theo thứ tự ngay hàng thẳng lối trước khi chuyến vào hộp thư của người nhận. Việc xếp hàng các bức thư chính là Local Queue.

Để tăng cường khả năng bảo mật và giữ an toàn cho hệ thống email server. Trước khi thư được gửi đến người dùng, local queue và remote queue sẽ tiến hành quét virut. Sau đó kiểm tra spam để chắc chắn về chất lượng thư gửi đi. Tránh trường hợp mail server bị các Blacklist liệt vào danh sách IP spam.

8. Local Mailboxes
Local Mailboxes là hộp thư của các Account có đăng kí tài khoản mail server của công ty.

9. Email Authentication
Email Authentication là tính năng xác nhận danh tính của các user khi truy cập vào hộp thư email. Tính năng này giúp bạn bảo mật thông tin thư từ của chính mình. Nói cách khác Alternate Email là một dạng email dự phòng. Khi quên mật khẩu của mail server, bạn có thể sử dụng email này để giúp bạn lấy lại mật khẩu một cách nhanh chóng.

10. Mail Exchanger Record (MX)
MX record có nhiệm vụ là chỉ đường cho email đi đến mail server của bạn. MX Record thường đi kèm theo một A record sẽ trỏ về địa chỉ IP của mail server. Một thông số pref có giá trị số để chỉ ra mức độ ưu tiên của các mail server. Giá trị pref càng nhỏ thì mức độ ưu tiên càng cao.
