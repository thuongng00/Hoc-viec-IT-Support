**Yêu cầu hệ thống:**
- Đã cài đặt máy chủ web Apache.
- PHP và các extension cần thiết.
- Máy chủ Cơ sở dữ liệu MySQL/MariaDB.

### Bước 1: Cài đặt các gói cần thiết

- Cài đặt Zabbix repository

```
rpm -Uvh https://repo.zabbix.com/zabbix/5.0/rhel/7/x86_64/zabbix-release-5.0-1.el7.noarch.rpm
yum clean all
```

- Cài đặt Zabbix Server và Zabbix Agent

```
yum install zabbix-server-mysql zabbix-agent
```

- Cài đặt Zabbix Frontend

Enable Red HAt Software Collections

```
yum install -y centos-release-scl
```

Chỉnh sửa tập tin `zabbix.repo` để bật cho phép cài zabbix-frontend từ repository.

```
nano /etc/yum.repos.d/zabbix.repo

Đặt giá trị enable=1 vào [zabbix-frontend]
```

Cài đặt Zabbix frontend từ repository

```
yum install zabbix-web-mysql-scl zabbix-apache-conf-scl
```

### Bước 2: Tạo và thêm database Zabbix

- Tạo database cho Zabbix

Login vào MariaDB, sau đó tạo user và database cho Zabbix.

```
MariaDB [(none)]> create database zabbix character set utf8 collate utf8_bin;
MariaDB [(none)]> create user zabbix@localhost identified by 'password';
MariaDB [(none)]> grant all privileges on zabbix.* to zabbix@localhost;
MariaDB [(none)]> quit;
```

- Import database Zabbix

```
zcat /usr/share/doc/zabbix-server-mysql*/create.sql.gz | mysql -uzabbix -p zabbix
```

Nhập password đã tạo ở trên.

### Bước 3: Cấu hình Zabbix

- Chỉnh sửa file `zabbix_server.conf`, thay đổi các thông số: database host, database name, database username, database password.

```
nano /etc/zabbix/zabbix_server.conf
```

### Bước 4: Cấu hình PHP

- Mở tập tin `zabbix.conf`

```
nano /etc/opt/rh/rh-php72/php-fpm.d/zabbix.conf
```

- Sửa [date.timezone] thành Asia/Ho_Chi_Minh

### Bước 5: Khởi động Zabbix server và agent

```
systemctl restart zabbix-server zabbix-agent httpd rh-php72-php-fpm
systemctl enable zabbix-server zabbix-agent httpd rh-php72-php-fpm
```

### Bước 6: Thiết lập firewall

```
firewall-cmd --add-service={http,https} --permanent
firewall-cmd --add-port={10051/tcp,10050/tcp} --permanent
firewall-cmd --reload
```

### Bước 7: Thiết lập Zabbix Dashboard

Sau khi cài đặt hoàn tất, mở trình duyệt và truy cập: http://IP-VPS/zabbix.


