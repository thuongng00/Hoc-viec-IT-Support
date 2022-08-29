# Linux
Linux là một hệ điều hành máy tính mã nguồn mở, cách hoạt động giống như các hệ điều hành khác như: Microsoft Windows, Apple Mac OS, iOS, Google android ... Đây là một HĐH sử dụng cả giao diện GUI và command line.

Nhiệm vụ của Linux là cho phép giao tiếp giữa phần cứng và phần mềm máy tính, xử lý tiếp nhận thông tin đầu vào và trả kết quả ra màn hình, đây chính là chứ năng cơ bản nhất của một hệ điều hành.

Linux xuất hiện giữa những năm 90, nó đã từng được sử dụng phát triển cho đồng hồ, và đến nay là được đưa vào máy tính. Nó có ở khắp mọi nơi như trong điện thoại, máy tính xách tay, PC, ô tô và thậm chí trong tủ lạnh của chúng ta. Nó rất nổi tiếng trên các cộng đồng lập trình viên, cũng như những người sử dụng bình thường yêu thích sử dụng máy tính bằng command line.

Đối với Windows, nếu bạn muốn cài đặt một phần mềm nào đó thì sẽ lên trang chủ để tải về, sau đó cài đặt bằng cách sử dụng chuột để thao tác trên giao diện đồ họa GUI. Nhưng với Linux thì khác, hầu như những thao tác này đều thực hiện bằng command line, bởi trên Linux có một kho lưu trữ dữ liệu (ta gọi là repo), bạn chỉ cần chạy lệnh cài đặt là được. Đương nhiên chỉ những phần mềm nào được tích hợp trên repo đó.

Hệ điều hành là tập hợp nhiều phần mềm khác nhau, và mỗi phần mềm có một nhiệm vụ khác nhau.

Hệ điều hành Linux có những thành phần dưới đây:

![image](https://user-images.githubusercontent.com/111716161/187139312-26c2a276-5d3b-4175-afca-0cafd0d4460f.png)

### Kernel
Kernel chính là phần nhân của linux, là thành phần quan trọng nhất và có nhiệm vụ thiết lập giao tiếp giữa các phần mềm và thiết bị phần cứng. Hơn thế nữa, nó còn đảm nhận việc quản lý tài nguyên của hệ thống.

Nó có bốn nhiệm vụ chính như sau:

- Quản lý thiết bị: Một máy tính sẽ có nhiều thiết bị như CPU, RAM, card âm thanh, card đồ họa, v.v. kernel sẽ lưu trữ tất cả dữ liệu liên quan đến tất cả các thiết bị trong trình điều khiển thiết bị driver (nếu không có kernel thì sẽ không thể để điều khiển các thiết bị). Do đó kernel biết mỗi thiết bị có thể làm gì và thao tác với nó như thế nào để mang lại hiệu suất tốt nhất.
- Quản lý bộ nhớ: Một chức năng khác đó là quản lý bộ nhớ. Kernel theo dõi bộ nhớ đã sử dụng và chưa sử dụng và đảm bảo rằng các tiến trình không được sử dụng dữ liệu của nhau bằng địa chỉ bộ nhớ ảo.
- Quản lý quy trình: Kernel chỉ định đủ thời gian và ưu tiên cho các quy trình trước khi CPU xử lý cho các quy trình khác.
- Xử lý lệnh gọi hệ thống: Xử lý lệnh gọi hệ thống có nghĩa là một lập trình viên có thể viết một truy vấn hoặc yêu cầu Karnel thực hiện một tác vụ nào đó.

### System Libraries
System Libraries là những thư viện / phần mềm đặc biệt giúp truy cập vào các tính năng của Karnel. Mỗi Karnel sẽ phải được kích hoạt để thực hiện một tác vụ các ứng dụng sẽ hoàn thành những tác vụ đó.

### System Tools
Hệ điều hành Linux có một tập hợp các công cụ tiện ích, thường là các lệnh command line đơn giản. Nó là một phần mềm mà dự án GNU đã viết và xuất bản theo giấy phép mã nguồn mở của họ, nhằm giúp phần mềm cung cấp miễn phí cho tất cả mọi người.

Với sự trợ giúp của các lệnh, bạn có thể truy cập file của mình, chỉnh sửa và thao tác dữ liệu trong thư mục hoặc file của bạn, thay đổi vị trí của file hoặc bất cứ một thao tác nào khác.

### Development Tools
Với ba thành phần trên là hệ điều hành Linux có thể hoạt động được rồi đấy. Nhưng nhằm giúp các nhà phát triển có thể cập nhật hệ thống, cũng như tạo ra những công cụ khác thì Linux cho phép lập trình viên sử dụng những công cụ riêng của nó, ta gọi là toolchain.

### End User Tools
Đây chính là tập hợp những phần mềm mà người dùng cài vào máy tính để sử dụng như: Trình duyệt web, phần mềm nghe nhạc, office ...

# Lý do nên sử dụng Linux

Linux là một mã nguồn mở: Nghĩa là bạn sẽ cài đặt miễn phí và không tốn một đồng nào cả. Nếu bạn sử dụng Windows thì sẽ phải bỏ ra một khoản tiền lớn để mua key bản quyền.

Linux an toàn hơn Windows: Điều này hoàn toàn đúng, bởi Linux hỗ trợ các tùy chọn bảo mật khác nhau sẽ giúp bạn tránh khỏi vi rút, phần mềm độc hại, làm chậm máy, treo máy. Hơn nữa, nó sẽ giữ cho dữ liệu của bạn được bảo vệ. Với tính năng bảo mật này khiến nhiều nhà phát triển lựa chọn nó hơn là Windows, đương nhiên không phải nó luôn luôn an toàn, mà có chút phụ thuộc vào cách sử dụng cua mỗi người.

Linux là hệ điều hành linh hoạt và ứng dụng đa dạng: Vì nó có thể được sử dụng cho các ứng dụng máy tính để bàn, hệ thống nhúng và ứng dụng máy chủ server. Nó có thể được sử dụng từ đồng hồ đeo tay đến siêu máy tính. Nó có ở khắp mọi nơi trong điện thoại, máy tính xách tay, PC, ô tô và thậm chí trong tủ lạnh của chúng ta.

Linux ổn định: Linux ổn định hơn các hệ điều hành khác. Linux không yêu cầu phải khởi động lại hệ thống để lấy lại hiệu suất. Nó hiếm khi bị treo, điều mà ta thường thấy ở Windows.

Giao diện đồ họa + command line: Đây chính là đặc điểm rất hay trên Linux, nó vừa hỗ trợ giao diện GUI vừa hỗ trợ command line.

Cộng đồng lớn: Có rất nhiều cộng đồng riêng về Linux ra đời, bởi vì nó là một mã nguồn mở nên kiến thức chia sẻ rất phổ biến.
