# Linux
Linux là một hệ điều hành máy tính mã nguồn mở, cách hoạt động giống như các hệ điều hành khác như: Microsoft Windows, Apple Mac OS, iOS, Google android ... Đây là một HĐH sử dụng cả giao diện GUI và command line.

Nhiệm vụ của Linux là cho phép giao tiếp giữa phần cứng và phần mềm máy tính, xử lý tiếp nhận thông tin đầu vào và trả kết quả ra màn hình, đây chính là chứ năng cơ bản nhất của một hệ điều hành.

Linux xuất hiện giữa những năm 90, nó đã từng được sử dụng phát triển cho đồng hồ, và đến nay là được đưa vào máy tính. Nó có ở khắp mọi nơi như trong điện thoại, máy tính xách tay, PC, ô tô và thậm chí trong tủ lạnh của chúng ta. Nó rất nổi tiếng trên các cộng đồng lập trình viên, cũng như những người sử dụng bình thường yêu thích sử dụng máy tính bằng command line.

Đối với Windows, nếu bạn muốn cài đặt một phần mềm nào đó thì sẽ lên trang chủ để tải về, sau đó cài đặt bằng cách sử dụng chuột để thao tác trên giao diện đồ họa GUI. Nhưng với Linux thì khác, hầu như những thao tác này đều thực hiện bằng command line, bởi trên Linux có một kho lưu trữ dữ liệu (ta gọi là repo), bạn chỉ cần chạy lệnh cài đặt là được. Đương nhiên chỉ những phần mềm nào được tích hợp trên repo đó.

Hệ điều hành là tập hợp nhiều phần mềm khác nhau, và mỗi phần mềm có một nhiệm vụ khác nhau.

Hệ điều hành Linux có những thành phần dưới đây:

![image](https://user-images.githubusercontent.com/111716161/187139312-26c2a276-5d3b-4175-afca-0cafd0d4460f.png)

### Kernel
Kernel chính là phần nhân của linux, là thành phần quan trọng nhất và có nhiệm vụ thiết lập giao tiếp giữa các phần mềm và thiết bị phần cứng. Hơn thế nữa, nó còn đảm nhận việc quản lý tài nguyên của hệ thống.

Nó có bốn nhiệm vụ chính như sau:

- Quản lý thiết bị: Một máy tính sẽ có nhiều thiết bị như CPU, RAM, card âm thanh, card đồ họa, v.v. kernel sẽ lưu trữ tất cả dữ liệu liên quan đến tất cả các thiết bị trong trình điều khiển thiết bị driver (nếu không có kernel thì sẽ không thể để điều khiển các thiết bị). Do đó kernel biết mỗi thiết bị có thể làm gì và thao tác với nó như thế nào để mang lại hiệu suất tốt nhất.
- Quản lý bộ nhớ: Một chức năng khác đó là quản lý bộ nhớ. Kernel theo dõi bộ nhớ đã sử dụng và chưa sử dụng và đảm bảo rằng các tiến trình không được sử dụng dữ liệu của nhau bằng địa chỉ bộ nhớ ảo.
- Quản lý quy trình: Kernel chỉ định đủ thời gian và ưu tiên cho các quy trình trước khi CPU xử lý cho các quy trình khác.
- Xử lý lệnh gọi hệ thống: Xử lý lệnh gọi hệ thống có nghĩa là một lập trình viên có thể viết một truy vấn hoặc yêu cầu Karnel thực hiện một tác vụ nào đó.

### System Libraries
System Libraries là những thư viện / phần mềm đặc biệt giúp truy cập vào các tính năng của Karnel. Mỗi Karnel sẽ phải được kích hoạt để thực hiện một tác vụ các ứng dụng sẽ hoàn thành những tác vụ đó.

### System Tools
Hệ điều hành Linux có một tập hợp các công cụ tiện ích, thường là các lệnh command line đơn giản. Nó là một phần mềm mà dự án GNU đã viết và xuất bản theo giấy phép mã nguồn mở của họ, nhằm giúp phần mềm cung cấp miễn phí cho tất cả mọi người.

Với sự trợ giúp của các lệnh, bạn có thể truy cập file của mình, chỉnh sửa và thao tác dữ liệu trong thư mục hoặc file của bạn, thay đổi vị trí của file hoặc bất cứ một thao tác nào khác.

### Development Tools
Với ba thành phần trên là hệ điều hành Linux có thể hoạt động được rồi đấy. Nhưng nhằm giúp các nhà phát triển có thể cập nhật hệ thống, cũng như tạo ra những công cụ khác thì Linux cho phép lập trình viên sử dụng những công cụ riêng của nó, ta gọi là toolchain.

### End User Tools

Đây chính là tập hợp những phần mềm mà người dùng cài vào máy tính để sử dụng như: Trình duyệt web, phần mềm nghe nhạc, office ...

# Lý do nên sử dụng Linux

Linux là một mã nguồn mở: Nghĩa là bạn sẽ cài đặt miễn phí và không tốn một đồng nào cả. Nếu bạn sử dụng Windows thì sẽ phải bỏ ra một khoản tiền lớn để mua key bản quyền.

Linux an toàn hơn Windows: Điều này hoàn toàn đúng, bởi Linux hỗ trợ các tùy chọn bảo mật khác nhau sẽ giúp bạn tránh khỏi vi rút, phần mềm độc hại, làm chậm máy, treo máy. Hơn nữa, nó sẽ giữ cho dữ liệu của bạn được bảo vệ. Với tính năng bảo mật này khiến nhiều nhà phát triển lựa chọn nó hơn là Windows, đương nhiên không phải nó luôn luôn an toàn, mà có chút phụ thuộc vào cách sử dụng cua mỗi người.

Linux là hệ điều hành linh hoạt và ứng dụng đa dạng: Vì nó có thể được sử dụng cho các ứng dụng máy tính để bàn, hệ thống nhúng và ứng dụng máy chủ server. Nó có thể được sử dụng từ đồng hồ đeo tay đến siêu máy tính. Nó có ở khắp mọi nơi trong điện thoại, máy tính xách tay, PC, ô tô và thậm chí trong tủ lạnh của chúng ta.

Linux ổn định: Linux ổn định hơn các hệ điều hành khác. Linux không yêu cầu phải khởi động lại hệ thống để lấy lại hiệu suất. Nó hiếm khi bị treo, điều mà ta thường thấy ở Windows.

Giao diện đồ họa + command line: Đây chính là đặc điểm rất hay trên Linux, nó vừa hỗ trợ giao diện GUI vừa hỗ trợ command line.

Cộng đồng lớn: Có rất nhiều cộng đồng riêng về Linux ra đời, bởi vì nó là một mã nguồn mở nên kiến thức chia sẻ rất phổ biến.

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
