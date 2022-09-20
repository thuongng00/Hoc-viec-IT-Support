# SQL Server

SQL server hay còn được gọi là Microsoft SQL Server, nó từ viết tắt của MS SQL Server. Đây chính là một loại phần mềm đã được phát triển bởi Microsoft và nó được sử dụng để có thể dễ dàng lưu trữ cho những dữ liệu dựa theo tiêu chuẩn RDBMS.

Từ đó, người ta sẽ lưu trữ dữ liệu dựa vào tiêu chuẩn RDBMS và nó cũng là một  trong những hệ quản trị cơ sở dữ liệu dạng quan hệ đối tượng. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/191168485-affbfc3c-dbbc-410a-9bf3-2a872f30a2d2.png" width="600"/>
</p>

SQL Server có khả năng cung cấp đầy đủ các công cụ cho việc quản lý từ giao diện GUI đến sử dụng ngôn ngữ cho việc truy vấn SQL. Điểm mạnh của SQL điểm mạnh của nó là có nhiều nền tảng được kết hợp cùng như: ASP.NET, C# để xây dựng Winform cũng chính nó có khả năng hoạt động độc lập. 

Tuy nhiên, SQL Server thường đi kèm với việc thực hiện riêng các ngôn ngữ SQL, T-SQL,...

- T-SQL là một trong những loại ngôn ngữ thuộc quyền sở hữu của Microsoft và được gọi với cái tên Transact-SQL. Nó thường cung cấp thêm rất nhiều cho các  khả năng khai báo biến, thủ tục lưu trữ và xử lý ngoại lệ,... 
- SQL Server Management Studio là một loại công cụ giao diện chính cho máy chủ cơ sở của chính dữ liệu SQL, thông thường thì nó hỗ trợ cho cả môi trường 64 bit và 32 bit. 

## Thành phần của SQL Server

SQL Server đã trải qua hơn 20 năm phát triển và đã đề ra những version cụ thể khác nhau. Các mô hình Client - Server được chia làm 2 thành phần chính bao gồm: 

- Workstation: Nó được cài đặt trên các thiết bị vận hành để trở thành phần mềm tương tác với hệ thống máy chủ Server. 
- Server: Được cài đặt ở trên máy chủ chính, nó có thể là: SQL server, SQL Server Agent, SSIS, SSAS,...

Ngoài ra, bạn hoàn toàn có thể cài đặt nhiều phiên bản của SQL Server trên cùng một máy chủ và điều này sẽ giúp tiết kiệm được các chi phí mua Server để hoạt động và cần nhiều phiên bản khác nhau. Nó bảo mật và cũng được tách biệt hoàn toàn giúp cho hệ thống được an toàn hơn.

## Mục đích sử dụng SQL Server

SQL Server thông thường được sử dụng cho mục đích lưu trữ dữ liệu. Ngoài ra, nó còn mang lại những tính năng làm việc giúp người dùng làm việc hiệu quả hơn như sau: 

- Giúp người sử dụng có thể duy trì việc lưu trữ bền vững.
- Cho phép bạn tạo ra nhiều cơ sở dữ liệu hơn. 
- Có khả năng phân tích dữ liệu bằng SSAS
- Nó có khả năng bảo mật cao
- Việc tạo ra được các báo cáo bằng SSRS — SQL Server Reporting Services sẽ được dễ dàng hơn. 
- Các quá trình sẽ được thực hiện bằng SSIS — SQL Server Integration Services.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/191167051-34dc4b37-021e-4626-948d-f3b8488fec60.png" width="600"/>
</p>

## Lý do nên sử dụng SQL Server

- Nó cho phép người sử dụng có thể dùng để truy cập dữ liệu bên trong hệ thống quản lý cơ sở dữ liệu quan hệ. 
- Người ta cho phép người dùng mô tả dữ liệu. 
- Cho phép người dùng thực hiện xác định dữ liệu bên trong cơ sở dữ liệu và thực hiện các thao tác dữ liệu. 
- Nó cho phép nhúng trong các ngôn ngữ khác có thể sử dụng mô-đun SQL, thư viện và thực hiện trình biên dịch trước. 
- Nó sẽ cho phép người dùng tạo và thả cho các cơ sở dữ liệu cũng như bảng. 
- SQL cho phép người sử dụng để thực hiện tạo ra các chế độ view, các thủ tục lưu trữ và chức năng trong cơ sở dữ liệu. 
- Nó sẽ cho phép người dùng để thực hiện thiết lập quyền trên các bảng, view và thủ tục. 

# Các phiên bản SQL Server

Trong  khoảng từ năm 1995 đến năm 2019 thì Microsoft đã cho phát hành nhiều phiên bản cơ sở dữ liệu SQL. Ngoài ra, Microsoft đã kết hợp được với nhiều  công cụ cho việc thực hiện quản lý dữ liệu cũng như phân tích được dữ liệu vào SQL Server. Một số chức năng và công nghệ mới được xuất hiện bao gồm: web, điện toán đám mây và các thiết bị di động.

## Microsoft SQL Server 2012

Bản 2012 được cung cấp các tính năng mới như chỉ mục cột, có thể được sử dụng để thực hiện các lưu trữ theo hướng định dạng trên cột dành cho các ứng dụng. Ngoài ra, việc phân tích dữ liệu luôn được sẵn sàng và trang bị công nghệ để có thể khắc phục các thảm họa.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/191167281-eddc1ba1-fb8a-4a11-885f-daf040723426.png" width="600"/>
</p>

## Microsoft SQL Server 2014

SQL 2014 đã được thêm OLTP trong bộ nhớ nên người dùng có thể thực hiện chạy cho các ứng dụng xử lý giao dịch trực tuyến. Quá trình thực hiện sẽ dựa trên dữ liệu lưu trữ bên trong những bảng đã được tối ưu hóa cho bộ nhớ thay vì phải sử dụng các tệp dựa trên bộ đĩa tiêu chuẩn.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/191167356-6b5ab9aa-c3b6-4445-b5d1-add2a0f32319.png" width="600"/>
</p>

Một trong những tính năng khác của bản 2014 sở hữu phần mở rộng nhóm bộ đệm và được tích hợp thêm bộ nhớ ở vùng đệm cho máy chủ SQL nhờ vào ổ đĩa có trạng thái rắn cũng như được thiết kế với thông lượng I/O nhờ việc giảm tải đi các dữ liệu từ những đĩa cứng có dạng thông thường khác. 

## Microsoft SQL Server 2016

Microsoft của máy chủ SQL 2016 nó đã có sẵn từ tháng 6/2016. Nó được phát triển như một phần của các chiến lược công nghệ đầu tiên đối với một thiết bị di động đầu tiên trên nền tảng đám mây (nó được Microsoft áp dụng vào khoảng 2 năm trước đó).

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/191167454-f97e888e-78b7-4f2e-9c38-7afa81bc5398.png" width="600"/>
</p>

Phiên bản này cũng có thêm nhiều tính năng bao gồm sự điều chỉnh hiệu suất, phân tích hoạt động cho thời gian thực, sự hỗ trợ của đám mây.

Từ đó, cho phép DBA chạy dựa trên cơ sở dữ liệu được kết hợp hệ thống tại chỗ và dịch vụ đám mây có khả năng giảm thiểu được các chi phí CNTT. SQL Server 2016 có khả năng tăng hỗ trợ cho việc phân tích luồng dữ liệu lớn và ứng dụng nhiều trong việc phân tích các ứng dụng nâng cao khác thông qua hệ thống máy chủ cơ sở dữ liệu SQL R Services.

Nó còn cho phép DBMS chạy ứng dụng phân tích được viết bằng loại ngôn ngữ lập trình R nguồn mở và polyBase. Công nghệ này cho phép người sử dụng máy chủ SQL truy cập dữ liệu trong cụm Hadoop hoặc lưu trữ Azure blob để thực hiện phân tích.

## Microsoft SQL Server 2017

Bản cập nhật chính thức và đổi mới được phát hành vào tháng 10 năm 2017. Việc hỗ trợ cho máy chủ SQL trên Linux đã chuyển nền tảng cho cơ sở dữ liệu lên một hệ điều hành nguồn mở thường thấy ở trong các doanh nghiệp.

Từ đó, nó mang lại tiềm năng cho Microsoft với những khách hàng không sử dụng Windows hoặc ở trong môi trường máy chủ hỗn hợp.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/191167517-3149f32c-a40d-4c17-953b-4162b5b63cb7.png" width="600"/>
</p>

SQL Server 2017 đã được mở rộng để hỗ trợ Docker được thêm các hệ thống Windows dựa trên phiên bản trước để bao gồm các thùng chứa dựa trên Linux. 
SQL Server 2017 hỗ trợ lập trình Python, vì là ngôn ngữ mở nguồn và được sử dụng tương đối rộng rãi trong các ứng dụng phân tích. 

SQL Server R Services được đổi tên thành Machine Learning Services và được mở rộng để thực hiện chạy cho cả ứng dụng R và Python. Ban đầu thì bộ công cụ máy và một loạt tính năng khác chỉ có trong các phiên bản Windows của phần mềm cơ sở dữ liệu với các tính năng hạn chế hơn được hỗ trợ trên Linux. 

## Microsoft SQL Server 2019

Bản 2019 cho phép người được sử dụng để tham gia vào các thùng chứa SQL Server, HDFS và Spark cùng nhau bằng nhiều tính năng. Ngoài ra, nó còn giới thiệu cho việc xây dựng chỉ mục cột, xây dựng lại cũng như che giấu đi dữ liệu tĩnh. Từ đó, phục hồi dữ liệu tăng tốc mới và thực hiện, hoàn tác các giai đoạn làm lại số thứ tự nhật ký trang. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/191168396-83ad42c1-fafb-4c0c-a22e-0a78f81f655e.png" width="600"/>
</p>


