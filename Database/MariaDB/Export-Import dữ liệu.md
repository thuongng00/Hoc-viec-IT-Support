Nhập và xuất cơ sở dữ liệu là một nhiệm vụ phổ biến trong phát triển phần mềm. Bạn có thể sử dụng kết xuất dữ liệu để sao lưu và khôi phục thông tin của mình. Bạn cũng có thể sử dụng chúng để di chuyển dữ liệu sang máy chủ hoặc môi trường phát triển mới.

Điều kiện tiên quyết
Để nhập hoặc xuất cơ sở dữ liệu MySQL hoặc MariaDB cần:

- Một máy ảo với người dùng sudo không root
- Máy chủ đã được cài đặt MySQL hoặc MariaDB.
- Cơ sở dữ liệu được tạo trong máy chủ cơ sở dữ liệu của bạn.

## 1. Export database

- Tạo một thư mục để lưu file khi xuất dữ liệu ở trong thư mục /home/.

```
mkdir dbbackup
```

- Di chuyển đến thư mục vừa tạo

```
cd dbbackup
```

![image](https://user-images.githubusercontent.com/111716161/191156963-48fcfc2b-c51e-4e06-8f93-f6b97d9d01ca.png)

- Xuất dữ liệu

Tiện tích console `mysqldump` được sử dụng để xuất database sang file văn bản SQL, giúp việc chuyển và di chuyển tương đối dễ dàng. Bạn cần chính tên database cũng như tên user và password cho một account có quyền cho phép ít nhất là toàn quyền truy cập chỉ đọc vào database.

```
MYSQLDUMP - u username -p database_name > data-dump.sql
```

*Trong đó*:

`username` là tên người user bạn có thể đăng nhập vào database. 

`database_name` là tên của cơ sở dữ liệu để xuất nhập.

`data-dump.sql` là tên tệp trong thư mục hiện tại lưu trữ đầu ra. 

Lệnh này sẽ không tạo ra kết quả trực quan, nhưng bạn có thể kiểm tra nội dung của filename.sql để kiểm tra xem đó có phải là file kết xuất SQL hợp lệ hay không. 

```
head -n 5 data-dump.sql
```

![image](https://user-images.githubusercontent.com/111716161/191157370-7a5ec0c4-cf25-4e4d-9998-64033f2823e4.png)

Để xem toàn bộ nội dung file, sử dụng lệnh:

```
cat filename.sql
```

![image](https://user-images.githubusercontent.com/111716161/191158698-a4dbb86a-cd2e-4218-b4a8-3a3849affc8d.png)

## 2. Import database

Để nhập file kết xuất hiện có vào MySQL hoặc MariaDB, bạn sẽ phải tạo database mới. Đây là nơi nội dung của file kết xuất sẽ được nhập. 

- Đăng nhập và tạo database mới:

![image](https://user-images.githubusercontent.com/111716161/191157756-56a386bd-5c2b-4834-aec2-59913a910b74.png)

- Thoát khỏi MariaDB/MySQL.

```
exit
```

- Nhập dữ liệu

```
mysql -u username -p new_database < data-dump.sql
```

*Trong đó:*

`username` là tên user bạn có thể đăng nhập vào database bằng.

`newdatabase` là tên của database mới được tạo.

`data-dump.sql` là file kết xuất dữ liệu sẽ được nhập, nằm trong folder hiện tại.

![image](https://user-images.githubusercontent.com/111716161/191158332-2f44ce15-368a-4064-8490-e3400552ea75.png)

- Vào MySQL/MariaDB để kiểm tra kết quả.

![image](https://user-images.githubusercontent.com/111716161/191158486-2881e57c-2211-4c8e-9d45-1513d1d01cd4.png)
