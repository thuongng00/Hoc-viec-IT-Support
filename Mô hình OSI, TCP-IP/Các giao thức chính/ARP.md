# Mục lục

[Giao thức ARP là gì?](#arp)

[Cơ chế hoạt động của ARP](#coche)

[Các loại bản tin ARP](#bantin)

[Các bước hoạt động của giao thức mạng ARP](#hoatdong)

# Giao thức ARP
<a name="arp"></a>
## Giao thức ARP là gì?

### Khái niệm
ARP (viết tắt của cụm từ Address Resolution Protocol) là giao thức mạng được dùng để tìm ra địa chỉ phần cứng (địa chỉ MAC) của thiết bị từ một địa chỉ IP nguồn. Nó được sử dụng khi một thiết bị giao tiếp với các thiết bị khác dựa trên nền tảng local network. Ví dụ như trên mạng Ethernet mà hệ thống yêu cầu địa chỉ vật lý trước khi thực hiện gửi packets. 

Thiết bị gửi sử dụng ARP để có thể dịch địa chỉ IP sang địa chỉ MAC. Thiết bị sẽ gửi một request ARP đã chứa địa chỉ IP của thiết bị nhận. Tất cả thiết bị trên đoạn local network sẽ nhìn thấy thông điệp này. Tuy nhiên, chỉ thiết bị có địa chỉ IP chứa trong request mới có thể phản hồi lại với thông điệp mà chứa địa chỉ MAC của nó. Thiết bị gửi khi đó sẽ có đầy đủ các thông tin để gửi packet tới thiết bị nhận.
### Lịch sử hình thành
ARP được hình thành và phát triển vào đầu những năm 1980 như một giao thức dịch địa chỉ chung cho các mạng IP. Bên cạnh Ethernet và WiFi thì ARP đã được triển khai cho ATM, Token Ring và cả những loại mạng vật lý khác.
### Mục đích
ARP cho phép một mạng quản lý các kết nối độc lập với những thiết bị vật lý cụ thể được gắn vào từng mạng. Điều này cho phép giao thức Internet vận hành hiệu quả hơn so với việc nó phải tự quản lý địa chỉ của các thiết bị phần cứng và mạng vật lý.

<a name="coche"></a>
## Cơ chế hoạt động của ARP
Quá trình hoạt động của ARP được bắt đầu khi một thiết bị nguồn trong một mạng IP có nhu cầu thực hiện gửi một gói tin IP. Trước hết thiết bị đó phải xác định được xem địa chỉ IP đích của gói tin có phải đang nằm cùng trong mạng nội bộ của mình hay không. Nếu đúng vậy thì thiết bị sẽ thực hiện gửi trực tiếp gói tin đến thiết bị đích. Nếu địa chỉ IP đích đang  nằm trên mạng khác, thì thiết bị sẽ gửi gói tin đến một trong các router nằm cùng ở trên mạng nội bộ để router này làm nhiệm vụ forward gói tin.

Cả hai trường hợp, bạn đều thấy được là thiết bị phải gởi gói tin IP đến một thiết bị IP khác trên cùng mạng nội bộ. Chúng ta biết rằng việc gửi gói tin trong cùng mạng thông qua Switch là dựa vào địa chỉ MAC hay là địa chỉ phần cứng của thiết bị. Sau khi gói tin được đóng gói thì hệ thống mới bắt đầu được chuyển qua quá trình phân giải địa chỉ ARP và thực hiện chuyển đi.

ARP về cơ bản là một quá trình có 2 chiều request/response giữa các thiết bị trong cùng mạng nội bộ. Thiết bị nguồn request bằng cách gửi một bản tin local broadcast  lên trên toàn mạng. Thiết bị đích response bằng một bản tin unicast để trả lại cho thiết bị nguồn.

<a name="bantin"></a>
## Các loại bản tin ARP

### ARP probe
Đây là loại bản tin ARP dùng để máy thăm dò xem địa chỉ mà máy được cấp phát (cấu hình manual hoặc DHCP, ...) có bị trùng với địa chỉ IP của máy nào trong cùng mạng hay không. Khi mới ban đầu, các máy đều thực hiện broadcast bản tin ARP này.

Bản tin này có cấu trúc địa chi IP của máy gửi là 0.0.0.0 (thể hiện máy gửi bản tin này chưa xác định IP, đồng thời cũng là để các máy khác trong mạng không cập nhật MAC của máy vào ARP caching - vì nó chưa được gán IP cụ thể nào)

Địa chỉ MAC đích là 00:00:00:00:00:00

Địa chỉ IP đích là địa chỉ IP mà máy gửi được cấp phát.

Thông thường bản tin ARP request này sẽ không có reply.

### ARP announcements
ARP cũng sử dụng một cách đơn giản để thông báo tới các máy trong mạng khi địa chỉ IP hoặc địa chỉ MAC của nó thay đổi. Đó chính là bản tin gratuitous ARP

Bản tin Gratuitous ARP được gửi broadcast request trong mạng với địa chỉ MAC và IP máy gửi là địa chỉ sau khi thay đổi.

Địa chỉ MAC đích là 00.00.00.00.00.00. Địa chỉ IP đích là chính nó. Điều này đảm bảo các máy trong mạng khi nhận được bản tin này sẽ chỉ cập nhật địa chỉ MAC và IP của máy gửi vào trong ARP caching của mình => không có bản tin reply cho bản tin này.

### ARP request
Là bản tin ARP request mà máy gửi gửi broadcast để tìm địa chỉ MAC của máy nhận.

Địa chỉ MAC và IP gửi là địa chỉ của máy gửi.

Địa chỉ MAC nhận được set là 0 hết.

Địa chỉ IP nhận là địa chỉ IP của máy cần tìm.

### ARP reply
Là bản tin mà máy nhận sau khi nhận được ARP request sẽ đóng gói lại MAC của mình và gửi bản tin reply về cho máy gửi.

Nó sẽ đóng gói là địa chỉ IP và MAC của mình vào địa chỉ SHA và PHA.

Địa chỉ mà máy gửi gửi tới nó sẽ được đóng gói và phần địa chỉ THA và TPA.

Gửi bản tin unicast.

Có 4 loại địa chỉ nằm trong một bản tin ARP  đó là:
- Sender Hardware Address: Đây là địa chỉ lớp hai của thiết bị gửi bản tin.
- Sender Protocol Address: Đây là địa chỉ lớp ba (hay còn gọi là địa chỉ logic) của thiết bị gửi bản tin.
- Target Hardware Address: Địa chỉ lớp hai (hay còn được gọi là địa chỉ phần cứng) của thiết bị đích của bản tin.
- Target Protocol Address: Địa chỉ lớp ba (hay gọi là  địa chỉ logic) của thiết bị đích của bản tin.

<a name="hoatdong"></a>
## Các bước hoạt động của giao thức mạng ARP
1. Source Device Checks Cache: Trong bước này, thiết bị sẽ  thực hiện kiểm tra cache (bộ đệm) của mình. Nếu đã có địa chỉ IP đích tương ứng với MAC nào đó rồi thì lập tức hệ thống chuyển sang bước 9.
2. Source Device Generates ARP Request Message:  Hệ thống bắt đầu khởi tạo gói tin ARP Request với các trường địa chỉ như trên.
3. Source Device Broadcasts ARP Request Message: Thiết bị nguồn truyền gói tin ARP Request trên toàn mạng
4. Local Devices Process ARP Request Message: Các thiết bị trong mạng đều sẽ nhận được gói tin ARP Request. Gói tin được xử lý bằng cách đưa thiết bị vào trường địa chỉ Target Protocol Address. Nếu trùng với địa chỉ của mình thì tiếp tục xử lý, nếu không thì hủy gói tin
5. Destination Device Generates ARP Reply Message: Nếu Thiết bị với IP trùng với IP trong trường Target Protocol Address sẽ thực hiện quá trình khởi tạo gói tin ARP Reply. Đồng thời thiết bị sẽ lấy địa chỉ datalink của mình để tiến hành đưa vào trường Sender Hardware Address
6. Destination Device Updates ARP Cache: Thiết bị đích cập nhật bảng ánh xạ địa chỉ IP và MAC của thiết bị nguồn vào bảng ARP cache của mình để giảm bớt thời gian xử lý cho những lần sau.
7. Destination Device Sends ARP Reply Message: Thiết bị đích sẽ bắt đầu gửi gói tin Reply đã được khởi tạo đến thiết bị nguồn. 
8. Source Device Processes ARP Reply Message: Thiết bị nguồn nhận được gói tin reply và tiến hành xử lý bằng cách lưu trường Sender Hardware Address trong gói reply như những địa chỉ phần cứng của thiết bị đích.
9. Source Device Updates ARP Cache: Thiết bị nguồn update vào ARP cache giá trị tương ứng giữa địa chỉ network và cả địa chỉ datalink của thiết bị đích. Do đó, những lần tiếp theo sẽ không còn cần tới request.
