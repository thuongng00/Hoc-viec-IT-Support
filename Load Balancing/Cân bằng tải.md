# Cân bằng tải

Load Balancing hay “Cân bằng tải” là một trong những tính năng rất quan trọng với những nhà phát triển, lập trình mạng.

Khi máy chủ down hoặc không thể xử lý, một Load Balancer sẽ được bổ sung. Người dùng truy cập vào load balancer. Tiếp tục được chuyển đến một máy chủ khác để thực hiện tác vụ. Dù máy chủ chính bị down hoặc nghẽn thì tất cả các yêu cầu của người dùng đều được giải quyết.

Load Balancing là tính năng giúp máy chủ ảo hoạt động đồng bộ và hiệu quả hơn thông qua việc phân phối đồng đều tài nguyên. 

# Lợi ích khi có Load Balancing

![image](https://user-images.githubusercontent.com/111716161/194447107-6a4392c8-d136-44c5-9354-77585d148fdd.png)

- Uptime

Với Load Balancing, khi máy chủ gặp sự cố, lưu lượng truy cập sẽ được tự động chuyển đến máy chủ còn lại. Nhờ đó, trong hầu hết mọi trường hợp, sự cố bất ngờ có thể được phát hiện và xử lý kịp thời, không làm gián đoạn các truy cập của người dùng.

- Datacenter linh hoạt

Khả năng linh hoạt trong việc điều phối giữa các máy chủ cũng là một ưu điểm khác của Load Balancing. Tự động điều phối giữa các máy chủ cũ và mới để xử lý các yêu cầu dịch vụ mà không làm gián đoạn các hoạt động chung của hệ thống.

- Bảo mật cho Datacenter

Bằng cách sử dụng Load Balancing, những yêu cầu từ người dùng sẽ được tiếp nhận và xử lý trước khi phân chia đến các máy chủ. Đồng thời, quá trình phản hồi cũng được thông qua Load Balancing, ngăn cản việc người dùng giao tiếp trực tiếp với máy chủ, ẩn đi thông tin và cấu trúc mạng nội bộ, từ đó chặn đứng những cuộc tấn công mạng hay truy cập trái phép…

# Health Checks

Có thể hiểu một cách đơn giản, Health Checks là việc kiểm tra tình trạng của một Backend Server. Bằng cách kết nối đến Backend Server dùng giao thức và cổng được định nghĩa bởi các quy tắc chuyển tiếp, nó đảm bảo rằng các máy chủ vẫn đang hoạt động ổn định.

Trong trường hợp máy chủ không hoạt động, Health Checks sẽ loại chúng ra khỏi vùng chứa. Điều này đồng nghĩa với việc các request sẽ không được chuyển tiếp đến máy chủ này nữa cho đến khi chúng vượt qua “bài kiểm tra” Health Checks sau. 

Qua quá trình này, Load Balancing có thể chuyển tiếp trực tiếp lưu lượng đến các Backend Server đang thật sự hoạt động nhằm giải quyết mọi tác vụ của người dùng.

# Cách Load Balancing xử lý trạng thái

![image](https://user-images.githubusercontent.com/111716161/194447317-1780377c-f588-4c8f-ac3c-ce96278e5b6e.png)

Trong nhiều trường hợp ứng dụng yêu cầu người truy cập tiếp tục kết nối đến cùng một Backend Server. Một thuật toán mã nguồn sẽ tạo ra một mối quan hệ dựa trên thông tin là IP của khách hàng. Đối với ứng dụng web thông qua sticky sessions, Load Balancer sẽ đặt một cookie. Tất cả các requests từ sessions hướng đến một máy chủ vật lý.

# Load Balancer dự phòng

![image](https://user-images.githubusercontent.com/111716161/194447362-d2ae65cc-0f47-4a71-af17-cabaec585f18.png)

Trong nhiều trường hợp, chỉ có một Load Balancer là điểm truy cập duy nhất. Chính vì vậy, chúng ta cần có một Load Balancer thứ hai. Nó sẽ được kết nối với Load Balancer ban đầu. Mục đích để mỗi Load Balancer đều có khả năng phát hiện lỗi và phục hồi.

Sẽ ra sao khi xảy ra trường hợp Load Balancer chính bị lỗi? Balancer thứ hai sẽ nhận trách nhiệm thay thế, do DNS di chuyển người dùng đến. Tuy nhiên, việc thay đổi DNS có thể mất nhiều thời gian trên internet. Và để chuyển đổi dự phòng được tự động, các quản trị viên sẽ cho phép linh hoạt địa chỉ IP Remapping. Chẳng hạn như trường hợp này là floating IPs.

IP Remapping giúp loại bỏ các vấn đề bộ nhớ đệm vốn có trong những thay đổi DNS. IP Remapping sẽ cung cấp một địa chỉ IP tĩnh. Địa chỉ IP này có thể được dễ dàng ánh xạ lại khi cần thiết. Tên miền có thể duy trì liên kết với các địa chỉ IP. Trong khi các địa chỉ IP của chính nó được di chuyển giữa các máy chủ.

