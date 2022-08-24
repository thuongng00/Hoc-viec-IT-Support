# NAT là gì?
Nat (Network Address Translation) là một kỹ thuật cho phép chuyển đổi từ một địa chỉ IP này thành một địa chỉ IP khác. Thông thường, NAT được dùng phổ biến trong mạng sử dụng địa chỉ cục bộ, cần truy cập đến mạng công cộng (Internet). Vị trí thực hiện NAT là router biên kết nối giữa hai mạng.
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186323926-3b4167ec-53b1-4919-a8b2-34bc7f10e53a.png"/>
 </p>
 
# Nhiệm vụ của NAT 

NAT (Network Address Translation) giống như một Router, chuyển tiếp các gói tin giữa những lớp mạng khác nhau trên một mạng lớn. NAT dịch hay thay đổi một hoặc cả hai địa chỉ bên trong một gói tin khi gói tin đó đi qua một Router, hay một số thiết bị khác. Thông thường NAT thường thay đổi địa chỉ thường là địa chỉ riêng (IP Private) của một kết nối mạng thành địa chỉ công cộng (IP Public).

NAT cũng có thể coi như một Firewall (tường lửa) cơ bản. NAT duy trì một bảng thông tin về mỗi gói tin được gửi qua. Khi một máy tính trên mạng kết nối đến 1 website trên Internet header của địa chỉ IP nguồn được thay thế bằng địa chỉ Public đã được cấu hình sẵn trên NAT sever, sau khi có gói tin trở về NAT dựa vào bảng record mà nó đã lưu về các gói tin, thay đổi địa chỉ IP đích thành địa chỉ của PC trong mạng và chuyển tiếp đi. Thông qua cơ chế đó quản trị mạng có khả năng lọc các gói tin được gửi đến hay gửi từ một địa chỉ IP và cho phép hay ngăn truy cập đến một port cụ thể.

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
