# Import file sql vào SQL Server

### Cách 1: Dùng Detach CSDL

Bước 1: Chuột phải vào Database -> Task -> Detach...

![image](https://user-images.githubusercontent.com/111716161/191416520-f95c15e3-b6d3-45c6-86be-f359eadcab3d.png)

Nhấn OK.

![image](https://user-images.githubusercontent.com/111716161/191416598-d7093730-87ac-4f16-b4e4-88f52e5a03a0.png)

Bước 2: Thực hiện copy 2 file Database

Truy cập đường dẫn:

```
C:\Program Files\Microsoft SQL Server\MSSQL15.THUONG\MSSQL\DATA
```

![image](https://user-images.githubusercontent.com/111716161/191417031-8c09e1e7-4593-4289-a357-1a88df616b25.png)

Copy 2 file này và gửi file cho máy khác.

Bước 3: Khôi phục trên máy khác

Sau khi nhận được file, dán file vào đường dẫn:

```
C:\Program Files\Microsoft SQL Server\MSSQL15.THUONG\MSSQL\DATA
```

- Attach... lại Database

Chuột phải Database -> Attach... -> Add -> tên tệp -> OK

![image](https://user-images.githubusercontent.com/111716161/191418034-6fe6dcb6-2da5-440b-b07b-e955a916c500.png)

![image](https://user-images.githubusercontent.com/111716161/191418100-794d6a43-0747-49cb-8e51-5e74301113e1.png)

![image](https://user-images.githubusercontent.com/111716161/191418141-60dde6af-d6ef-4b9b-99f4-d1e9a500ed76.png)

![image](https://user-images.githubusercontent.com/111716161/191418185-8c49086d-4fb4-4516-a474-c8d1e7a60c77.png)

### Cách 2: Cách thức xuất file

Cách làm này sẽ xuất file định hình .sql từ máy này và chạy file .sql này trên máy khác để có được “Cơ sở dữ liệu” cần khôi phục.

Bước 1: Chuột phải vào Database -> Task -> Generate Scripts...

Bước 2: Nhấn Next để tiếp tục.


