**MariaDB** và **MySQL** là hai trong số những hệ quản trị cơ sở dữ liệu đang được sử dụng rộng rãi nhất trên thế giới hiện nay.

MySQL là một trong những cơ sở dữ liệu được sử dụng rộng rãi nhất trên thế giới được phát triển dựa trên C/C++. MySQL sau đó được Sun Microsystems mua lại vào năm 2008. Tiếp đó vào sau năm 2010 Sun Microsystems đã được Oracle mua lại và kể từ đó MySQL được suy trì quản lý bởi đội ngũ Oracle.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/190974321-a6921693-f867-406e-8bbb-06372974421b.png" width=600/>
</p>

Trong quá trình mua lại Sun Microsystems của Oracle thì một số kỹ sư cao cấp đang nghiên cứu phát triển MySQL cảm thấy có xung đột lợi ích giữa cơ sở dữ liệu thương mại của MySQL và Oracle. Kết quả là các kỹ sư đó đã tạo ra một nhánh của cơ sở mã MySQL và như thế MariaDB được tạo ra. 

Điểm tương đồng duy nhất giữa 2 hệ quản trị cơ sở dữ liệu này chính là mục đích thiết kế đều dựa trên hệ quản trị cơ sở dữ liệu và được sử dụng vô cùng rộng rãi. Nhưng với MariaDB là một phiên bản nâng cấp hơn vẫn có sự khác biệt về ngôn ngữ lập trình, cơ sở hình thành và đặc biệt là công cụ lưu trữ.

Ngỗ ngữ lập trình hỗ trợ của hai hệ quản trị cơ sở dữ liệu này khá là tương đồng nhau đều là C, C#, Ada, D, C++, Eiffel, Haskell, Java, JavaScript. Điểm khác ở đây là Maria không hỗ trợ ngôn ngữ Delphi nhưng MySQL thì có.

Công cụ hỗ trợ lưu trữ của 2 ứng dụng khá giống nhau chỉ có điều là MariaDB có thể hỗ trợ nhiều phần mềm lưu trữ hơn như CSV, INNODB, MYISAM, ARCHIVE, MERGE, MyRocks, TokuDB, Aria, Sequence, Connect vì MariaDB là sự tích hợp ưu điểm của cả 2 thư viện SQL và NoSQL nên tính năng lưu trữ được mở rộng hỗ trợ người dùng nhiều hơn.

MariaDB là một hệ quản trị cơ sở dữ liệu được cộng đồng người sử dụng đánh giá cao nhất thế giới hiện nay. Hy vọng thông qua bài viết mà Dizibrand đã cung cấp cho người sử dụng những thông tin cần thiết. Từ đó hỗ trợ một phần nào giúp người sử dụng sẽ có được sự lựa chọn phù hợp nhất cho hệ thống máy tính của mình.

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/190974344-f247dc0a-dcfe-497f-8466-2b2fe60821a1.png" width=600/>
</p>

Maria DB có một số tối ưu hóa có xu hướng cải thiện hiệu suất so với MySQL. Bảng sau minh họa sự khác biệt so sánh giữa MariaDB và MySQL

| | MariaDB | MySQL |
|---|---|---|
| Nhà phát triển | MariaDB Corporation AB (MariaDB Enterprise) và MariaDB Foundation (community MariaDB Server) | Oracle | 
|Phát hành lần đầu | 2009 | 1995 |
|Phát hành hiện tại| 10.10 | 8.0 |
| Giấy phép | Mã nguồn mở | Mã nguồn mở + độc quyền |
|Phát triển | Mở | Đóng |
| Công cụ lưu trữ | InnoDB, MyISAM, BLACKHOLE, CSV, ARCHIVE, MERGE, ColumnStore, MyRocks, Aria, SphinxSE, TokuDB, CONNECT, SEQUENCE, Spider, Cassandra | InnoDB, MyISAM, BLACKHOLE, CSV, ARCHIVE, MERGE |
| Quản lý SQL | HeidiSQL | MySQL Workbench |
| Ngôn ngữ triển khai | C và C ++ | C và C ++ |
| hệ điều hành máy chủ | FreeBSD, Linux, Solaris, Windows |  FreeBSD, Linux, Solaris, Windows, OS X|
| API | Proprietary native API, ADO.NET, JDBC, ODBC | Proprietary native API, ADO.NET, JDBC, ODBC |
| Ngôn ngữ lập trình hỗ trợ | Ada, C, C#, C++, D, Eiffel, Erlang, Go, Haskell, Java, Javascript (Node.js), Objective-C, Ocaml, Perl, PHP, Python, Ruby, Scheme, Tcl | Ada, C, C#, C++, D, Eiffel, Erlang, Delphi, Haskell, Java, Javascript (Node.js), Objective-C, Ocaml, Perl, PHP, Python, Ruby, Scheme, Tcl | 
| Khách hàng | Booking.com, Wikipedia, Google, Canal+, ClubMed, Deutsche, Telekom, La Poste, Virgin...| NASA, US NAvy, Spotify, Netflix, Nokia, Joomla, Uber, PHP-Nuke, Tesla, Fujitsu...|
|Thị trường | MariaDB mặc định trong LAMP | MySQL mặc định trong AppServ |





