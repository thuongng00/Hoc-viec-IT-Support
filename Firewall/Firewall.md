# Tường lửa

Tường lửa hay còn được gọi với cái tên là FireWall thuật ngữ trong chuyên ngành mạng máy tính, nói nôm na có thể gọi là bức tường lửa một hệ thống an ninh mạng, bảo mật an toàn thông tin mạng.

Tường lửa tồn tại ở 2 loại phần cứng và phần mềm được tích hợp vào bên trong hệ thống và nó hoạt động như một rào chắn phân cách giữa truy cập an toàn và truy cập không an toàn, chống lại truy cập trái phép, ngăn chặn virus… đảm bảo thông tin nội bộ được an toàn không bị truy cập xấu đánh cắp.

<img src="https://user-images.githubusercontent.com/111716161/194462030-6928daa4-3beb-42ad-a831-ee698bab6901.png" width=500/>

# Vai trò của firewall

![image](https://user-images.githubusercontent.com/111716161/194461931-50a1a403-9bfd-48f5-9c7c-0e006926dbe7.png)

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

### 1. Personal Firewall

Loại này được thiết kế để bảo vệ một máy tính trước sự truy cập trái phép từ bên ngoài. Bên cạnh đó thì Personal Firewall còn được tích hợp thêm tính năng như theo dõi các phần mềm chống virus, phần mềm chống xâm nhập để bảo vệ dữ liệu. 

Một số Personal Firewall thông dụng như: Microsoft Internet connection firewall, Symantec personal firewall, Cisco Security Agent…. Loại Firewall này thì thích hợp với cá nhân bởi vì thông thường họ chỉ cần bảo vệ máy tính của họ, thường được tích hợp sẵn trong máy tính Laptop, máy tính PC..

Personal firewall chỉ bảo vệ cho một máy duy nhất.

### 2. Network Firewalls

Được thiết kế ra để bảo vệ các host trong mạng trước sự tấn công từ bên ngoài. Chúng ta có các Appliance-Based network Firewalls như Cisco PIX, Cisco ASA, Juniper NetScreen firewall, Nokia firewalls, Symantec’s Enterprise Firewall. Hoặc một số ví dụ về Software-Base firewalls include Check Point’s Firewall, Microsoft ISA Server, Linux-based IPTables.

Network firewall bảo vệ cho cả một hệ thống mạng máy tính.

Hệ thống Network Firewall được cấu tạo bởi các thành phần chính như sau:

- Bộ lọc Packet (Packet- Filtering Router)

- Cổng ứng dụng ( đó là Application-Level Gateway hay Proxy Server).

- Cổng mạch (Circuite Level Gateway).

![image](https://user-images.githubusercontent.com/111716161/194461126-cf1c7e34-1fed-48fb-8ae2-d3744fe9ddb5.png)

## Phân loại dựa vào phương thức hoạt động và tính năng 

Gồm 5 loại: bộ lọc gói, cổng vòng (circuit gateway), cổng ứng dụng (application-level gateway), tường lửa kiểm tra trạng thái và tường lửa thế hệ tiếp theo.

### 1. Bộ lọc gói
Tường lửa ban đầu chỉ đọc dữ liệu tiêu đề gói, như địa chỉ nguồn và địa chỉ đích. Một hành động sau đó có thể được thực hiện dựa trên thông tin thu được. Điều này hiệu quả và nhanh chóng nhưng có thể dễ bị tấn công theo một số cách.

Ví dụ, các cuộc tấn công giả mạo có thể rất hiệu quả đối với bộ lọc gói. Các phiên bản nâng cao của tường lửa lọc gói giữ dữ liệu về các gói trong bộ nhớ và có thể thay đổi hành vi của chúng dựa trên những sự kiện mạng. Chúng tương ứng được gọi là tường lửa "trạng thái" và "động".

### 2. Cổng vòng (circuit gateway)
Cổng vòng không chỉ xử lý dữ liệu tiêu đề gói. Chúng cũng cố gắng đảm bảo rằng một gói chuyển tiếp kết nối là hợp lệ. Để làm điều này, cổng vòng chú ý đến dữ liệu gói và tìm kiếm các thay đổi, chẳng hạn như địa chỉ IP nguồn bất thường hoặc cổng đích. Nếu một kết nối được xác định là không hợp lệ, nó có thể bị đóng. Các tường lửa này cũng tự động từ chối thông tin không được người dùng yêu cầu cụ thể bên trong tường lửa.

### 3. Cổng ứng dụng (ALG)
Những tường lửa này có cùng các thuộc tính giống như cổng vòng. Tuy nhiên, chúng nghiên cứu sâu hơn về thông tin được gửi qua tường lửa và xem nó liên quan như thế nào đến các ứng dụng, dịch vụ và trang web cụ thể. Ví dụ, một cổng ứng dụng có thể xem xét các gói mang lưu lượng truy cập web và xác định lưu lượng truy cập đến từ những trang nào. Tường lửa sau đó có thể chặn dữ liệu từ các trang web nhất định nếu người quản trị muốn.

### 4. Tường lửa kiểm tra trạng thái
Tường lửa kiểm tra trạng thái giám sát trạng thái của kết nối mạng đang hoạt động và lưu lượng truy cập qua một mạng cụ thể. Nó cũng phân tích các gói dữ liệu đến, nguồn, địa chỉ IP và cổng của chúng để tìm các mối đe dọa và rủi ro trên không gian mạng

### 5. Tường lửa thế hệ tiếp theo (NGFW)
Loại tường lửa mới nhất, tường lửa thế hệ tiếp theo, kết hợp tất cả các tính năng của những loại tường lửa trước đó để tạo ra một tường lửa toàn diện giám sát tất cả lưu lượng mạng và bảo vệ khỏi những cuộc tấn công bên trong và bên ngoài.

# Những tùy chọn triển khai firewall

### Tường lửa có trạng thái (Stateful firewall)
Khi tường lửa được tạo ra lần đầu tiên, chúng không có trạng thái, nghĩa là phần cứng mà lưu lượng truy cập đi qua trong khi được kiểm tra sẽ theo dõi từng gói lưu lượng mạng riêng và chặn hoặc cho phép nó.

Bắt đầu từ giữa đến cuối những năm 1990, những tiến bộ đầu tiên về tường lửa đã được ra đời. Tường lửa có trạng thái kiểm tra lưu lượng truy cập, liên quan đến trạng thái hoạt động và đặc điểm kết nối mạng để cung cấp tường lửa toàn diện hơn. Việc duy trì trạng thái này cho phép tường lửa cho lưu lượng nhất định truy cập đến người dùng cụ thể trong khi chặn lượng truy cập tương tự đến người dùng khác.

### Tường lửa thế hệ tiếp theo (Next-generation firewalls - NGFW)
Qua nhiều năm tường lửa đã bổ sung thêm vô số tính năng mới, bao gồm phân tích sâu các gói (Deep Packet Inspection - DPI), phát hiện xâm nhập, ngăn và kiểm tra lưu lượng được mã hóa. Tường lửa thế hệ tiếp theo đề cập đến tường lửa được tích hợp nhưng tính năng tiên tiến này.

### Tường lửa dựa trên proxy (Proxy-based firewall)
Các tường lửa này hoạt động như một cổng nối giữa những người dùng cuối yêu cầu dữ liệu và nguồn của dữ liệu đó. Tất cả lưu lượng truy cập được lọc qua proxy này trước khi được chuyển cho người dùng cuối. Điều này nhằm bảo vệ máy khách khỏi tiếp xúc với các mối đe dọa bằng cách che giấu danh tính của người yêu cầu thông tin ban đầu.

### Tường lửa ứng dụng web (Web application firewall - WAF)
Các tường lửa được sử dụng cho các ứng dụng cụ thể thay vì được đặt trên một điểm vào hoặc ra của một mạng lưới rộng hơn. Trong khi các tường lửa dựa trên proxy thường bảo vệ máy khách người dùng cuối, thì tường lửa ứng dụng web bảo vệ máy chủ ứng dụng.

### Phần cứng tường lửa
Phần cứng tường lửa thường là một máy chủ đơn giản có thể hoạt động như một router lọc lưu lượng truy cập và chạy phần mềm tường lửa. Những thiết bị này được đặt ở trong mạng công ty, giữa router và điểm kết nối của nhà cung cấp dịch vụ Internet. Một doanh nghiệp có thể triển khai hàng chục tường lửa vật lý trong một trung tâm dữ liệu. Người dùng cần xác định dung lượng thông qua mà họ cần tường lửa hỗ trợ dựa trên kích thước cơ sở người dùng và tốc độ kết nối Internet.

### Phần mềm tường lửa
Thông thường người dùng cuối triển khai nhiều điểm cuối phần cứng tường lửa và hệ thống phần mềm tường lửa trung tâm để quản lý việc triển khai. Hệ thống trung tâm này là nơi các chính sách và tính năng được cấu hình, nơi có thể thực hiện phân tích và phản hồi lại các mối đe dọa.

### Kiểm tra trạng thái
Đây là chức năng tường lửa cơ bản trong đó thiết bị chặn lưu lượng truy cập không mong muốn đã biết.

### Diệt virus
Nhờ vào các bản cập nhật các mối đe dọa mới nhất mà tường lửa có thể phát hiện virus, lỗ hổng đã biết trong lưu lượng mạng, từ đó bảo vệ chúng khỏi những mối nguy hại này.

### Hệ thống phòng chống xâm nhập (Intrusion Prevention Systems - IPS)
Lớp bảo mật này có thể được triển khai như một sản phẩm độc lập hoặc được tích hợp vào tường lửa thế hệ tiếp theo. Trong khi công nghệ tường lửa cơ bản xác định và chặn các loại lưu lượng mạng nhất định, hệ thống IPS sử dụng nhiều biện pháp bảo mật chi tiết hơn như truy tìm chữ ký, phát hiện bất thường để ngăn chặn các mối đe dọa không mong muốn xâm nhập vào mạng công ty.

### Phân tích sâu các gói (DPI)
DPI có thể là một phần hoặc được sử dụng kết hợp với hệ thống IPS, nhưng nó trở thành một tính năng quan trọng của tường lửa thế hệ tiếp theo vì khả năng phân tích lưu lượng truy cập chi tiết, đặc biệt là các tiêu đề của các gói và dữ liệu lưu lượng. DPI cũng có thể được sử dụng để theo dõi lưu lượng gửi đi để đảm bảo thông tin nhạy cảm không rời khỏi mạng công ty, một công nghệ được gọi là ngăn chặn mất dữ liệu (Data Loss Prevention - DLP).

### Kiểm tra SSL
Kiểm tra tầng ổ bảo mật (SSL) được sử dụng để kiểm tra lưu lượng được mã hóa xem có các mối đe dọa không. Khi ngày càng nhiều lưu lượng được mã hóa, kiểm tra SSL trở thành một phần quan trọng của công nghệ DPI đang được triển khai trong tường lửa thế hệ mới. Kiểm tra SSL hoạt động như một buffer giải mã hóa lưu lượng trước khi nó được chuyển đến địa điểm cuối để kiểm tra.

### Sandboxing
Sandboxing là một trong những tính năng mới được triển khai trong tường lửa thế hệ tiếp theo, đề cập đến khả năng của tường lửa để nhận lưu lượng hoặc mã không xác định nhất định và chạy nó trong môi trường thử nghiệm để xác định xem nó có vấn đề gì hay không.
