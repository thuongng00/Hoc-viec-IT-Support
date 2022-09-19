[NoSQL](#nosql)

[So sánh SQL và NoSQL](#sosanh)

<a name="nosql"></a>
# NOSQL

![image](https://user-images.githubusercontent.com/111716161/190938721-a4be036a-b954-4352-a468-84ec6102e7d4.png)

NoSQL là một dạng cơ sở dữ liệu mã nguồn mở và được viết tắt bởi Non-Relational SQL hay có nơi thường gọi là Not-Only SQL.

NoSQL được phát triển trên Javascript Framework với kiểu dữ liệu là JSON và dạng dữ liệu theo kiểu key và value.

NoSQL ra đời như là một mảnh vá cho những khuyết điểm và thiếu sót cũng như hạn chế của mô hình dữ liệu quan hệ RDBMS (Relational Database Management System - Hệ quản trị cơ sở dữ liệu quan hệ) về tốc độ, tính năng, khả năng mở rộng...

Với NoSQL bạn có thể mở rộng dữ liệu mà không lo tới những việc như tạo khóa ngoại, khóa chính, kiểm tra ràng buộc,...

NoSQL bỏ qua tính toàn vẹn của dữ liệu và transaction để đổi lấy hiệu suất nhanh và khả năng mở rộng.

NoSQL được sử dụng ở rất nhiều công ty, tập đoàn lớn, ví dụ như Facebook sử dụng Cassnadra, do Facebook phát triển, Google phát triển và sử dụng BigTable,...


# So sánh SQL và NoSQL

![image](https://user-images.githubusercontent.com/111716161/190938736-31f17f36-2a07-4595-8e13-4bf753b8be3a.png)

| | SQL | NoSQL |
|---|---|---|
| Định nghĩa | Cơ sở dữ liệu SQL chủ yếu được gọi là RDBMS hoặ cơ sở dữ liệu quan hệ | Cơ sở dữ liệu NoSQL chủ yếu được gọi là cơ sở dữ liệu không liên quan hoặc phân tán | Cơ sở dữ liệu NoSQL chủ yếu được gọi là cơ sở dữ liệu không liên quan hoặc phân tán |
| Design for | RDBMS truyền thống sử dụng cú pháp và truy vấn SQL để phân tích và lấy dữ liệu để có thêm thông tin chi tiết. Chúng được sử dụng cho các hệ thống OLAP | Hệ thống cơ sở dữ liệu NoSQL bao gồm nhiều loại công nghệ cơ sở dữ liệu khác nhau. Các cơ sở dữ liệu này được phát triển để đáp ứng nhu cầu trình bày cho sự phát triển của ứng dụng hiện đại |
| Ngôn ngữ Query | Structured query language (SQL) | Không có ngôn ngữ query |
| Type | SQL databases là cơ sở dữ liệu dựa trên bảng | NoSQL databases có thể dựa trên tài liệu, cặp khóa-giá trị, cơ sở dữ liệu biểu đồ |
| Schema | SQL databases có lược đồ được xác định trước | NoSQL databases sử dụng lược đồ động cho dữ liệu phi cấu trúc |
| Khả năng mở rộng | SQL databases có thể mở rộng theo chiều dọc | NoSQL databases có thể mở rộng theo chiều ngang |
| Ví dụ | Oracle, Postgres, and MS-SQL | MongoDB, Redis, , Neo4j, Cassandra, Hbase |
| Phù hợp cho | Đây là 1 lựa chọn lý tưởng cho môi trường truy vấn phức tạp | Không phù hợp với truy vấn phức tạp | 
| Lưu trữ dữ liệu phân cấp | SQL databases không thích hợp cho việc lưu trữ dữ liệu phân cấp | Phù hợp hơn cho kho lưu trữ dữ liệu phân cấp vì nó hỗ trợ phương thức cặp khóa-giá trị |
| Variations | Một loại có biến thể nhỏ | Nhiều loại khác nhau bao gồm các kho khóa-giá trị, cơ sở dữ liệu tài liệu và cơ sở dữ liệu đồ thị |
| Năm phát triển | Nó được phát triển vào những năm 1970 để giải quyết các vấn đề với lưu trữ tệp phẳng | Được phát triển vào cuối những năm 2000 để khắc phục các vấn đề và hạn chế của SQL databases |
| Open-source | Một sự kết hợp của mã nguồn mở như Postgres & MySQL, và thương mại như Oracle Database | Open-source |
| Tính nhất quán | Nó phải được cấu hình cho sự nhất quán chặt chẽ | Nó phụ thuộc vào DBMS như một số cung cấp tính nhất quán mạnh mẽ như MongoDB, trong khi những người khác cung cấp chỉ cung cấp sự nhất quán cuối cùng, như Cassandra |
| Được sử dụng tốt nhất cho | RDBMS database là tùy chọn thích hợp để giải quyết các vấn đề về ACID | NoSQL được sử dụng tốt nhất để giải quyết các vấn đề về tính khả dụng của dữ liệu | 
| Tầm quan trọng | Nó nên được sử dụng khi hiệu lực dữ liệu là siêu quan trọng | Sử dụng khi nó quan trọng hơn để có dữ liệu nhanh hơn dữ liệu chính xác |
| Lựa chọn tốt nhất | Khi bạn cần hỗ trợ truy vấn động | Sử dụng khi bạn cần mở rộng quy mô dựa trên yêu cầu thay đổi |
| Hardware | 	Specialized DB hardware (Oracle Exadata, etc.) | Commodity hardware |
| Network | Highly available network (Infiniband, Fabric Path, etc.) | Commodity network (Ethernet, etc.) |
| Loại lưu trữ | Highly Available Storage (SAN, RAID, etc.) | Commodity drives storage (standard HDDs, JBOD) |
| Tính năng tốt nhất | Hỗ trợ đa nền tảng, Bảo mật và miễn phí | Dễ sử dụng, hiệu suất cao và công cụ linh hoạt | 
| Mô hình ACID và BASE | ACID (Atomicity, nhất quán, cách ly và độ bền) là một chuẩn cho RDBMS | Cơ bản (Về cơ bản có sẵn, trạng thái mềm, phù hợp cuối cùng) là một mô hình của nhiều hệ thống NoSQL |
| Performance | SQL hoạt động tốt và nhanh thì việc desgin tốt là cực kì quan trọng và ngược lại | Nhanh hơn SQL NoSQL thì denormalized cho phép bạn lấy được tất cả thông tin về một item cụ thể với các codition mà không cần JOIN liên quan hoặc truy vấn SQL phức tạp | 
| Kết luận | Dự án đã có yêu cầu dữ liệu rõ ràng xác định quan hệ logic có thể được xác định trước | Phù hợp với những dự án yêu cầu dữ liệu không liên quan, khó xác định, đơn giản mềm dẻo khi đang phát triển |

### Khi nào sử dụng SQL?
- SQL là ngôn ngữ đơn giản nhất được sử dụng để giao tiếp với RDBMS.
- Phân tích các phiên bản liên quan đến hành vi và tùy chỉnh.
- Tạp trang tổng quan tùy chỉnh.
- Cho phép lưu trữ và lấy dữ liệu từ cơ sở dữ liệu một cách nhanh chóng. 
- Được ưu tiên khi muốn sử dụng các phép nối và thực hiện các truy vấn phức tạp.

### Khi nào sử dụng NoSQL?
- Khi không cần hỗ trợ ACID.
- Khi mô hình RDBMS truyền thống không đủ. 
- Dữ liệu cần lược đồ linh hoạt.
- Csc ràng buộc và logic xác thực không bắt buộ cphari được thực hiện trong cơ sở dữ liệu. 
- Ghi nhật ký dữ liệu từ các nguồn được phân phối.
- Nó nên được sử dụng để lưu trữ dữ liệu tạm thời như giỏ mua hàng, danh sách mong muốn và dữ liệu phiên. 

### Tổng kết

- Ngôn ngữ truy vấn có cấu trúc (SQL) được phát âm là "S-Q-L" hoặc là "See-Quel" là ngôn ngữ chuẩn
- NoSQL là một DMS không quan hệ, không yêu cầu một lược đồ cố định, tránh tham gia và dễ dàng mở rộng
- Cơ sở dữ liệu SQL chủ yếu được gọi là RDBMS hoặc Cơ sở dữ liệu quan hệ
- Cơ sở dữ liệu NoSQL chủ yếu được gọi là cơ sở dữ liệu không liên quan hoặc phân tán
- Cơ sở dữ liệu SQL là cơ sở dữ liệu dựa trên bảng
- Cơ sở dữ liệu NoSQL có thể dựa trên tài liệu, cặp khóa-giá trị, cơ sở dữ liệu biểu đồ
- SQL nên được sử dụng để giao tiếp với RDBMS
- NOSQL nên được sử dụng khi mô hình RDBMS truyền thống không đủ
