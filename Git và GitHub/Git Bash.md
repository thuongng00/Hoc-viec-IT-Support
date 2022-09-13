# Git bash

**Git bash** là một tập hợp các chương trình tiện ích command line được thiết kế để thực thi trên môi trường Windows. Nhiều hệ điều hành như Linux và macOS có tích hợp sẵn các UNIX command line terminal. Nó làm cho hệ điều hành Linux và macOS bổ sung cho nhau khi làm việc với Git.

![image](https://user-images.githubusercontent.com/111716161/189792597-64b891ec-564a-40ad-82dc-d00c6376ad68.png)

Windows không có giao diện UNIX style command. Thay vào đó, Microsoft Windows sử dụng command prompt của Windows, không phải là một thiết bị UNIX terminal. Do đó, Git for Windows cung cấp một giả lập Bash để chạy Git từ command line. 

Git Bash là một ứng dụng bổ sung thêm một layer giả lập trên môi trường Microsoft Windows để trải nghiệm Git command line. Nó giống như một package cài đặt một số tiện ích bash phổ biến trên hệ điều hành Windows. Mặt khác, nó cho phép chúng ta sử dụng tất cả tính năng Git cũng như hầu hết các UNIX command tiêu chuẩn trong giao diện command line trên Windows.

# Khái niệm cơ bản trong Git bash

### 1. Repository

Repository là nơi chứa cơ sở dữ liệu của Git bash. Đây là những dữ liệu quan trọng để duy trì, quản lý lịch sử của dự án. Hai cấu trúc dữ liệu chính thường dùng trong Repository là Index và Store.

![image](https://user-images.githubusercontent.com/111716161/189793185-d26b2238-a0ea-4a30-a0c7-6ffddf4e7392.png)

### 2. Object store

Object store là trung tâm, nơi chứa dữ liệu gốc của Git bash. 

Có 4 loại Object store cần chú ý gồm:
- Blobs: File chứa mọi dữ liệu biểu diễn dưới dạng nhị phân.
- Trees: Lớp đại diện cho thông tin thư mục. 
- Commits: Chứa metadata gồm các thông tin như thông tin log, người tải lên, tên tác giả, ngày tải lên...
- Tags: Đánh dấu giúp việc đọc dễ dàng hơn. 

### 3. Index

Index là khái niệm dùng để miêu tả trạng thái dự án, cấu trúc thư mục của Repo. Index được biểu diễn dưới dạng file nhị phân động.

*Các lợi ích khi dùng Git bash*:
- *Tối ưu hóa công việc: Git bash cho phép người dùng giải quyết từng Task mà không sợ ảnh hưởng tới những Task liên quan. Điều đó giúp bạn chủ động sắp xếp công việc linh hoạt khi thực hiện nhiều Task cùng lúc.*
- *Phát triển những ý tưởng mới: Git bash giúp bạn tự tin hơn trong việc sáng tạo và phát triển những ý tưởng mới.*

# Cài đặt Git bash

Bước 1: Tải Git bash về máy, mở file cài đặt.

Bước 2: Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189794768-92876723-f37a-4346-9a44-cacaf549e957.png)

Bước 3: Chọn đường dẫn lưu trữ rồi nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189794815-0b950bcb-ff35-4917-92f3-e2282d89b9e2.png)

Bước 4: Chọn "Additional icon on the desktop" nếu muốn tạo biểu tượng Git bash trên màn hình desktop. Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189794878-8995319b-7252-4332-bb64-9ad43cd8f108.png)

Bước 5: Nếu không muốn tạo thư mục Git thì check "Don't create Start Menu Folder". Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189794942-48eefad5-69b1-40b4-944f-7a78b5640e12.png)

Bước 6: Tiếp tục nhấn Next cho đến khi hiện tùy chọn Install.

![image](https://user-images.githubusercontent.com/111716161/189795108-8de4e70a-741a-494c-b903-62dc65b8e8f5.png)

Bước 7: Nhấn Install để tiến hành cài đặt.

![image](https://user-images.githubusercontent.com/111716161/189795216-3bf56e3a-f850-4e57-a8a1-456fe636c72f.png)

![image](https://user-images.githubusercontent.com/111716161/189795302-d9b99903-b282-4ed6-8558-bfce1746dff7.png)

![image](https://user-images.githubusercontent.com/111716161/189795349-0ea4a45d-3390-46a2-9616-6d574898cc97.png)

Như vậy là ta đã cài đặt xong Git bash cho Windows.

# Các câu lệnh trong Git bash thường sử dụng

1. Thiết lập chứng thực cá nhân

```
git config --global user.name "User name"
git config -- global user.email "username@gmail.com"
```

*Lưu ý: Khi sử dụng lệnh -global, thiết lập chứng thực cá nhân áp dụng cho toàn bộ project. Nếu không, thiết lập này chỉ dùng riêng cho project chứa lệnh.*

2. Tạo kho chứa Git bash

```
git init
```

Lệnh này giúp tạo thư mục mới có tên .git và là kho chứa tất cả các tập tin cần thiết. Bạn có thể theo dõi các dự án đã thực hiện thông qua kho chứa này. 

3. Sao chép kho chứa Git bash đã tồn tại

```
git clone https://github.com/user/repository.git
```

Sử dụng lệnh để sao chép repo bằng giao thức https.

4. Tạo nhánh trong Git bash

Git bash cho phép tạo nhiều nhánh (branch) bằng các lệnh sau: 
- Tạo một nhánh mới: `git branch <name_branch>`
- Kiểm tra nhánh hiện tại: `git branch`
- Di chuyển và tạo mới: `git checkout -b <name_branch>`

5. Chuyển nhánh trong Git bash

Checkout code là yêu cầu bắt buộc nếu muốn chuyển nhánh, thay đổi source code.

```
git checkout <name_branch>
```

6. Gộp nhánh trong Git bash

Quá trình gộp nhánh gồm 2 bước là checkout khỏi nhánh hiện tại và tiến hành gộp code (merge) vào nhánh gốc (master). 

```
git checkout master
git merge <new_branch>
```

7. Cập nhật thay đổi trong Git bash

Sau quá trình thực hiện thao tác thêm, sửa, xóa dữ liệu trong source code, bạn cần cập nhật những thay đổi này lên Staging Area bằng lệnh:

```
git add .
```

Sau đó, những thay đổi này cũng cần được cập nhật lên Local Repository bằng lệnh sau:
```
git commit -m "Message"
```

8. Cập nhật lên server

Trước khi cập nhật thông tin lên server, bạn cần xác định đã tồn tại remote trên server chưa. Nếu chưa, cần add remote trước theo lệnh sau:

```
git remote add origin <remote_url>
```

Sau đó, cập nhật thông tin thay đổi lên server:

```
git push origin <name_branch>
```

9. Xem lại lịch sử trong Git bash

Xem lịch sử người chỉnh sửa, ngày giờ, nội dung mỗi lần chỉnh sửa trong Git bash.

```
git log
```
10. Xem thay đổi trước khi push

Xem những thay đổi giữa nhánh đã được cập nhật và nhánh chưa được cập nhật.

```
git diff
```
