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

- Hiển thị toàn bộ bảng:

```
SHOW TABLES;
```

- Xóa bảng

```
DROP DATABASE table_name;
```

- Sao chép dữ liệu từ bảng này sang bảng mới

```
CREATE TABLE IF NOT EXISTS new_table SELECT * FROM old_table
```

- Đổi tên bảng

```
RENAME TABLE old_table TO new_table
```

## 3. Thao tác với cột trong bảng

- Hiển thị toàn bộ cột trong bảng:

```
SHOW COLUMNS FROM table_name;
```

- Thêm mới cột:

```
ALTER TABLE table_name ADD column_name column_definition;
```

- Đổi tên cột:

```
ALTER TABLE table_name CHANGE COLUMN old_column new_column VARCHAR(25)
```

- Xóa cột:

```
ALTER TABLE table_name DROP COLUMN column_name;
```

- Thay đổi kiểu dữ liệu của cột:

```
ALTER TABLE table_name MODIFY column_name VARCHAR(50);
```

## 4. Thao tác với dữ liệu trong bảng

- Xem dữ liệu:

```
SELECT field, field2,... FROM table_name WHERE...
```

- Thêm mới dữ liệu:

```
INSERT INTO table_name (field1, field2,...) VALUES (value1, value2,...);
```

- Cập nhật dữ liệu:

```
UPDATE table_name SET field1=new_value1, field2=new_value2,... [WHERE ...]
```

- Xóa dữ liệu:

```
DELETE FROM table_name [WHERE …]
```
