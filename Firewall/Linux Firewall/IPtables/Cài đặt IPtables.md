### Bước 1: Tắt FirewallD

- Trên CentOS, mặc định sử dụng tường lửa là firewalld. Để cài đặt IPTABLES thì trước tiên phải tắt service firewalld:

```
systemctl stop firewalld
```

- Không cho phép firewalld tự bật khi reboot server:

```
systemctl disable firewalld
```

- Đảm bảo không cho các dịch vụ khác start firewalld:

```
systemctl mask --now firewalld
```

![image](https://user-images.githubusercontent.com/111716161/194684463-9b5ee107-79d3-497f-8ae5-13ee1f63f5ff.png)

### Bước 2: Cài đặt packages iptables-services từ CentOS repositories:

```
yum install iptables-services -y
```
 
![image](https://user-images.githubusercontent.com/111716161/194684483-337cdea4-df6c-4faf-8b9b-18a035efc59a.png)

### Bước 3: Khởi động dịch vụ iptables

```
systemctl start iptables
```

- Bật tự động iptables khi boot server, để đảm bảo server luôn luôn có sự bảo vệ từ iptables.

```
systemctl enable iptables
```

- Kiểm tra trạng thái iptables đảm bảo nó đang hoạt động:

```
systemctl status iptables
```

![image](https://user-images.githubusercontent.com/111716161/194684513-64bf26af-b8c6-49c8-b85d-a985caa4f1bc.png)
