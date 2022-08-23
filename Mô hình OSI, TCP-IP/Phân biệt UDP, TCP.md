### TCP là gì?
Transmission Control Protocol (TCP) là giao thức điều khiển truyền dữ liệu hướng kết nối, có nghĩa là một khi kết nối đã được thiết lập, dữ liệu có thể được truyền theo hai hướng. TCP có các hệ thống tích hợp để kiểm tra lỗi và đảm bảo dữ liệu sẽ được phân phối theo thứ tự được gửi, khiến nó trở thành giao thức hoàn hảo để truyền thông tin như ảnh tĩnh, tệp dữ liệu và trang web.
  
### UDP là gì?
User Datagram Protocol (UDP) là một giao thức Internet không kết nối, đơn giản hơn, trong đó dịch vụ kiểm tra lỗi và khôi phục không bắt buộc. Với UDP, không có chi phí để mở kết nối, duy trì kết nối hoặc ngắt kết nối; dữ liệu liên tục được gửi đến người nhận, cho dù họ có nhận được hay không. 

### Sự khác biệt giữa TCP và UDP là gì?

TCP là một giao thức hướng kết nối, trong khi UDP là một giao thức không kết nối. Sự khác biệt chính giữa TCP và UDP là tốc độ, vì TCP tương đối chậm hơn UDP. Nhìn chung, UDP là một giao thức nhanh hơn, đơn giản hơn và hiệu quả hơn nhiều, tuy nhiên, việc truyền lại các gói dữ liệu bị mất chỉ có thể thực hiện được với TCP. 

Một sự khác biệt đáng chú ý khác giữa TCP và UDP là TCP cung cấp phân phối dữ liệu theo thứ tự từ người dùng đến máy chủ (và ngược lại), trong khi UDP không dành riêng cho truyền thông end-to-end, cũng như không kiểm tra mức độ sẵn sàng của người nhận (yêu cầu ít chi phí hơn và chiếm ít không gian hơn). 

| Đặc tính | TCP | UDP |
|----------|-----|-----|
| Tình trạng kết nối| Yêu cầu kết nối được thiết lập để truyền dữ liệu (Kết nối phải được đóng khi quá trình truyền hoàn tất) | Giao thức không kết nối không có yêu cầu để mở, duy trì hoặc chấm dứt kết nối |
| Giải trình tự dữ liệu | Có thể trình tự | Không thể trình tự |
| Dữ liệu đảm bảo | Có thể đảm bảo cung cấp dữ liệu đến bộ định tuyến đích | Không thể đảm bảo cung cấp dữ liệu đến đích |
| Truyền lại dữ liệu | Có thể truyền lại các gói bị mất | Không truyền lại các gói bị mất |
| Kiểm tra lỗi | Kiểm tra lỗi rộng rãi và xác nhận dữ liệu | Cơ chế kiểm tra lỗi cơ bản sử dụng tổng kiểm tra |
| Phương thức chuyển | Dữ liệu được đọc dưới dạng một luồng byte; thông điệp được truyền đến  ranh giới phân đoạn | Các gói UDP có ranh giới xác định; được gửi riêng lẻ và được kiểm tra tính toàn vẹn khi đến |
| Tốc độ | Chậm hơn UDP | Nhanh hơn TCP |
| Broadcasting | Không hỗ trợ broadcasting | Có hỗ trợ broadcasting |
| Nên sử dụng cho | Được sử dụng bởi HTTPS, HTTP, SMTP, POP, FTP, v.v | Hội nghị truyền hình, phát trực tuyến, DNS, VoIP, v.v. | 
