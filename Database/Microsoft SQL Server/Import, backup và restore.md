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

- Có 2 lựa chọn: 

`Script entire database and all database objects`: Chọn toàn bộ cơ sở dữ liệu và tất cả đối tượng trong CSDL.

`Select specific database objects`: Chọn các đối tượng CSDL cụ thể. 

Sau khi chọn, nhấn Next. 

![image](https://user-images.githubusercontent.com/111716161/191435724-26f00aa2-486c-430e-828d-9c545a796532.png)

- Để xuất file .sql kèm dữ liệu thì cần cấu hình như sau: Chọn Save as script file.

![image](https://user-images.githubusercontent.com/111716161/191436955-fefc46ae-ecea-4caa-aa1e-fd39a3e89134.png)

Chọn Advanced -> Tại: Types of data to script chọn Schema and data (Có cả dữ liệu trong file xuất ra) -> OK -> Next.

![image](https://user-images.githubusercontent.com/111716161/191435984-8ba7520d-74ef-4230-89d9-8863193db7f1.png)

- Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/191437028-38fac58d-db33-48a9-843a-47d56781a3ea.png)

- Kiểm tra tình trạng xuất file, sau đó nhấn Finish để hoàn tất.

![image](https://user-images.githubusercontent.com/111716161/191436286-130f306a-6f70-4f1c-8080-40f9700f8a23.png)

Một file .sql đã được tạo.

![image](https://user-images.githubusercontent.com/111716161/191437186-b7e14db5-33b3-4be4-88e7-c862b3ba4c4c.png)

Bước 2: Mở file trong SQL Server

- Chọn File -> Open -> File...

![image](https://user-images.githubusercontent.com/111716161/191439277-c1591451-b6ef-4d2d-ba3d-c834fea918b7.png)

- Chọn file script.sql để mở. 

![image](https://user-images.githubusercontent.com/111716161/191439430-6dc99941-7e78-44f3-ad6d-fe9ff6ea8f60.png)

![image](https://user-images.githubusercontent.com/111716161/191439569-918c7aa7-7b9b-46e4-a20f-e9aae626e94a.png)

- Tạo một database giống với tên của database cũ để chứa dữ liệu sắp nhập vào.

![image](https://user-images.githubusercontent.com/111716161/191439775-7b0077da-d8da-4375-90df-c457dea29947.png)

-  Chọn all câu lệnh và nhấn Execute. Như vậy toàn bộ dữ liệu của database đã được chuyển qua thành công. 

![image](https://user-images.githubusercontent.com/111716161/191439933-e947be86-9e6f-4205-9c55-afcfd3ddc518.png)

# Back up database

Bước 1: Chuột phải database -> Task -> Backup...

![image](https://user-images.githubusercontent.com/111716161/191442511-073c550c-5339-4aff-b3e7-cc1e5a1bbc8f.png)

Bước 2: Chọn đường dẫn mặc định để lưu file hoặc thêm đường dẫn mới. 

![image](https://user-images.githubusercontent.com/111716161/191442920-fedac984-261b-4527-b33d-3038a7449f0e.png)

Backup thành công. 

![image](https://user-images.githubusercontent.com/111716161/191443018-b9adbdec-7406-41e9-b83a-4ef325ccf43c.png)

Xem file backup. 

![image](https://user-images.githubusercontent.com/111716161/191443205-be37275a-db43-4592-a854-5fb3809c3916.png)

# Restore Database

Bước 1: Chuột phải database -> Task -> Restore -> Database...

![image](https://user-images.githubusercontent.com/111716161/191444928-8b11becc-2606-4e0d-af47-63b36a303e54.png)

Bước 2: Chọn Device -> Dấu "..."

![image](https://user-images.githubusercontent.com/111716161/191445319-4748eb7e-2037-4d7c-8e6e-8c65f31330d0.png)

Bước 3: Chọn Add -> chọn file backup -> OK.

![image](https://user-images.githubusercontent.com/111716161/191443923-2103a75c-6ade-4e2c-bec6-7c4fd44ce3bf.png)

Bước 4: Nhấn Ok.

![image](https://user-images.githubusercontent.com/111716161/191444021-d5c2704c-f5fd-4f31-92cd-e95c0bde7bc4.png)

Bước 5: Nhấn Ok để hoàn tất.

![image](https://user-images.githubusercontent.com/111716161/191445500-93817707-ebe8-43e4-9922-23c7c8271730.png)

