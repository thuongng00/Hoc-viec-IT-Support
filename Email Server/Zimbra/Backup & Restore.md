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

- Dừng các chương trình đang chạy

```
zmcontrol stop
```

- Sao chép bản sao lưu đã tạo trước đó vào thư mục /otp

```
cp -rp /mnt/zimbra_backup/ /opt
```

- Đổi tên thư bản sao lưu thành Zimbra

```
mv /opt/zimbra_backup/ /opt/zimbra
```

- Cài đặt lại Zimbra

Lưu ý: Không chạy tập lệnh với option -u. Nó sẽ xóa dữ liệu sao lưu và chạy với quyền root Nếu không gặp lỗi nào, sẽ có thông báo hiện thị như sau:

```
The Zimbra Collaboration Suite appears already to be installed.

It can be upgraded with no effect on existing accounts,

or the current installation can be completely removed prior

to installation for a clean install.

Do you wish to upgrade? [Y]
```

- Tập lệnh sẽ xóa bỏ các gói hiện tại và cài đặt lại chúng. Nó sẽ dừng dịch vụ Zimbra cũ và chạy với file đã sao lưu trước đó.

- Đặt lại quyền

```
chown -R zimbra:zimbra /opt/zimbra/store
chown -R zimbra:zimbra /opt/zimbra/index
/opt/zimbra/libexec/zmfixperms
```

