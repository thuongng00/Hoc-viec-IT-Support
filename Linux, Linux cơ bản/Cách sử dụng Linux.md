# Cấu trúc thư mục trong Linux

Cấu trúc thư mục trong Linux là danh sách các folder được xắp xếp bên trong hệ điều hành Linux, qua đó dữ liệu sẽ được lưu trữ đúng nơi vị trí của nó. Ví dụ các phần mềm được người dùng cài đặt thì sẽ lưu trong thư mục bin, cdrom sẽ là thư mục chứa thông tin về CD Room...

Mỗi hệ điều hành sẽ có một quy tắc riêng của nó và Linux cũng vậy. Với Windows thì bạn có thể tạo và sử dụng nhiều ổ đĩa cùng lúc như ổ C, ổ D, .. Còn Linux thì khác, khi được cài đặt thì nó chỉ sử dụng trên đúng ổ đĩa được cài đặt đó, và từ đó nó sẽ phân chia thành nhiều thư mục nhỏ khác.

## Danh sách cấu trúc thư mục trong Linux

Thư mục cấp cao nhất trong Linux chính là thư mục gốc /. Bên trong thư mục gốc là những thư mục nhỏ khác, mỗi thư mục sẽ có một ý nghĩa khác nhau.

| Folder	| Ý nghĩa |
|---------|---------|
| / | Đây là thư mục gốc (cấp cao nhất), chứa toàn bộ các thư mục phía dưới |
| /bin | Chứa các chương trình cài đặt vào Linux. |
| /etc	| Chứa file cấu hình hệ thống Linux, khởi động, tắt máy, bắt đầu, dừng script cho từng chương trình riêng lẻ. |
| /home |	Thư mục home, mỗi user sẽ có một thư mục bên trong này, chứa dữ liệu riêng cho từng user. Nếu là user root đang đăng nhập thì sẽ thấy tất cả các folder của users. |
| /opt |	Optional or third party software. |
| /tmp |	Chứa các file tạm, thường sẽ bị xóa khi khởi động lại máy tính. |
| /usr | Các chương trình thực thi, tài liệu, mã nguồn, thư viện cho chương trình cấp 2. |
| /var	| Chứa các file dữ liệu, thường là các file log hệ thống, file biến lưu trữ ... |
| /boot	| Chứa các file khởi động hệ thống (kernel, boot ..) |
| /dev	| Đây là thư mục chứa các file đặc biệt, bao gồm cả những file liên quan đến thiết bị phần cứng. Nó là các file ảo và không có ghi trên đĩa cứng. |
| /root	| Đây là thư mục gốc của người dùng (người đang sử dụng máy tính), đừng nhầm lẫn với thư mục gốc của máy tính nhé. |
| /proc	| Một hệ thống file ảo và giả chứa thông tin về quá trình chạy với một quy trình Process id id aka pid. |

## Xem danh sách các file và folder trong Linux
Để xem danh sách các file và folder trong Linux thì bạn phải đăng nhập bằng tài khoản root, sau đó sử dụng ứng dụng quản lý file của Linux hoặc là bằng dòng lệnh command line.

Nếu sử dụng giao diện GUI thì bạn vào File -> Computer thì sẽ thấy danh sách folder.

# Cách sử dụng Terminal trên Linux

Terminal là một ứng dụng thực thi dòng lệnh trên Linux, được tích hợp sẵn trong Linux nên bạn chỉ việc gọi ra để sử dụng.

Với terminal thì bạn có thể chạy mọi lệnh, nó sẽ tiếp nhận lệnh và thực thi chúng, sau đó trả kết quả trên màn hình. Nếu bạn đã từng sử dụng Windows Command Line thì Terminal có công dụng y như vậy.

Để mở Terminal thì bạn hãy nhập từ khóa "terminal" vào khung search của Linux.

Để chạy lệnh gì thì bạn chỉ cần gõ lệnh đó vào terminal và nhấn Enter để nó thực thi.

# Biến môi trường trong Linux

Khi làm việc trên máy tính chúng ta cần những thông tin như tên phiên bản hệ điều hành (HĐH) đang chạy, tên thư mục home, thư mục chứa lệnh chương trình …

Một khái niệm quan trọng trên linux đó là môi trường (environment) được định nghĩa qua các biến môi trường. Một số biến được đặt bởi hệ thống, số khác do bạn đặt, hoặc set bởi shell (các lệnh) hay từ một chương trình nào đó.

Một biến môi trường có tên là một dãy chữ cái và nhận một giá trị nhất định, giá trị này có thể là số, chữ, tên file, thiết bị (device) hay một kiểu dữ liệu nào đó, đặc biệt là các biến không được trùng nhau.

Trên Linux: Bạn có thể set và get ra biến môi trường như sau:

```
1. TEST=”Linux programming”
2. echo $TEST
3. Linux programming
```

Các bạn để ý khi khai báo biến TEST chúng ta không dùng dấu $, dấu $ đầu dòng là ký hiệu của bash trên terminal. Khi truy cập giá trị biến TEST thì cần thêm dấu $ thành echo $TEST. Những biến khai báo trực tiếp trên terminal kiểu này sẽ không giữ được khi bạn thoát khỏi Terminal.

## Danh sách biến môi trường và cách cài đặt

### Biến $PATH
Biến PATH cho thấy đường dẫn tới các thư mục chứa câu lệnh (chương trình) để chạy khi bạn gõ trên terminal, các mục cách nhau dấu “:” ví dụ /usr/local/sbin; /usr/local/bin...

Với biến PATH như trên thì bạn không cần biết ffmpeg, imagick cài ở đâu, mỗi khi bạn gõ lệnh ffmpeg hay convert (của imagick) trên terminal thì hệ thống tự biết tìm đến mục chứa nó để chạy.

Muốn hiện đường dẫn tuyệt đối của một lệnh thì bạn gõ lệnh whereis:

```
1. whereis ffmpeg
2. ffmpeg: /usr/local/bin/ffmpeg
```

Muốn hiện hết các mục chứa chương trình (câu lệnh) thì bạn echo $PATH:

```
1. echo $PATH 
2. /usr/lib/jvm/java-7-openjdk-i386/bin:/home/nickfarrow/bin:/usr/lib/lightdm/lightdm:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/home/nickfarrow/Public/android-sdk-linux/tools:/home/nickfarrow/Public/android-sdk-linux/platform-tools:/home/nickfarrow/Public/android-ndk-r9d::/home/nickfarrow/D/DPublic/Google/google_appengine/
```

### HOME 
Đường dẫn tới thư mục home của người dùng hiện tại, để tiện lợi hơn bạn có thể thay bằng dấu ~ trong nhiều trường hợp.

### TERM (terminal)

### DISPLAY
Số (mã) màn hình mặc định các ứng dụng đồ họa sẽ chạy trên đó.

Việc thiết lập giá trị cho các biến môi trường khá đơn giản. Trên Linux các biến môi trường lưu trong mục home của người dùng: .bashrc, .bash_profile, .bash_aliasses, /etc/profile ... Biến môi trường quan trọng nhất là PATH, nó lưu vị trí các mục chứa chương trình chạy trên hệ thống, thường là /usr/bin /bin, /usr/local/bin /sbin
