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

![image](https://user-images.githubusercontent.com/111716161/187335878-16c9c094-648b-49e7-98b3-68ed8c6e5a14.png)

Bước 2: Nhấn Next để tiếp tục.

![image](https://user-images.githubusercontent.com/111716161/187335914-a95ea4d3-7879-46b7-adc2-5f669381eea7.png)

Bước 3: Chọn "Installer disc image file (iso)" > Nhấn vào Brower... và chọn file iso Windows server 2016 đã tải về máy.

![image](https://user-images.githubusercontent.com/111716161/187335955-e69e7c58-97ad-4154-b270-498542877839.png)

Bước 4: Nhập thông tin tài khoản. (thuong/123456a@) và key bản quyền.

![image](https://user-images.githubusercontent.com/111716161/187336078-77279a64-dab2-40d0-9e32-314515de74a1.png)

Bước 5: Đặt tên và chọn nơi lưu file (đây là file đĩa ảo, file này khá nặng nên lưu ở ổ đĩa nào còn trống nhiều dung lượng để tránh gặp lỗi khi cài đặt).

![image](https://user-images.githubusercontent.com/111716161/187336104-e8333efa-756a-4d6b-82b4-5e81344ec966.png)

Bước 6: Chọn BIOS hoặc UEFI nếu thiết bị hỗ trợ UEFI, nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/187336123-fb94f142-8f9f-4ef7-b9fa-80128c938f52.png)

Bước 7: Chọn tốc độ xử lý của máy ảo.

![image](https://user-images.githubusercontent.com/111716161/187336143-d963b938-cbf1-4689-aca7-cbf223f77445.png)

Bước 8: Chọn RAM, nếu ram bạn nhiều thì có thể để lên cao hơn nữa.

![image](https://user-images.githubusercontent.com/111716161/187336186-23bc9add-08a2-4726-acf7-eb9fc4a61ad7.png)

Bước 9: Thiết lập card mạng cho máy ảo ( bạn có thể chọn card nat hoặc bried).

![image](https://user-images.githubusercontent.com/111716161/187336222-5633e56d-8005-46d9-a945-d8a569ef9ce4.png)

Bước 10: Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/187336246-49fb30cd-0d0b-42e0-af57-b8fb5d5d6b0d.png)

Bước 11: Chọn loại ổ đĩa là SATA, nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/187336287-c53625c7-c6be-4ee5-a9b8-56c5f21075ea.png)

Bước 12: Tạo một ổ đĩa ảo mới. Chọn Create a new virtual disk > Next

![image](https://user-images.githubusercontent.com/111716161/187336303-ec00a98d-3aa8-44ac-81ed-cb07d8d45522.png)

Bước 13:  Chọn dung lượng cho ổ đĩa đó, mặc định là 60GB, chọn Store virtual disk as a single file.

![image](https://user-images.githubusercontent.com/111716161/187336323-244c5c3c-c933-4e94-bcc1-6fe99cff04e8.png)

Bước 14: Chọn đường dẫn lưu file ổ đĩa ảo, sau này có thể copy và chuyển qua máy tính khác mã vẫn dùng được máy ảo.

![image](https://user-images.githubusercontent.com/111716161/187336363-df0aa9ab-ab82-4def-a811-86c9be93c123.png)

Bước 15: Chọn Customize Hardware để kiểm tra lại các thiếp lập. Nhấn Finish.

![image](https://user-images.githubusercontent.com/111716161/187336388-731b6234-800e-45d6-8bcb-d9e9adeb16d0.png)

Bước 16: Windows Server 2016 Standard (Desktop Experience) đây là bản Windows Server có giao diện GUI của Windows 10 và giao diện Server Manager được cài đặt thêm. Ta chọn phiên bản này.

![image](https://user-images.githubusercontent.com/111716161/187336586-cd3342a0-3659-474b-ae6e-6dd90e460b1e.png)

Chờ đợi quá trình cài đặt. 
![image](https://user-images.githubusercontent.com/111716161/187336615-fa53469d-c382-429b-90ed-5c41e9b26f58.png)

Giao diện Windows Server 2016 sau khi cài đặt hoàn tất: 

![image](https://user-images.githubusercontent.com/111716161/187338092-07438da7-da49-463f-aa19-91d475f54fb8.png)

