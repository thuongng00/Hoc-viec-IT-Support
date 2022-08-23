# Mục lục

# Giao thức SNMP

## Giao thức SNMP là gì?
SNMP (Simple Network Management Protocol) là một giao thức tầng ứng dụng được Hội đồng Kiến trúc Internet (IAB) xác định trong RFC1157 để trao đổi thông tin quản lý giữa các thiết bị mạng. Nó là một phần của Transmission Control Protocol/Internet Protocol (TCP/IP).

## Các thành phần của giao thức SMNP
### 1. SNMP Manager
Trình quản lý hoặc hệ thống quản lý là một thực thể riêng biệt có trách nhiệm giao tiếp với các thiết bị mạng được triển khai SNMP agent. Đây thường là một máy tính được sử dụng để chạy một hoặc nhiều hệ thống quản lý mạng.

Các chức năng chính của SNMP manager:
- Agent truy vấn.
- Nhận response từ các agent.
- Đặt các biến trong agent.
- Xác nhận các sự kiện không đồng bộ từ các agent.
### 2. Các thiết bị được SNMP quản lý
Thiết bị được quản lý hoặc phần tử mạng là một phần của mạng yêu cầu một số hình thức giám sát và quản lý, ví dụ: router, switches, server, máy trạm, máy in, UPS, v.v.

### 3. SNMP Agent
Agent là một chương trình được đóng gói trong các thiết bị mạng. Việc kích hoạt agent cho phép nó thu thập cơ sở dữ liệu thông tin quản lý từ thiết bị cục bộ và cung cấp nó cho SNMP manager khi được truy vấn. Các agent này có thể là tiêu chuẩn (ví dụ: Net-SNMP) hoặc cụ thể cho một nhà cung cấp (ví dụ: HP insight agent).

Các chức năng chính của SNMP agent:
- Thu thập thông tin quản lý về các chỉ số hoạt động cuả thiết bị.
- Lưu trữ và truy xuất thông tin quản lý như được định nghĩa trong MIB.
- Báo hiệu sự kiện cho trình quản lý.
- Hoạt động như một proxy cho một số nút mạng không quản lý được – SNMP.

## Giao thức SNMp hoạt động như thế nào?

SNMP thực hiện vô số chức năng, dựa trên sự pha trộn giữa truyền tin push-and-pull giữa các thiết bị mạng và hệ thống quản lý. Nó có thể ra lệnh đọc hoặc ghi, chẳng hạn như đặt lại mật khẩu hoặc thay đổi cài đặt cấu hình. Nó có thể báo cáo lại mức độ sử dụng băng thông, CPU và bộ nhớ, với một số trình quản lý SNMP tự động gửi cho người quản trị một email hoặc thông báo tin nhắn văn bản nếu vượt quá ngưỡng xác định trước.

Trong hầu hết các trường hợp, SNMP hoạt động trong một mô hình đồng bộ, với giao tiếp được khởi tạo bởi người quản lý SNMP và tác nhân gửi phản hồi. Các lệnh và thông báo này, thường được vận chuyển qua giao thức UDP hoặc TCP/IP, được gọi là đơn vị dữ liệu giao thức (PDU):

- GET: Được tạo bởi trình quản lý SNMP và được gửi đến một agent để lấy giá trị của một biến số nào đó, được xác định bởi OID của nó, trong một MIB .
- RESPONSE: Được gửi bởi agent cho người quản lý SNMP, được phát đi để trả lời yêu cầu GET. Chứa các giá trị của các biến được yêu cầu.
- GETNEXT: Được gửi bởi người quản lý SNMP đến agent để lấy các giá trị của OID tiếp theo trong hệ thống phân cấp của MIB.
- GETBULK: Được gửi bởi người quản lý SNMP cho agent để có được các bảng dữ liệu lớn bằng cách thực hiện nhiều lệnh GETNEXT.
- SET: Được gửi bởi người quản lý SNMP cho agent để đưa ra các cấu hình hoặc lệnh.
- TRAP: Một cảnh báo không đồng bộ được gửi bởi agent đến trình quản lý SNMP để chỉ ra một sự kiện quan trọng, chẳng hạn như lỗi hoặc sự cố, đã xảy ra.

## Cấu trúc của SNMP
<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/186101169-58e5989f-9018-4cef-94f1-00a9a490d169.png"/>
</p>
Để gửi thông tin, SNMP sử dụng mô hình truyền thông phân lớp.
- Layer 1 – Lớp ứng dụng (SNMP)
- Layer 2 – Lớp vận chuyển (UDP)
- Layer 3 – Lớp Internet (IP)
- Layer 4 – Lớp Network interface
Mặc dù mô hình nhiều lớp này có vẻ hơi khó hiểu, nhưng nó rất hiệu quả trong việc tách biệt các nhiệm vụ giao tiếp và hỗ trợ thiết kế, triển khai mạng.

## Lợi ích của SNMP
Sử dụng SNMP cho phép bạn quản lý các asset mạng không có hệ điều hành, nhưng là các thành phần quan trọng của cơ sở hạ tầng. 

Nó đơn giản hóa nhiệm vụ và giúp bạn có thể tập trung mạng. Nó còn cho phép kiểm soát hiệu quả hơn, ngay cả đối với thiết bị không có hệ điều hành như máy in.

Một ưu điểm khác của SNMP là nó có một ngôn ngữ duy nhất cho phép người dùng tương tác với tất cả các thiết bị từ các nhà sản xuất khác nhau.

Vì vậy, nó tương thích với hầu hết mọi asset và dịch vụ mạng, chẳng hạn như Windows, Linux, Mac và máy ảo Java.

SNMP không chỉ hữu ích để cung cấp hỗ trợ chủ động mà còn để cải thiện trải nghiệm khách hàng, cho phép bạn dự đoán nhu cầu.

Các lợi ích chính khác của SNMP:
- Ưu điểm chính của việc sử dụng SNMP là thiết kế đơn giản. Dễ dàng triển khai nó trên mạng, vì nó không yêu cầu cấu hình lâu.
- Hơn nữa, SNMP rất phổ biến ngày nay. Hầu hết tất cả các nhà sản xuất thiết bị phần cứng liên mạng lớn, như switch hoặc router, đều triển khai hỗ trợ SNMP trong các sản phẩm của họ.
- Mở rộng là một ưu thế khác của SNMP. Do thiết kế đơn giản, dễ dàng cập nhật giao thức để đáp ứng nhu cầu của user trong tương lai.
- SNMP dựa trên giao thức truyền tải UDP, yêu cầu ít tài nguyên hơn và kết nối đồng thời hơn với TCP.
