# Backup

- Đăng nhập user Zimbra

```
su zimbra
```

- Dừng các chương trình đang chạy

```
zmcontrol stop
```

- Kiểm tra để đảm bảo rằng Zimbra đã dừng hoàn toàn

```
ps auxww | grep zimbra
```

- Hủy tất cả tiến trình còn sót lại

```
kill -9
```

- Tạo bản sao lưu. 

Cần đảm bảo vị trí sao lưu đủ dung lượng để chứa bản sao lưu. 

Tất cả thành phần Zimbra cần đều được lưu trữ trong thư mục Zimbra, chỉ cần sao chép thư mục này vào vị trí an toàn, nên thêm ngày sao lưu vào:

```
cp -rp /opt/zimbra /mnt/zimbra_backup.$(date "+%Y%m%d")
```

# Restore

- Đăng nhập user Zimbra

```
su zimbra
```

