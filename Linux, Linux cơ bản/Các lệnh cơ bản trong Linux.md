### 1. pwd

Sử dụng lệnh pwd để tìm ra đường dẫn của thư mục (folder) làm việc hiện tại mà bạn đang đứng.

Lệnh này sẽ trả về một đường dẫn tuyệt đối (đầy đủ), về cơ bản là đường dẫn của tất cả các thư mục bắt đầu bằng dấu gạch chéo lên (/).

![image](https://user-images.githubusercontent.com/111716161/187575406-02cb4bcd-59d7-44bf-9204-1aa3902c2f7c.png)

### 2. cd

Để điều hướng qua các tệp và thư mục Linux, hãy sử dụng lệnh cd.

Nó yêu cầu đường dẫn đầy đủ hoặc tên của thư mục, tùy thuộc vào thư mục làm việc hiện tại mà bạn đang ở.

Có một số phím tắt giúp bạn điều hướng nhanh chóng hơn:
```
cd .. (2 dấu hai chấm) để di chuyển một cấp lên thư mục bên trên thư mục hiện tại
cd để chuyển thẳng đến thư mục chính
cd - (có dấu gạch ngang) để chuyển đến thư mục trước của bạn
cd / để chuyển đến thư mục gốc
```

![image](https://user-images.githubusercontent.com/111716161/187575608-da0260fd-8723-4d51-b7f9-f3b8b892ac11.png)

### 3. ls 

Lệnh ls được sử dụng để xem nội dung của một thư mục. Theo mặc định, lệnh này sẽ hiển thị nội dung của thư mục làm việc hiện tại của bạn.

Nếu bạn muốn xem nội dung của các thư mục khác, hãy nhập ls rồi đến đường dẫn của thư mục.

Có các biến thể bạn có thể sử dụng với lệnh ls:
```
ls -R cũng sẽ liệt kê tất cả các tệp trong các thư mục con
ls -a sẽ hiển thị các tệp ẩn
ls -al sẽ liệt kê các tệp và thư mục với thông tin chi tiết như quyền, kích thước, chủ sở hữu, v.v.
```

![image](https://user-images.githubusercontent.com/111716161/187575965-a3e9f1a6-55e9-4111-9cdc-617e7d6cebd8.png)

### 4. cat

cat (viết tắt của concatenate) là một trong những lệnh được sử dụng thường xuyên nhất trong Linux.

Nó được sử dụng để liệt kê nội dung của một tệp trên đầu ra chuẩn (sdout).

Để chạy lệnh này, hãy nhập cat, theo sau là tên tệp và phần mở rộng của nó.

Dưới đây là các cách khác để sử dụng lệnh cat:
```
cat > filename để tạo một tệp mới tên là filename
Cat filename1 filename2>filename3 kết hợp hai tệp (1 và 2) và lưu trữ kết quả đầu ra của chúng trong một tệp mới (3)
Để chuyển đổi một tệp sang sử dụng chữ hoa hoặc chữ thường, cat filename | tr a-z A-Z>output.txt
```

