# Shell của UNIX/Linux

Mọi thứ được thực hiện trên Unix đều bởi tiến trình. Cũng như csc hệ điều hành làm việc kiểu ảo khác, Unix hỗ trợ một phương tiện xử ký lệnh làm giao diện giữa lệnh máy (mà người dùng đưa vào) và việc thực thi của lệnh đó (bởi Unix). Phương tiện đó gọi là **shell**.

Mục đích của shell là để khởi động các tiến trình xử lý lệnh đưa vào: yêu cầu đưa dòng lệnh vào, đọc đầu vào, thông dịch dòng lệnh đó, tạo ra tiến trình để thực hiện lệnh đó. 

Hệ thống cung cấp cho người dùng rất nhiều chương trình shell. Mỗi shell có một số tiện ích như hỗ trợ chế độ gõ phím, ghi nhớ lệnh. Kết hợp các tiện ích của shell để tạo ra một chương trình chạy được, thì một chương trình như vậy được lưu dưới dạng một tệp, gọi là tệp kịch bản (script). Viết được một tệp script, thực chất là đã lập trình theo shell. Một khi đã quen thuộc với một shell và cách hoạt động của shell đó, người dùng có thể làm chủ được các shell khác một cách dễ dàng. 

Các shell trên Unix/Linux:

| Shell | Ý nghĩa |
|---|---|
| sh (bourne) | shell nguyên thủy áp dụng cho Unix |
| csh, tcsh, zsh | dòng shell sử dụng cấu trúc lệnh của C làm ngôn ngữ kịch bản, được tạo ra đầu tiên bởi Bia Joy, là shell thông dụng thứ 2 sau bash shell |
| bash | shell chủ yếu của Linux, ra đời từ dự án GNU, bash là viết tắt của Bourne Again Shell có điểm lợi là mã nguồn được công bố rộng rãi, nếu bash chưa có sẵn trong hệ thống Unix/Linux hãy tải về và biên dịch, sử dụng miễn phí |
| rc | shell mở rộng của csh với nhiều tương thích với ngôn ngữ C hơn, rc cũng ra đời từ dự án GNU |

Shell chuẩn thường được các nhà phân phối sử dụng hiện nay là **bash shell**. Khi cài đặt Linux, trình cài đặt thường mặc định bash là shell khởi động. Có thể tìm thấy chương trình shell này trong thư mục /bin với tên chương trình là *bash*. bash đôi khi là một chương trình nhị phân đôi khi là một script gọi đến liên kết nhị phân khác. Có thể dùng lệnh `file` để xem bash là một tập tin nhị phân hay script như sau:

` $ file /bin/bash `

/bin/bash: ELF 32-bit LSB executable. Intel 80386

Nếu kết quả kết xuất là dạng ELF thì có nghĩa bash là chương trình nhị phân. 

` $ file /bin/sh `

/bin/sh: symbolic link to bash

Điều này có nghĩa là bash hoàn toàn có thể diễn dịch và điều khiển các lệnh của shell sh.

Để bắt đầu viết bash shell, nhập lệnh `! /bin/sh`

# Tính toán trong bash shell

### 1. Expr
Kiểu dữ liệu số áp dụng : số nguyên (integer).

Dùng để tính toán đơn giản cộng trừ nhân chia: “+” , “–” , “*” , “/” .

Ví dụ:
```
expr 1 + 1
myvar=$(expr 1 + 1)
echo ${myvar}
expr $myvar + 1
expr $myvar / 3
expr $myvar \* 3
```

![image](https://user-images.githubusercontent.com/111716161/189313896-97aed689-df93-4d4d-a58e-d25989cd5804.png)

Lưu ý :
- Phải chú ý khoảng trắng, tách biệt giữa các số các biến không được để dính liền.
- Ở phép toán nhân, các bạn phải thêm dấu “\” trước dấu “*” thì lệnh mới hiểu đó là phép nhân.

### 2. Let
Kiểu dữ liệu số áp dụng : số nguyên (integer).

Dùng để tính toán đơn giản “+” , “–” , “*” , “/” .

Ví dụ:
```
a=5
let a+=1
echo ${a}
let a+1
echo ${a}
let b=a+5; echo ${b}
let c=a+b; echo ${c}
let d=$b+3; echo ${d}
```

![image](https://user-images.githubusercontent.com/111716161/189314175-1456f287-9a41-477c-8950-975e83d30950.png)

Lưu ý :
- Phải sử dụng biến đã quy định trước trong biểu thức tính toán “let“, không áp dụng số rời nhau.
- Phải viết các biến số hoặc số dính liền nhau không được tách khoảng trắng như “expr“.

### 3. Sử dụng $((expression)) hoặc $[expression]
Kiểu dữ liệu số áp dụng : số nguyên (integer) .

Dùng để tính toán đơn giản “+” , “-” , “*” , “/” .

Ví dụ:
```
echo $((5+6))
echo $[5+7]
echo $[5+7.5]
var=10
echo ${var}
var=$((var+5))
echo $var
echo var=$[var+5]
var=20
echo $[var+5]
echo $var
var=$[var+5]
echo $var
var2=7
var=$((var+${var2}))
echo $var
```

![image](https://user-images.githubusercontent.com/111716161/189314667-18ea15c4-ac26-4ab7-bc03-78db864d348e.png)

### 4. “bc” – An arbitrary precision calculator language”
Kiểu dữ liệu số sử dụng : integer, float (số nguyên và số thập phân).

Dùng trong rất nhiều trường hợp không chỉ tính toán cơ bản, công cụ tính toán mạnh mẽ nhất trong shell, nắm tốt nó thì không sợ gì cả. Đây là công cụ bên thứ 3 nên nếu OS không có thì ta cần cài đặt vào gói ‘bc‘.

Các trường hợp ngoài tính toán có thể sử dụng “bc” : đổi số nhị phân – thập phân – thập lục phân, so sánh các số với nhau, tính toán các số thập phân,… và rất nhiều tính năng khác.

Ví dụ:
```
echo "2 + 3" | bc
bc <<< "3.4+7/8-(5.94*3.14)"
echo "3.4+7/8-(5.94*3.14)" | bc
echo "2/3" | bc
echo "scale=2; 2/3" | bc
echo "(2/3)+(7/8)" | bc
echo "scale=2;(2/3)+(7/8)" | bc
echo "scale=4;(2/3)+(7/8)" | bc
echo "scale=6;(2/3)+(7/8)" | bc
echo "(2/3)+(7/8)" | bc -l
```

![image](https://user-images.githubusercontent.com/111716161/189314996-ee811be0-8c5d-4158-b816-2803a1384b52.png)

# Biến trong bash shell
Tạo các biến trong bash cũng tương tự như trong các ngôn ngữ lập trình. Nó không có kiểu dữ liệu. Biến trong bash có thể chưa số, ký tự, chuỗi ký tự, … Bạn cũng không cần phải khai báo biến, chỉ cần gán giá trị cho biến và tham chiếu của nó sẽ được tạo ra.

Dòng lệnh trên tạo một biến tên str và gán giá trị “hello world” cho nó. Để lấy giá trị của biến, bạn chỉ cần thêm $ vào trước tên biến:

![image](https://user-images.githubusercontent.com/111716161/189302075-43d8534e-e02b-4756-b162-ff97f8bf3ff2.png)

# Mảng trong bash shell
Tương tự các ngôn ngữ lập trình, bash cũng có mảng. Một mảng là một tập hợp chứa nhiều giá trị. Không có kích thước giới hạn cho mảng. Mảng trong bash có chỉ số bắt đầu từ 0. Có một vài cách khác nhau để tạo ra biến mảng trong bash:

```
Cách 1: 
<tên mảng>[0]= <giá trị 0>
<tên mảng>[1]= <giá trị 1>
<tên mảng>[i]= <giá trị i>
Cách 2: 
<tên mảng>=([i]=<giá trị i> [1]=<giá trị 1> [0]=<giá trị 0>)
Cách 3: 
<tên mảng>=(<giá trị 1> <giá trị 2> <giá trị 3>)
```

Để hiển thị một giá trị ở chỉ số nhất định, sử dụng cú pháp sau:

```
${<tên mảng>[i]} # trong đó i là chỉ số mảng
```

Nếu không chỉ định chỉ số mảng, chỉ số 0 sẽ được ngầm định. Để xem có bao nhiêu phần từ trong mảng, sử dụng cú pháp sau:

```
${#<tên mảng>[@]}
```

![image](https://user-images.githubusercontent.com/111716161/189305154-fdc23341-0c78-430c-b103-6e669b482a31.png)

# String trong Bash shell
Xem một số cú pháp dưới đây để biết các thao tác thay thế chuỗi trong bash script:

```
{variable#pattern} 
{variable##pattern}
{variable%pattern}
{variable%%pattern}
{variable/pattern/string}
{variable//pattern/string}
{#varname}
```

# Hàm trong bash script
Như hầu hết các ngôn ngữ lập trình, bạn có thể sử dụng hàm để nhóm các đoạn code vào thành tức chức năng riêng nhằm mục đích cấu trúc và tái sử dụng. Trong Bash, khai báo một hàm nó như thế này function my_func { my_code }. Còn việc gọi hàm chỉ đơn giản là viết tên hàm ra thôi.

# Cấu trúc điều khiển
Cấu trúc điều khiển trong Bash tương tự như các ngôn ngữ lập trình khác. Có nhiều dạng cấu trúc điều khiển nhưng cơ bản nhất là câu lệnh if điều kiện then khối lệnh và khối lệnh chỉ được thực thi khi điều kiện là đúng (true).

```
if [điều kiện]: then
  # thực thi khi điều kiện đúng
else
  # thực thi khi điều kiện sai
```

Đôi khi việc sử dụng case statements sẽ làm code bạn rõ ràng hơn so với sử dụng if.

```
case expression in
  pattern1 )
    statements;;
  pattern2 )
    statements;;
  ...
esac
```

# Vòng lặp trong bash
Có 3 loại vòng lặp trong Bash: for, while và until.

Các cú pháp for khác nhau:

```
for x : = 1 to 10 do
begin
  statements
end

for name [in list]
do
  statements có thể sử dụng $name
done

for (( initialisation; ending condition ; update ))
do 
  statements...
done
```

Cú pháp while:

```
while condition; do
  statements
done
```

Cú pháp until:

```
until condition; do
  statements
done
```

# Các mẹo dùng Bash

### Tạo alias (viết tắt)
Việc này giúp bạn tiết kiệm thời gian bằng cách gõ alias để chạy một command dài nào đó thường xuyên. Ví dụ:

Chạy nano ~/.bash_profile và thêm dòng dưới đây vào:

```
alias dockerlogin='ssh www-dât@adnan.local -p2222'
```

Sau khi sửa bạn cần cập nhật lại:

```
source ~/.bash_profile
```

### Di chuyển nhanh chóng
Chạy nano ~/.bashrc và thêm vào dòng dưới đây:

```
export hottellogs="/workspace/hotel-api/storage/logs"
```

Bây giờ, bạn cần cập nhật lại bashrc và việc di chuyển tới một đường dẫn dài trở nên rất đơn giản:

```
source ~/.bashrc
cd $hotellogs
```

### Chạy lại command trước đó
Cái này giúp bạn thực thi lại lệnh ngay trước đó. Bạn có thể sử dụng phím mũi tên UP cũng được. Nhưng có thể đôi khi nó vẫn hữu ích.

Để thực thi command ngay trước đó, chạy:

```
!!
```

### Exit traps
Làm cho các tập lệnh bash của bạn hoàn hảo hơn bằng cách thực hiện dọn dẹp một cách đáng tin cậy.

```
function finish {
  jobs -p | xargs kill
}
trap finish EXIT
```

### Lưu lại các biến môi trường
Khi bạn thực thi export FOO = BAR, biến của bạn chỉ được lưu trong shell làm việc hiện tại. Để có thể lưu và tiếp tục sử dụng trong tương lai, bạn hãy thêm nó vào tệp ~/.bash_profile như sau:

```
echo export FOO-BAR >> ~/.bash_profile
```

### Truy cập các script của bạn
Bạn có thể dễ dàng sử dụng các script bằng cách tạo một thư mục bin trong thư mục HOME của bạn với mkdir ~/bin. Bây giờ tất cả các script bạn để trong đó có thể sử dụng chỉ bằng cách gọi tên ở bất kỳ nơi đâu.

Nếu trong trường hợp có lỗi, hãy thử thêm code dưới đây vào cuối ~/.bash_profile và chạy source ~/.bash_profile để thử lại xem sao nhé.

```
if [ -d "$HOME/bin" ] ; then
  PATH="$HOME/bin:$PATH"
fi
```

### Debug trong Bash shell
Bạn có thể dễ dàng debug trong khi học bash shell (bash script) hoặc trong khi làm bằng cách thêm các option vào command. Ví dụ, -n để chỉ kiểm tra cú pháp mà không chạy command đó. -v để in ra command đó trước khi chạy. -x để in ra command đó sau khi chạy xong.

```
bash -n scriptname
bash -v scriptname
bash -x scriptname
```

