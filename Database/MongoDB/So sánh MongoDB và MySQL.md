<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/190943942-08496340-144a-4ed6-9c67-37391a1f7f05.png" width=500/>
</p>

## 1. Định nghĩa

- MySQL là một hệ quản lý cơ sở dữ liệu quan hệ mã nguồn mở phổ biến (RDBMS) được phát triển, phân phối và hỗ trợ bởi Oracle Corporation. Giống như các hệ thống quan hệ khác, MySQL lưu trữ dữ liệu trong bảng và sử dụng ngôn ngữ truy vấn có cấu trúc (SQL) để truy cập cơ sở dữ liệu. Trong MySQL, bạn định nghĩa sơ đồ cơ sở dữ liệu của bạn dựa trên yêu cầu của bạn và thiết lập các quy tắc để điều chỉnh mối quan hệ giữa các trường trong bảng của bạn. Bất kỳ thay đổi nào trong lược đồ đòi hỏi một thủ tục chuyển đổi có thể làm cho cơ sở dữ liệu ngoại tuyến hoặc giảm đáng kể hiệu suất ứng dụng. 
- MongoDB là một cơ sở dữ liệu nguồn mở, không quan hệ được phát triển bởi MongoDB, Inc MongoDB lưu trữ dữ liệu dưới dạng các tài liệu trong một biểu diễn nhị phân được gọi là BSON (Binary JSON). Thông tin liên quan được lưu trữ cùng nhau để truy cập truy vấn nhanh thông qua ngôn ngữ truy vấn MongoDB. Các trường có thể khác nhau từ tài liệu này sang tài liệu khác; không cần khai báo cấu trúc của tài liệu vào hệ thống - các tài liệu tự mô tả. Nếu một lĩnh vực mới cần phải được thêm vào một tài liệu, sau đó lĩnh vực này có thể được tạo ra mà không ảnh hưởng đến tất cả các tài liệu khác trong collection, mà không cần cập nhật một danh mục hệ thống trung ương, và không cần dùng hệ thống ngoại tuyến. Theo tùy chọn, tính hợp lệ của lược đồ có thể được sử dụng để thực thi kiểm soát quản trị dữ liệu đối với mỗi collection.

| | MySQL | MongoDB |
|---|---|---|
| Viết bởi ngôn ngữ | C++, C | C++, C và Javascript |
| Kiểu | RDBMS(Hệ thống quản lý cơ sở dữ liệu quan hệ) | Hướng tài liệu |
| Các điểm chính | Table, Row, Column | Collection, Document, Field |
| License | 	GPL v2 / Giấy phép thương mại có sẵn OD | OD GNU AGPL v3.0 / Giấy phép thương mại có sẵn OD |
| Lược đồ | Strict | Dynamic |
| Scaling | Theo chiều dọc | Theo chiều ngang |
| Các tính năng chính | Tìm kiếm và đánh chỉ số full text, Hỗ trợ nhân rộng tích hợp, Trigger, SubSELECT, Truy vấn bộ nhớ đệm, Hỗ trợ SSL, Hỗ trợ Unicode, Công cụ lưu trữ khác nhau với các đặc tính hiệu suất khác nhau | Auto-sharding, Native replication, Hỗ trợ mô hình dữ liệu nhúng, Chỉ số phụ toàn diện, Hỗ trợ ngôn ngữ truy vấn phong phú, Hỗ trợ công cụ lưu trữ khác nhau |
| Sử dụng tốt nhất cho | Cấu trúc dữ liệu phù hợp với bảng và hàng, Sự phụ thuộc mạnh mẽ vào,các giao dịch nhiều hàng,Cập nhật thường xuyên và sửa đổi khối lượng lớn bản ghi, Bộ dữ liệu tương đối nhỏ | Tải ghi cao, Lược đồ không ổn định, DB của bạn được thiết lập để phát triển lớn,Dữ liệu dựa trên vị trí, HA (tính sẵn sàng cao) trong môi trường không ổn định là bắt buộc,Không có quản trị viên cơ sở dữ liệu (DBA) |

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
| Ưu điểm | Xác thực tài liệu, Công cụ lưu trữ tích hợp, Rút ngắn thời gian giữa thất bại chính và phục hồi | Hỗ trợ giao dịch Atomic, Hỗ trợ JOIN, Giải pháp Mature,Hệ thống bảo mật đặc quyền và mật khẩu |
| Nhược điểm | Không phải là lựa chọn tốt nhất cho các ứng dụng có giao dịch phức tạp, Không phải là một thay thế snap-in cho các giải pháp cũ, Giải pháp trẻ | Mở rộng quy mô, Mối quan tâm ổn định, Phát triển dựa vào cộng đồng |

## 6. MongoDB Vs. MySQL: Sử dụng khi nào?

Thật khó để nói cơ sở dữ liệu nào tốt hơn khi tất cả phụ thuộc vào ngữ cảnh mà chúng đang được khám phá. Sự thật mà nói, cả MySQL và MongoDB đều là những hệ thống quản lý hữu ích và hữu ích hoạt động hoàn toàn khác nhau. Do đó, ngay cả khi một trong những cơ sở dữ liệu là lựa chọn phù hợp nhất cho một doanh nghiệp hoặc dự án cụ thể, nó có thể không phải là giải pháp tốt nhất cho một mục đích khác. Một số công ty dựa vào cả hai hệ thống theo các nhiệm vụ riêng biệt.

Một trong số rất ít điểm chung của chúng là chúng đều là mã nguồn mở và dễ truy cập. Hơn nữa, cả hai hệ thống đều cung cấp các phiên bản thương mại với các tính năng bổ sung. Ngoài những điểm tương đồng này, cốt lõi của hiệu suất của chúng là bản chất quan hệ và không quan hệ.

**MongoDB**, một cơ sở dữ liệu tài liệu, là giải pháp phù hợp nhất cho các môi trường có dung lượng lớn, vì nó không giới hạn số lượng và loại dữ liệu mà người ta muốn lưu trữ. Nó đặc biệt có lợi cho các dịch vụ dựa trên đám mây vì khả năng mở rộng theo chiều ngang của MongoDB hoàn toàn phù hợp với tính linh hoạt của đám mây. Thêm vào đó, nó làm giảm khối lượng công việc, giảm quy mô trong một doanh nghiệp hoặc dự án, đồng thời cung cấp tính khả dụng cao và phục hồi dữ liệu nhanh chóng.

Mặc dù có nhiều lợi thế mà hệ thống này có thể có, nhưng MySQL vượt qua MongoDB ở một số khía cạnh, chẳng hạn như độ tin cậy và tính nhất quán của dữ liệu. Hơn nữa, nếu bảo mật cũng là một ưu tiên, thì MySQL thực sự là một trong những DBMS an toàn nhất.

Hơn nữa, khi loại ứng dụng yêu cầu giao dịch nhiều hàng (ví dụ, trong hệ thống kế toán và ngân hàng), cơ sở dữ liệu quan hệ là lựa chọn thích hợp nhất. Ngoài việc cung cấp sự an toàn, MySQL cũng cho phép tỷ lệ giao dịch cao. Trên thực tế, trong khi MongoDB tập trung vào việc cho phép tỷ lệ chèn cao, thì ngược lại, MySQL hỗ trợ các giao dịch ACID và tập trung vào việc cung cấp an toàn giao dịch.

Nhìn chung, MySQL rất được khuyến khích cho các doanh nghiệp hoặc dự án có lược đồ dữ liệu cố định và không có ý định mở rộng quy mô đa dạng dữ liệu, do đó yêu cầu bảo trì dễ dàng và thấp trong khi đảm bảo tính toàn vẹn và độ tin cậy của dữ liệu.

Mặt khác, MongoDB là sự lựa chọn phù hợp nhất cho các doanh nghiệp hoặc dự án đang phát triển nhưng có lược đồ dữ liệu không ổn định . Bản chất dữ liệu phi quan hệ của hệ thống này cho phép các tài liệu được sử dụng và lưu trữ tự do mà không cần cấu trúc, giúp dễ dàng cập nhật và truy xuất. MongoDB thường được sử dụng trong các dự án yêu cầu quản lý nội dung, xử lý IoT (Internet-of-Things), thực hiện phân tích thời gian thực, v.v.

Nói tóm lại, cả hai cơ sở dữ liệu sẽ mang lại hiệu suất rất hài lòng nếu được áp dụng cho bối cảnh phù hợp với nhu cầu và mong muốn của ứng dụng với các đặc điểm và tính năng của hệ thống.
