# Một số linux command cơ bản trong quản trị mạng
 
## 1. ifconfig

- `ifconfig -a` - Liệt kê tất cả các inteface hiện đang có, kể cả các interface không sử dụng.
- `ifconfig <interface>` - Thông tin chi tiết của một interface cụ thể.
- `ifconfig <interface> <address> netmask <address>` - Gán địa chỉ IP và Gateway cho một giao diện. Tuy nhiên, các cấu hình này sẽ được thiết lập lại sau khi hệ thống khởi động lại.
- `ifup <interface> hay ifdown <interface>` - Để bật hay tắt một interface.

![image](https://user-images.githubusercontent.com/111716161/188848360-36227ced-48bc-44fa-abb0-94a32eb53f0a.png)

## 2. ip

- `ip a` - Lệnh này cung cấp thông tin chi tiết của tất cả các mạng như ifconfig.
- `ip link` - Cấu hình, thêm và xóa các interface. Sử dụng ip link show để hiển thị tất cả các interface trên hệ thống.
- `ip address` - Hiển thị địa chỉ ip, gắn địa chỉ ip mới hoặc xóa địa chỉ ip chỉ cũ.
- `ip route` - Được sử dụng để Cấu hình quản lý bảng định tuyến.

![image](https://user-images.githubusercontent.com/111716161/188849728-347c0b93-515b-486b-9aee-13d2b24fec8c.png)
## 3. hostname

- `hostname` - Hiển thị hostname
- `hostname --all-ip-addresses` - Hiển thị tất cả các địa chỉ IP
- `sudo hostname <new hostname>` - Thay đổi hostname. Tuy nhiên thay đổi bằng hostname chỉ tạm thời. Sau khi reboot, hostname sẽ bị đưa trở về như cũ.
  
![image](https://user-images.githubusercontent.com/111716161/188849988-6fe2f46d-cbcb-4aad-ab01-e00320de6325.png)

## 4. ping

- `ping <destination>` - Lệnh ping gửi gói tin echo ICMP để kiểm tra kết nối mạng, destination có thể là tên miền hoặc địa chỉ ip trực tiếp
- `ping -c <number> <destination>` - Bạn có thể giới hạn số lượng gói tin bằng cách thêm " -c " vào lệnh ping.
  
  ![image](https://user-images.githubusercontent.com/111716161/188851488-abcee0de-dff3-48e8-a402-ce44399f7bc4.png)

## 5. telnet

telnet là lệnh sẽ thực hiện kết nối máy chủ và máy đích thông qua một port bằng cách sử dụng giao thức telnet TCP/IP. Nếu kết nối được thiết lập có nghĩa là kết nối giữa hai máy đang hoạt động tốt. Trong trường hợp bạn không xác định một port cụ thể nào thì telnet sẽ sử dụng port mặc định là 23. 
  
`telnet <hostname/IP address> <port> `

## 6. traceroute

traceroute chính là một trong những lệnh hữu ích nhất trong khắc phục sự cố mạng qua những thông tin mà lệnh này cung cấp gồm:

- Cung cấp tên và xác định mọi thiết bị trên đường dẫn.
- Theo dõi lộ trình để đến đích của gói tin.
- Xác định và chỉ ra vị trí các sự cố trong kết nối mạng, độ trễ trong kết nối mạng đến từ đâu.

`traceroute <option> <destination>`
  
## 7. nslookup
nslookup là lệnh được sử dụng để thực hiện các tra cứu liên quan đến DNS. nslookup có thể cho chúng ta biết các thông tin quan trọng như MX records và địa chỉ IP liên kết với tên miền.

`nslookup <domainName>`

## 8. dig
dig là viết tắt của Domain Information Groper, có nghĩa là công cụ tìm kiếm thông tin tên miền. Nó có tác dụng để kiểm tra và xử lí sự cố DNS Server, tìm kiếm DNS và hiển thị các nội dung được yêu cầu. Lệnh dig như là một phiên bản mới hơn của nslookup, có thể thay thế cho những công cụ cũ trước đây là nslookup hay host và được sử dụng phổ biến để khắc phục sự cố DNS vì tính linh hoạt và dễ sử dụng của nó.

- `dig <domainName>` - Đây là lệnh truy vấn DNS cơ bản. Theo mặc định, nó sẽ xuất ra các bản ghi A
- `dig <domainName> MX` - Truy vấn các bản ghi MX
- `dig <domainName> NS` - Truy vấn các bản ghi NS
- `dig <domainName> ANY` - Truy vấn tất cả các loại bản ghi
  
## 9. netstat

netstat là một công cụ dòng lệnh rất hữu ích khi nó giúp ta hiển thị các thông tin bảng định tuyến, thông tin kết nối, trạng thái của các cổng, các cài đặt và nhiều các thống kê mạng khác nhau,...

Một số cú pháp lệnh netstat:

- `netstat -i` - Liệt kê các interface
- `netstat -r` - Hiển thị bảng định tuyến

## 10. curl 

Lệnh curl là 1 công cụ để truy cập trang web thông qua command, curl hỗ trợ những protocol khác nhau như FILE, FTP, FTPS, Gopher, HTTP, HTTPS, IMAP, LDAP, POP3, RTSP, SMTP, …

Mặc định curl chưa có sẵn trong Linux, để cài đặt curl từ Ubuntu repository sử dụng lệnh sau:

`sudo apt-get install curl`

Và tiến hành cài đặt những thư viện liên quan:

`sudo apt-get install libc6 libcurl3 zlib1g`

Và có thể curl với những lệnh thường xuyên sử dụng dưới đây, ví dụ lấy về nội dung của trang web www.google.com.

`curl http://www.google.com`
