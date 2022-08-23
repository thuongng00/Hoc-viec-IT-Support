# Mục lục

[Mô hình TCP/IP](#mohinhtcpip)

  [*Định nghĩa*](#dinhnghia)
  
  [*Quá trình phát triển*](#quatrinhphattrien)
  
  [*Cách thức hoạt động*](#cachthuchoatdong)
  
  [*Các giao thức TCP/IP phổ biến hiện nay*](#phobien)
  
  [*Ưu, nhược điểm*](#uunhuoc)

[Mô hình phân tầng trong TCP/IP](#mohinhphantang)

  [*1. Tầng ứng dụng*](#tangungdung)
  
  [*2. Tầng giao vận*](#tanggiaovan)
  
  [*3. Tầng mạng*](#tangmang)
  
  [*4. Tầng vật lý*](#tangvatly)
  
<a name="mohinhtcpip"></a>
# Mô hình TCP/IP
<a name="dinhnghia"></a>
## Định nghĩa
Bộ giao thức TCP/IP (TCP/IP protocol suite) hay còn gọi là bộ giao thức Internet (Internet protocol suite/IP suite) là một mô hình khái niệm (conceptual model) và một tập hợp các giao thức truyền thông dùng trong mạng Internet và các hệ thống mạng máy tính tương tự. Tên gọi TCP/IP đến từ hai giao thức nền tảng của bộ giao thức là TCP (Transmission Control Protocol) và IP (Internet Protocol). TCP và IP cũng là hai giao thức đầu tiên được định nghĩa. Bộ giao thức này được phát triển vào năm 1978 bởi 2 kỹ sư Vint Cerf và Bob Kahn.

Như nhiều bộ giao thức khác, bộ giao thức TCP/IP có thể được coi là một tập hợp các tầng, mỗi tầng giải quyết một tập các vấn đề có liên quan đến việc truyền dữ liệu, và cung cấp cho các giao thức tầng cấp trên một dịch vụ được định nghĩa rõ ràng dựa trên việc sử dụng các dịch vụ của các tầng thấp hơn. Về mặt logic, các tầng trên gần với người dùng hơn và làm việc với dữ liệu trừu tượng hơn, chúng dựa vào các giao thức tầng cấp dưới để biến đổi dữ liệu thành các dạng mà cuối cùng có thể được truyền đi một cách vật lý.

<a name="quatrinhphattrien"></a>
## Quá trình phát triển
Năm 1970, TCP/IP là gì được mọi người biết đến từ bộ giao thức liên mạng của công trình DARPA. Trải qua nhiều năm nghiên cứu và phát triển, bộ giao thức này đã nhận được nhiều kết quả tốt. Cũng bởi điều này mà cuộc hội thảo được Internet Architecture Broad mở ra với sự tham gia của hơn 250 đại biểu đại diện cho các công ty thương mại cho ra mắt giao thức và mô hình TCP/IP. Kể từ đó giao thức này được phổ biến rộng rãi trên toàn thế giới.

Vào năm 1975, cuộc thử nghiệm thông nối hai mạng lưới TCP/IP, giữa Stanford và UCL đã được tiến hành. Vào tháng 11 năm 1977, một cuộc thử nghiệm thông nối ba mạng lưới TCP/IP, giữa Mỹ, Anh và Na Uy đã được chỉ đạo. Giữa năm 1978 và 1983, một số những bản mẫu của TCP/IP đã được thiết kế tại nhiều trung tâm nghiên cứu. Ngày 1 tháng 1 năm 1983, ARPANET đã hoàn toàn được chuyển hóa sang dùng TCP/IP.

Vào tháng 3 năm 1982, Bộ Quốc phòng Mỹ chấp thuận TCP/IP thành một tiêu chuẩn cho toàn bộ mạng lưới vi tính truyền thông quốc phòng. Vào năm 1985, Uỷ ban kiến trúc Internet (Internet Architecture Board) đã dành 3 ngày hội thảo về TCP/IP cho công nghiệp điện toán, với sự tham dự của 250 đại biểu từ các công ty thương mại. Cuộc hội thảo này đã làm tăng thêm uy tín và sự nổi tiếng của giao thức, khiến nó ngày càng phổ biến trên thế giới.

Ngày 9 tháng 11 năm 2005 Kahn và Cerf đã được tặng thưởng Huy chương Tự do Tổng thống (Presidential Medal of Freedom) cho những thành tích cống hiến của họ đối với nền văn hóa của Mỹ.

Với số lượng thông tin ngày càng khủng như hiện nay, nếu như không có giao thức đóng gói đơn giản hóa và phân tích dữ liệu của TCP/IP thì con người sẽ bị đẩy lùi đi rất nhiều. Bằng chứng rõ ràng nhất là bất cứ máy tính nào muốn lên Internet đều phải dùng kết nối thông qua TCP/IP.

<a name="cachthuchoatdong"></a>
## Cách thức hoạt động
TCP đóng vai trò quan trọng trong việc kiểm tra và đảm bảo sự an toàn cho từng gói tin khi đi qua mỗi trạm. Khi thực hiện quá trình này nếu như giao thức TCP nhận thấy gói tin bị lỗi, một tín hiệu khác sẽ được truyền đi và gửi yêu cầu hệ thống gửi lại 1 gói tin khác. Quá trình này sẽ giúp người dùng hiểu rõ hơn chức năng của mỗi tầng trong mô hình TCP IP.

Còn IP (hay giao thức liên mạng) cho phép các gói tin được gửi tới địch đã được định sẵn bằng cách bổ sung các thông tin dẫn đường vào các gói tin để chúng được tới đúng đích đã quy định từ ban đầu.

Trong bộ giao thức TCP/IP, IP đóng vai trò vô cùng quan trọng trong việc chuyển tiếp gói tin tới một máy tính khác. Thông qua 1 hoặc nhiều khoảng (chuyển tiếp) gần nhất với người nhận gói tin. Còn giao thức TCP sẽ giúp kiểm tra các gói dữ liệu xem có bất cứ lỗi nào không. Sau đó gửi yêu cầu truyền lại nếu như phát hiện ra lỗi.
<a name="phobien"></a>
## Các giao thức TCP/IP phổ biến hiện nay
Hiện nay có 3 giao thức TCP/IP phổ biến trên thị trường đó là http, https và ftp.
- HTTP: Đây là giao thức được sử dụng giữa 1 web client và 1 web server để truyền thông tin dữ liệu không an toàn. Một trình duyệt Internet trên máy tính (web client) gửi 1 yêu cầu tới 1 web server để xem 1 trang web. Máy chủ web khi nhận được yêu cầu đó và gửi thông tin trang web về cho trình duyệt Internet đó.
- HTTPS: Giao thức này được sử dụng bởi 1 web client và 1 web server để truyền tải thông tin dữ liệu an toàn. Giao thức này được sử dụng để gửi dữ liệu giao dịch thẻ tín dụng hoặc là các dữ liệu cá nhân khác từ 1 web client (cụ thể như trình duyệt Internet trên máy tính) đến 1 web server.
- FTP: Giao thức này được dùng giữa 2 hoặc nhiều máy tính với nhau. Khi 1 máy tính gửi dữ liệu đến hoặc nhận thông tin dữ liệu từ máy tính khác một cách trực tiếp.

<a name="uunhuoc"></a>
## Ưu, nhược điểm
**Ưu điểm**
- Giúp bạn thiết lập hoặc thiết lập kết nối giữa các loại máy tính khác nhau.
- Nó hoạt động độc lập với hệ điều hành.
- Nó hỗ trợ nhiều giao thức định tuyến.
- Nó cho phép kết nối internet giữa các tổ chức.
- Mô hình TCP/IP có kiến trúc client-server có khả năng mở rộng cao.
- Nó có thể hoạt động độc lập.
- Hỗ trợ 1 số giao thức định tuyến.
- Nó có thể được sử dụng để thiết lập kết nối giữa 2 máy tính.

**Nhược điểm**
- TCP/IP là một mô hình phức tạp để thiết lập và quản lý.
- Với mô hình TCP/IP thì lớp truyền tải không đảm bảo việc phân phối các gói tin.
- Thay thế giao thức trong TCP/IP không hề dễ dàng.
- Nó không có sự tách biệt rõ ràng với các dịch vụ,giao diện và giao thức của nó.

<a name="mohinhphantang"></a>
# Mô hình phân tầng trong TCP/IP
Các giao thức TCP/IP tập hợp rất nhiều dữ liệu được phân cấp theo từng tầng khác nhau. Trong đó, từng tầng đóng vai trò khác nhau giúp xử lý dữ liệu thô từ các tầng dữ liệu dưới cùng, sau đó vận chuyển lên trên để các giao thức khác dễ làm việc hơn. Xét về mặt thực tế thì các tầng gần với người dùng và nhận nhiều dữ liệu phức tạp, vì thế cúng phải dựa vào những tầng thấp hơn để có thể xử lý dữ liệu phức tạp thành đơn giản mà mạng vật lý truyền đi được.

Cấu trúc 4 tầng của mô hình TCP/IP được chồng lên nhau theo thứ tự từ tầng thấp nhấp đến cao nhất như sau:
- Tầng 1: Tầng vật lý (Physical Layer).
- Tầng 2: Tầng mạng (Network Layer).
- Tầng 3: Tầng giao vận (Transport Layer)
- Tầng 4: Tầng ứng dụng (Application Layer).
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186059558-acb7214e-ac4c-43a8-bd83-4bd7edaa582e.jpg"/>
 </p>

<a name="tangungdung"></a>
## 1. Tầng ứng dụng
Tầng này đảm nhận vai trò giao tiếp giữa 2 loại máy khác nhau thông qua các.dịch vụ mạng khác nhau như: duyệt web, các giao thức trao đổi dữ liệu FTP, SSH, SMTP,… Toàn bộ dữ liệu khi tới được tầng 4 sẽ định dạng để kết nối theo kiểu Byte nối Byte. Những thông tin định tuyến tại đây sẽ giúp người dùng xác định đường đi của một gói tin.

Chức năng của tầng Application là:
- Là tầng giúp bạn xác định các đối tác giao tiếp, xác định tính khả dụng của tài nguyên và đồng bộ hóa giao tiếp.
- Nó cho phép người dùng đăng nhập vào một máy chủ từ xa.
- Tầng này cung cấp các dịch vụ email khác nhau.
- Ứng dụng này cung cấp các nguồn cơ sở dữ liệu phân tán và quyền truy cập thông tin toàn cầu về các đối tượng và dịch vụ khác nhau.
<a name="tanggiaovan"></a>
## 2. Tầng giao vận
Tầng giao vận hoạt động thông qua 2 giao thức chính đó là TCP (Transmisson Control Protocol) và UDP (User Datagram Protocol).

Trong đó TCP sẽ đảm bảo chất lượng truyền gửi gói tin, tuy nhiên chúng lại mất quá nhiều thời gian để có thể thực hiện các thủ tục kiểm soát dữ liệu. Ngược lại thì UDP lại cho tốc độ truyền tải dữ liệu nhanh.chóng hơn nhưng không đảm bảo được chất lượng dữ liệu như TCP. Ở tầng này, 2 giao thức TCP và UDP sẽ hỗ trợ lẫn nhau để phân luồng dữ liệu.

Chức năng của tầng Transport:
- Nó chia thông điệp nhận được từ lớp phiên thành các phân đoạn và đánh số chúng để tạo thành 1 chuỗi.
- Đảm bảo rằng thông báo được gửi đến đúng tiến trình trên máy đích.
- Nó cũng đảm bảo rằng toàn bộ dữ liệu đến mà không có bất kỳ lỗi nào.

<a name="tangmang"></a>
## 3. Tầng mạng
Tầng mạng là tầng thứ 2 của mô hình TCP/IP. Công việc chính của tầng này là gửi các gói tin từ bất kỳ mạng nào và bất kỳ máy tính nào chúng vẫn đến được chính xác đích của nó, bất kể nó đi con đường nào.

Tầng này cung cấp phương thức chức năng và thủ tục để chuyển các chuỗi dữ liệu có độ dài thay đổi từ nút này sang nút khác với sự trợ giúp của nhiều mạng khác nhau.

Tầng mạng đảm nhận việc truyền tải dữ liệu một cách hợp lý. Toàn bộ các giao thức của tầng này gồm có ICMP (Internet Control Message Protocol), IP (Internet Protocol) và IGMP (Internet Group Message Protocol).
<a name="tangvatly"></a>
## 4. Tầng vật lý
Tầng vật lý hay còn được gọi là tầng liên kết dữ liệu là tầng thấp nhất của mô hình TCP/IP. Tầng này có nhiệm vụ truyền dữ liệu giữa 2 thiết bị trong cùng 1 mạng. Tại đây, toàn bộ các gói dữ liệu sẽ được đóng vào khung được gọi là.Fram và được định tuyến đi tới đích đã được chỉ định sẵn ban đầu.
