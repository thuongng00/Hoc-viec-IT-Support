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
- `username` là tên người user bạn có thể đăng nhập vào database. 
- `database_name` là tên của cơ sở dữ liệu để xuất nhập
- `data-dump.sql` là tên tệp trong thư mục hiện tại lưu trữ đầu ra. 

Lệnh này sẽ không tạo ra kết quả trực quan, nhưng bạn có thể kiểm tra nội dung của filename.sql để kiểm tra xem đó có phải là file kết xuất SQL hợp lệ hay không. 

```
head -n 5 data-dump.sql
```



## 2. Import database
