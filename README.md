#**I.Tạo sửa xóa user , group - Linux**

![Cấu trúc gói tin IP](https://kysudien.files.wordpress.com/2014/12/1e56a-capture.png?w=665.png)

##**1. Tạo user:** 
*# useradd [options]*  
 - Các tùy chọn:
- u UID
- g GID
- G GID : Danh sách các Secondary group có thể cách nhau bằng dấu phẩy ","
- c : ghi chú
- d directory
- m Nếu như thư mục của -d chưa có, thì tự động tạo mới.
- s shell : mặc nhiên sẽ dùng bash shell

##**2. Sửa user:** 
*usermod [options] [-l ]*
- Options: hầu hết giống như của lệnh useradd.
-l, login_name : thay đổi tên đăng nhập của người dùng. Trong một số trường hợp, tên thư mục riêng của người dùng có thể sẽ thay đổi để tham chiếu đến tên đăng nhập mới.

##**3.Xóa user:** 
*# userdel [-r]*
- r : xóa luôn home directory

##**4.Tạo group:** 
*# groupadd [-g groupid]*

##**5.Sửa group:** 
*# groupmod [-n New name] [-g new goupid]*
- u, uid : thay đổi chỉ số người dùng.

##6. Xóa group:**
*# groupdel<groupname>*












