# Mục lục

[Giao thức DHCP là gì?](#dhcplagi)

[Cách thức hoạt động của DHCP](#hoatdong)

[Các thuật ngữ](#thuatngu)

[Các thông điệp giao tiếp giữa DHCP server và DHCP client](#thongdiep)

[Ưu, nhược điểm khi sử dụng DHCP)(#uunhuoc)

# Giao thức DHCP

<a name="dhcplagi"></a>
## Giao thức DHCP là gì?

### Khái niệm
Dynamic Host Configuration Protocol (DHCP - giao thức cấu hình động máy chủ) là một giao thức cho phép cấp phát địa chỉ IP một cách tự động cùng với các cấu hình liên quan khác như subnet mask và gateway mặc định. Máy tính được cấu hình một cách tự động vì thế sẽ giảm việc can thiệp vào hệ thống mạng. Nó cung cấp một database trung tâm để theo dõi tất cả các máy tính trong hệ thống mạng. Mục đích quan trọng nhất là tránh trường hợp hai máy tính khác nhau lại có cùng địa chỉ IP.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/186096478-9e022e0b-3cd7-4850-a497-53b54c5be67d.png"/>
</p>

Nếu không có DHCP, các máy có thể cấu hình IP thủ công (cấu hình IP tĩnh). Ngoài việc cung cấp địa chỉ IP, DHCP còn cung cấp thông tin cấu hình khác, cụ thể như DNS. Hiện nay DHCP có 2 version: cho IPv4 và IPv6.

### Lịch sử phát triển

DHCP đầu tiên được định nghĩa trong RFC 1531 vào tháng 10/1993, là phần mở rộng của Bootstrap Protocol(BOOTP). Động cơ để cải tiến BOOTP là BOOTP đòi hỏi phải cấu hình thủ công để thêm thông tin cho từng máy client, và không cung cấp cơ chế tái sử dụng lại địa chỉ IP. Năm 1997, RFC 2131 ra đời vẫn còn chuẩn IPv4 cho đến năm 2011. DHCPv6 được định nghĩa trong RFC 3315 RFC 3633 được thêm vào DHCPv6 cơ chế prefix delegation.

Giao thức BOOTP lần đầu tiên được định nghĩa trong RFC 951 thay thế cho RARP (Reverse Address Resolution Protocol), mà động cơ thiết yếu để thay thế RARP bằng BOOTP là RARP hoạt động ở tầng data link, điều này làm cho việc thực hiện trên nhiều máy server trở nên khó khăn, và đòi hỏi một server xử lý trên riêng trên từng network. BOOTP có đổi mới relay agent, cho phép forwarding đến gói BOOTP trong mạng cục bộ, vì vậy BOOTP server có thể phục vụ cho nhiều IP subnet.

<a name="hoatdong"></a>
## Cách thức hoạt động của DHCP

Về cơ bản, cách thức hoạt động của DHCP đơn giản. Đó là, khi một thiết bị muốn truy cập mạng phát tín hiệu, DHCP sẽ thực hiện việc gửi yêu cầu từ router. Sau đó, router tiến hành gán cho địa chỉ IP khả dụng.

Cụ thể, khi có nhu cầu kết nối mạng, thiết bị thực hiện gửi yêu cầu DHCP DISCOVER đến máy chủ. Tiếp đến, DHCP server tiến hành tìm kiếm địa chỉ IP khả dụng, sau đó, cung cấp lại cho thiết bị và gói DHCP OFFER.

Khi đã có được địa chỉ, thiết bị sử dụng một gói tin DHCP REQUEST để trả lời lại cho máy chủ. Lúc này, máy chủ sẽ gửi xác nhận thiết bị đã có IP, cũng như thời gian sử dụng nó cho đến khi thay thế bằng địa chỉ mới.

Chính vì cơ chế hoạt động này nên đối với các mạng có quy mô nhỏ hoặc hộ gia đình thì router hoạt động như máy chủ DHCP. Còn với các mô hình mạng lớn hơn, một router sẽ không có khả năng quản lý tất cả các thiết bị nên cần đến máy chủ chuyên dụng để thực hiện việc cấp IP.

<a name="thuatngu"></a>
## Các thuật ngữ

**DHCP server** là một máy chủ thực hiện việc kết nối mạng. Nó có chức năng phản hồi thông tin khi máy trạm (DHCP client) phát yêu cầu. Ngoài ra, DHCP server còn có nhiệm vụ truyền thông tin một cách hợp lý nhất đến các thiết bị, đồng thời, thực hiện cấu hình cổng mặc định (Default gateway) hay Subnet mask.

**DHCP Client** được định nghĩa là máy trạm chạy dịch vụ DHCP. DHCP Client được sử dụng để thực hiện đăng ký, cập nhật thông tin về địa chỉ IP cùng với những bản ghi DNS cho chính nó. Cụ thể, khi cần một địa chỉ IP hay tham số TCP/IP để làm việc trong hệ thống mạng, DHCP Client sẽ tiến hành gửi yêu cầu đến DHCP Server. 

**BOOTP relay agents - Thiết bị chuyển tiếp BOOTP**: là một máy trạm hoặc một router có khả năng chuyển các thông điệp DHCP giữa DHCP server và DHCP client.

**Binding - Kết nối**: là một tập hợp các thông tin cấu hình trong đó có ít nhất một địa chỉ IP, được sử dụng bởi một DHCP client. Các nối kết được quản lý bởi máy chủ DHCP

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/186096200-883e142d-2a97-4da3-bffb-aa9da83172ef.png">
</p>

<a name="thongdiep"></a>
## Các thông điệp giao tiếp giữa DHCP server và DHCP client 
- DHCP Discover: Đây là một gói thông tin được gửi đến DHCP server bởi một thiết bị yêu cầu cung cấp địa chỉ IP để truy cập mạng. 
- DHCP Offer: Đây là gói thông tin chứa địa chỉ IP, cấu hình TCP/IP bổ sung. DHCP Offer được máy chủ DHCP gửi phản hồi cho Client sau khi nhận DHCP Discover.
- DHCP Request: Đây là gói thông tin được DHCP Client trả lời cho server về sự chấp nhận đối với IP, sau khi nó nhận được DHCP Offer.
- DHCP Acknowledge: Đây là gói thông tin mà máy chủ DHCP phản hồi lại cho Client nhằm xác định là đã chấp nhận DHCP Request, đồng thời, định hướng những tham số tùy chọn để thực hiện việc cho phép Client truy cập mạng TCP/IP, cũng như hoàn tất hệ thống khởi động.
- DHCP Nak: Nếu Client không sử dụng địa chỉ IP do nó không còn giá trị hoặc đã được máy khác dùng, thì máy chủ DHCP thực hiện gửi một gói DHCP Nak. Sau đó, Client phải thực hiện lại quá trình thuê bao.
- 
Như vậy, DHCP Nak là một gói thông tin do máy chủ gửi đến Client, trong trường hợp nó nhận được yêu cầu xuất phát từ một IP không có giá trị. Việc xác định địa chỉ IP có hay không có giá trị được dựa vào phạm vi mà nhà sản xuất đã cấu hình cho máy chủ.
- DHCP Decline: Khi DHCP Client quyết định các tham số trong đề nghị không có giá trị, nó thực hiện gửi gói DHCP Decline đến máy chủ và lúc này Client phải làm lại tiến trình thuê bao.
- DHCP Release: Đây là gói tin mà DHCP Client gửi đến máy chủ để giải phóng địa chỉ IP, đồng thời, thực hiện xóa các thuê bao đang tồn tại.

<a name="uunhuoc"></a>
## Ưu, nhược điểm khi sử dụng DHCP
### Ưu điểm của DHCP
- Máy tính hay bất cứ thiết bị nào phải cấu hình đúng cách thì mới có thể kết nối với mạng được. DHCP cho phép cấu hình tự động nên dễ dàng cho các thiết bị máy tính, điện thoại, các thiết bị thông minh khác...có thể kết nối mạng nhanh.

- Vì DHCP thực hiện theo kiểu gán địa chỉ IP nên sẽ không xảy ra trường hợp trùng địa chỉ IP, vậy việc gán theo cách thủ công của IP tĩnh sẽ dễ dàng hơn và giúp hệ thống mạng luôn hoạt động ổn định.

- DHCP giúp quản lý mạng mạnh hơn vì các cài đặt mặc định và thiết lập tự động lấy địa chỉ sẽ cho mọi thiết bị kết nối mạng đều có thể nhận được địa chỉ IP.

- DHCP quản lý cả địa chỉ IP và các tham số TCP/IP trên cùng một màn hình như vậy sẽ dễ dàng theo dõi các thông số và quản lý chúng qua các trạm.

- Khi đánh tự động nhờ máy chủ DHCP giúp cho người quản lý quản lý có khoa học hơn và không bị nhầm lẫn.

- Ngoài ra người quản lý có thể thay đổi cấu hình và thông số của các địa chỉ IP giúp việc nâng cấp cơ sở hạ tầng được dễ dàng hơn.

- Một ưu điểm nữa là các thiết bị có thể di chuyển tự do từ mạng này sang mạng khác và nhận địa chỉ IP tự động mới vì các thiết bị này có thể tự nhận IP.

### Nhược điểm của DHCP
- DHCP mang lại nhiều ưu điểm, song bên cạnh đó cũng còn mặt hạn chế. Chẳng hạn  như việc ta không nên sử dụng địa chỉ IP động, địa chỉ IP thay đổi đối với các thiết bị cố định và cần truy cập liên tục. Ví dụ như không nên sử dụng IP động cho các thiết bị máy in ở các văn phòng.

- Mặc dù có rất nhiều lợi ích khi sử dụng DHCP, vẫn có một số hạn chế mà chúng ta cần lưu ý. Không nên sử dụng địa chỉ IP động, địa chỉ IP thay đổi đối với các thiết bị cố định và cần truy cập liên tục như máy in và file server.

- Bởi DHCP sử dụng chủ yếu với các hộ gia đình hay văn phòng. Đối với các thiết bị dùng trong văn phòng, như máy in thì việc việc gán chúng với các địa chỉ IP thay đổi không mang tính thực tiễn. Lúc đó mỗi khi kết nối với máy tính khác thì máy in đó sẽ phải thường xuyên cập nhật cài đặt để máy tính có thể kết nối với máy in.

- Cũng giống như việc bạn điều khiến máy tính từ xa và cần có quyền truy cập thì bạn phải có địa chỉ IP. Nếu như địa chỉ IP đó động thì những gì máy tính đã ghi lại sẽ không chính xác được lâu. Vậy nên nếu trong trường hợp này thì bạn nên sử dụng IP tĩnh là phù hợp hơn cả.
