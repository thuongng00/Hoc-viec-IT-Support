# Bash Shell

## 1. Viết script nhập xuất thông tin

- Sử dụng bất kỳ chương trình soạn thảo (vi, nano, vim...) để tạo script có tên yeucau1.sh có nội dung nhập tên, địa chỉ. Sau đó thực hiện lệnh chạy script này và hiện kết quả.
- Sử dụng lệnh `echo` để xuất thông tin và `read` để đọc dữ liệu nhập vào, các dữ liệu nhập sẽ được lưu vào các biến có dạng $<tên biến>

![image](https://user-images.githubusercontent.com/111716161/189596770-9b9a5053-17ce-4643-936a-85b35ed2fde7.png)

![image](https://user-images.githubusercontent.com/111716161/189596639-e3d5cb29-8c24-4dec-a69a-07c0bcb03ed3.png)

## 2. Viết script hiển thị thông tin thư mục

- Viết script yeucau2.sh liệt kê tất cả tệp có trong thư mục /etc và ghi vào file danhsachtep.txt.
- Sử dụng `ls` để liệt kê, `grep` để lọc và `>` để ghi kết quả vào file.

![image](https://user-images.githubusercontent.com/111716161/189611474-2590f4b2-9ed8-4a1d-9bb6-ca97d374f7a2.png)

![image](https://user-images.githubusercontent.com/111716161/189599269-ee67a57d-efbc-434f-9afe-1cbd499c8b0e.png)

## 3. Viết script đếm số lượng

- Viết script yeucau3.sh đếm số lượng file có trong thư mục do người dùng truyền vào, nếu thư mục người dùng truyền vào không tồn tại hoặc không chứa tập tin nào thì xuất ra thông báo: "thu muc nay khong ton tai hoac khong chua tap tin nao".
- Sử dụng biến count để tính số lượng file, kiểm tra trường hợp count = 0.
- Sử dụng lệnh ls để liệt kê, wc để đếm. 

![image](https://user-images.githubusercontent.com/111716161/189619794-5beb8c0a-e361-4e95-be27-fed32fdbe3d0.png)

## 4. Viết script tìm kiếm

- Viết script yeucau4.sh cho phép người dùng nhập tên file và đường dẫn, sau đó tìm kiếm file tại đường dẫn vừa nhập.
  - Nếu đường dẫn không tồn tại thì đưa ra thông báo "Duong dan khong ton tai"
  - Nếu file không tồn tại thì đưa ra thông báo "File khong ton tai"
  - Nếu file tồn tại thì đưa ra thông báo "Tim thay file tai duong dan"
  
## 5. Viết script kiểm tra user

- Viết script yeucau5.sh cho phép người dùng nhập tên user. Sau đó hiện thông tin của user này, nếu user không tồn tại thì xuất thông báo "User khong ton tai"

## 6. Viết script back up

- Viết script yeucau6.sh cho phép người dùng backup thư mục /home và lưu vào thư mục /var/backups với định dạng home-yyyy-mm-dd.tgz

