Khôi phục mật khẩu root trên CentOS 7.

*Lưu ý: Chỉ có thể áp dụng khôi phục mật khẩu user nếu GRUB2 boot loader không set up mật khẩu khoá.*

### Bước 1
khởi động lại hệ thống, chỉnh sửa ‘grub2’

- Khởi động lại hệ thống và tinh chỉnh chế độ GRUB2 ở màn hình boot GRUB2.
- Bấm nút ESC để màn hình dừng lại, sau đó ấn nút ‘e’ để thực hiện chỉnh sửa.

![image](https://user-images.githubusercontent.com/111716161/187154038-678f6b51-d90a-4325-bcc1-08685a96a7dc.png)

### Bước 2
Chỉnh thông số entry cần thiết
- Tìm đến dòng entry cấu hình “linux16” hoặc “linuxefi” đối với hệ thống UEFI.
- Xoá 2 thông số “rhgb quiet” để kích hoạt log message hệ thống khi thực hiện đổi mật khẩu root.
- Thêm vào cuối dòng “linux16..” thông số sau.
```
rd.break
```

![image](https://user-images.githubusercontent.com/111716161/187154160-0f09fe2f-e464-4cdd-98b7-a0e3d7d95a14.png)

- Ấn Ctrl+X để lưu và tự động boot vào môi trường initramfs.

![image](https://user-images.githubusercontent.com/111716161/187154208-87bacbbb-97e0-4bd3-b01a-bf2416a61c50.png)

### Bước 3

Remount filesystem và chuyển chế độ chroot
- Hệ thống filesystem hiện tại đang ở chế độ “read only” được mount ở thư mục /sysroot/, để thực hiện khôi phục mật khẩu root thì ta cần thêm quyền ghi (write) trên filesystem. Ta sẽ tiến hành remount lại filesystem /sysroot/ với quyền đọc-ghi (read-write).
- Kiểm tra lại xem filesystem đã được remount quyền đọc-ghi hay chưa.
```
switch_root:/# mount -o remount, rw /sysroot
switch_root:/# mount | grep -w “/sysroot“
```

![image](https://user-images.githubusercontent.com/111716161/187154323-fd4070a2-f4d2-4201-8e05-4335a8fc12b6.png)

- Lúc này filesystem đã được mount và ta sẽ chuyển đổi sang môi trường filesystem (prompt: sh-4.2#).
```
switch_root:/# chroot /sysroot
```
- Tiến hành reset password user root.
```
sh-4.2# passwd root
```

### Bước 4
Relabel SELINUX
Chạy lệnh sau để update lại các thông số cấu hình SELINUX, nếu bạn có sử dụng SELINUX. Nguyên nhân khi ta update file /etc/passwd chứa mật khẩu thì các thông số SELINUX security contex sẽ khác nên cần update lại.
```
sh-4.2# touch /.autorelabel
```
### Bước 5
Remount và reboot
- Remount filesystem “/“ ở chế độ read-only.
```
sh-4.2# mount -o remount, ro /
```
- Thoát môi trường chroot và Khởi động lại hệ thống.
```
sh-4.2# exit
switch_root:/# exec /sbin/reboot
```
 
Bạn sẽ thấy hệ thống reboot và chậm hơn bình thường , do hệ thống đang tiến hành hoạt động SELINUX relabel. Sau khi boot vào hệ thống prompt console thành công thì bạn có thể đăng nhập bằng mật khẩu mới.
