### Bước 1: Đăng nhập vào dashboard Zabbix Server

### Bước 2: Tạo host

- Chọn tab Configuration -> Host -> Create host.

![image](https://user-images.githubusercontent.com/111716161/194245489-b8d61a63-ca19-41f5-bd22-240f72d035db.png)

- Điền các thông số của host, bắt buộc phải điền Hostname, Group, IP

![image](https://user-images.githubusercontent.com/111716161/194245685-248c8f47-33b7-4f92-8b79-ea4d566bef32.png)

### Bước 3: Tạo Template cho host

- Chọn Template -> Select -> Template OS Linux by Zabbix agent -> Select.

![image](https://user-images.githubusercontent.com/111716161/194245799-1a5ff192-a47c-48ad-9739-9df519cd3dc0.png)

![image](https://user-images.githubusercontent.com/111716161/194245954-2d362409-5775-4a25-b78c-b2b509e36c1c.png)

Như vậy ta đã tạo thành công host. 

![image](https://user-images.githubusercontent.com/111716161/194245113-69b0b9da-c93a-41ae-b500-f3f0dc6357e6.png)

### Bước 4: Tạo Application, Item giám sát process

![image](https://user-images.githubusercontent.com/111716161/194246113-b6194150-e615-44a6-8cbb-2759ddbfcc0a.png)

- Vào Applications -> Create Application -> Nhập tên -> Add.

![image](https://user-images.githubusercontent.com/111716161/194247109-afbffa35-54f2-4c58-800a-df6a8310924c.png)

- Vào Items -> Create Item -> Nhập các tham số -> Add.

`Name`: Đặt tên tùy ý
`Type`: Zabbix Agent
`Key`: Lựa chọn key tùy vào process muốn giám sát
`Type of Information`: Numeric (Unsigned)
`Update interval`: 1m
`Show value`: As is
`Application`: Application đã tạo ở trên

![image](https://user-images.githubusercontent.com/111716161/194247420-2e7cd387-2032-4c90-b77e-b151cff78f6e.png)

### Bước 5: Kiểm tra kết quả



