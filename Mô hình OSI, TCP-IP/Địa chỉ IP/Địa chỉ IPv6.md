# IPv6
IPv6 (Internet protocol version 6) là thể hệ địa chỉ Internet phiên bản mới hoạt động trên Layer 3,được thiết kế để thay thế cho phiên bản địa chỉ IPv4 trong hoạt động Internet. Vậy cấu trúc, địa chỉ của IPv6 là gì, nó có gì vượt trội hơn IPv4 mà lại được thúc đẩy để giải quyết vấn đề cạn kiệt địa chỉ cũng như những thiếu sót của IPv4 trong thời đại công nghệ như hiện nay.

# Cấu trúc IPv6

Trong IPV6, thay vì sử dụng một địa chỉ nguồn và đích là 32bit để cung cấp khoảng 4.294.967.296 (232) địa chỉ  như IPv4, địa chỉ IPv6 có chiều dài 128bit, do đó độ dài của IP sẽ lớn hơn,tương đương với việc số địa chỉ được tạo ra từ bội số 128bit sẽ lớn hơn rất nhiều ,có thể lên đến 3.4x1038 địa chỉ.Ngoài ra,có một vài sự khác nhau trong cách biểu diễn địa chỉ của IPv6, một địa chỉ IPv6 thường được viết thành 8 nhóm, mỗi nhóm gồm có 4 số hex và mỗi nhóm được tách biệt với nhau bằng dấu “:”. 

Ví dụ: 2001:0f68:0000:0000:0000:0000:1986:69af.

*Cấu trúc IPv6 gồm 2 phần:*

### Payload 
Là sự kết hợp của Extension và PDU.Thông thường có thể lên tới 65535 byte.PDU thường bao gồm header của giao thức tầng cao và độ dài của nó, còn Extension là những thông tin liên quan đến dịch vụ kèm theo trong IPv6 được chuyển tới một trường khác và nó có thể có hoặc không.

### IPv6 Header
Là thành phần luôn phải có trong một gói tin IPv6 và cố định 40 bytes.

- Version: 4 bits giúp xác định phiên bản của giao thức.
- Traffic class: 8 bits giúp xác định loại lưu lượng.
- Flow label: 20 bits giá mỗi luồng dữ liệu.
- Payload length: 16 bits (số dương). Giúp xác định kích thước phần tải theo sau IPv6 Header.
- Next-Header: 8 bits giúp xác định Header tiếp theo trong gói  tin.
- Hop Limit: 8 bits (số dương). Qua mỗi node, giá trị này giảm 1 đơn vị (giảm đến 0 thì gói bị loại bỏ).
- Source address: 128 bits mang địa chỉ IPv6 nguồn của gói tin.

Trong khi địa chỉ Unicast được sử dụng để phân biệt các host đơn lẻ trên một mạng, thì địa chỉ multicast lại sử dụng để phân biệt một nhóm các giao diện mạng cư trú điển hình trong các máy tính phức hợp. Giống như địa chỉ multicast, các địa chỉ anycast cũng phân biệt một nhóm cụ thể các giao diện mạng thường trú trong các máy tính phức hợp, nhưng khác với địa chỉ multicast khi có một gói dữ liệu được gửi đi nó sẽ không được gửi đến tất cả các giao diện mạng trong nhóm, mà chỉ được gửi đến thành viên gần nhất với người gửi.

| Các địa chỉ IPv6 đặc biệt | IPv6 Address | Meaning |
|---------------------------|--------------|---------|
| 0:0:0:0:0:0:0:0/128 | ::/128 | Địa chỉ không xác định |
| 0:0:0:0:0:0:0:0 | ::/0 | Tuyến đường mặc định |
| 0:0:0:0:0:0:0:1/128 | ::1/128 | Địa chỉ Loopback |

Trong mạng máy tính, các chế độ địa chỉ đề cập đến việc lưu trữ một địa chỉ trên mạng. IPv6 cung cấp một số chế độ địa chỉ mà theo đó một máy chủ có thể được xử lý như: Unicast, Multicast và Anycast.

### Địa chỉ Unicast
Trong chế độ địa chỉ unicast, máy chủ được xác định duy nhất trong một phân đoạn mạng. Gói IPv6 chứa cả địa chỉ IP nguồn và đích. Giao diện máy chủ được trang bị một địa chỉ IP duy nhất trong phân khúc mạng đó. Khi bộ chuyển mạch mạng hoặc bộ định tuyến nhận được gói IP unicast thì nó được gửi đến một máy chủ duy nhất.

Địa chỉ unicast gồm có 4 loại khác nhau :
- Global Unicast Address: tương ứng với địa chỉ public của IPv4, là loại địa chỉ được cho phép truy cập rộng rãi trên mạng internet, hỗ trợ cho việc định tuyến và đánh địa chỉ phân cấp.
- Link-Local Address: địa chỉ này luôn được cấu hình một cách tự động trên interface của một thiết bị. Địa chỉ này luôn bắt đầu với FE80. 16 bit đầu tiên của địa chỉ liên kết cục bộ luôn được đặt thành 1111 1110 1000 0000 (FE80). 48 bit tiếp theo được đặt thành 0, do đó nó chỉ được sử dụng để liên lạc giữa các máy chủ IPv6 trên một liên kết (phân đoạn quảng bá). Các địa chỉ này không thể định tuyến, do đó, Bộ định tuyến không bao giờ chuyển tiếp các địa chỉ này bên ngoài liên kết.
- Site-Local Address: tương tự như địa chỉ Private trong IPv4(10.0.0.0/8,172.16.0.0/12 và 192.168.0.0/16), dùng trong nội bộ một Site.
- Unique-Local Address: được sử dụng trong phạm vi toàn cầu, dùng để thay thế cho địa chỉ site-local.

### Địa chỉ Multicast
Chế độ Multicast IPv6 giống như của IPv4. Gói tin được gửi đến nhiều node với một địa chỉ multicast đặc biệt. Tất cả các node quan tâm đến thông tin phát multicast đó, trước tiên cần tham gia nhóm multicast .Toàn bộ các node tham gia nhóm đều sẽ nhận được gói phát multicast này và xử lý nó, trong khi các node khác không quan tâm đến gói phát multicast đó thì bỏ qua.

Địa chỉ multicast cũng có các phạm vi: global, site-local, link-local ngoài ra multicast còn có thêm 2 phạm vi mới đó là organization-local và node-local. Một node IPv6 có thể được gắn rất nhiều địa chỉ.
- Organization-local: được sử dụng trong phạm vi một tổ chức với một số site.
- Node-local: chỉ có tính tương ứng trong phạm vi một node.

### Địa chỉ Anycast
IPv6 đã giới thiệu một loại địa chỉ mới, được gọi là địa chỉ Anycast.Trong chế độ địa chỉ này, nhiều Hosts được gán cùng một địa chỉ IP Anycast. Khi một node muốn liên lạc với một node được trang bị địa chỉ IP Anycast, nó sẽ gửi một tin nhắn Unicast.Tin nhắn này sẽ không được gửi đến tất cả các node trong nhóm giống như Multicast mà với sự trợ giúp của cơ chế định tuyến, thông điệp Unicast đó được gửi đến node gần nhất trong nhóm với người gửi(tính theo thủ tục định tuyến) .
