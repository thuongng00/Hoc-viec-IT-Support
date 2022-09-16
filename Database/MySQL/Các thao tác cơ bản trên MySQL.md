# Tạo mới MySQL User, Database

Là user root trong MySQL, bạn có toàn quyền truy cập vào mọi database.

Tuy nhiên, nếu bạn làm việc trong một nhóm, có nhiều trường hợp bạn cần áp dụng hạn chế. Bạn sẽ cần tạo database mới hoặc user mới với phân quyền đặc biệt.

### 1. Tạo mới database.

- Tạo một database mới

```
CREATE DATABSE dbname;
```

- Xem các database

```
show databases;
```

- Bắt đầu làm việc với database

```
USE dbname;
```

- Xóa database

```
DROP DATABASE dbname;
```

![image](https://user-images.githubusercontent.com/111716161/190344207-3c14d4b2-1678-4aaf-aa81-fa476dfa3957.png)

### 2. Tạo mới User

- Tạo một user mới

```
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password'
```

![image](https://user-images.githubusercontent.com/111716161/190346011-99bb48eb-ec48-4154-b783-167fa437ea09.png)

- Hiển thị toàn bộ user

```
SELECT * FROM mysql.user;
```

- Xóa user

```
DROP USER ‘username’@‘localhost’
```

# Quản lý MySQL User Permissions (quyền thao tác của MySQL user)

Gán quyền truy cập vào database cho user mới:

```
GRANT ALL PRIVILEGES ON dbname.* TO 'username'@'localhost'
```

Bạn cũng có thể gán từng quyền riêng biệt, bao gồm:

- SELECT – user có quyền đọc (read) database bằng lệnh select
- CREATE – user có thể tạo bảng mới
- DROP – cho phép người dùng xóa bảng
- DELETE – user có thể xóa dòng khỏi bảng
- INSERT – giúp user thêm dòng vào bảng
- UPDATE – giúp cập nhật dòng
- GRANT OPTION – có thể gán hoặc xóa quyền của user khác

Ví dụ, để gán quyền CREATE: 

```
GRANT CREATE ON dbname.* TO 'username'@'localhost'
```

Mặt khác, nếu bạn muốn xóa quyền truy cập của ai đó, sử dụng lệnh sau:

```
REVOKE permission_type ON dbname.* TO 'username'@'localhost'
```

Kiểm tra quyền mà user có

```
SHOW GRANTS username
```

Khi đã quản lý user xong, để áp dụng thay đổi 

```
FLUSH PRIVILEGES
```
# Thao tác với cơ sở dữ liệu

### 1. Tạo bảng table

```
CREATE TABLE table_name(
column_name1 data_type1(size),
column_name2 data_type2(size),
column_name3 data_type3(size),
...
);
```

![image](https://user-images.githubusercontent.com/111716161/190592846-0a076e48-64b0-4023-8d76-d0ef4aff8e54.png)

### 2. Kiểm tra bảng vừa tạo

```
show tables;
```

![image](https://user-images.githubusercontent.com/111716161/190592903-178cc162-685c-4ac7-b555-23ba2852410f.png)

- Xem cột đã tạo:

```
show columns from table_name;
```

![image](https://user-images.githubusercontent.com/111716161/190592996-42b80885-e900-4192-9006-10ca1cbeb989.png)

### 3. Thêm cột vào bảng

```
ALTER TABLE table_name ADD new _column data_type (size) AFTER old_column; 
```

![image](https://user-images.githubusercontent.com/111716161/190593255-7dcd0086-4c9a-46f3-8822-90020ec5cf1b.png)

### 4. Thêm giá trị vào các trường dữ liệu

```
INSERT INTO table_name (column1, columns2,...) VALUES (value1, value2...);
```

![image](https://user-images.githubusercontent.com/111716161/190593844-ef95d9f4-abfc-409c-84d8-58774566e3a1.png)

### 5. Xem giá trị trong bảng

```
SELECT * from table_name;
```

![image](https://user-images.githubusercontent.com/111716161/190593912-8b188179-2887-4eba-8828-ff59321cae82.png)

### 6. Xóa bảng

```
drop table table_name;
```

![image](https://user-images.githubusercontent.com/111716161/190598467-99a00449-4c03-471e-8984-ce3b75d2ce32.png)

# Các command trong MySQL

MySQL cũng có danh sách command hữu dụng. Bạn chỉ cần gõ \h hoặc help để xem bảng bên dưới:

![image](https://user-images.githubusercontent.com/111716161/190338664-95a216d2-0b07-4355-8799-2cec21da546a.png)

| Câu lệnh | Ý nghĩa |
|----------|---------|
| ? (\?) | Giống như help | 
| clear (\c) | Xóa câu lệnh | 
| connect (\r) | Kết nối lại với máy chủ, các đối số tùy chọn là database và host |
| delimiter (\d) | Đặt dấu phân cách câu lệnh. Lưu ý: Sử dụng phần còn lại của dòng làm dấu phân cách mới |
| edit (\e) | Chỉnh sửa lệnh với $EDITOR | 
| ego (\G) | Gửi lệnh đến MySQL server, hiển thị kết quả theo hàng dọc | 
| exit (\q) | Thoát khỏi MySQL, giống như quit | 
| go (\g) | Gửi lệnh đến MySQL server |
| help (\h) | Hiển thị danh sách câu lệnh và ý nghĩa của chúng |
| nopager (\n) | Tắt trang, in ra stdout |
| notee (\t) | Không viết vào file ngoài |
| pager (\P) | Đặt PAGER[to_pager]. In kết quả truy vấn qua PAGER |
| print (\p) | In lệnh hiện tại | 
| prompt (\R) | Thay đổi lời nhắc MySQL của bạn |
| quit (\q) | Thoát MySQL |
| rehash (\#) | Xây dựng lại hàm hoàn thành |
| source (\.) | Thực thi một số tệp kịch bản SQL. Lấy tên tệp làm đối số |
| status (\s) | Nhận thông tin trạng thái từ máy chủ |
| system (\!) | Thực hiện lệnh shell hệ thống | 
| tee (\T) | Đặt outfile [to_outfile]. Nối mọi thứ vào outfile đã cho |
| use (\u) | Sử dụng cơ sở dữ liệu khác. Lấy tên cơ sở dữ liệu làm đối số |
| charset (\C) | Chuyển sang bộ ký tự khác. Có thể cần thiết để xử lý binlog với các bộ ký tự nhiều byte |
| warnings (\W) | Hiển thị cảnh báo sau mỗi câu lệnh |
| nowarning (\w) | Không hiển thị cảnh báo sau mỗi câu lệnh |
| resetconnection (\x) | Làm sạch phiên hoạt động | 
