Link tải: https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2019



Yêu cầu cấu hình phần cứng: 
Bộ xử lý CPU:

- Bộ xử lý 64-bit 1.4 GHz
- Tương thích với bộ lệnh x64
- Hỗ trợ NX và DEP
- Hỗ trợ CMPXCHG16b, LAHF/SAHF, and PrefetchW
- Hỗ trợ Second Level Address Translation (EPT hoặc NPT)
- Ethernet: Adapter Gigabit Ethernet (10/100/1000 Base-T)
- Display Resolution: Monitor Super VGA (1024 x 768) hoặc cao hơn

Bộ nhớ RAM:

- 512 MB (2 GB với tùy chọn máy chủ cài đặt Desktop Experience)
- ECC (Error Correcting Code – mã sửa lỗi) hoặc công nghệ tương tự

# Cách cài đặt Windows Server 2016 trên máy ảo VMware


Bước 1: Khởi động phần mềm VMware Workstation, chọn File, chọn New Virtual Machine hoặc nhấn vào Create a new virtual machine. Chọn Custom, nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189274783-618ec749-5200-4128-a691-3ad6ab5bfe2d.png)

Bước 2: Nhấn Next để tiếp tục.

![image](https://user-images.githubusercontent.com/111716161/189274989-b51e44e1-cc96-4fa6-a111-5999402b77ee.png)

Bước 3: Chọn "Installer disc image file (iso)" > Nhấn vào Brower... và chọn file iso Windows server 2016 đã tải về máy.

![image](https://user-images.githubusercontent.com/111716161/189275031-63ceffac-e90c-43d0-80d4-0ac13db8eb48.png)

Bước 4: Nhập thông tin tài khoản. (thuong/123456a@) và key bản quyền.

![image](https://user-images.githubusercontent.com/111716161/189292609-148dda89-3037-4cbb-8868-db8636518d5f.png)

Bước 5: Đặt tên và chọn nơi lưu file (đây là file đĩa ảo, file này khá nặng nên lưu ở ổ đĩa nào còn trống nhiều dung lượng để tránh gặp lỗi khi cài đặt).

![image](https://user-images.githubusercontent.com/111716161/189275259-0ebfce43-ac6c-4899-af57-89f7653ba875.png)

Bước 6: Chọn BIOS hoặc UEFI nếu thiết bị hỗ trợ UEFI, nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189288814-f38acf3c-6f0b-4b1e-9079-feb373c28aa6.png)

Bước 7: Chọn tốc độ xử lý của máy ảo.

![image](https://user-images.githubusercontent.com/111716161/189288896-d789b67d-4c76-401b-8368-3882712d36ec.png)

Bước 8: Chọn RAM, nếu ram bạn nhiều thì có thể để lên cao hơn nữa.

![image](https://user-images.githubusercontent.com/111716161/189289274-a47f7fa5-edbc-485b-adde-2c23ebc538ea.png)

Bước 9: Thiết lập card mạng cho máy ảo ( bạn có thể chọn card nat hoặc bried).

![image](https://user-images.githubusercontent.com/111716161/189289313-1d0f5aa3-7d8a-4502-8488-2246953d0de3.png)

Bước 10: Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189289356-8aaecd8b-b73e-427c-80a4-431a8ebe9110.png)

Bước 11: Chọn loại ổ đĩa là SATA, nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189289422-569d232a-5f6c-411b-9214-8754ca170759.png)

Bước 12: Tạo một ổ đĩa ảo mới. Chọn Create a new virtual disk > Next

![image](https://user-images.githubusercontent.com/111716161/189289474-808b6478-201e-4494-979b-11e16b54cd57.png)

Bước 13:  Chọn dung lượng cho ổ đĩa đó, mặc định là 60GB, chọn Store virtual disk as a single file.

![image](https://user-images.githubusercontent.com/111716161/189289521-74cb3a39-dcec-4793-896a-329167a471df.png)

Bước 14: Chọn đường dẫn lưu file ổ đĩa ảo, sau này có thể copy và chuyển qua máy tính khác mã vẫn dùng được máy ảo.

![image](https://user-images.githubusercontent.com/111716161/189289567-e58cbbeb-82b4-4629-80ed-69b58fad27c5.png)

Bước 15: Chọn Customize Hardware để kiểm tra lại các thiếp lập. Nhấn Finish.

![image](https://user-images.githubusercontent.com/111716161/189289600-4bc431cb-5838-4f10-91cc-346cbfead9ef.png)

Bước 16: Windows Server 2019 Standard (Desktop Experience) đây là bản Windows Server có giao diện GUI của Windows 10 và giao diện Server Manager được cài đặt thêm. Ta chọn phiên bản này.

![image](https://user-images.githubusercontent.com/111716161/187336586-cd3342a0-3659-474b-ae6e-6dd90e460b1e.png)

Chờ đợi quá trình cài đặt. 
![image](https://user-images.githubusercontent.com/111716161/187336615-fa53469d-c382-429b-90ed-5c41e9b26f58.png)

Giao diện Windows Server 2019 sau khi cài đặt hoàn tất: 

![image](https://user-images.githubusercontent.com/111716161/187338092-07438da7-da49-463f-aa19-91d475f54fb8.png)
