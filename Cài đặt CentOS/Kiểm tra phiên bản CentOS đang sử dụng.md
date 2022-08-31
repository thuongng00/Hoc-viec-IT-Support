## 1. Kiểm tra version CentOS bằng Command Line
Lệnh lsb_release sẽ hiển thị thông tin chuẩn cơ bản (Linux Standard Base) về bản phân phối của Linux đang chạy trên máy tính.

Đây là cách đơn giản nhất để kiểm tra version của CentOS , nó chạy trên mọi phiên bản của CentOS nên bạn cứ yên tâm mà sử dụng.

Hãy mở Terminal của bạn lên và nhập lệnh sau:
```
lsb_release -a
```

Kết quả như sau:

![image](https://user-images.githubusercontent.com/111716161/187593218-69a171ec-c9ae-4fa1-93d7-064da6052880.png)

Phiên bản của CentOS sẽ được hiển thi trong mục Description mà mình đã bôi đỏ trong hình. Như bạn thấy thì máy tính của mình đang sử dụng phiên banr 7.5.1804.

- 7 là phiên bản CentOS chính
- 5 là phiên bản mới nhất của phiên bản chính
- 1804 chính là mã ngày của phiên bản mới nhất này, có nghĩa là tháng 4 năm 2018 chính là thời điểm phát hành phiên bản 7.5.
Lưu ý: Nếu bạn nhận thông báo lỗi lsb_release: command not found thì tức là máy bạn chưa được cài đặt gói redhat-lsb-core nhé. Hãy chạy lệnh dưới đây để cài đặt nó:
```
sudo yum install redhat-lsb-core
```

## 2. Kiểm tra version CentOS bằng lệnh rpm
rpm (Red Hat Package Manager) là một công cụ quản lý gói cho các hệ thống dựa trên Red Hat như RHEL, CentOS và Fedora.

Bạn có thể sử dụng công cụ rpm để hiển thị thông tin về gói centos-release, bao gồm phiên bản CentOS trong tên gọi của nó:
