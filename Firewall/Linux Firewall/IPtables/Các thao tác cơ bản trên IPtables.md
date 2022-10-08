# Một số nguyên tắc áp dụng trong Iptables

- Đầu tiên cần xác định các service muốn đóng/mở và các port tương ứng. 

```
Ví dụ:

Để truy cập VPS bằng SSH, cần mở port SSH - 22

Truy cập Website, cần mở port HTTP - 80 và HTTPS - 443

Để gửi mail, cần mở port SMTP - 22 và SMTPS - 465/587

Để người dùng nhạn được mail, cần mở port POP3 -110, POP3S - 995, IMAP - 143 và IMAPS - 993.
```

Sau khi đã xác định được các port cần mờ, cần thiết lập các quy tắt tường lửa tương ứng để cho phép.

- Xem các rules hiện tại:

```
iptables -L
```

![image](https://user-images.githubusercontent.com/111716161/194684684-227ee087-07f3-49a9-b838-efd073153f8d.png)

- Clear đi rules cũ dùng :

```
iptables -F
```        

![image](https://user-images.githubusercontent.com/111716161/194684696-71f7e810-60d5-4341-a3c7-96047f026a87.png)

- Thông tin về các cột :
    + Cột 1 target: Hành động sẽ được áp dụng cho mỗi qui tắc, gồm:
        - Accept : gói dữ liệu được chuyển tiếp để xử lí tại ứng dụng cuối hoặc hệ điều hành
        - Drop: gói dữ liệu bị chặn, loại bỏ
        - Reject: gói dữ liệu bị chặn, loại bỏ đồng thời gửi một thông báo lỗi tới người gửi
    + Cột 2: PROT (protocol – giao thức) quy định các giao thức sẽ được áp dụng để thực thi quy tắc, bao gồm all, TCP hay UDP. Các ứng dụng SSH, FTP, sFTP… đều sử dụng giao thức TCP.
    + Cột 4, 5: SOURCE và DESTINATION địa chỉ của lượt truy cập được phép áp dụng quy tắc

# Cách sử dụng iptables để mở port cho VPS
- Để mở port trong iptables, cần chèn chuỗi ACCEPT PORT. Cấu trúc lệnh để mở port xxx như sau:

```
iptables -A INPUT -p tcp -m tcp --dport xxx -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport xxx -j ACCEPT
```

- A tức Append – chèn vào chuỗi INPUT (chèn xuống cuối)
- I tức Insert - chèn vào chuỗi INPUT (chèn vào dòng chỉ định rulenum)
- Để tránh xung đột với rule gốc, các bạn nên chèn rule vào đầu, sử dụng -I

![image](https://user-images.githubusercontent.com/111716161/194684730-90f73bed-18e4-496b-95bf-e559ef655373.png)

## Mở port SSH
- Để truy cập VPS qua SSH, bạn cần mở port SSH 22:

```
iptables -I INPUT -p tcp -m tcp --dport 22 -j ACCEPT
```

![image](https://user-images.githubusercontent.com/111716161/194684970-ed574df2-0b91-48f3-b8b1-703a9926c8d5.png)

- Có thể cho phép kết nối VPS qua SSH duy nhất từ 1 ip bằng lệnh:

```
iptables -I INPUT -p tcp -s 192.168.30.142 -m tcp --dport 22 -j ACCEPT
```

![image](https://user-images.githubusercontent.com/111716161/194684963-e7f7fa45-8bee-4b9b-8a7e-35c382833bcc.png)

## Mở port Webserver

```
iptables -I INPUT -p tcp -m tcp --dport 80 -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport 443 -j ACCEPT
```

![image](https://user-images.githubusercontent.com/111716161/194684950-6c1f64d9-4e70-4014-a70d-bc2363afc4ff.png)

## Mở port Mail

- SMTP

```
iptables -I INPUT -p tcp -m tcp --dport 25 -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport 465 -j ACCEPT
```

![image](https://user-images.githubusercontent.com/111716161/194684940-7d96d546-51ec-4a16-902d-7afaeb7953c1.png)

- POP3

```
iptables -A INPUT -p tcp -m tcp --dport 110 -j ACCEPT
iptables -A INPUT -p tcp -m tcp --dport 995 -j ACCEPT
```

![image](https://user-images.githubusercontent.com/111716161/194684900-6dcdae2c-b4bf-4a8e-8fd5-8bc177d711c3.png)

- IMAP

```
iptables -A INPUT -p tcp -m tcp --dport 143 -j ACCEPT
iptables -A INPUT -p tcp -m tcp --dport 993 -j ACCEPT
```

![image](https://user-images.githubusercontent.com/111716161/194684893-b6712907-6d71-4ca6-b6b9-92d9cd1c4e8b.png)

## Chặn 1 IP truy cập

```
iptables -A INPUT -s IP_ADDRESS -j DROP
```

- Chặn 1 IP truy cập 1 port cụ thể:

```
iptables -A INPUT -p tcp -s IP_ADDRESS –dport PORT -j DROP
```

## Reload IPtables

- Sau khi đã thiết lập đầy đủ, bao gồm mở các port cần thiết hay hạn chế các kết nối, cần block toàn bộ các kết nối còn lại và cho phép toàn bộ các kết nối ra ngoài từ VPS.

```
iptables -P OUTPUT ACCEPT
iptables -P INPUT DROP
```

![image](https://user-images.githubusercontent.com/111716161/194684815-754c3740-6903-4b6c-8d44-5f338f055cb5.png)

- Load lại:
 
```
systemctl reload iptables
```

## Cách remove 1 rule

- Đầu tiên cần tìm dòng của rule đấy:

```
iptables -L INPUT --line-numbers
```

- Xóa theo dòng:

```
sudo iptables -D INPUT 5
```

![image](https://user-images.githubusercontent.com/111716161/194684877-0c03709e-0978-40e8-8dd9-174c48648f8a.png)
