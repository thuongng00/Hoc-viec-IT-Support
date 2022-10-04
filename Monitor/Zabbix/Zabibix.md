# Zabbix

**Zabbix** là một giải pháp giám sát dịch vụ hệ thống mạng phân tán mã nguồn mở nổi tiếng, có nhiều tính năng độc đáo và khả năng tùy biến cao. 

Zabbix có khả năng phục vụ cho hệ thống mạng tầm trung và lớn của các doanh nghiệp hiện tại với mức chi phí đầu tư vừa phải. 

![image](https://user-images.githubusercontent.com/111716161/193794501-63d85b11-6eb6-4735-81f2-2d380779e138.png)

Zabbix được sáng lập bởi Alexei Vladishev và hiện tại được viết và phát hành dưới bản quyền General Public License GPL phiên bản 2. 

Zabbix sử dụng các cơ chế thông báo vấn đề linh hoạt cho quản trị viên như email, sms, OTT App,... Zabbix cũng cung cấp báo cáo và dữ liệu cực kì chính xác dựa trên cơ sở dữ liệu đã thu thập được từ thiết bị mạng. Tất cả báo cáo, thống kê cũng như cấu hình thông số của Zabbix có thể dễ dàng truy cập qua giao diện wb tinh tế, đẹp mắt, giúp chúng ta theo dõi được tình trạng hệ thống thiết bị server, dịch vụ,...

![image](https://user-images.githubusercontent.com/111716161/193794553-d3c35617-ea2f-4aa6-be2d-03a340960c75.png)

# Các thành phần của hệ thống giám sát Zabbix

### Zabbix Server

Đây là ứng dụng chương trình dịch vụ chính của dịch vụ Zabbix. Zabbix Server sẽ chịu trách nhiệm cho các hoạt động kiểm tra dịch vụ mạng từ xa, thu thập thông tin, lưu trữ, hiển thị, cảnh báo,... từ đó các quản trị viên có thể thao tác giám sát hệ thống tốt nhất. 

### Zabbix Proxy

Là một máy chủ được dùng cho việc quản lý nhiều nhánh hệ thống ở xa, hoặc ở các lớp mạng khác nhau. Từ Zabbix Proxy sẽ thu thập các thông tin thiết bị mạng rồi chuyển tiếp về cho máy chủ dịch vụ chính Zabbix Server.

![image](https://user-images.githubusercontent.com/111716161/193795575-b4d154fa-a176-4413-a7f2-d20b5074f29f.png)

### Zabbix Agent

Zabbix Agent là chương trình zabbix dùng để cài đặt lên các máy chủ hoặc thiết bị phía client, từ đó hỗ trợ kết nối từ Zabbix Server để lấy các thông tin cần thiết từ Client nhằm kiểm tra các tình trạng hệ thống hoặc theo nhu cầu quản trị viên. 

![image](https://user-images.githubusercontent.com/111716161/193796256-55f9e35a-774e-45e0-aa99-a92de206fdbf.png)

### Giao diện Web

Cung cấp giao diện Web trên nền tảng mã nguồn PHP cùng phong cách metro tinh tế. Hiện tại có thể xem Zabbix là một trong những ứng dụng có giao diện đẹp nhất, thiết kế vị trí tính năng bắt mắt và hợp lý. 

# Ưu, nhược điểm của Zabbix

### Ưu điểm

- Tự động tìm, phát hiện server và hệ thống mạng. 
- Hỗ trợ server cài đặt trên dòng hệ điều hành Unix/Linux.
- Hỗ trợ máy trạm client nhiều hệ điều hành. 
- Giao diện web cực kì tinh tế và đẹp mắt.
- Có thông báo sự cố qua email hoặc OTP App.
- Có báo cáo, biểu đồ qua giao diện web đẹp mắt. 
- Kiểm tra theo dõi việc đăng nhập. 
- Linh động trong việc phân quyền người sử dụng. 
- Mã nguồn mở, chi phí đầu tư thấp.
- Nhiều plugin hỗ trợ cho các dịch vụ hệ thống khác nhau. 

### Nhược điểm

- Không có giao diện web mobile hỗ trợ.
- Không phù hợp với hệ thống mạng lớn hơn 1000+ node thiết bị client cần giám sát, lúc này phát sinh vấn đề hiệu suất về PHP và Database. 
- Thiết kế template/alerting rule đôi khi khá phức tạp. 
