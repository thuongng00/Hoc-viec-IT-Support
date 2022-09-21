# Import file sql vào SQL Server

### Cách 1: Dùng Detach CSDL

Bước 1: Chuột phải vào Database -> Task -> Detach...

Bước 2: Thực hiện copy 2 file Database

Truy cập đường dẫn:

```
C:\Program Files\Microsoft SQL Server\MSSQL11.SQLEXPRESS\MSSQL\DATA
```

Copy và gửi file cho máy khác.

Bước 3: Khôi phục trên máy khác

Sau khi nhận được file, dán file vào đường dẫn:

```
C:\Program Files\Microsoft SQL Server\MSSQL11.SQLEXPRESS\MSSQL\DATA
```

- Attach... lại Database

Chuột phải Database -> Attach... -> Add -> tên tệp -> OK

### Cách 2: Cách thức xuất file

Cách làm này sẽ xuất file định hình .sql từ máy này và chạy file .sql này trên máy khác để có được “Cơ sở dữ liệu” cần khôi phục.

Bước 1: Chuột phải vào Database -> Task -> Generate Scripts...

Bước 2: Nhấn Next để tiếp tục.


