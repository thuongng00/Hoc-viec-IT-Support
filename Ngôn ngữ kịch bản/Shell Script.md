## Shell Script

Nhìn vào sơ đồ này bạn có thể thấy phía trong cùng là phần cứng (hardware), tiếp đến là Karnel, Shell và cuối cùng là các ứng dụng (application). Như vậy shell script là lớp trung gian thứ hai (tính tử lớp vỏ) dùng để ngăn cách các ứng dụng được cài đặt trên hệ điều hành và lớp Karnel (karnel cũng là lớp phần mềm nằm giữa phần cứng và các ứng dụng). Như vậy shell sẽ tập hợp đầu vào và thực hiện các chương trình dựa vào đầu vào đó, khi một chương trình kết thúc nó sẽ hiển thị đầu ra của chương trình đó.

![image](https://user-images.githubusercontent.com/111716161/187581797-80f9e2b4-9811-48d8-81e7-e34ac0197ac9.png)

Shell là môi trường mà ta có thể chạy các lệnh, các chương trình và các đoạn mã script. Shell có nhiều phiên bản khác nhau, và nó cũng có chút khác nhau ở mỗi phiên bản của hệ điều hành. Ví dụ trong ubuntu thì ta dùng lệnh apt-get, còn ở Cent OS thì ta dùng lệnh yum, sẽ cho kết quả tương đương, nếu muốn dùng apt-get thì ban phải cài thêm gói đó vào.

Nếu bạn là dân lập trình thì chắc chắn rất quan thuộc với script phải không nhỉ, ví dụ PHP script, Java script, C Script ... ý nghĩa của nó là tập hợp các lệnh trên máy tính, các lệnh này sẽ được biên dịch bởi một compiler và thứ tự biên dịch đi từ trên xuống dưới và từ trái qua phải.

Trong Linux, shell script sẽ được lưu trữ trong một file đơn giản với phần mở rộng là .sh. Ví dụ bạn muốn viết chương trình gửi mail tự động thì có thể đặt tên là auto-mail.sh.
