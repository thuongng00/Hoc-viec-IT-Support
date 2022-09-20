# SQL Server và MySQL

<img src="https://user-images.githubusercontent.com/111716161/191230052-e1a345d4-c639-47c4-a31b-13a2d218a51a.png" width=600/>

## 1. SQL Server

SQL Server, còn được gọi là Microsoft SQL Server (MSSQL), đã tồn tại lâu hơn MySQL rất nhiều. SQL Server được phát triển bởi Microsoft vào những năm 80. Kể từ đó, nó đã trở thành nền tảng dành cho các doanh nghiệp quy mô lớn do khả năng mở rộng và độ tin cậy của nó.

SQL Server được xây dựng dựa trên SQL, một ngôn ngữ lập trình tiêu chuẩn để tương tác với các cơ sở dữ liệu quan hệ. Máy chủ SQL được liên kết với Transact-SQL hoặc T-SQL.

Microsoft cung cấp các công cụ và dịch vụ để quản lý dữ liệu. Để quản lý dữ liệu, chúng ta có SQL Server Integration Services (SSIS) và Data Quality Services. Để phân tích dữ liệu, chúng ta có SQL Server Reporting Services (SSRS) và SQL Server Analysis Services (SSAS).

SQL Server được lập trình viên sử dung khi dùng với .NET, đối trọng của PHP và MySQL. Cả .NET và SQL server đều được bảo vệ dưới cái tên Microsoft.

## 2. MySQL

Được phát triển vào giữa những năm 90 bởi MySQL AB (sau đó bị thâu tóm bởi Oracle), MySQL là một trong những hệ quản trị cơ sở dữ liệu mã nguồn mở đầu tiên và vẫn như vậy cho đến ngày nay. Mặc dù nó có rất nhiều biến thể nhưng chúng không quá khác nhau về cú pháp và chức năng cơ bản. Nhiều tổ chức phổ biến như Alcatel Lucent, Zappos, Google, Adobe, Facebook dựa vào hệ thống quản lý cơ sở dữ liệu này.

MySQL thường được sử dụng cùng với PHP và Apache Web Server, trên bản phân phối Linux. Bộ tứ này đã trở thành một tên gọi nổi tiếng và quyền lực: LAMP (Linux, Apache, MySQL, PHP).

# Những điểm khác biệt giữa SQL Server và MySQL

<img src="https://user-images.githubusercontent.com/111716161/191230192-477d0638-664c-407e-b65d-ce8b135f55f0.png" width="600"/>

## 1. Bản chất
 
- SQL Server: SQL Server được phát triển bởi Microsoft. Microsoft đã xây dựng nhiều công cụ mạnh mẽ cho SQL Server, hỗ trợ lớn hơn cho RDBMS, bao gồm các công cụ phân tích dữ liệu. SQL Server hoạt động tốt trong môi trường .NET

- MySQL: MySQL thuộc sở hữu của Oracle, là một phần mềm mã nguồn mở, chạy trên hơn 20 nền tảng bao gồm Linux, Windows, OS / X, HP-UX, AIX, Netware. MySQL có thể kết hợp với mọi ngôn ngữ lập trình khác, thông thường là PHP. 

## 2. Cú pháp

Tuy đều sử dụng câu lệnh truy vấn nhưng giữa hai cơ sở dữ liệu vẫn có điểm khác biệt. 

Xem chi tiết tại link sau: http://troels.arvin.dk/db/rdbms/

## 3. Giá cả

Khi nói đến SQL Server và MySQL, sự khác biệt dễ dàng nhất giữa cả hai sẽ là chi phí.

- SQL Server: Microsoft yêu cầu người dùng mua giấy phép để truy cập các tính năng đầy đủ của SQL Server.
- MySQL: Ngược lại, MySQL sử dụng General Public License (mã nguồn mở), điều này làm cho nó hoàn toàn miễn phí để sử dụng.

## 4. Lưu trữ dữ liệu

Một sự khác biệt lớn nữa giữa cả hai là cách chúng lưu trữ dữ liệu.

- SQL Server: SQL Server sử dụng một công cụ lưu trữ duy nhất do Microsoft phát triển.
- MySQL: MySQL cung cấp cho các nhà phát triển sự linh hoạt hơn nhiều, vì họ có thể sử dụng các công cụ khác nhau cho các bảng khác nhau dựa trên tốc độ, độ tin cậy hoặc một số thứ nguyên khác. Hai trong số các công cụ lưu trữ MySQL phổ biến nhất là InnoDB và MyISAM.

## 5. Sao lưu và phục hồi

- MySQL: Khi bạn sao lưu cơ sở dữ liệu MySQL, dữ liệu được trích xuất dưới dạng câu lệnh SQL. Do đó, việc sao lưu và khôi phục một lượng lớn dữ liệu có thể mất vĩnh viễn do thực hiện nhiều câu lệnh SQL. Hơn nữa, để tránh sự mâu thuẫn, MySQL sẽ khóa cơ sở dữ liệu trong quá trình sao lưu. Khóa này làm cho cơ sở dữ liệu của bạn không sử dụng được. 
- SQL Server: Trong khi đó, người dùng SQL Server không phải trải qua tình huống đó. SQL Server sẽ không khóa cơ sở dữ liệu, vì vậy bạn vẫn có thể sử dụng nó trong quá trình sao lưu.

## 6. Bảo mật

Cả hai công cụ đều tuân thủ EC2, có nghĩa là chúng tuân thủ các tiêu chuẩn bảo mật được thiết kế cho điện toán đám mây an toàn. Tuy nhiên, có một sự khác biệt đáng chú ý về cách họ hạn chế quyền truy cập vào cơ sở dữ liệu.

- MySQL: MySQL cho phép các tệp cơ sở dữ liệu của nó được chỉnh sửa và truy cập bởi các quy trình khác trong thời gian chạy.
- SQL Server: Điều này không xảy ra với SQL Server vì người dùng của nó được yêu cầu chạy một phiên bản để thực hiện chức năng. Nó làm cho SQL Server ít bị hack hơn vì dữ liệu không thể được thao tác hoặc truy cập trực tiếp.

## 7. Cộng đồng hỗ trợ

- MySQL: Mặc dù bạn có thể trả tiền để được hỗ trợ MySQL, nhưng trường hợp này hiếm khi phát sinh do sự đóng góp và hỗ trợ của cộng đồng xuất sắc của nó. Hầu hết mọi người không cần liên hệ với sự trợ giúp chính thức vì họ có thể tìm kiếm trên web và tìm thấy rất nhiều giải pháp.
- SQL Server: Mặt khác, vì SQL Server là một dịch vụ trả phí nên bạn sẽ không nhận được nhiều sự hỗ trợ của cộng đồng. Nếu bạn cần bất kỳ hỗ trợ nào, bạn có thể tham khảo trang hỗ trợ chính thức của nó.

## 8. IDEs

- MySQL sử dụng Enterprise Manager của Oracle.
- SQL Server sử dụng Management Studio (SSMS).

Cả 2 RDMBSs đều hỗ trợ công cụ Integrated Development Environment (IDE). Công cụ này tạo ra môi trường lập trình cho lập trình viên, bạn nên chọn loại phù hợp nhất cho mình.
