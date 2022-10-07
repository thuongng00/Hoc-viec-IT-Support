# Cài đặt FirewallD

FirewallD được cài đặt mặc định trên CentOS 7 . Cài đặt nếu chưa có :

# yum install firewalld

Khởi động firewalld :

# systemctl start firewalld

Thiết lập firewalld khởi động cùng hệ thống :

# systemctl enable firewalld

Khởi động lại firewalld :

# systemctl restart firewalld

hoặc

# firewall-cmd --reload

Tạm dừng và vô hiệu hóa firewalld :

# systemctl stop firewalld

# systemctl disable firewalld

Kiểm tra tình trạng firewalld :

Cách 1 :

# systemctl status firewalld

Cách 2 :

# firewall-cmd --state

Cách 3 :

# systemctl is-active firewalld

# systemctl is-enabled firewalld
