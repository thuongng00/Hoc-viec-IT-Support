# Mục lục

[DNS là gì?](#dnslagi)

[DNS dùng để làm gì?](#dnsdungdelamgi)

[Cách thức hoạt động của DNS](#cachthuchoatdong)

[Các loại DNS bản ghi DNS thường sử dụng](#banghi)

[Các loại DNS Server](#dnsserver)

[Các loại truy vấn DNS](#truyvandns)

[Cách sử dụng DNS](#cachsudung)

[DNS bị lỗi thì điều gì sẽ xảy ra?](#loi)

[Nguyên nhân DNS dễ bị tấn công](#tancong)

# Giao thức DNS
<a name="dnslagi"></a>
## DNS là gì?

DNS viết tắt của Domain Name System có nghĩa là hệ thống phân giải tên miền. DNS là hệ thống cho phép thiết lập tương ứng giữa địa chỉ IP và tên miền trên Internet.

DNS được phát minh vào năm 1984 cho Internet và đây là một trong số các chuẩn công nghiệp của các cổng bao gồm cả TCP/IP. Hệ thống phân giải tên miền chính là chìa khóa chủ chốt của nhiều dịch vụ mạng hiện nay như Internet, Mail server, Web server…

<a name="dnsdungdelamgi"></a>
## DNS dùng để làm gì?

Mỗi máy tính khi kết nối vào Internet sẽ được gán cho 1 địa chỉ IP (Ví dụ: 1414.1158.62462) riêng biệt và không trùng lẫn với bất kỳ máy tính nào khác trên thế giới. Cũng giống như vậy đối với website cũng có địa chỉ IP riêng biệt của website đó. Tuy nhiên, mỗi website đề có một địa chỉ IP là các con số khá dài và khó nhớ khiến bạn không thể nhớ rõ con số IP đó.

Nói cách khác, DNS cũng giống như một danh bạ điện thoại dành riêng cho Internet. Nếu bạn biết tên của một người nhưng không biết số điện thoại hay ngược lại, bạn có thể tham khảo trong sổ danh bạ dễ dàng.

<a name="cachthuchoatdong"></a>
## Cách thức hoạt động của DNS
Quá trình phân giải DNS bao gồm chuyển đổi tên máy chủ (chẳng hạn như www.example.com) thành địa chỉ IP thân thiện với máy tính (chẳng hạn như 192.168.1.1). Một địa chỉ IP được cung cấp cho mỗi thiết bị trên Internet và địa chỉ đó là cần thiết để tìm thiết bị Internet phù hợp. Giống như một địa chỉ đường phố được sử dụng để tìm một ngôi nhà cụ thể.

Khi người dùng muốn tải một trang web, một bản dịch phải xảy ra giữa những gì người dùng nhập vào trình duyệt web của họ (example.com) và địa chỉ thân thiện với máy cần thiết để định vị trang web example.com.

Để hiểu quy trình đằng sau quá trình phân giải DNS, điều quan trọng là phải tìm hiểu về các thành phần khác nhau mà một truy vấn DNS phải vượt qua. Đối với trình duyệt web, việc tra cứu DNS diễn ra ở chế độ ẩn. Và không yêu cầu sự tương tác từ máy tính của người dùng ngoài yêu cầu ban đầu.

<a name="banghi"></a>
## Các loại DNS bản ghi DNS thường sử dụng
- CNAME Record: Là một bản ghi tên quy chuẩn (Canonical Name Record). Đây là một dạng bản ghi tài nguyên trong hệ thống tên miền.
- A Record: Dùng để trỏ tên miền website tới một địa chỉ IP cụ thể. Đây được xem là bản ghi DNS đơn giản nhất.
- MX Record: Bản ghi này bạn có thể sử dụng để trỏ tên miền đến mail server. MX Record chỉ định server nào quản lý các dịch vụ Email của tên miền đó.
- AAAA Record: Dùng để trỏ tên miền đến địa chỉ IPv6 và cho phép thêm host mới, TTL và IPv6.
- TXT Record: Ngoài ra, có thể thêm giá trị TXT, Host mới, TTL và Point To để chứa các thông tin định dạng văn bản domain.
- SRV Record: Đây là bản ghi DNS đặc biệt, dùng để xác định chính xác dịch vụ nào đang chạy Port nào. Và thông qua bản ghi này bạn có thể thêm Priority, Port, Weight, TTL, Point to.
- NS Record: Bản ghi này có thể chỉ định Name Server cho từng tên miền phụ và bên cạnh đó có thể tạo tên Name Server, TTL hay host mới.

<a name="dnsserver"></a>
## Các loại DNS Server
DNS Server gồm hai loại là Root Name Server và Local Name Server. Để hiểu hơn, cùng Vietnix tìm hiểu chi tiết hơn về hai DNS Server này ngay dưới đây:

### Root Name Server
Root Name Server là một dịch vụ phân giải tên miền gốc và trên thế giới có khoảng 12 DNS root Server.

DNS root Server quản lý tất cả các tên miền Top-level. Khi có yêu cầu phân giải một Domain Name thành một địa chỉ IP, client sẽ gửi yêu cầu đến DNS gần nhất (DNS ISP). DNS ISP sẽ kết nối tới DNS root Server để hỏi địa chỉ của Domain Name.

DNS root Server sẽ căn cứ và dựa vào các Top Level của tên miền và từ đó có những tài liệu hướng dẫn phù hợp để chuyển hướng cho khách hàng đến đúng địa chỉ cần truy vấn.

### Local Name Server
DNS Server này dùng để chứa thông tin để truy xuất và tìm kiếm máy chủ tên miền. Và thường được duy trì và phát triển bởi các doanh nghiệp hay các nhà cung cấp dịch vụ Internet.

<a name="truyvandns"></a>
## Các loại truy vấn DNS
Trong một truy vấn DNS thông thường, ba loại truy vấn xảy ra. Bằng cách sử dụng kết hợp các truy vấn này. Một quy trình được tối ưu hóa cho quá trình phân giải DNS có thể giúp giảm khoảng cách di chuyển. Trong một tình huống lý tưởng, dữ liệu bản ghi được lưu trong bộ nhớ cache sẽ khả dụng, cho phép máy chủ định danh DNS trả về truy vấn không đệ quy.

Có 3 loại truy vấn DNS:
- Recursive query: DNS client yêu cầu máy chủ DNS (thường là recursive DNS resolver). Sẽ trả lời máy khách bằng bản ghi tài nguyên được yêu cầu. Hoặc thông báo lỗi nếu resolver không thể tìm thấy bản ghi.
- Iterative query: Trong tình huống này, DNS client sẽ cho phép máy chủ DNS trả về câu trả lời tốt nhất có thể. Nếu máy chủ DNS được truy vấn không có kết quả trùng khớp với tên truy vấn. Nó sẽ trả về một giới thiệu đến máy chủ DNS có thẩm quyền cho mức thấp hơn. DNS client sau đó sẽ thực hiện một truy vấn đến địa chỉ được giới thiệu. Quá trình này tiếp tục với các máy chủ DNS bổ sung trong chuỗi truy vấn cho đến khi xảy ra lỗi hoặc hết thời gian.
- Non-recursive query: Thông thường điều này sẽ xảy ra khi DNS resolver client truy vấn máy chủ DNS một record mà server có quyền truy cập hoặc bản ghi tồn tại bên trong bộ đệm của server. Thông thường, một máy chủ DNS sẽ lưu các bản ghi DNS để ngăn chặn việc tiêu thụ thêm băng thông và giảm tải cho các máy chủ DNS khác.

<a name="cachsudung"></a>
## Cách sử dụng DNS
Nếu bạn sử dụng DNS của nhà cung cấp mạng thì bạn sẽ không cần điền địa chỉ DNS. Nhưng neeys trường hợp bạn sử dụng DNS khác, thì bạn phải điền địa chỉ cụ thể của máy chủ đó để thay đổi DNS Server:

Bước 1: Nhấn vào Start Menu > Gõ Control Panel > Chọn Control Panel.

Bước 2: Truy cập vào View network status and task.

Bước 3: Truy cập vào mạng Internet.

Bước 4: Vào phần Properties để bắt đầu thay đổi DNS máy tính.

Bước 5: Nhấp vào Internet Protocol Version 4 > Chọn Use the following DNS server addresses > Đổi DNS > OK.

<a name="loi"></a>
## DNS Server bị lỗi thì điều gì sẽ xảy ra?
DNS Server có thể bị lỗi vì nhiều lý do, chẳng hạn như mất điện, tấn công mạng và trục trặc phần cứng. Những ngày đầu của Internet, sự cố ngừng hoạt động của DNS Server có thể có tác động rất lớn. Tuy nhiên, ngày nay có rất nhiều dự phòng được tích hợp vào DNS.

Ví dụ: Có nhiều trường hợp root DNS server, TLD nameserver. Và hầu hết các ISP đều có các recursive resolver dự phòng cho người dùng của họ. (Người dùng cá nhân cũng có thể sử dụng public DNS resolvers, như Cloudflare’s 1.1.1.1.) Hầu hết các trang web phổ biến cũng có nhiều phiên bản authoritative nameserver của họ.

Trong trường hợp DNS server chính bị ngừng hoạt động, một số người dùng có thể gặp phải sự chậm trễ do lượng yêu cầu được xử lý bởi các server dự phòng. Nhưng sẽ mất một lượng lớn DNS khiến một phần đáng kể Internet không khả dụng. (Điều này thực sự xảy ra vào năm 2016 khi nhà cung cấp DNS Dyn trải qua một trong những cuộc tấn công DDoS lớn nhất trong lịch sử).

<a name="tancong"></a>
## Nguyên nhân DNS dễ bị tấn công?
Vì hệ thống tên miền khá phức tạp và người tấn công có thể tận dụng điểm yếu trong DNS để tấn công với nhiều phương thức khác nhau. Đa số các cuộc tấn công đều tập trung vào việc lạm dụng DNS để ngăn người dùng không thể truy cập vào Internet.

Bên cạnh đó, DNS cũng có thể bị tấn công bằng phướng pháp tận dụng giao thức DNS để chuyển hướng người dùng truy cập vào các trang web độc hại nhằm đánh cắp dữ liệu nhạy cảm của cá nhân, doanh nghiệp.

Ngoài ra, việc sử dụng server đệ quy sẽ lưu phản hồi vào bộ nhớ tạm để tăng tốc độ của các truy vấn tiếp theo. Nhằm giảm số lượng request thông tin, nhưng khá nguy hiểm và dễ bị tấn công bởi Man-In-The-Middle. Những kẻ tấn công có thể truy cập vào Over IP (VoIP) để đánh cắp thông tin, mạo danh, trích xuất dữ liệu, thông tin,…
