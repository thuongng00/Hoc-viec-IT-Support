[Cài đặt Zabbix Server](#sv)

[Cài đặt Zabbix Agent](#agent)

<a name="sv"></a>
# Cài đặt Zabbix Server

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

![image](https://user-images.githubusercontent.com/111716161/193998919-0ad94dfa-c34c-4ad8-a329-d159f348a23a.png)

- Cài đặt Zabbix Server và Zabbix Agent

```
yum install zabbix-server-mysql zabbix-agent
```

![image](https://user-images.githubusercontent.com/111716161/193999279-7d79f316-abc3-4735-9e53-0de3d81b74ae.png)

- Cài đặt Zabbix Frontend

Enable Red HAt Software Collections

```
yum install -y centos-release-scl
```

![image](https://user-images.githubusercontent.com/111716161/193999348-29765bb8-b6dd-4a0a-9476-ce79cba07cca.png)

Chỉnh sửa tập tin `zabbix.repo` để bật cho phép cài zabbix-frontend từ repository.

```
nano /etc/yum.repos.d/zabbix.repo

Đặt giá trị enable=1 vào [zabbix-frontend]
```

![image](https://user-images.githubusercontent.com/111716161/193999583-80ae9eb0-a51b-4da1-9970-5898e06b6309.png)

Cài đặt Zabbix frontend từ repository

```
yum install zabbix-web-mysql-scl zabbix-apache-conf-scl
```

![image](https://user-images.githubusercontent.com/111716161/193999703-9c45023b-1d9a-4430-8774-f05bc0d82c5e.png)

### Bước 2: Tạo và thêm database Zabbix

- Tạo database cho Zabbix

Login vào MariaDB.

```
mariadb -u root -p
```

Tạo user và database cho Zabbix.

```
MariaDB [(none)]> create database zabbix character set utf8 collate utf8_bin;
MariaDB [(none)]> create user zabbix@localhost identified by 'password';
MariaDB [(none)]> grant all privileges on zabbix.* to zabbix@localhost;
MariaDB [(none)]> flush privileges;
MariaDB [(none)]> quit;
```

![image](https://user-images.githubusercontent.com/111716161/194013676-f1ed8579-6ac2-4aba-a7cc-893fb13c89af.png)

- Import database Zabbix

```
zcat /usr/share/doc/zabbix-server-mysql*/create.sql.gz | mysql -u zabbix -p zabbix
```

Nhập password đã tạo ở trên.

![image](https://user-images.githubusercontent.com/111716161/194013917-a8c7f409-11a2-4380-b57a-0f8905759d09.png)

### Bước 3: Cấu hình Zabbix server

- Chỉnh sửa file `zabbix_server.conf`, thay đổi các thông số: database host, database name, database username, database password.

```
nano /etc/zabbix/zabbix_server.conf
```

![image](https://user-images.githubusercontent.com/111716161/194005567-fbddd9e6-5790-4957-b936-3c8443df3e56.png)

![image](https://user-images.githubusercontent.com/111716161/194024725-1d57725b-2318-4043-8a3b-3a1abf6463d1.png)

### Bước 4: Cấu hình PHP

- Mở tập tin `zabbix.conf`

```
nano /etc/opt/rh/rh-php72/php-fpm.d/zabbix.conf
```

nano ./conf/zabbix.conf.php
- Sửa [date.timezone] thành Asia/Ho_Chi_Minh

![image](https://user-images.githubusercontent.com/111716161/194003256-cd629827-2b5b-466f-9f0f-38c8dead9b0e.png)

### Bước 5: Khởi động Zabbix server và agent

```
systemctl restart zabbix-server zabbix-agent httpd rh-php72-php-fpm
systemctl enable zabbix-server zabbix-agent httpd rh-php72-php-fpm
```

![image](https://user-images.githubusercontent.com/111716161/194002348-e02a385e-1fe7-4d49-b8af-feb7bd950862.png)

### Bước 6: Thiết lập firewall

```
firewall-cmd --add-service={http,https} --permanent
firewall-cmd --add-port={10051/tcp,10050/tcp} --permanent
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/194002455-a7db70b1-3090-4f5f-964a-d7027242c7a4.png)

### Bước 7: Thiết lập Zabbix Dashboard

- Sau khi cài đặt hoàn tất, mở trình duyệt và truy cập: http://IP-VPS/zabbix.

![image](https://user-images.githubusercontent.com/111716161/194002613-8ce67f1a-79cc-4bd8-b0c2-481e434fb059.png)

- Nhấn Next Step.

![image](https://user-images.githubusercontent.com/111716161/194003510-090a7777-bdd4-4707-8b2c-a51e0fd998e8.png)

- Nhập tài khoản mật khẩu database đã thiết lập -> Next Step.

![image](https://user-images.githubusercontent.com/111716161/194003847-f58ff80d-a003-4c98-a4d7-9431cab12f68.png)

- Đặt tên Zabbix Server -> Next Step.

![image](https://user-images.githubusercontent.com/111716161/194004315-c3035a78-dc27-49b5-9b52-2a1df7b7f481.png)

- Kiểm tra lại thông tin đã nhập -> Next Step.

![image](https://user-images.githubusercontent.com/111716161/194004462-efa301f3-be0c-418b-84af-a21265eebd1c.png)

- Nhấn Finish.

![image](https://user-images.githubusercontent.com/111716161/194004587-e9b164c0-a70f-411d-867f-17641c659e19.png)

- Sau khi thiết lập xong, bạn đăng nhập vào Zabbix Dashboard bằng tài khoản mặc định Admin / zabbix.

![image](https://user-images.githubusercontent.com/111716161/194005062-261b2693-1209-4983-b7e4-07899399a0b6.png)

Giao diện Zabbix Server

![image](https://user-images.githubusercontent.com/111716161/194024333-d86198ca-07f9-4b57-9eee-519877d320c3.png)

<a name="agent"></a>
# Cài đặt Zabbix Agent

### Bước 1: Tải về Zabbix-Agent

```
rpm -Uvh https://repo.zabbix.com/zabbix/4.4/rhel/7/x86_64/zabbix-agent-4.4.0-1.el7.x86_64.rpm
```

### Bước 2: Cài đặt Zabbix-agent

```
yum install zabbix-agent -y
```

![image](https://user-images.githubusercontent.com/111716161/194214045-836080b1-3e49-4b5b-8897-ac380435d8bc.png)

### Bước 3: Cấu hình Zabbix agent

Sửa file cấu hình:

```
nano /etc/zabbix/zabbix_agentd.conf
```

Sửa theo các tham số sau: 
```
Server=<IP_ZABBIX_SERVER>
ServerActive=<IP_ZABBIX_SERVER>
Hostname=<ZABBIX_SERVER_HOSTNAME>
```

![image](https://user-images.githubusercontent.com/111716161/194214154-d7619597-3154-4a3e-a58c-02395cfaea7a.png)

![image](https://user-images.githubusercontent.com/111716161/194214249-1bad1374-f274-4742-801e-0679324bb305.png)

![image](https://user-images.githubusercontent.com/111716161/194214325-9efb8822-dbd1-4fbc-84c0-b25c17681225.png)

### Bước 4: Bước 4: Cấu hình firewalld

```
firewall-cmd --zone=public --add-port=10050/tcp --permanent
firewall-cmd --reload
```

### Bước 5: Kiểm tra việc cài đặt

Khởi động lại dịch vụ

```
systemctl enable zabbix-agent
systemctl restart zabbix-agent
systemctl status zabbix-agent
```

![image](https://user-images.githubusercontent.com/111716161/194214563-64c08219-3f98-4cd8-9d01-5232dc2795e1.png)



