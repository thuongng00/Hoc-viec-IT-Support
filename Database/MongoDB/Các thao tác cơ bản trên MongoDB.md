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

![image](https://user-images.githubusercontent.com/111716161/190947776-78da775d-3fda-463a-99ff-bbd2bd405983.png)

Nếu muốn insert nhiều documents trong một lệnh, bạn cần cho array vào trong lệnh insert().

- Tìm kiếm Collection

```
db.COLLECTION_NAME.find()
```

![image](https://user-images.githubusercontent.com/111716161/190947911-ffd6476f-7e57-48fc-bbfd-2cd0c214a77e.png)

Để hiện thể kết quả đẹp hơn. Bạn có thể dùng thêm phương thức pretty().

![image](https://user-images.githubusercontent.com/111716161/190948202-b3ef0573-d4d9-447e-9d47-6b842964e654.png)

- Cách sử dụng find AND trong MongoDB

```
db.COLLECTION_NAME.find({key1:value1, key2:value2}).pretty()
```

- Cách sử dụng find OR trong MongoDB

```
db.COLLECTION_NAME.find(
   {
      $or: [
         {key1: value1}, {key2:value2}
      ]
   }
).pretty()
```

![image](https://user-images.githubusercontent.com/111716161/190950215-4b49bdbe-34ea-471b-a385-0c852672bbd4.png)

- Sửa đổi một collection

```
db.COLLECTION_NAME.update(SELECTIOIN_CRITERIA, UPDATED_DATA)
```

![image](https://user-images.githubusercontent.com/111716161/190950491-c666d674-dd20-4d47-a37f-3a5f378b72da.png)

Có thể update nhiều documents bằng cach truyền một param 'multi' cho nó true.

- Lệnh SAVE

```
db.COLLECTION_NAME.save({_id:ObjectId(),NEW_DATA})
```

- Projection

Trong mongodb, projection có nghĩa là bạn chỉ cần chọn những dữ liệu cần hthieets thay vì select hết mọi dữ liệu của documents. Nó khác find trong find Collection ở chỗ là find thì tìm kiếm dữ liệu document trong collection. Còn khía niệm này sẽ tìm kiếm kết quả fields trong documents. ví dụ bạn cần hiển thị 3 fields kết quả trong 5 fields của một documents.

```
db.COLLECTION_NAME.find({},{KEY:1})
```

- Limit Records

Để giới hạn số lượng records trong MongoDB, bạn sẽ dùng phương thức limit(). Limit() sẽ chấp nhận số lượng record giới hạn thông qua argument mà bạn truyền vào. Nó sẽ thể hiện số lượng documents bạn muốn hiển thị.

```
db.COLLECTION_NAME.find().limit(NUMBER)
```

- Sort Records

Để sort các document trong MongoDB, bạn cần phải sử dụng sort(). sort() cho pehsp một document trong chứa các fields theo thứ tự order. có 2 loại thứ tự, 1 sẽ tương đương với ascending và -1 sẽ tương đương với descending.

```
db.COLLECTION_NAME.find().sort({KEY:1})
```

- Indexing

Index hỗ trợ độ phân tích một cách hiệu quả các truy vấn. Nếu không có chỉ mục, MongoDB sẽ phải quét tất cả các documents của collection để chọn ra những document phù hợp với câu truy vấn. Quá trình quét này là không hiệu quả và yêu cầu MongoDB để xử lý một khối lượng lớn dữ liệu.

Index là những cấu trúc dữ liệu đặc biệt, dùng để chứa một phần nhỏ của các tập dữ liệu một cách dễ dàng để quét. Chỉ số lưu trữ giá trị của một fields cụ thể hoặc thiết lập các fields, sắp xếp theo giá trị của các fields này.

```
db.COLLECTION_NAME.ensureIndex({KEY:1})
```

- Aggregation

Aggregation xử lý các record dữ liệu va trả về kết quả đã tính toán rồi. Aggregation sẽ group giá trị từ nhiều documents khác nhau và có thể tiến hành xử lý rất nhiều nhóm dư liệu để trả về một kết quả đơn lẻ. Xử lý này tương đương với count trong SQL.

```
db.COLLECTION_NAME.aggregate(AGGREGATE_OPERATION)
```
