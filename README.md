
 Mỗi đối tượng file được gắn với ba loại quyền: read (đọc), write (sửa đổi) và execute (thực thi). Và mỗi quyền này lại được chỉ định cho ba loại user:
- owner : chủ sở hữu của đối tượng – mặc định ban đầu là user tạo ra đối tượng đó.
-	group : nhóm các user chia sẻ chung quyền hạn truy cập - mặc định ban đầu là group mà owner ở trên thuộc về.
-	others : tất cả các user không thuộc hai nhóm trên.

+ User root (siêu người dùng) có đủ tất cả các quyền đối với mọi đối tượng trên hệ thống. Ngoài ra, root có thể thay đổi quyền hạn truy cập đối tượng cho bất kỳ user nào và còn có thể chuyển quyền sở hữu đối tượng qua lại giữa các user.
+ Ý nghĩa của ba loại quyền này là:
 - Read: cho phép đọc.
 - Write: cho phép chỉnh sửa nội dung, xóa file; cho phép tạo và xóa các đối tượng trong thư mục.
 - Excute: cho phép thực thi hoặc truy cập nếu đó là thư mục.

**Các quyền cho mỗi đối tượng được biểu diễn theo hai cách**

**Cách thứ nhất** là biểu diễn bằng một chuỗi gồm 10 ký tự:
- 	Ký tự đầu thể hiện loại file:
- : Tệp tin thông thường
d : Thư mục
l : Liên kết
c : Special file
s : Socket
p : Named pipe
b : Thiết bị
-	Ba ký tự tiếp là các quyền cho owner.
-	Kế đến là ba ký tự biểu diễn các quyền cho group.
-	Còn lại ba ký tự cuối dành cho other.

+ Quyền được phép read sẽ là r, write là w, e là excute. Các quyền bị cấm được biểu diễn bằng dấu –  .Để xem chi tiết các quyền của tệp tin, bạn sử dụng lệnh ls với tùy chọn -l .
$ ls -l 
 - rwxr-xr-x 1 ubuntu ubuntu 9144 2011-07-07 15:16 a.out
 - drwxr-xr-x 2 ubuntu ubuntu 4096 2011-07-07 15:29 Desktop
 - rw-r--r-- 1 ubuntu ubuntu 68 2011-07-07 15:16 main.c
+ Giải thích chi tiết:
 -	a.out : đây là file thực thi thông thường
 - Desktop : đây là một thư mục
 -	main.c : đây là file thường, chủ sở hữu có quyền đọc và ghi; nhóm có quyền đọc; người khác có quyền đọc

**Cách hai:** ngắn gọn hơn, gồm ba con số biểu diễn theo hệ bát phân.
 + Số đầu cho owner, số thứ hai cho group, số còn lại cho other. Mỗi một số nhận một trong tám giá trị sau:
- 0 : cấm tất cả các quyền
- 1 : execute
- 2 : write
- 3 : execute + write
- 4 : read
- 5 : read + execute
- 6 : read + write
- 7 : read + write + execute

*Chỉ cần đổi ra dạng nhị phân, bạn sẽ hiểu ngay được các con số này*
- Để thay đổi quyền hạn truy cập cho các user sử dụng lệnh **chmod** (bạn phải là owner của file hoặc có quyền root)
$ chmod 744 main.c # main.c sẽ có thuộc tính là: -rwxr--r--

 + Có một cách khác là sử dụng chmod bằng cách sử dụng ký tự đại diện. Các ký tự đại diện cho nhóm là:
-	u : user sở hữu file
-	g : group của user trên
-	o : others
-	a : tất cả ba ký hiệu ở trên

 + Các toán tử:
-	+ : thêm quyền
-	- : bớt quyền
-	= : gán quyền



- Để thay đổi owner cho đối tượng sử dụng lệnh chown (bạn phải có quyền root): $ chown User_Name File_Name
+  Để thay đổi group cho đối tượng sử dụng lệnh chgrp nhưng phải thỏa một trong hai điều kiện sau:
 - 1.	Bạn sử dụng quyền root
 - 2.	Bạn là chủ sở hữu và thuộc Group (có tên là Group_Name trong lệnh) mà bạn muốn thay đổi Group cho file: $ chgrp Group_Name File_Name .

 + Để biết mình thuộc các nhóm nào, bạn sử dụng lệnh 'id'. Lệnh này cho biết id cùng với tên của bạn và các nhóm mà bạn tham gia.
Các thuộc tính khác của tệp tin liên quan đến quyền truy cập rất đáng chú ý khác nữa là: Set user ID, set group ID, sticky bit. Các bít này bổ xung thêm cho các quyền đã mô tả ở trên. Sau đây là mô tả chi tiết ba bít này:
-	SUID hay setuid: thay đổi việc thực thi dành cho user ID. Nếu như setuid được đặt, khi tệp tin được thực thi bởi người dùng (user), tuyến trình được tạo ra sẽ có cùng quyền với tệp tin.
-	SGID hay setgid: thay đổi việc thực thi dành cho group ID. Giống như ở trên, nhưng kế thừa các quyền của nhóm. Đối với các thư mục điều đó có nghĩa là khi một tệp tin được tạo ra trong thư mục nó sẽ kế thừa nhóm của thư mục (và không ai là người tạo ra cả).
-	Bít Sticky: Hiện nay nó ứng xử phụ thuộc vào từng hệ thống và nó thường được sử dụng để chống việc xóa các tệp tin mà tập tin này có quan hệ với những người dùng khác trong thư mục nơi bạn có quyền "write".
Để biểu diễn các bít này, các bạn có thể sử dụng chữ số theo hệ bát phân như ở trên. Hay có thể biểu diễn theo dạng chuỗi ký tự như sau:
- SUID: Nếu được đặt, sẽ thay thế "x" trong quyền chủ sở hữu thành "s", nếu chủ sở hữu có quyền thực thi, còn nếu không thì thành "S". -	SGID: Nếu được đặt, sẽ thay thế "x" trong nhóm thành "s", nếu nhóm có quyền thực thi, còn nếu không thì thành "S". 
-	Sticky: Nếu được đặt, sẽ thay thế "x" trong others thành "t", nếu others có quyền thực thi, còn nếu không thì thành "T". 











