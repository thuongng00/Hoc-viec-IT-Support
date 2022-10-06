# Giám sát Windows process

### Bước 1: Thêm host windows cần giám sát

Chọn Tab Configuration -> Host -> Create Host, nhập thông tin server Linux cần giám sát process.

# Giám sát Linux process

### Bước 1: Thêm host linux cần giám sát

Chọn Tab Configuration -> Host -> Create Host, nhập thông tin server Linux cần giám sát process.

![image](https://user-images.githubusercontent.com/111716161/194197629-046c7d29-ef3a-4393-b0f3-6c845f21469d.png)

`Hostname`: Đặt tên cho host.
`Visible Hostname`: Đặt tên hiển thị.
`New group`: Bắt buộc phải thêm vào một group
Agent Interface: IP Client cần giám sát

![image](https://user-images.githubusercontent.com/111716161/194197932-f934e889-3588-49e3-bce6-4486ee6dea9e.png)

Nhấn Add để thêm host.

![image](https://user-images.githubusercontent.com/111716161/194198045-b32ff76f-1a79-44c8-9293-fcc8bb2ab326.png)

### Bước 2: Tạo application, item giám sát process

Tạo application: Chọn Applications -> Create application -> Nhập Name -> Add.

![image](https://user-images.githubusercontent.com/111716161/194198544-5778ada7-7045-472c-a831-acf926bfa1ab.png)

![image](https://user-images.githubusercontent.com/111716161/194198799-a4bb1f46-ec2e-4047-8195-843569b93214.png)

![image](https://user-images.githubusercontent.com/111716161/194198901-f389e8e3-26fd-48e4-9e9e-f581f64fb5d6.png)

Tạo item: Chọn Items -> Create item -> Nhập các tham số -> Add.

`Name`: Tên item.
`Type`: Zabbix Agent.
`Key`: Chọn key tùy vào process muốn giám sát.
`Type of Information`: Numeric (Unsigned).
`Update interval`: 1m
`Show value`: As is.
`Application`: Application đã tạo trở trên.

![image](https://user-images.githubusercontent.com/111716161/194199400-7fd55573-cceb-4beb-a562-ce5ec441d7fa.png)

![image](https://user-images.githubusercontent.com/111716161/194199475-963bf84e-cd7c-45bc-89c7-dfdc38284006.png)

![image](https://user-images.githubusercontent.com/111716161/194199765-f5c1fd3f-3ce2-4e9a-b8cd-e0e4833b3b0b.png)

### Bước 3: Kiểm tra kết quả

Chọn tab Monitoring -> Lastest data -> Hosts.


# Giám sát UDP port

# Giám sát TCP port

# Giám sát Windows Server sử dụng SMNP

# Giám sát Windows Server bằng zabbix-agent

