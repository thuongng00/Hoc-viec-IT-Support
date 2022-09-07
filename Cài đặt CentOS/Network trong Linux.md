# Các lệnh cơ bản về network trong linux

Xác định địa chỉ ip và các network interface

```
ifconfig -a
```
![image](https://user-images.githubusercontent.com/111716161/188848360-36227ced-48bc-44fa-abb0-94a32eb53f0a.png)

Để xem những thiết bị được kết nối vào computer từ IRQ 1 - IRQ 15 :

```
cat /proc/interrupts
```
![image](https://user-images.githubusercontent.com/111716161/188848705-1690dad9-cb40-41e6-b5dd-f0357e53ccc6.png)

Thiết lập địa chỉ ip cho một card mạng ta dùng command sau :

``` 
ifconfig eth0 192.168.1.5 netmask 255.255.255.0 up
```
