### Bước 1: Kiểm tra hỗ trợ ảo hóa
Để kiểm tra máy có hỗ trợ ảo hóa hay không
```
egrep -c "svm|vmx" /proc/cpuinfo
```
Nếu kết quả trả về 0 thì máy không hỗ trợ ảo hóa. Còn khác 0 tức là máy có hỗ trợ ảo hóa.

![image](https://user-images.githubusercontent.com/111716161/187574420-fe341877-a83a-4497-964c-c31edb30d89a.png)

### Bước 2: Cài đặt các gói cần thiết
```
yum -y install qemu-kvm libvirt virt-install bridge-utils virt-manager
```
Trong đó:

qemu-kvm: Phần phụ trợ cho KVM

libvirt: cung cấp libvirt mà bạn cần quản lý qemu và KVM bằng libvirt.

bridge-utils: chứa một tiện ích cần thiết để tạo và quản lý các thiết bị bridge

virt-manager: cung cấp giao diện đồ họa để quản lý máy ảo

virt-install: Cung cấp lệnh để cài đặt máy ảo

Sau khi cài đặt hoàn tất, ta kiểm tra các module KVM
```
lsmod | grep kvm
```

### Bước 3: Bật libvirt và khởi động cùng hệ thống
```
systemctl start libvirt
systemctl enable libvirtd
```

### Bước 4: Tạo một card bridge
Ta sẽ tạo 1 card bridge br0 ở chế độ NAT để khi tạo KVM sẽ gắn card mạng vào bridge này:
```
nmcli connection add type bridge autoconnect yes con-name br0 ifname br0
nmcli connection modify br0 ipv4.addresses 192.168.37.55/24 ipv4.method manual  
nmcli connection modify br0 ipv4.gateway 192.168.37.1
nmcli connection modify br0 ipv4.dns 192.168.37.1  
nmcli connection delete ens33
nmcli connection add type bridge-slave autoconnect yes con-name ens33 ifname ens33 master br0
```

### Bước 5: Khởi động lại hệ thống
```
reboot
```

