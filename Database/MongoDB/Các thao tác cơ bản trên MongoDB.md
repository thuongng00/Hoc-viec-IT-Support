## 1. Thao tác với Database

Database là một container vật lý cho các collection. Mỗi DB được thiết lập cho riêng nó một danh sách các files hệ thống files. Một máy chủ MongoDB đơn thường có nhiều DB.

- Tạo database.

```
USE database_name
```

![image](https://user-images.githubusercontent.com/111716161/190946017-fb07d90d-7f59-4f11-ae35-65ccd58cdd8b.png)

- Kiểm tra đang sử dụng database nào. 

```
db
```

![image](https://user-images.githubusercontent.com/111716161/190946058-fea0b789-0519-4be6-a8ae-be02d5ce9b5a.png)

- Xem danh sách database trong server. 

```
SHOW dbs
```

![image](https://user-images.githubusercontent.com/111716161/190946130-aba677b4-c856-44f2-8fbf-737a081e28f9.png)

DB của bạn vừa mới create ko có ở đây. Bạn phải insert một documents về nó vào list.

```
db.movie.insert({"name":"tutorials point"})
```

![image](https://user-images.githubusercontent.com/111716161/190946357-0d8b8859-ac22-455e-853b-723c480967c7.png)

- Xóa database.

```
db.dropDatabase()
```

![image](https://user-images.githubusercontent.com/111716161/190946393-e11b0ac2-ebb3-4e50-bacf-e9390544b166.png)

## 2. Thao tác với Collection

Collection là một nhóm các documents của MongoDB. Nó tương đương với một table trong RDBMS. Một Collection tồn tại trong một cơ sở dữ liệu duy nhất. Các collection ko tạo nên một schema. Documents trong collection có thể có các fields khác nhau. Thông thường, tất cả các documents trong collections có mục đích khá giống nhau hoặc liên quan tới nhau.

**Tạo một Collection**

```
db.createCollection(name, options)
```

Trong đó: 

`name`: yêu cầu phải là một string.

*Kiểu dữ liệu*
  - String: String trong MongoDB phải là UTF-8 hợp lệ.
  - Integer: Số nguyên có thể là 32 bit hoặc 64 bit tùy   - thuộc vào máy chủ của bạn.
  - Boolean
  - Double
  - Min/ Max keys: Loại này được sử dụng để so sánh giá trị đối với các yếu tố thấp nhất và cao nhất BSON.
  - Array
  - Timestamp
  - Object
  - Null
  - Symbol
  - Date
  - Object ID
  - Binary data
  - Code
  - Regular expression
`option`: chứa khá nhiều thông số về capped, autoIndexId, size, max. 

`capped` là một tập hợp các collection có size fixed và tự động viết đề lên các entries cũ của nó khi chạm đến max size. Nếu bạn cho nó true thì bạn phải điền size với lại max. 

`autoIndexID` sẽ tự động tạo một index trên biến _id field.s Mặc định giá trị này là false.

![image](https://user-images.githubusercontent.com/111716161/190946613-ddca19e8-8665-4f98-83ec-92d61c8110e1.png)

**Xem các collection**

```
show collections
```

![image](https://user-images.githubusercontent.com/111716161/190946703-452a5d48-ea22-421b-8c07-f68799e359c8.png)

**Xóa một collection**

```
db.COLLECTION_NAME.drop()
```

![image](https://user-images.githubusercontent.com/111716161/190946765-451e0559-8a3a-4baa-bae5-9b64fe329cb6.png)

## 3. Thao tác với Document

Một document là một tập hợp các cặp key-value. Documents có schema động. Schema động có nghĩa là documents trong cùng một collection không cần phải có cùng một nhóm các fields hay cấu trúc giống nhau, và các fields phổ biến trong các documents của collection có thể chứa các loại dữ liệu khác nhau.

- Thêm một document

```
db.COLLECTION_NAME.insert(document)
```

Nếu muốn insert nhiều documents trong một lệnh, bạn cần cho array vào trong lệnh insert().

- Tìm kiếm Collection

```
db.COLLECTION_NAME.find()
```
Để hiện thể kết quả đẹp hơn. Bạn có thể dùng thêm phương thức pretty()

- Cách sử dụng find AND trong MongoDB

```
db.mycol.find({key1:value1, key2:value2}).pretty()
```

- Cách sử dụng find OR trong MongoDB

```
db.mycol.find(
   {
      $or: [
         {key1: value1}, {key2:value2}
      ]
   }
).pretty()
```

- Sửa đổi một collection

```
db.COLLECTION_NAME.update(SELECTIOIN_CRITERIA, UPDATED_DATA)
```

Có thể update nhiều documents bằng cach truyền một param 'multi' cho nó true.

```
db.mycol.update({'title':'MongoDB Overview'},
   {$set:{'title':'New MongoDB Tutorial'}},{multi:true})
```

- Lưu collection

```
db.COLLECTION_NAME.save({_id:ObjectId(),NEW_DATA})
```

