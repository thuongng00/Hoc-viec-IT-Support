# FirewallD

FirewallD là giải pháp tường lửa mạnh mẽ, toàn diện được cài đặt mặc định trên CentOS/RHEL 7, nhằm thay thế Iptables với những khác biệt cơ bản:

- FirewallD sử dụng “zones” và “services” thay vì “chain” và “rules” trong Iptables.

- FirewallD quản lý các quy tắc được thiết lập tự động, có tác dụng ngay lập tức mà không làm mất đi các kết nối và session hiện có.

![image](https://user-images.githubusercontent.com/111716161/194788584-9d935a67-7c3a-48c0-987e-9dae64e9fc48.png)

Firewalld cung cấp một firewall động có thể quản lý được, hỗ trợ cho các vùng mạng/ tường lửa xác định mức độ tin cậy của các kết nối hoặc giao diện. Nó có hỗ trợ cài đặt tường lửa IPv4, IPv6, ethernet bridge và IP set. Các tùy chọn cấu hình giữa runtime và  permanent là tách biệt. Nó cũng cung cấp một giao diện cho các dịch vụ hoặc ứng dụng để thêm các rule một cách trực tiếp.

# Tính năng

Firewalld hỗ trợ cả mạng IPv4 và IPv6 và có thể quản lý các vùng tường lửa riêng biệt với các mức độ tin cậy khác nhau như được xác định trong hồ sơ vùng . Quản trị viên có thể định cấu hình Trình quản lý mạng để tự động chuyển đổi cấu hình vùng dựa trên các mạng Wi-Fi (không dây) và Ethernet (có dây) đã biết, nhưng firewalld không thể tự thực hiện việc này. 

Các dịch vụ và ứng dụng có thể sử dụng giao diện D-Bus để truy vấn và cấu hình tường lửa. Firewalld hỗ trợ các quy tắc hẹn giờ, có nghĩa là số lượng kết nối (hoặc "số lần truy cập") đến một dịch vụ có thể bị giới hạn trên toàn cầu. Không có hỗ trợ tính lần truy cập và từ chối kết nối tiếp theo trên mỗi IP nguồn; một kỹ thuật phổ biến được triển khai để hạn chế tác động của hack brute-force và các cuộc tấn công từ chối dịch vụ phân tán.

Cú pháp lệnh của firewalld tương tự nhưng dài dòng hơn các giao diện người dùng iptables khác như Tường lửa không phức tạp của Ubuntu (ufw). Giao diện dòng lệnh cho phép quản lý các bộ quy tắc tường lửa cho giao thức, cổng, nguồn và đích; hoặc các dịch vụ được xác định trước theo tên.

Các dịch vụ được định nghĩa là các tệp XML có chứa các ánh xạ cổng và giao thức, và các thông tin bổ sung tùy chọn như chỉ định các mạng con và liệt kê các mô-đun trợ giúp Kernel cần thiết. Cú pháp tương tự như cú pháp của các tệp dịch vụ của systemd.

# Lợi ích của việc sử dụng FirewallD

Các thay đổi có thể được thực hiện ngay lập tức trong môi trường runtime. Không cần khởi động lại dịch vụ hoặc daemon.

Với giao diện firewalld D-Bus, rất dễ dàng cho các dịch vụ, ứng dụng và cả người dùng để điều chỉnh cài đặt tường lửa. Giao diện hoàn chỉnh và được sử dụng cho các công cụ cấu hình tường lửa firewall-cmd, firewall-config và firewall-applet.

Sự tách biệt giữa runtiem và cấu hình permanent giúp bạn có thể thực hiện các đánh giá và bài test trong runtime. Cấu hình runtime chỉ có hiệu lực cho đến khi reload và restart lại dịch vụ tiếp theo hoặc khởi động lại hệ thống. Sau đó, cấu hình permanent sẽ được tải lại. Với môi trường runtime, có thể sử dụng runtime cho các cài đặt chỉ hoạt động trong một khoảng thời gian giới hạn. Nếu cấu hình runtime đã được sử dụng để đánh giá, đã hoàn tất và hoạt động, thì có thể lưu cấu hình này vào môi trường permanent. 

# Các khái niệm cơ bản trong FirewallD

### 1. Zone

Trong FirewallD, zone là một nhóm các quy tắc nhằm chỉ ra những luồng dữ liệu được cho phép, dựa trên mức độ tin tưởng của điểm xuất phát luồng dữ liệu đó trong hệ thống mạng. Để sử dụng, bạn có thể lựa chọn zone mặc định, thiết lập các quy tắc trong zone hay chỉ định network interface để quy định hành vi được cho phép.

Các zone được xác định trước theo mức độ tin cậy, theo thứ tự từ “ít-tin-cậy-nhất” đến “đáng-tin-cậy-nhất”:

- drop: ít tin cậy nhất – toàn bộ các kết nối đến sẽ bị từ chối mà không phản hồi, chỉ cho phép duy nhất kết nối đi ra.

- block: tương tự như drop nhưng các kết nối đến bị từ chối và phản hồi bằng tin nhắn từ icmp-host-prohibited (hoặc icmp6-adm-prohibited).

- public: đại diện cho mạng công cộng , không đáng tin cậy. Các máy tính/services khác không được tin tưởng trong hệ thống nhưng vẫn cho phép các kết nối đến trên cơ sở chọn từng trường hợp cụ thể.

- external: hệ thống mạng bên ngoài trong trường hợp bạn sử dụng tường lửa làm gateway, được cấu hình giả lập NAT để giữ bảo mật mạng nội bộ mà vẫn có thể truy cập.

- internal: đối lập với external zone , sử dụng cho phần nội bộ của gateway. Các máy tính/services thuộc zone này thì khá đáng tin cậy.

- dmz: sử dụng cho các máy tính/service trong khu vực DMZ (Demilitarized) – cách ly không cho phép truy cập vào phần còn lại của hệ thống mạng , chỉ cho phép một số kết nối đến nhất định.

- work: sử dụng trong công việc, tin tưởng hầu hết các máy tính và một vài services được cho phép hoạt động.

- home: môi trường gia đình – tin tưởng hầu hết các máy tính khác và thêm một vài services được cho phép hoạt động.

- trusted: đáng tin cậy nhất – tin tưởng toàn bộ thiết bị trong hệ thống.

### 2. Hiệu lực của các quy tắc

- Runtime ( mặc định ): có tác dụng ngay lập tức , mất hiệu lực khi reboot hệ thống .

- Permanent : không áp dụng cho hệ thống đang chạy, cần reload mới có hiệu lực , tác dụng vĩnh viễn cả khi reboot hệ thống .

Việc Restart/Reload sẽ hủy bộ các thiết lập Runtime đồng thời áp dụng thiết lập Permanent mà không hề phá vỡ các kết nối và session hiện tại. Điều này giúp kiểm tra hoạt động của các quy tắc trên tường lửa và dễ dàng khởi động lại nếu có vấn đề xảy ra.
