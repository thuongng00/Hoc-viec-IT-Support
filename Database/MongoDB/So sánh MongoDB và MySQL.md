<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/190942151-27119286-e9bc-44be-b864-81b0f0b286e6.png" width=500/>
</p>

## 1. Định nghĩa

- MySQL là một hệ quản lý cơ sở dữ liệu quan hệ mã nguồn mở phổ biến (RDBMS) được phát triển, phân phối và hỗ trợ bởi Oracle Corporation. Giống như các hệ thống quan hệ khác, MySQL lưu trữ dữ liệu trong bảng và sử dụng ngôn ngữ truy vấn có cấu trúc (SQL) để truy cập cơ sở dữ liệu. Trong MySQL, bạn định nghĩa sơ đồ cơ sở dữ liệu của bạn dựa trên yêu cầu của bạn và thiết lập các quy tắc để điều chỉnh mối quan hệ giữa các trường trong bảng của bạn. Bất kỳ thay đổi nào trong lược đồ đòi hỏi một thủ tục chuyển đổi có thể làm cho cơ sở dữ liệu ngoại tuyến hoặc giảm đáng kể hiệu suất ứng dụng. 
- MongoDB là một cơ sở dữ liệu nguồn mở, không quan hệ được phát triển bởi MongoDB, Inc MongoDB lưu trữ dữ liệu dưới dạng các tài liệu trong một biểu diễn nhị phân được gọi là BSON (Binary JSON). Thông tin liên quan được lưu trữ cùng nhau để truy cập truy vấn nhanh thông qua ngôn ngữ truy vấn MongoDB. Các trường có thể khác nhau từ tài liệu này sang tài liệu khác; không cần khai báo cấu trúc của tài liệu vào hệ thống - các tài liệu tự mô tả. Nếu một lĩnh vực mới cần phải được thêm vào một tài liệu, sau đó lĩnh vực này có thể được tạo ra mà không ảnh hưởng đến tất cả các tài liệu khác trong collection, mà không cần cập nhật một danh mục hệ thống trung ương, và không cần dùng hệ thống ngoại tuyến. Theo tùy chọn, tính hợp lệ của lược đồ có thể được sử dụng để thực thi kiểm soát quản trị dữ liệu đối với mỗi collection.

## 2. Thuật ngữ và khái niệm

Nhiều khái niệm trong MySQL có các khái niệm tương tự gần nhau trong MongoDB. Bảng dưới đây phác thảo các khái niệm chung trên MySQL và MongoDB.

| MySQL	| MongoDB |
|---|---|
| ACID | Transactions	ACID Transactions |
| Table	| Collection |
| Row	| Document |
| Column	| Field |
| Secondary Index |	Secondary Index | 
| JOINs	| Embedded documents, $lookup & $graphLookup |
| GROUP_BY	| Aggregation Pipeline |

## 3. Tính năng

Giống như MySQL, MongoDB cung cấp nhiều tính năng và chức năng vượt xa những tính năng được cung cấp bởi các kho dữ liệu NoSQL đơn giản. MongoDB có một ngôn ngữ truy vấn phong phú, các chỉ mục phụ có chức năng cao (bao gồm tìm kiếm văn bản và không gian địa lý), một khung kết hợp mạnh mẽ để phân tích dữ liệu, tìm kiếm nhiều mặt, xử lý biểu đồ và hơn thế nữa. Với MongoDB bạn cũng có thể sử dụng các tính năng này trên các loại dữ liệu đa dạng hơn là cơ sở dữ liệu quan hệ và bạn có thể thực hiện nó theo quy mô.

| | MongoDB | MySQL |
|---|---|---|
| Open source | có | có |
| ACID transaction | có | có |
| Mô hình dữ liệu linh hoạt và phong phú | có | không |
| Quản trị Schema | có | có |
| Kết hợp biểu cảm, tìm kiếm theo từng khía cạnh, truy vấn biểu đồ, tổng hợp mạnh mẽ | có | có |
| Trình điều khiển ngôn ngữ | có | không |
| Chia tỷ lệ theo chiều ngang với các điều khiển vị trí dữ liệu | có | không |
| Analytics and BI ready | có | có |
| Bảo mật cấp doanh nghiệp và các công cụ quản lý | có | có |
| Cơ sở dữ liệu như một dịch vụ trên tất cả các đám mây chính | có | có |

## 4. Ngôn ngữ truy vấn

Cả MySQL và MongoDB có một ngôn ngữ truy vấn phong phú. Một danh sách đầy đủ các báo cáo có thể được tìm thấy trong tài liệu MongoDB.

| MySql	| MongoDB | 
|---|---|
| INSERT INTO users (user_id, age, status)VALUES ('bcd001', 45, 'A') | db.users.insert({ user_id: 'bcd001', age: 45, status: 'A'}) | 
| SELECT * FROM users	| db.users.find() | 
| UPDATE users SET status = 'C' WHERE age > 25	| db.users.update( { age: { $gt: 25 } }, { $set: { status: 'C' } }, { multi: true }) | 

## 5. Ưu và nhược điểm

So sánh hiệu năng MongoDB và MySQL là khó khăn, vì cả hai hệ thống quản lý đều cực kỳ hữu ích và sự khác biệt cốt lõi làm nền tảng cho các hoạt động cơ bản và cách tiếp cận ban đầu của chúng. Tuy nhiên, MongoDB vs MySQL là một đối số nóng đang diễn ra trong một thời gian: cơ sở dữ liệu quan hệ trưởng thành chống lại một hệ thống phi quan hệ trẻ. Cả hai đều là nguồn mở và dễ dàng có sẵn, cũng như cả hai hệ thống cung cấp các phiên bản thương mại với hàng tấn các tính năng bổ sung.

| | MongoDB | MySQL | 
|---|---|---|
| Ưu điểm | Xác thực tài liệu,Công cụ lưu trữ tích hợp,Rút ngắn thời gian giữa thất bại chính và phục hồi | Hỗ trợ giao dịch Atomic, Hỗ trợ JOIN, Giải pháp Mature,Hệ thống bảo mật đặc quyền và mật khẩu |
| Nhược điểm | Không phải là lựa chọn tốt nhất cho các ứng dụng có giao dịch phức tạp, Không phải là một thay thế snap-in cho các giải pháp cũ, Giải pháp trẻ | Mở rộng quy mô, Mối quan tâm ổn định, Phát triển dựa vào cộng đồng |
