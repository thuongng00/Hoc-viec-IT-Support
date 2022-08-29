Một số lệnh linux cơ bản, thường dùng, các dòng lệnh linux có thể thực hiện qua putty, lệnh về process, lệnh phân quyền, lệnh nén và giải nén.

# FILE COMMANDS - CÁC LỆNH VỀ FILE
li - Liệt kê thư mục

li -al - liệt kê thư mục, cả file ẩn

cd đường-dẫn-thư-mục - chuyển đến thư mục

cd - chuyển đến thư mục gốc

pwd - hiện thị thư mục hiện tại

mkdir tên-thư-mục - tạo thư mục

rm filename - xóa file

rm -f filename - xóa file không cần hỏi

rm -r thư-mục - xóa thư mục

rm -rf thư-mục - xóa thư mục, không hỏi

cp file1 file2 - copy file1 vào file2

mv file1 file2 - di chuyển file, đổi tên file

ln -s file link - tạo symbolic link ('link' trỏ đến file)

touch file - tạo file hoặc cập nhật file

cat > file - đè nội dung soạn thảo vào file (CTRL+D để ghi lại)

cat file - hiện thị nội dung file

more file - hiện thị nội dung file

less file - hiện thị nội dung file

head file - hiện thị 10 dòng đầu của file

tail file - hiện thị 10 dòng cuối của file

# KẾT NỐI SSH

ssh user@host - kết nối đến host với user

ssh -p port user@host - kết nối có chỉ ra port

# CÀI ĐẶT SOFTWARE

./configure

make

make install

# LỆNH VỀ MẠNG - NETWORK
ping host - ping đến host

dig domain - lấy thông tin DNS cho domain

wget file - tải file

curl --head url - xem phần header của URL

# THÔNG TIN HỆ THỐNG
date - ngày/tháng giờ hiện tại

cal - lịch tháng hiện tại

uptime - thời gian hệ thống hoạt động (kể từ khi khởi động)

w - xem các user đang online trong hệ thống

whoami - tài khoản đang đăng nhập

uname -a - thông tin hệ thống linux

cat /proc/cpuinfo - thông tin CPU

cat /proc/meminfo - thông tin bộ nhớ

df - thông tin đĩa cứng

df -BM - thông tin đĩa cứng

du - thông tin thư mục

du -sh - thông tin thư mục

du --max-depth=1 -B M |sort -rn - thông tin thư mục, xếp theo dung lượng

free - thông tin bộ nhớ trống và swap

# TÌM KIẾM - SEARCHING
grep 'word' file1 file2 ... - tìm kiếm 'word' trong file1, file2 ...

grep -rnw '/path/to/somewhere/' -e 'word' - tìm kiếm các file chứa 'word' trong thư mục

locate "*.png" - tìm vị trí theo tên file

# PROCESS
top - các tiến trình đang chạy

ps -aux - các tiến trình đang chạy

kill -9 PID - dừng tiến trình PID

killall [process name] - dừng tiến trình

# FILE PERMISSION
chmod octal file - thay đổi permission

octal con số bát phân (1)(2)(3) thể hiện permision (rwx == read-write-execute)

chmod 775 file - rw cho owner, rx cho group/world

chmod 777 file - file rwx cho tất các các user

chmod -R 755 directory-name/ - thiết lập cho toàn thư mục

chown -R owner:group file/directory - đổi owner|group của file

# NÉN FILE

tar -cvf /tenfilenen.tar /thu-muc-can-nen - nén thư mực vào .tar

tar -xvf file-nen.tar - giải nén file .tar

gzip file - nén file thành file.gz

gzip -d file.gz - giải nén file.gz
