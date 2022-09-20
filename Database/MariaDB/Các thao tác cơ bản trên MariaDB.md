## 1. Thao tác với database

- Tạo database:

```
CREATE DATABASE database_name;
```

![image](https://user-images.githubusercontent.com/111716161/191149487-187ee230-5aac-47c2-a119-7c014b3aede6.png)

- Hiển thị toàn bộ database:

```
SHOW DATABASES;
```

![image](https://user-images.githubusercontent.com/111716161/191149506-220a3176-119f-4390-81d9-eb2c1623054b.png)

- Sử dụng một database:

```
USE database_name;
```

![image](https://user-images.githubusercontent.com/111716161/191149524-29750dcc-6709-4153-aaae-4de905a10e54.png)

- Xóa database:

```
DROP DATABASE database_name;
```

![image](https://user-images.githubusercontent.com/111716161/191149569-f89de10f-0573-45f9-a8f2-3e1d66c51ed8.png)

## 2. Thao tác với bảng

- Tạo bảng

```
CREATE TABLE table_name(column_name column_type);
```

![image](https://user-images.githubusercontent.com/111716161/191151421-5ca4aaaa-2b9c-4f0f-b146-3336a31b65f1.png)

- Hiển thị toàn bộ bảng:

```
SHOW TABLES;
```

![image](https://user-images.githubusercontent.com/111716161/191151581-ed82c354-31aa-40e7-b65e-590e94b6d67d.png)

- Xóa bảng

```
DROP TABLE table_name;
```

![image](https://user-images.githubusercontent.com/111716161/191151656-6d67f7c5-856b-4732-a90f-714fdff808c3.png)

- Đổi tên bảng

```
RENAME TABLE old_table TO new_table
```

![image](https://user-images.githubusercontent.com/111716161/191151961-37791395-694e-4a6b-af86-4a8f31f9976d.png)

## 3. Thao tác với cột trong bảng

- Hiển thị toàn bộ cột trong bảng:

```
SHOW COLUMNS FROM table_name;
```

![image](https://user-images.githubusercontent.com/111716161/191152050-cad9c271-bb00-4224-9cee-2893b1fb7148.png)

- Thêm mới cột:

```
ALTER TABLE table_name ADD column_name column_definition;
```

![image](https://user-images.githubusercontent.com/111716161/191152189-d90cd382-b2df-4e72-b76a-ce8e972df1dc.png)

- Đổi tên cột:

```
ALTER TABLE table_name CHANGE COLUMN old_column new_column VARCHAR(25)
```

![image](https://user-images.githubusercontent.com/111716161/191152408-fae860e4-55b0-420b-afdb-7f8918c420f0.png)

- Xóa cột:

```
ALTER TABLE table_name DROP COLUMN column_name;
```

![image](https://user-images.githubusercontent.com/111716161/191152547-177eca52-97be-4c90-acd5-8ada963380bf.png)

- Thay đổi kiểu dữ liệu của cột:

```
ALTER TABLE table_name MODIFY column_name VARCHAR(50);
```

![image](https://user-images.githubusercontent.com/111716161/191152644-65aee1ea-b23b-4968-889d-134be25da2ab.png)

## 4. Thao tác với dữ liệu trong bảng

- Thêm mới dữ liệu:

```
INSERT INTO table_name (field1, field2,...) VALUES (value1, value2,...);
```

![image](https://user-images.githubusercontent.com/111716161/191152905-4e7f8de3-a662-4564-934c-f881589e68ed.png)

- Cập nhật dữ liệu:

```
UPDATE table_name SET field1=new_value1, field2=new_value2,... [WHERE ...]
```

![image](https://user-images.githubusercontent.com/111716161/191153041-4803c667-4db6-4af1-ae4f-d34da97fdadc.png)

- Xem dữ liệu:

```
SELECT field, field2,... FROM table_name WHERE...
```

![image](https://user-images.githubusercontent.com/111716161/191153108-6f4ba386-b451-4f95-9690-7d6b5959b00f.png)

- Sao chép dữ liệu từ bảng này sang bảng mới

```
CREATE TABLE IF NOT EXISTS new_table SELECT * FROM old_table;
```

![image](https://user-images.githubusercontent.com/111716161/191153227-fda1ea9d-e236-43f8-89e3-ec48651b3cf1.png)

- Xóa dữ liệu:

```
DELETE FROM table_name [WHERE …]
```

![image](https://user-images.githubusercontent.com/111716161/191153315-6a924ce5-3ab5-4634-833a-6cc5bd9b4362.png)

## 5. Thao tác với user

- Hiển thị toàn bộ user:

```
SELECT USER, HOST, PASSWORD FROM MYSQL.USER;
```

![image](https://user-images.githubusercontent.com/111716161/191154021-b26694f9-f3f8-4b91-b946-67f327680cda.png)

- Tạo user mới:

```
CREATE USER '<user_name>'@'<hostname>' IDENTIFIED BY '<user_password>';
```

![image](https://user-images.githubusercontent.com/111716161/191154123-b5bc8092-60e5-4151-b38d-730fbac9bd08.png)

- Gán quyền cho user

```
GRANT <permision> ON <database name>.<table name> TO <user name>@<host name>;
```

![image](https://user-images.githubusercontent.com/111716161/191154228-f66fa3ef-7dc7-4708-9259-6d218f95dbef.png)

Sau khi hoàn tất cần reload lại toàn bộ quyền của user

```
FLUSH PRIVILEGES;
```

![image](https://user-images.githubusercontent.com/111716161/191154325-1af38ae5-b658-48e2-8093-a3cdd9ab787f.png)

- Gỡ bỏ quyền của một user:

```
REVOKE <permission> ON <database name>.<table name> FROM <user name>@<host name>;
```

REVOKE ALL PRIVILEGES ON * . * TO 'thuong'@'localhost';
