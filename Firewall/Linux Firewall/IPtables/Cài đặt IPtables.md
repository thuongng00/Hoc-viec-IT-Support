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

### Bước 2: Cài đặt packages iptables-services từ CentOS repositories:

```
yum install iptables-services
```
 
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

