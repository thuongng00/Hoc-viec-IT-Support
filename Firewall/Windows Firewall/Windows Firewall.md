# Windows Firewall

Windows Firewall (tên chính thức là Windows Defender Firewall trong Windows 10), là thành phần tường lửa của Microsoft Windows. 

Windows Firewall lần đầu tiên được bao gồm trong Windows XP và Windows Server 2003. Trước khi phát hành Windows XP Service Pack 2 vào năm 2004, nó được gọi là Tường lửa kết nối Internet. Với việc phát hành Windows 10 phiên bản 1709, vào tháng 9 năm 2017, nó đã được đổi tên thành Windows Defender Firewall như một phần của chiến dịch quảng bá thương hiệu "Windows Defender".

# Tác dụng của Windows Firewall

Nhiệm vụ cơ bản của Windows Firewall là kiểm soát giao thông dữ liệu giữa hai vùng có độ tin cậy khác nhau điển hình gồm:

- Mạng Internet (vùng không đáng tin cậy).

- Mạng nội bộ (một vùng có độ tin cậy cao).

Mục đích cuối cùng của Windows Firewall là cung cấp kết nối có kiểm soát giữa các vùng với độ tin cậy khác nhau thông qua việc áp dụng một chính sách an ninh và mô hình kết nối dựa trên nguyên tắc quyền tối thiểu.

![image](https://user-images.githubusercontent.com/111716161/194465410-e006215d-1215-4626-8265-0fbfef1a82e4.png)

Nguyên lý hoạt động của tường lửa là phân tách dữ liệu thành kết nối an toàn và kết nối không an toàn. Việc này sẽ gây khó khăn cho người dùng máy tính khi cài đặt thêm phần mềm, tiện ích của bên thứ ba như phần mềm Avast Free Antivirus, phần mềm KMSpico,… Hệ thống yêu cầu người dùng phải tắt tường lửa thì mới có thể cài đặt những phần mềm này.

Tuy nhiên, để ngăn chặn những nguy cơ Virus xâm nhập, bạn nên bật tường lửa để máy tính của mình được an toàn hơn.

# Cách tắt/mở Windows Firewall

### 1. Thông qua Control Panel

Bước 1: Mở Control Panel -> -> Chọn System and Security -> Chọn Windows Defender Firewall.

![image](https://user-images.githubusercontent.com/111716161/194465678-492fd78c-301f-473f-b645-87a5dbad5596.png)

Bước 2: Trong cửa sổ Windows Firewall bạn hãy nhấn vào mục Turn Windows Firewall on or off để có thể bắt đầu lựa chọn bật tắt tường lửa tùy ý.

![image](https://user-images.githubusercontent.com/111716161/194465792-a028eee6-8bb4-49ec-862f-ab428108b8ed.png)

Bước 3: Nhấn vào 2 ô tùy chọn Turn off windows firewall(not recommended) để tắt, Turn on Windows Defender Firewall và nhấn OK.

![image](https://user-images.githubusercontent.com/111716161/194465960-c5a31358-4483-4dab-82b0-41103765f849.png)

### Thông qua Command Prompt

Bước 1: Mở Command Prompt bằng cách nhập vào ô tìm kiếm từ khóa "cmd" hoặc nhấn tổ hợp phím Windows + R, chọn Run as administrator.

![image](https://user-images.githubusercontent.com/111716161/194466239-dc323a0c-cba2-4bf1-90e3-be661237d08c.png)

Bước 2: Tại giao diện của Command Prompt bạn dùng lệnh netsh advfirewall set allprofiles state on/off để bật/tắt tường lửa trên Windows 10.

![image](https://user-images.githubusercontent.com/111716161/194466484-ecf60e01-13f1-4d38-bd71-7adf07da8578.png)

### Thông qua Windows security

Bước 1: Bấm Windows + S > Gõ Windows Security > Bấm chọn Firewall & network protection.

![image](https://user-images.githubusercontent.com/111716161/194466657-a793506d-539e-49a6-9d32-665a80b80b6d.png)

![image](https://user-images.githubusercontent.com/111716161/194466748-deb0f99b-db43-4aec-a1e6-2fd8c5bb4345.png)

Bước 2: Chọn Private Network nếu bạn đang sử dụng mạng tại nhà hoặc Public Network nếu bạn sử dụng mạng công cộng.

![image](https://user-images.githubusercontent.com/111716161/194466821-5cf04254-d440-44af-9080-736e5b50cf2c.png)

Bước 3: Tắt/bật Windows Defender Firewall và hoàn thành.

![image](https://user-images.githubusercontent.com/111716161/194466911-fceca159-a999-4263-bf33-d808e1cd2bf6.png)
