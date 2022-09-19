# MariaDB 

**MariaDB** là một hệ quản trị cơ sở dữ liệu mã nguồn mở (DBMS) được phát triển bởi các nhà sáng lập MySQL và hiện tại đang được đông đảo cộng đồng các nhà phát triển sử dụng. 

MariaDB có sẵn để cài đặt trên các hệ điều hành như Linux CentOS, Ubuntu và Window và được phát triển nhằm thay thế cho công nghệ cơ sở dữ liệu MySQL bởi nó có độ tương thích và cho hiệu suất cao hơn so với MySQL.

MariaDB dựa trên SQL và hỗ trợ xử lý dữ liệu kiểu ACID. Trong số các tính năng khác, cơ sở dữ liệu cũng hỗ trợ các API JSON, sao chép dữ liệu song song và nhiều công cụ lưu trữ bao gồm InnoDB, MyRocks, Spider, Aria, TokuDB và MariaDB ColumnStore.

Phần lớn công việc phát triển trên Open Source Database tập trung vào việc đạt được feature parity giữa MariaDB và MySQL. MariaDB Corp đã tuyên bố rằng cơ sở dữ liệu sẽ tương thích nhị phân với MySQL có nghĩa là hầu hết người dùng có thể chuyển đổi giữa hai công nghệ đơn giản bằng cách gỡ cài đặt MySQL và cài đặt MariaDB vào vị trí của nó.

## Ý nghĩa tên MariaDB
Sự phát triển của MariaDB được dẫn dắt bởi Michael “Monty” Widenius, developer hàng đầu về MySQL và là người sáng lập MySQL AB. Tiếc là vào năm 2008, MySQL AB đã được Sun mua.

Sau khi rời Sun, vào đầu năm 2009, anh và một số đồng nghiệp bắt đầu khởi đầu dự án về công cụ lưu trữ MySQL, sau này trở thành MariaDB, được đặt tên theo con gái út của Widenius.

## Ưu điểm của MariaDB

### Mã nguồn mở và hoàn toàn miễn phí 100%
MariaDB hay MySQL đều có 2 phiên bản: thương mại và cộng đồng.

Trái ngược với MySQL, MariaDB hoàn toàn mã nguồn mở được vận hành bởi cộng đồng thực sự (MariaDB Foundation), đứng đằng sau là công ty Monty Program, mặc dù cũng có bản thương mại nhưng không ảnh hưởng đến phiên bản mã nguồn mở.

### Được bảo trì bởi người tạo ra MySQL
Sau khi bị Oracle mua lại, một số thành viên chủ lực của MySQL đã ra đi, trong đó bao gồm những người tạo ra MySQL. Trong khi đó, MariaDB tiếp tục phát triển, đến bây giờ đã phát triển đến thế hệ 10.x. Do đó, tất cả những nhược điểm của MySQL đều được khắc phục ở MariaDB. 

## Hoàn toàn tương thích với MySQL
Do “sinh cùng cha” nên MariaDB có hệ thống hoàn toàn tương thích như với MySQL từ phiên bản 5.1 -> 5.5.  Do đó, nếu Website của bạn đang dùng MySQL 5.1 -> 5.5 thì việc chuyển qua MariaDB là cực kì dễ dàng.

Do sự tương thích giữa MariaDB và MySQL nên trong hầu hết trường hợp chúng ta có thể xóa bỏ MySQL và cài đặt MariaDB để thay thế mà hệ thống vẫn hoạt động bình thường.

Trên MariaDB và MySQL có những điểm tương đồng trong:

- Data and table definition files (.frm) files.
- Tất cả client APIs, protocols and structs.
- Tất cả filenames, binaries, paths, ports, sockets,…
- Tất cả MySQL connectors (PHP, Perl, Python, Java, .NET, MyODBC, Ruby, MySQL C connector etc) đều hoạt động bình thường khi đổi qua MariaDB.
- Gói mysql-client cũng hoạt động khi dùng với MariaDB

## Nhiều Engine lưu trữ hơn
Ngoài việc hỗ trợ các storage engines cơ bản như MyISAM, BLACKHOLE, CSV, MEMORY, ARCHIVE, and MERGE thì trên MariaDB còn bổ sung thêm các storage engines sau: Aria (được xem như một phiên bản cập nhập của MyISAM), XtraDB (thay thế cho InnoDB), FederatedX, OQGRAPH, SphinxSE, IBMDB2I, Spider, PBXT, …. 

Ngoài ra trên MariaDB còn cải thiện hiệu năng và cung cấp thêm một số chức năng mới. 

### Kết hợp 2 thế giới SQL và NoSQL
Cả 2 loại cơ sở dữ liệu này đều có điểm lợi riêng, việc MariaDB cho phép kết nối sẽ tận dụng được lợi thế của 2 thế giới này: Dynamic Column và Cassandra Store Engine.

### Tối ưu tốc độ
Trong cùng một điều kiện như nhau thì MariaDB nhanh hơn MySQL từ 3-5% tốc độ.

### Các Website lớn đã sử dụng MariaDB
Một trong những website lớn nhất thế giới là Wikipedia đã chuyển từ MySQL qua MariaDB. Ngay cả Fullstack-Station cũng đang dùng MariaDB.

### Tài liệu hỗ trợ Tiếng Việt
(Knowledge Base tiếng Việt) mariadb.com/kb , mặc dù bản dịch vẫn chưa phải quá tốt, tuy nhiên cho thấy sự tiếp cận cộng đồng là khá tốt.
