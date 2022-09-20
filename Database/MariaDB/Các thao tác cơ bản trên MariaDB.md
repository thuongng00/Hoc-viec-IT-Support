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



