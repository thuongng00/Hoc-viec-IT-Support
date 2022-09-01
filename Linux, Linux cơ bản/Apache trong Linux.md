**Apache** là chương trình dịch vụ Web Server miễn phí nổi tiếng nhất thế giới . Apache Web Server ban đầu được viết cho Unix, nhưng bây giờ Apache đã hỗ trợ các nền tảng khác như Microsoft Windows, MacOS, Linux (RedHat / CentOS / Fedora / Debian / Ubuntu …) . Mặc dù miễn phí, Apache Web Server có nhiều tính năng mạnh mẽ và hỗ trợ nhiều ngôn ngữ lập trình Web bao gồm Perl, Python, và PHP …

![image](https://user-images.githubusercontent.com/111716161/187828751-2bec8d09-bdf8-4e45-963b-7edbe7f321d1.png)

# Các lệnh cơ bản về Apache trên CentOS 7
## 1) Cài đặt Apache
Bước 1: Cài đặt repo Epel :
```
yum install -y epel-release
```

Bước 2: Cài đặt gói httpd :
```
yum install -y httpd
```
Bước 3: Cấu hình Firewalld Cho phép dịch vụ httpd  :
```
firewall-cmd --zone=public --permanent --add-service=http
firewall-cmd --reload
```
Bước 4: Khởi động dịch vụ httpd và cấu hình tự khởi động khi boot  :
```
systemctl start httpd
systemctl enable httpd
```
Bước 5: Kiểm tra trạng thái dịch vụ httpd :
```
systemctl status httpd
```

## 2) Gỡ cài đặt Apache
```
yum remove httpd -y
```
## 3) Kiểm tra version Apache đã cài
```
httpd -v
```
