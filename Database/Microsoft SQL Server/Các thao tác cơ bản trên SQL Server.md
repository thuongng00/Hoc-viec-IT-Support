## 1. Thao tác với database

- Tạo database mới: 

Cách 1: Vào File -> New -> Query with Current Connection hoặc tổ hợp phím Ctrl + N để tạo Query mới. 

![image](https://user-images.githubusercontent.com/111716161/191212258-9e4dcd19-6f74-4c18-bfc1-110f74aa3fcf.png)

Gõ lệnh:

```
CREATE DATABASE database_name;
```

Bôi đen dòng lệnh, nhấn chuột phải chọn Excute hoặc nhấn F5 để thực thi câu lệnh.

![image](https://user-images.githubusercontent.com/111716161/191215246-a8ea4d4b-6c9b-42bf-81d8-9a314e928dc5.png)

Database đã được tạo

![image](https://user-images.githubusercontent.com/111716161/191215334-b461776c-e9fe-4ef4-a845-ad6dafc564bf.png)

Cách 2: Nhấn chuột phải vào thư mục Database -> New database.

![image](https://user-images.githubusercontent.com/111716161/191213599-146dbb9f-68b9-4238-b5f2-8037239da0f2.png)

Nhập tên database, nhấn OK. 

![image](https://user-images.githubusercontent.com/111716161/191214351-d65dfddc-253f-45d5-8840-7b637bf72e70.png)

Database đã được tạo.

![image](https://user-images.githubusercontent.com/111716161/191215389-495498b7-c101-40b1-807b-65658f251833.png)

- Sử dụng một database

```
USE database_name;
```

![image](https://user-images.githubusercontent.com/111716161/191215880-7639be84-489b-41b6-941b-f57e3ac197ea.png)

- Xóa database

Cách 1: Sử dụng lệnh

```
DROP DATABASE database_name;
```

![image](https://user-images.githubusercontent.com/111716161/191216275-2c484c31-250f-48a2-aee6-3aa83b4c544e.png)

Cách 2: Nhấn chuột phải vào tên database, chọn Delete. 

![image](https://user-images.githubusercontent.com/111716161/191216386-b1d94c45-d92b-4b02-a832-b2de5cdd4cf2.png)

Nhấn OK để xóa.

![image](https://user-images.githubusercontent.com/111716161/191216507-9c07533f-7846-4d0d-8baf-829b69625b87.png)

## 2. Thao tác với bảng

- Tạo bảng:

Cách 1: Sử dụng lệnh:

```
CREATE TABLE table_name(column_name column_type);
```

![image](https://user-images.githubusercontent.com/111716161/191219738-bbb068d1-8f82-4ddb-81ba-fe673f82d5ab.png)

Cách 2: Nhấn chuột phải vào thư mục Tables thuộc database đang sử dụng, chọn New -> Table...

![image](https://user-images.githubusercontent.com/111716161/191217369-45951f57-e03a-45dc-8540-ee024b4b9a28.png)

Nhập tên cột, kiểu dữ liệu,...

![image](https://user-images.githubusercontent.com/111716161/191217670-0eddf3ce-9ef4-47ec-81d7-42a38294b146.png)

Nhấn chuột phải vào mũi tên trước tên cột muốn đặt khóa chính. 
 
![image](https://user-images.githubusercontent.com/111716161/191219248-b946cf59-a308-4ac3-876c-5da97184ca17.png)

Sau khi nhập xong, nhấn chuột phải vào tên file chọn Save.

![image](https://user-images.githubusercontent.com/111716161/191217818-b39d70b5-70d7-4db9-a5a9-6a19c71762eb.png)

Đặt tên bảng rồi nhấn ok

![image](https://user-images.githubusercontent.com/111716161/191219451-4adaabef-0e7a-4734-9ff6-10528c280ba3.png)

- Xóa bảng:

Cách 1: Sử dụng lệnh:

```
DROP TABLE table_name;
```

![image](https://user-images.githubusercontent.com/111716161/191221378-921660d2-ab4d-44c4-8be1-ed834038c715.png)

Cách 2: Nhấn chuột phải vào tên bảng, chọn Delete.

![image](https://user-images.githubusercontent.com/111716161/191220254-29498e73-8549-4da3-9c47-35440e91616f.png)

Nhấn OK để xóa.

![image](https://user-images.githubusercontent.com/111716161/191220333-adde0a03-d715-4bf2-8f67-c4adb1133702.png)

## 3. Thao tác với dữ liệu

- Thêm mới dữ liệu:

Cách 1: Sử dụng lệnh INSERT

```
INSERT INTO table_name (field1, field2,...) VALUES (value1, value2,...);
```
![image](https://user-images.githubusercontent.com/111716161/191221623-e26fca7e-800c-4838-a931-cec469f461e8.png)

Cách 2: Nhấn chuột phải vào tên bảng, chọn Edit Top 200 Rows.

![image](https://user-images.githubusercontent.com/111716161/191222339-146ebebd-20bd-462d-bf3b-ea9175742acf.png)

Nhập dữ liệu vào bảng

![image](https://user-images.githubusercontent.com/111716161/191222822-c9c8c559-bc86-4e7f-b347-efc0c080f9c9.png)

- Xem dữ liệu:

Cách 1: Sử dụng lệnh SELECT

```
SELECT field, field2,... FROM table_name WHERE...
```

![image](https://user-images.githubusercontent.com/111716161/191223119-b919e085-6643-4864-8b93-6d10cc07376b.png)

Cách 2: Chuột phải vào tên bảng, chọn Select Top 1000 Rows.

![image](https://user-images.githubusercontent.com/111716161/191223275-6dea3786-97ba-4fee-8c07-d883374c794f.png)

![image](https://user-images.githubusercontent.com/111716161/191223332-7c18ec70-964d-4f00-b9c4-904c57bde124.png)

- Cập nhật dữ liệu

Cách 1: Sử dụng lệnh UPDATE

```
UPDATE table_name SET field1=new_value1, field2=new_value2,... [WHERE ...]
```

![image](https://user-images.githubusercontent.com/111716161/191223663-5936f55b-b0f6-40fe-ba64-fdbb31483b47.png)

Cách 2: Nhấn chuột phải vào tên bảng, chọn Edit Top 200 Rows.

![image](https://user-images.githubusercontent.com/111716161/191223955-953e6b2a-eaf7-4e04-8456-cb87c233d1ed.png)

Chỉnh sửa dữ liệu trên bảng

![image](https://user-images.githubusercontent.com/111716161/191224033-eeb39aa0-7693-471c-a397-a99346934922.png)

Bảng sau khi được cập nhật:

![image](https://user-images.githubusercontent.com/111716161/191224161-3929d0d8-c3b6-4651-a719-ce894c5d8a47.png)

