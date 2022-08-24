# NAT là gì?
Nat (Network Address Translation) là một kỹ thuật cho phép chuyển đổi từ một địa chỉ IP này thành một địa chỉ IP khác. Thông thường, NAT được dùng phổ biến trong mạng sử dụng địa chỉ cục bộ, cần truy cập đến mạng công cộng (Internet). Vị trí thực hiện NAT là router biên kết nối giữa hai mạng.
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186323926-3b4167ec-53b1-4919-a8b2-34bc7f10e53a.png"/>
 </p>
 
# Nhiệm vụ của NAT 

NAT (Network Address Translation) giống như một Router, chuyển tiếp các gói tin giữa những lớp mạng khác nhau trên một mạng lớn. NAT dịch hay thay đổi một hoặc cả hai địa chỉ bên trong một gói tin khi gói tin đó đi qua một Router, hay một số thiết bị khác. Thông thường NAT thường thay đổi địa chỉ thường là địa chỉ riêng (IP Private) của một kết nối mạng thành địa chỉ công cộng (IP Public).

NAT cũng có thể coi như một Firewall (tường lửa) cơ bản. NAT duy trì một bảng thông tin về mỗi gói tin được gửi qua. Khi một máy tính trên mạng kết nối đến 1 website trên Internet header của địa chỉ IP nguồn được thay thế bằng địa chỉ Public đã được cấu hình sẵn trên NAT sever, sau khi có gói tin trở về NAT dựa vào bảng record mà nó đã lưu về các gói tin, thay đổi địa chỉ IP đích thành địa chỉ của PC trong mạng và chuyển tiếp đi. Thông qua cơ chế đó quản trị mạng có khả năng lọc các gói tin được gửi đến hay gửi từ một địa chỉ IP và cho phép hay ngăn truy cập đến một port cụ thể.

# Cơ chế hoạt động của NAT
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186326800-8127b6ba-a7f5-475d-aa92-52afcc93bf40.png"/>
 </p>
 
NAT hoạt động giống như một Router dùng để chuyển tiếp các gói tin giữa những lớp mạng khác nhau trên một mạng lớn. Khi gói tin đi qua Router, NAT dịch hay thay đổi một hoặc cả hai địa chỉ bên trong gói tin đó. Thông thường NAT thường thay đổi địa chỉ thường là địa chỉ riêng (IP Private) của một kết nối mạng thành địa chỉ công cộng (IP Public).

NAT cũng được xem như một tường lửa cơ bản, duy trì một bảng thông tin về mỗi gói tin được gửi qua. Khi một máy tính trên mạng kết nối đến 1 website trên Internet header của địa chỉ IP nguồn được thay thế bằng địa chỉ Public đã được cấu hình sẵn trên NAT sever, sau khi có gói tin trở về NAT dựa vào bảng record mà nó đã lưu về các gói tin, thay đổi địa chỉ IP đích thành địa chỉ của PC trong mạng và chuyển tiếp đi. Thông qua cơ chế đó quản trị mạng có khả năng lọc các gói tin được gửi đến hay gửi từ một địa chỉ IP và cho phép hay ngăn truy cập đến một port cụ thể.


# Các thuật ngữ liên quan đến NAT

- Địa chỉ inside local: Đây là địa chỉ IP được đặt cho 1 thiết bị ở mạng nội bộ bên trong. Nó không được cung cấp bởi NIC (Network Information Center).
- Địa chỉ inside global: Đây là địa chỉ IP đã được đăng ký tại NIC. Địa chỉ inside global thường được dùng để thay thế cho địa chỉ IP inside local.
- Địa chỉ outside local: Đây là địa chỉ IP của một thiết bị nằm ở mạng bên ngoài. Các thiết bị thuộc mạng bên trong sẽ tìm thấy thiết bị thuộc mạng bên ngoài thông qua địa chỉ IP này. Địa chỉ outside local không nhất thiết phải được đăng ký với NIC. Nó hoàn toàn có thể là một địa chỉ Private.
- Địa chỉ outside global: Đây là địa chỉ IP được đặt cho một thiết bị nằm ở mạng bên ngoài. Địa chỉ này là một IP hợp lệ trên mạng internet.

# Các loại NAT hiện nay
Hiện nay NAT được phân chia thành nhiều chủng loại khác nhau. Nhưng nhìn chung kỹ thuật thường bao gồm các loại cơ bản như sau:

## Static NAT
Static NAT được dùng để chuyển đổi một địa chỉ IP này sang một địa chỉ khác một cách cố định, thông thường là từ một địa chỉ cục bộ sang một địa chỉ công cộng và quá trình này được cài đặt thủ công, nghĩa là địa chỉ ánh xạ và địa chỉ ánh xạ chỉ định rõ ràng tương ứng duy nhất.

Static NAT rất hữu ích trong trường hợp những thiết bị cần phải có địa chỉ cố định để có thể truy cập từ bên ngoài Internet. Những thiết bị này phổ biến là những Server như Web, Mail,...
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186325134-ec6040e7-060e-4d90-b583-bd9947f5111b.png"/>
 </p>
 
 ### Cấu hình Static NAT
Thiết lập mối quan hệ chuyển đổi giữa địa chỉ nội bộ bên trong và địa chỉ đại điện bên ngoài.
```
Router (config) # ip nat inside source static [local ip] [global ip]
```
Xác định các cổng kết nối vào mạng bên trong và thực hiện lệnh
```
Router (config-if) # ip nat inside
```
Xác định các cổng kết nối ra mạng công cộng bên ngoài thực hiện lệnh
```
Router (config-if) # ip nat outside
```
## Dynamic NAT
Dynamic NAT được dùng để ánh xạ một địa chỉ IP này sang một địa chỉ khác một cách tự động, thông thường là ánh xạ từ một địa chỉ cục bộ sang một địa chỉ được đăng ký. Bất kỳ một địa chỉ IP nào nằm trong dải địa chỉ IP công cộng đã được định trước đều có thể được gán một thiết bị bên trong mạng.
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186325539-bb283b89-1c01-424e-b1dc-2d86fcf3b798.png"/>
 </p>
 
### Cấu hình Dynamic NAT
Xác định dải địa chỉ đại diện bên ngoài (public):các địa chỉ NAT
```
Router (config) # ip nat pool [name start ip] [name end ip] netmask [netmask]/prefix-lenght [prefix-lenght]
```
Thiết lập ACL cho phép những địa chỉ nội bộ bên trong nào được chuyển đổi: các địa chỉ được NAT
```
Router (config) # access-list [access-list-number-permit] source [source-wildcard]
```
Thiết lập mối quan hệ giữa địa chỉ nguồn đã được xác định trong ACL với dải địa chỉ đại diện ra bên ngoài.
```
Router (config) # ip nat inside source list <acl-number> pool <name>
```
Xác định các cổng kết nối vào mạng nội bộ
```
Router (config-if) # ip nat inside
```
Xác định các cổng kết nối ra bên ngoài
```
Router (config-if) # ip nat outside
```
## NAT Overload
Nat Overload là một dạng của Dynamic NAT, nó thực hiện ánh xạ nhiều địa chỉ IP thành một địa chỉ (many - to - one) và sử dụng các địa chỉ số cổng khác nhau để phân biệt cho từng chuyển đổi. NAT Overload còn có tên gọi là PAT (Port Address Translation).

Chỉ số cổng được mã hóa 16 bit, do đó có tới 65536 địa chỉ nội bộ có thể được chuyển đổi sang một địa chỉ công cộng.
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186325739-951de4cf-a009-462a-96e6-ccd173f15eec.png"/>
 </p>
 
### Cấu hình NAT Overload
Xác định dãy địa chỉ bên trong cần chuyển dịch ra ngoài (private ip addresses range)
```
Router (config) # access-list <ACL-number> permit <source> <wildcard>
```
Cấu hình chuyển đổi địa chỉ IP sang cổng nối ra ngoài
```
Router (config) # ip nat inside source list <ACL-number> interface <interface> overload
```
Xác định các cổng nối vào mạng bên trong và nối ra mạng bên ngoài

Đối với các cổng nối vào mạng bên trong:
```
Router (config-if) # ip nat inside
```
Đối với nối ra mạng bên ngoài:
```
Router (config-if) # ip nat outside
```
# Các lệnh kiểm tra cấu hình NAT
Hiển thị bảng NAT đang hoạt động
```
R#show ip nat translation
```
Hiển thị trạng thái hoạt động của NAT
```
R#show ip nat statistics
```
Xóa bảng NAT
```
R#clear ip nat translation
```
Kiểm tra hoạt động của NAT, hiển thị các thông tin chuyển đổi NAT bởi router.
```
R#debug ip nat
```
Tóm lại, Static NAT được sử dụng để ánh xạ địa chỉ theo kiểu “one-to-one” và được chỉ định bởi người quản trị. Dynamic NAT là kiểu chuyển dịch địa chỉ dạng “one-to-one” một cách tự động. NAT Overload là kiểu chuyển dịch địa chỉ dạng “many-to-one” một cách tự động, sử dụng các chỉ số cổng (port) để phân biệt cho từng chuyển dịch.

# Ưu, nhược điểm của NAT
### Ưu điểm

- Tiết kiệm địa chỉ IPv4: Lượng người dùng truy cập internet ngày càng tăng cao. Điều này dẫn đến nguy cơ thiếu hụt địa chỉ IPv4. Kỹ thuật NAT sẽ giúp giảm thiểu được số lượng địa chỉ IP cần sử dụng.
- Giúp che giấu IP bên trong mạng LAN.
- NAT có thể chia sẻ kết nối internet cho nhiều máy tính, thiết bị di động khác nhau trong mạng LAN chỉ với một địa chỉ IP public duy nhất.
- NAT giúp nhà quản trị mạng lọc được các gói tin đến và xét duyệt quyền truy cập của IP public đến 1 port bất kỳ.

### Nhược điểm 
- CPU sẽ phải kiểm tra và tốn thời gian để thay đổi địa chỉ IP. Điều này làm tăng độ trễ trong quá trình switching. Làm ảnh hưởng đến tốc độ đường truyền của mạng internet.
- Vì các máy chủ bên trong mạng đôi khi không thể truy cập được, một số ứng dụng có xu hướng gặp vấn đề về khả năng tương thích với NAT
Vì giá trị bên trong các tiêu đề được thay đổi trong NAT, các giao thức đường hầm như IPSec có thể phức tạp để sử dụng. Bất cứ khi nào các giá trị bên trong tiêu đề được sửa đổi, việc kiểm tra tính toàn vẹn sẽ bị can thiệp khiến chúng không thành công.
- NAT có khả năng che giấu địa chỉ IP trong mạng LAN nên kỹ thuật viên sẽ gặp khó khăn khi cần kiểm tra nguồn gốc IP hoặc truy tìm dấu vết của gói tin.
- NAT cần kiểm tra tất cả các gói dữ liệu đến và đi chuyển đổi địa chỉ IP cục bộ và toàn cầu. Điều này làm cho tất cả các chi tiết dịch được lưu trữ bên trong bộ nhớ. Do đó, rất nhiều bộ nhớ cũng như bộ xử lý được sử dụng bởi NAT.
