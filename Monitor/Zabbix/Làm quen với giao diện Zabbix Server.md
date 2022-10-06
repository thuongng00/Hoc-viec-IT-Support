# Giao diện Zabbix Server

![image](https://user-images.githubusercontent.com/111716161/194026123-ee0512d8-f352-4ad5-8a41-3ac8493cdbaa.png)

Gồm các tab lớn: Monitoring, Inventory, Reports, Configuration, Administration. Trong các tab lớn có các task thành phần nhỏ. 

## 1. Tab Monitoring

![image](https://user-images.githubusercontent.com/111716161/194026829-18f4ef3a-3ae4-4879-86f4-2f1c431a110e.png)

### 1.1. Dashboard

Là giao diện hiển thị các dashboard trực quan để người quản trị nhìn trực tiếp, người quản trị có thể tạo ra rất nhiều các dashboard khác nhau, nhưng tại một tab screen chỉ có thể xem được 1 dashboard bất kỳ nào đó.

Từ Dashboard có thể nhanh chống liên kết đến các thành phần như Graphs, Screens, Map bằng cách thêm các thành phần mong muốn vào mục Favourite graphs, Favourite Screen và Favourite map.

![image](https://user-images.githubusercontent.com/111716161/194027061-f0df4732-6c73-4d30-bc27-c2b2fd386f56.png)

- Status of Zabbix: Bảng này hiển thị trạng thái của zabbix server, số lượng các host, trigger, item, số người đang đăng nhập và trạng thái của các thông số trên ở 2 cột value và Details.

![image](https://user-images.githubusercontent.com/111716161/194027294-712e80d5-72cc-40b0-bf1f-dcf51f3bd74f.png)

- System status: Hiển thị mức độ cảnh báo của từ host trong từng group.

![image](https://user-images.githubusercontent.com/111716161/194027645-c79f25f6-69d3-4295-9a73-bdc7f66ef2b9.png)

- Host availability

![image](https://user-images.githubusercontent.com/111716161/194027911-ad2df37b-afa1-4262-967c-6c385964136a.png)

- Problems: Tất cả các vấn đề xảy ra với các host trong các group thống kê theo thời gian.

![image](https://user-images.githubusercontent.com/111716161/194027462-88030955-141f-4dd7-ab85-45efed181990.png)

### 1.2. Problems

![image](https://user-images.githubusercontent.com/111716161/194028360-a2fa450c-4cb6-4798-86e8-0ba20be03909.png)

Hiển thị các vấn đề đối với từng device mà zabbix server thu thập dữ liệu về. Hỗ trợ cơ chế lọc theo ý người quản trị.

- Có thể lọc theo các tiêu chí và có thể export ra file CSV để lưu trữ lại.

![image](https://user-images.githubusercontent.com/111716161/194028571-c95deb74-2748-42ed-a9d7-ec401456aa8b.png)

- Show: Recent problems (Hiển thị vấn đề hiện tại đang gặp phải), Problems (Hiển thị các vấn đề đã gặp phải), History (Lịch sử các vấn đề đã gặp phải).

Host group, Host, Application, Trigger, Problem, Host inventory, Tags, Show hosts in maintenance... là các lựa chọn để lọc thông tin, có thể lọc theo một tiêu chí hoặc kết hợp nhiều tiêu chí.

![image](https://user-images.githubusercontent.com/111716161/194029203-f9cf61d0-c035-4f00-ae73-e8e5a5fab2e2.png)

### 1.3. Host

Tạo và quản lý các host.

![image](https://user-images.githubusercontent.com/111716161/194030164-05935125-d3bc-4950-8d14-e8621287b738.png)

### 1.4. Overview

Là sự tổng hợp thông tin về data zabbix zerver thu thập được, có thể lọc them group -> host -> Kiểu data. Gồm tringger overview và data overview.

![image](https://user-images.githubusercontent.com/111716161/194030632-d378c797-ce00-40c1-a52c-6f1b3b45d010.png)

![image](https://user-images.githubusercontent.com/111716161/194030773-72639933-f3c8-40db-9a0a-77f76e6c3840.png)

### 1.5. Latest data

Dữ liệu mới nhất mà zabbix server thu thập được.

![image](https://user-images.githubusercontent.com/111716161/194030901-382566f4-33f2-47fc-8d21-08678b66d057.png)

### 1.6. Screens

Là tập hợp các thông tin như Graphs, maps,data overview… vào chung một màn hình giám sát. Giúp người quản trị có thể lựa chọn các thông tin cần thiết hiển thị, giúp có cái nhìn tổng quát những thông tin mà người quản trọ mong muốn.

![image](https://user-images.githubusercontent.com/111716161/194031017-13047a79-4a70-423e-b595-6d92dc8ca8f5.png)

![image](https://user-images.githubusercontent.com/111716161/194031542-05129904-ea4f-453b-a69c-1b4b1da9b4a2.png)

![image](https://user-images.githubusercontent.com/111716161/194031181-8ac7cc2c-7872-4a06-9e41-f9a3f5059360.png)

### 1.7. Maps

Là thành phân cung cấp khả năng giám sát hệ thống dưới hình thức mô hình mạng. Giúp người quản trị có cái nhìn tổng quan về hệ thống sống mạng dưới dạng sơ đồ, trong trường hợp có sự cố sẽ giúp người quản trị đánh giá tầm ảnh hưởng của thiết bị gặp sự cố và đưa ra giải pháp phù hợp.

![image](https://user-images.githubusercontent.com/111716161/194031341-0fade490-e1e2-4478-b48d-7872691a37f8.png)

![image](https://user-images.githubusercontent.com/111716161/194031458-3bc5c1a6-00fc-4a04-8c13-3d80bb9bb770.png)

### 1.8. Discovery

Tính năng cho phép zabbix server tự động tìm kiếm các thiết bị được cài đặt zabbix agent đã cấu hình kết nối về zabbix server trong cùng mạng với zabbix server.

![image](https://user-images.githubusercontent.com/111716161/194031890-91929995-89ad-46ca-9b1b-4dff825b1a5e.png)

### 1.9. Services

![image](https://user-images.githubusercontent.com/111716161/194031951-b5a3714b-189f-4f25-a747-712d05eabd72.png)


## 2. Tab Configuration

![image](https://user-images.githubusercontent.com/111716161/194032340-0536b9e3-2187-43f9-ab54-de977a450b81.png)

### 2.1. Host group

Tập hợp lại các host có chung một mục đích sử dụng hoặc người quản trị tâp hợp lại để phục vụ một mục đích quản lý chung.

![image](https://user-images.githubusercontent.com/111716161/194032178-8e049831-93a7-44a3-acaa-e632e1302e74.png)

### 2.2. Templates

Đây là tập hợp các thực thể có thể áp dụng cho các Host, một Template sẽ chứa trong nó các tập lệnh để truy vấn lấy dữ liệu, hiển thị thông tin dữ liệu lấy được, thông tin tình trạng thiết bị, hiển thị và thông báo lỗi…

Trong mỗi Template, các tệp lệnh được chia thành: items, triggers, graphs, applications, screens (có từ Zabbix 2.0),low-level discovery rules (có từ Zabbix 2.0), web scenarios (có từ Zabbix 2.2). Tùy theo giám sát thiết bị, dịch vụ, ứng dụng… nào thì các thành phần này được thiết lập khác nhau.

Có thể import template tự viết vào.

![image](https://user-images.githubusercontent.com/111716161/194032503-ddfa863a-8c37-4eb4-9503-3f8e3fbdc055.png)

### 2.3. Host

Là một máy tính, server, vps, chạy các hệ điều hành khác nhau hoặc một thực thể trong hệ thống mạng như là máy in, máy chấm công, máy photo, máy camera có hỗ trợ các giao thức mà monitor zabbix cung cấp.

![image](https://user-images.githubusercontent.com/111716161/194032952-219e067d-cb42-400b-81f2-cf506f96d49a.png)

### 2.4. Maintenance

Có thể xác định thời gian bảo trì cho máy chủ và group trong Zabbix. Có hai loại Maintance - với thu thập dữ liệu và không thu thập dữ liệu.

Ví dụ server của bạn off trong khoảng thời gian này để nâng cấp sửa chữa, thì maintance sẽ được lựa chọn cấu hình để không thu thập data trong khoảng thời gian đó.

![image](https://user-images.githubusercontent.com/111716161/194033029-572b7e58-0f8a-4811-a9b3-5513bd9fd63a.png)

### 2.5. Action

Nơi cấu hình, lựa chọn các kiểu thông báo khi có sự kiện xảy ra bởi cấu hình trigger. Người dùng phải tự định nghĩa các action theo mục đích.

![image](https://user-images.githubusercontent.com/111716161/194033218-6d07162c-77c4-46c4-b671-43c6b63441aa.png)

### 2.6. Event correlation

Cho phép cấu hình tương quan giữa các sự kiến với độ chính xác vào và tùy biến linh hoạt.

![image](https://user-images.githubusercontent.com/111716161/194033371-df953fc2-a5a6-4dd2-813d-02271f280698.png)

### 2.7. Discovery

Thiết lập range IP, nếu trong range có có thiết bị nào mà cài đặt các giao thức mà Zabbix server hỗ trợ thì sẽ tự động thu thập data về.

![image](https://user-images.githubusercontent.com/111716161/194033425-00666a49-1f10-4191-a506-e27ef11e23f5.png)

![image](https://user-images.githubusercontent.com/111716161/194033484-a496c5d4-e62c-4310-9e20-941414685160.png)

## 3. Tab Administration

Chức năng của của tab Administrator là để cấu hình chung cho zabbix đối với user có quyền Admin.

![image](https://user-images.githubusercontent.com/111716161/194033646-44cb0e72-de6e-4d86-be92-8426b2278c8d.png)

### 3.1. General 

Mục này cho phép người quản trị cấu hình tùy chỉnh giao diện cho Zabbix Webinterface.

![image](https://user-images.githubusercontent.com/111716161/194035231-f7598802-81ff-4413-abe7-425d271669d7.png)

Có thể tùy chỉnh rất nhiều giao diện như :

- GUI: Cung cấp một số tùy chỉnh mặc định liên quan đến giao diện người dùng.

![image](https://user-images.githubusercontent.com/111716161/194034323-72146330-9c03-4a4a-b346-d8fb9058f265.png)

- HouseKeeping: quy định các thời gian định kì được thực hiện bởi Zabbix. Quá trình xóa thông tin hết hạn và thông tin được xóa bởi người dùng .Có thể tùy chỉnh các dữ liệu được lưu tối đa trong bao lâu trên Zabbix. Gồm các phần có thể cấu hình như Event and alerts, Services, Audit, User sessions, History, Trends.

![image](https://user-images.githubusercontent.com/111716161/194034394-51035b35-3563-4370-8268-e611e586a1ee.png)

- Images: Chứa tất cả các hình ảnh, icon, background được hiển thị trong Zabbix.

![image](https://user-images.githubusercontent.com/111716161/194034541-049e9ddf-986b-4411-9645-47bd1c92f101.png)

- Icon mapping: Phần này cho phép tạo biểu tượng bản đồ của một host với các biểu tượng nhất định. Các thông tin trong các tùy chọn đều phục vụ cho việc tạo bản đồ.

- Regular expressions: Tạo và quy ước các biểu thức chính quy.

![image](https://user-images.githubusercontent.com/111716161/194034809-1177601a-6cab-4c5f-97be-26e9a770ef45.png)

- Macros: Tạo các đoạn macro tương ứng với giá trị.

![image](https://user-images.githubusercontent.com/111716161/194034862-fbaaf0fb-3373-42a1-94cf-87e274eace0f.png)

- Value mapping: Tạo các giá trị tương ức với các mức.

![image](https://user-images.githubusercontent.com/111716161/194034946-743e3aa0-b922-451e-8733-15dd2ba1c6f7.png)

- Working time: Tham số toàn hệ thống xác định thời gian làm việc.

![image](https://user-images.githubusercontent.com/111716161/194034993-979d5b64-19fa-40c7-89d7-2f954fac0b20.png)

- Trigger severities: Cấu hình màu hiển thị đối với các mức của trigger.

![image](https://user-images.githubusercontent.com/111716161/194035047-1640c5b5-aedc-4f44-ac55-431f7091fc7c.png)

- Trigger displaying options: Mầu sắc, hiệu ứng iển thị khi có event.

![image](https://user-images.githubusercontent.com/111716161/194035100-b448dbf9-b3ef-41a2-8ce7-de638aa1d905.png)

- Other configuration parameters

![image](https://user-images.githubusercontent.com/111716161/194035143-abc84ae0-8977-4478-b4d6-4238810638c6.png)

### 3.2. Proxies

Cho phép cấu hình các Proxy trên giao diện Zabbix.

![image](https://user-images.githubusercontent.com/111716161/194035436-1a89e195-39d2-460f-95d6-d785bdb5dd54.png)

Name: Tên của Proxy.

Mode: Chế độc của Proxy (active hoặc passive).

Encryption: Mã hóa kết nối từ Zabbix Server đến Proxy.

Last seen (age): Thời gian tại thời điểm kết nối cuối cùng với Proxy.

Host count: Số Host mà Proxy quản lý.

Item count: Số lượng Item mà Proxy sử dụng.

Required performance (vps): Hiệu suất Proxy.

Host: Danh sách các host mà proxy quản lý.

### 3.3. Authentication 

Phương pháp xác thực người dùng Zabbix : Thẩm định nội bộ, LDAP và HTTP

![image](https://user-images.githubusercontent.com/111716161/194035750-c57d5673-d61b-4f59-b15d-d5b14cc7154f.png)

### 3.4. User groups

Quản lý các nhóm trong Zabbix

![image](https://user-images.githubusercontent.com/111716161/194035792-121e9d48-b71b-426d-9f39-d8ee0728a30b.png)

### 3.5. Users

Tùy chỉnh các tài khoản user cho zabbix, có thể tạo thêm các user khác với việc phân quyền tương ứng.

![image](https://user-images.githubusercontent.com/111716161/194035848-420526fd-9e20-43c3-bfc9-fd4a4fe55ba2.png)

### 3.6. Media types

Các kênh alert.

![image](https://user-images.githubusercontent.com/111716161/194035932-1c8e5d59-3142-4382-a54f-4fd4b71e7c0c.png)

### 3.7. Scripts

![image](https://user-images.githubusercontent.com/111716161/194036229-5d2098e4-3859-493f-9f75-3ab476ccc98a.png)

### 3.8. Queue

Thông tin về hàng đợi trong quá trình cập nhật dữ liệu về từ các nguồn agent.

![image](https://user-images.githubusercontent.com/111716161/194036316-9cb5d1e7-ac57-45aa-a884-1ad55495a883.png)




