Bước 1: Boot CD ISO Windows Server 2016 

Bước 2: Sau khi boot vào cài đặt Windows Server 2016 . Click "Next".

![image](https://user-images.githubusercontent.com/111716161/189070009-b68fcd51-adf3-47b8-8f40-ef324903e29c.png)

Bước 3: Tiếp theo Click "Repair your computer".

![image](https://user-images.githubusercontent.com/111716161/189070157-135c516d-f7f9-4773-8693-818ab8d8ad71.png)

Bước 4: Tiếp theo Click "Troubleshoot".

![image](https://user-images.githubusercontent.com/111716161/189070271-6ceeaa3b-325c-4940-9df5-861848470cc1.png)

Bước 5: Tiếp Theo Click "Command Pront"

![image](https://user-images.githubusercontent.com/111716161/189070406-90ff3e29-9055-4087-a069-36870e1d33f3.png)

Bước 6: Sau khi Click "Command Pront" Cửa sổ Command xuất hiện.

x:\source>d:  =>  ( D – là partition OS chứa các file system )

D:\>cd Windows\system32  ( dùng lệnh `cd` truy cập vào đường dẫn Windows\system32 )

D:\Windows\system32>ren Utilman.exe Utilman.exe.old  ( dùng lệnh `ren`  rename lại file Utilman.exe thành file Ultilman.exe.old)

D:\Windows\system32>copy cmd.exe Utilman.exe ( dùng lệnh `copy` copy file “cmd.exe” đè lên “Utilman.exe”. Mục đích copy như vậy để khi login windows bấm phím Windows+U để mở cửa sổ Command Line.

![image](https://user-images.githubusercontent.com/111716161/189070720-2f3991f9-a85e-47b9-ba24-d8f892d156c5.png)

Bước 7: Sau khi thực hiện xong bước 6 , tắt của sổ command, và chọn "Continue" Server sẽ reboot lại, và để server boot vào.

![image](https://user-images.githubusercontent.com/111716161/189070980-bd451090-ee1e-4450-aaf7-9b8f3c2b247a.png)

Bước 8: Sau khi windows khởi động đến phần login bấm phím Windows+U  để mở cửa sổ Command Line ( Nếu bấm phím mà không mở ra cửa sổ CMD thì Click vào biểu tượng đồng hồ góc phải phía dưới như hình ) sẽ mở ra cửa sổ CMD.

Tiếp theo dùng lệnh sau để change lại Password administrator 
`net user administrator (password cần đặt)`  

![image](https://user-images.githubusercontent.com/111716161/189071039-c17d0a44-f35e-4576-b5e1-b95c9b48dd29.png)

Bước 9: Sau khi change pass xong, login và thử lại với pass mới change.
