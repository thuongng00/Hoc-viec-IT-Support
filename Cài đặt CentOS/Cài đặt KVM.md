Cài đặt KVM trên CentOS chạy trên máy ảo VMware.

Lưu ý: Để cài được KVM thì cần phải được CPU hỗ trợ. Để kiểm tra xem CPU có hỗ trợ hay không sử dụng lệnh.
```
egrep -c "svm|vmx" /proc/cpuinfo
```
Nếu kết quả trả về là khác 0 thì CPU có hỗ trợ.

![image](https://user-images.githubusercontent.com/111716161/187161455-529e0abd-77c2-4844-8113-fbf5e9c3ac11.png)

*Nếu chưa bật ảo hóa trong VMware thì ta thực hiện các bước sau:*

Bước 1: Nhấn vào Edit virtual machine settings.

![image](https://user-images.githubusercontent.com/111716161/187162000-eaea2da1-d038-4b33-8f0f-ece731e45e97.png)

Bước 2: Bật các tùy chọn như hình. 

![image](https://user-images.githubusercontent.com/111716161/187162315-97c351d0-c191-464d-bcc1-1b0e2aed2f61.png)

Bước 3: Nhấn Ok để hoàn tất cài đặt. 

