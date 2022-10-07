# Tường lửa

Tường lửa hay còn được gọi với cái tên là FireWall thuật ngữ trong chuyên ngành mạng máy tính, nói nôm na có thể gọi là bức tường lửa một hệ thống an ninh mạng, bảo mật an toàn thông tin mạng.

Tường lửa tồn tại ở 2 loại phần cứng và phần mềm được tích hợp vào bên trong hệ thống và nó hoạt động như một rào chắn phân cách giữa truy cập an toàn và truy cập không an toàn, chống lại truy cập trái phép, ngăn chặn virus… đảm bảo thông tin nội bộ được an toàn không bị truy cập xấu đánh cắp.

# Vai trò của firewall

Tường lửa có vai trò như nào?
Firewall giúp kiểm soát luồng thông tin giữa Intranet và Internet, chúng phát hiện và phán xét những hành vi được truy cập và không được truy cập vào bên trong hệ thống, đảm bảo tối đa sự an toàn thông tin.

Tính năng chính của dòng thiết bị này có thể được tóm tắt ở những gạch đầu dòng dưới đây:

- Cho phép hoặc vô hiệu hóa các dịch vụ truy cập ra bên ngoài, đảm bảo thông tin chỉ có trong mạng nội bộ.

- Cho phép hoặc vô hiệu hóa các dịch vụ bên ngoài truy cập vào trong.

- Phát hiện và ngăn chặn các cuộc tấn công từ bên ngoài.

- Hỗ trợ kiểm soát địa chỉ truy cập (bạn có thể đặt lệnh cấm hoặc là cho phép).

- Kiểm soát truy cập của người dùng.

- Quản lý và kiểm soát luồng dữ liệu trên mạng.

- Xác thực quyền truy cập.

- Hỗ trợ kiểm soát nội dung thông tin và gói tin lưu chuyển trên hệ thống mạng.

- Lọc các gói tin dựa vào địa chỉ nguồn, địa chỉ đích và số Port ( hay còn cổng), giao thức mạng.

- Người quản trị có thể biết được kẻ nào đang cố gắng để truy cập vào hệ thống mạng.

- Firewall hoạt động như một Proxy trung gian.

- Bảo vệ tài nguyên của hệ thống bởi các mối đe dọa bảo mật.

- Cân bằng tải: Bạn có thể sử dụng nhiều đường truyền internet cùng một lúc, việc chia tải sẽ giúp đường truyền internet ổn định hơn rất nhiều.

# Phân loại firewall

## Phân loại dựa trên nhu cầu sử dụng hệ thống

Gồm 2 loại chính: Personal Firewall và Network Firewall.

### Personal Firewall

Loại này được thiết kế để bảo vệ một máy tính trước sự truy cập trái phép từ bên ngoài. Bên cạnh đó thì Personal Firewall còn được tích hợp thêm tính năng như theo dõi các phần mềm chống virus, phần mềm chống xâm nhập để bảo vệ dữ liệu. 

Một số Personal Firewall thông dụng như: Microsoft Internet connection firewall, Symantec personal firewall, Cisco Security Agent…. Loại Firewall này thì thích hợp với cá nhân bởi vì thông thường họ chỉ cần bảo vệ máy tính của họ, thường được tích hợp sẵn trong máy tính Laptop, máy tính PC..

Personal firewall chỉ bảo vệ cho một máy duy nhất.

### Network Firewalls

Được thiết kế ra để bảo vệ các host trong mạng trước sự tấn công từ bên ngoài. Chúng ta có các Appliance-Based network Firewalls như Cisco PIX, Cisco ASA, Juniper NetScreen firewall, Nokia firewalls, Symantec’s Enterprise Firewall. Hoặc một số ví dụ về Software-Base firewalls include Check Point’s Firewall, Microsoft ISA Server, Linux-based IPTables.

Network firewall bảo vệ cho cả một hệ thống mạng máy tính.

Hệ thống Network Firewall được cấu tạo bởi các thành phần chính như sau:

- Bộ lọc Packet (Packet- Filtering Router)

- Cổng ứng dụng ( đó là Application-Level Gateway hay Proxy Server).

- Cổng mạch (Circuite Level Gateway).

![image](https://user-images.githubusercontent.com/111716161/194461126-cf1c7e34-1fed-48fb-8ae2-d3744fe9ddb5.png)
