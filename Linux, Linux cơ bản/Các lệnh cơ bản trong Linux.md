# Quản lý User

### 1. Lấy danh sách User
- Sử dụng lệnh dưới đây để lấy danh sách User:
```
less /etc/passwd
```
hoặc
```
getent passwd
```
![image](https://user-images.githubusercontent.com/111716161/187380301-53af32ac-a62a-4eab-9ede-9bbb39fa2e78.png)

- Chỉ hiển thị thông tin username thì dùng một trong các lệnh dưới đây:
```
awk -F: '{ print $1}' /etc/passwd
cut -d: -f1 /etc/passwd
getent passwd | awk -F: '{ print $1}'
getent passwd | cut -d: -f1
```
![image](https://user-images.githubusercontent.com/111716161/187380711-9e7d98af-3e82-4902-94fe-02e50b4bddfc.png)

- Kiểm tra một người dùng có tồn trại trong hệ thống Linux không thì ta dùng lệnh sau:
```
getent passwd | grep [tên người dùng]
```

- Đếm tổng số người dùng trong hệ thống
```
getent passwd | wc -l
```

- Phân biệt người dùng hệ thống và người dùng bình thường:
```
grep -E '^UID_MIN|^UID_MAX' /etc/login.defs
```
![image](https://user-images.githubusercontent.com/111716161/187382494-05970171-4316-472c-9089-ffd644c72c15.png)


