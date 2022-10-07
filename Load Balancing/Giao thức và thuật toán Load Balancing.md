# Các giao thức Load Balancing có thể xử lý

![image](https://user-images.githubusercontent.com/111716161/194447878-b2f2fe4f-2890-4a4a-b3a5-2221cfafb1a4.png)

Có 4 loại giao thức chính mà quản trị Load Balancer có thể tạo quy định chuyển tiếp:

### HTTP
Dựa trên cơ chế HTTP chuẩn, HTTP Balancing đưa ra yêu cầu tác vụ. Load Balancer đặt X-Forwarded-For, X-Forwarded-Proto và tiêu đề X-Forwarded-Port cung cấp các thông tin backends về những yêu cầu ban đầu.

### HTTPS
Các chức năng tương tự HTTP Balancing. HTTPS Balancing được bổ sung mã hóa và nó được xử lý bằng 2 cách: passthrough SSL duy trì mã hóa tất cả con đường đến backend hoặc: chấm dứt SSL, đặt gánh nặng giải mã vào load balancer và gửi lưu lượng được mã hóa đến backend.

### TCP
Trong một số trường hợp khi ứng dụng không sử dụng giao thức HTTP hoặc HTTPS, TCP sẽ là một giải pháp để cân bằng lưu lượng. Cụ thể, khi có một lượng truy cập vào một cụm cơ sở dữ liệu, TCP sẽ giúp lan truyền lưu lượng trên tất cả các máy chủ

### UDP
Trong thời gian gần đây, Load Balancer đã bổ sung thêm hỗ trợ cho cân bằng tải giao thức internet lõi như DNS và syslogd sử dụng UDP.

Các quy tắc chuyển tiếp sẽ xác định loại giao thức và cổng vào Load Balancer để di chuyển đến các giao thức. Cổng Load Balancer lúc này được sử dụng để định tuyến lưu lượng trên backend.

# Các thuật toán Load Balancing

![image](https://user-images.githubusercontent.com/111716161/194448067-a52566eb-8025-4b36-a02a-fd2d88e1c181.png)

Tùy thuộc công nghệ Load Balancing mà các thuật toán khác nhau sẽ được sử dụng để định tình trạng của máy chủ có hoạt động hay không. Có các loại thuật toán thường thấy là:

- Round Robin
- Weighted Round Robin
- Dynamic Round Robin
- Fastest
- Least Connections

### Thuật toán Load Balancing – Round Robin

Round Robin là thuật toán lựa chọn các máy chủ theo trình tự. Theo đó, Load Balancer sẽ bắt đầu đi từ máy chủ số 1 trong danh sách của nó ứng với yêu cầu đầu tiên. Tiếp đó, nó sẽ di chuyển dần xuống trong danh sách theo thứ tự và bắt đầu lại ở đầu trang khi đến máy chủ cuối cùng.

Khi có 2 yêu cầu liên tục từ phía người dùng sẽ có thể được gửi vào 2 server khác nhau. Điều này làm tốn thời gian tạo thêm kết nối với server thứ 2 trong khi đó server thứ nhất cũng có thể trả lời được thông tin mà người dùng đang cần. Để giải quyết điều này, round robin thường được cài đặt cùng với các phương pháp duy trì session như sử dụng cookie.

### Thuật toán Load Balancing – Weighted Round Robin 

Tương tự như kỹ thuật Round Robin nhưng WRR còn có khả năng xử lý theo cấu hình của từng server đích. Mỗi máy chủ được đánh giá bằng một số nguyên (giá trị trọng số Weight – mặc định giá trị là 1). Một server có khả năng xử lý gấp đôi server khác sẽ được đánh số lớn hơn và nhận được số request gấp đôi từ bộ cân bằng tải.

Weighted Round Robin gây mất cân bằng tải động nếu như tải của các request liên tục thay đổi trong một khoảng thời gian rộng.

### Thuật toán Load Balancing – Dynamic Round Robin (DRR)

Thuật toán DRR hoạt động gần giống với thuật toán WRR. Điểm khác biệt là trọng số ở đây dựa trên sự kiểm tra server một cách liên tục. Do đó trọng số liên tục thay đổi.

Việc chọn server sẽ dựa trên rất nhiều khía cạnh trong việc phân tích hiệu năng của server trên thời gia thực. Ví dụ: số kết nối hiện đang có trên các server hoặc server trả lời nhanh nhất, …

Thuật toán này thường không được cài đặt trong các bộ cân bằng tài đơn giản. Nó thường được sử dụng trong các sản phẩm cân bằng tải của F5 Network.

### Thuật toán Load Balancing – Fastest 

Đây là thuật toán dựa trên tính toán thời gian đáp ứng của mỗi server (response time). Thuật toán này sẽ chọn server nào có thời gian đáp ứng nhanh nhất. Thời gian đáp ứng được xác định bởi khoảng thời gian giữa thời điểm gửi một gói tin đến server và thời điểm nhận được gói tin trả lời.

Việc gửi và nhận này sẽ được bộ cân bằng tải đảm nhiệm. Dựa trên thời gian đáp ứng, bộ cân bằng tải sẽ biết chuyển yêu cầu tiếp theo đến server nào.

Thuật toán Fastest thường được dùng khi các server ở các vị trí địa lý khác nhau. Như vậy người dùng ở gần server nào thì thời gian đáp ứng của server đó sẽ nhanh nhất. Cuối cùng server đó sẽ được chọn để phục vụ.

### Thuật toán Load Balancing – Least Connections

Các request sẽ được chuyển vào server có ít kết nối nhất trong hệ thống. Thuật toán này được coi như thuật toán động, vì nó phải đếm số kết nối đang hoạt động của server.

Least Connections có khả năng hoạt động tốt. Ngay cả khi tải của các kết nối biến thiên trong một khoảng lớn. Do đó nếu sử dụng RC sẽ khắc phục được nhược điểm của Round Robin.
