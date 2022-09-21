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

![image](https://user-images.githubusercontent.com/111716161/191432292-8d66ba81-9cda-47e1-a1ab-e85cd6acccc5.png)

- Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/191432790-78850796-c785-48ce-8b79-4e403ee99c97.png)

Có 2 lựa chọn: 

`Script entire database and all database objects`: Chọn toàn bộ cơ sở dữ liệu và tất cả đối tượng trong CSDL.

`Select specific database objects`: Chọn các đối tượng CSDL cụ thể. 

- Sau khi chọn, nhấn Next. 

![image](https://user-images.githubusercontent.com/111716161/191433357-c4d49e9f-afde-4756-838f-5b65e73771d9.png)

- Chọn cách lưu tệp, nhấn Next. 

![image](https://user-images.githubusercontent.com/111716161/191433659-9b79c796-4e57-412a-8c95-6e35bca9bef3.png)

- Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/191433768-e7ec4032-84a0-49d8-832b-e11704170be3.png)

- Nhấn Finish.

![image](https://user-images.githubusercontent.com/111716161/191433832-e12744a5-8c0a-492a-b7a3-65ad1c73b213.png)

Bước 2: Nhấn Next để tiếp tục.


