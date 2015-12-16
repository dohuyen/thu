##**1. Lệnh Ping**
- Cú pháp: **ping ip/host/[/t][/a][/l][/n]**
- **Ip:** địa chỉ IP của máy cần kiểm tra; host là tên của máy tính cần kiểm tra kết nối mạng (có thể sử dụng địa chỉ IP hoặc tên của máy tính).
- **/t:** sử dụng để máy tính liên tục "ping" đến máy tính đích, bấm Ctrl +C để dừng.
- **/a:** nhận địa chỉ IP từ tên máy tính (host).
- **/l:** xác định độ rộng của gói tin gửi đi kiểm tra.
- **/n:** Xác định số gói tin gửi đi.

- Công dụng : Sử dụng lện Ping để kiểm tra xem một máy tính có kết nối mạng không. Lệnh PING gửi các gói tin từ máy tính bạn tới máy tính đích, các bạn có thể xác định được tình trạng đường truyền hoặc xác định máy tính đó có kết nối hay không.

##**2. Lệnh Tracert :**
- Cú pháp : **Code: tracert ip/host** 
- Công dụng : Lệnh này sẽ cho phép bạn "nhìn thấy" đường đi của các gói
tin từ máy tính của bạn đến máy tính đích, xem gói tin của bạn vòng qua
các server nào, các router nào... Quá hay nếu bạn muốn thăm dò một
server nào đó.

##**3.Lệnh Net Send :** gửi thông điệp trên mạng (chỉ sử dụng trên hệ thống máy tình Win NT/2000/XP).
- Cú pháp: **Net send ip/host thông_điệp_muốn_gửi**
- Công dụng: Lệnh này sẽ gửi thông điệp tới máy tính đích (có địa chỉ IP hoặc tên host) thông điệp: thông_điệp_muốn_gửi. 
Trong mạng LAN, ta có thể sử dụng lệnh này để chat với nhau. Trong
phòng vi tính của trường các bạn có thể dùng lệnh này để ghẹo mọi
người!
 - Cũng có thể gửi cho tất cả các máy tính trong mạng LAN theo cấu trúc sau :** Code: Net send * thông_điệp_muốn_gửi** 

##**4. Lệnh Netstat :** 
- Cú pháp: **Code: Netstat [/a][/e][/n]**
 - Tham số /a: Hiển thị tất cả các kết nối và các cổng đang lắng nghe (listening) 
 - Tham số /e: hiển thị các thông tin thống kê Ethernet 
 - Tham số /n: Hiển thị các địa chỉ và các số cổng kết nối... Ngoải ra còn một vài tham số khác
- Các bạn hãy gõ Netstat /? để biết thêm Công dụng :Lệnh Netstat cho phép ta liệt kê tất cả các kết nối ra và vào máy tính của chúng ta. 

##**5. Lệnh IPCONFIG :** 
- Cú pháp: **Code: ipconfig /all**
- Công dụng: Lệnh này sẽ cho phép hiển thị cấu hình IP của máy tính bạn đang sử dụng, như tên host, địa chỉ IP, mặt nạ mạng... 

##**6. Lệnh FTP (truyền tải file):**
- Cú pháp: **Code: ftp ip/host**
- Nếu kết nối thành công đến máy chủ, bạn sẽ vào màn hình ftp, có dấu nhắc như sau: 
Code: ftp>_ Tại đây, bạn sẽ thực hiện các thao tác bằng tay với ftp,
thay vì dùng các chương trình kiểu Cute FTP, Flash FXP. Nếu kết nối
thành công, chương trình sẽ yêu cầu bạn nhập User name, Password. Nếu
username và pass hợp lệ, bạn sẽ được phép upload, duyệt file... trên
máy chủ. 

+ *Một số lệnh ftp cơ bản:* 
 - **cd thu_muc:** Chuyển sang thư mục khác trên máy chủ
 - **dir:** Xem danh sách các file và thư mục của thư mục hiện thời trên máy chủ
 - **mdir thu_muc:** Tạo một thư mục mới có tên thu_muc trên máy chủ
 - **rmdir thu_muc:** Xoá (remove directory) một thư mục trên máy chủ 
 - **put file:** tải một file file (đầy đủ cả đường dẫn. VD: c:\tp\bin\baitap.exe) từ máy bạn đang sử dụng lên máy chủ. 
 - **close:** Đóng phiên làm việc 
 - **quit:** Thoát khỏi chương trình ftp, quay trở về chế độ DOS command.

- Công dụng : FTP là một giao thức được sử dụng để gửi và nhận file
giữa các máy tính với nhau. Windows đã cài đặt sẵn lệnh ftp, có tác
dụng như một chương trình chạy trên nền console (văn bản), cho phép
thực hiện kết nối đến máy chủ ftp.

##**7. Lệnh Net View :**
- Cú pháp: **Code: Net View [\\computer|/Domain[:ten_domain]]**
- Công dụng: Nếu chỉ đánh net view [enter], nó sẽ hiện ra danh sách các
máy tính trong mạng cùng domain quản lý với máy tính bạn đang sử dụng. 
+ Nếu đánh net view \\tenmaytinh, sẽ hiển thị các chia sẻ tài nguyên
của máy tính tenmaytinh . Sau khi sử dụng lệnh này, các bạn có thể sử
dụng lệnh net use để sử dụng các nguồn tài nguyên chia sẻ này.

##**8. Lệnh Net Use :**
- Cú pháp: **Code: Net use \\ip\ipc$ "pass" /user:"***"**
- ip: địa chỉ IP của victim. 
- ***: user của máy victim 
- pass: password của user Giả sử ta có đc user và pass của victim có IP
là 68.135.23.25 trên net thì ta đã có thể kết nối đến máy tính đó rùi
đấy! 
- Công dụng: kết nói một IPC$ đến máy tính victim (bắt đầu quá trình xâm nhập). 

##**9. Lệnh Net User :**
- Cú pháp: **Code: Net User [username pass] [/add]**
- Username : tên user cấn add 
- pass : password của user cần add Khi đã add được user vào rùi thì ta tiến hành add user này vào nhóm administrator.
Code: Net Localgroup Adminstrator [username] [/add] 
+ Công dụng: 
 - Nếu ta chỉ đánh lệnh Net User thì sẽ hiển thị các user có trong máy .
 - Nếu ta đánh lệnh Net User [username pass] [/add] thì máy tính sẽ tiến hành thêm một người dùng vào. 

##**10. Lệnh Shutdown :**
- Cú pháp: **Code: Shutdown [-m \\ip] [-t xx] [-i] [-l] [-s] [-r] [-a] [-f] [-c "commet] [-d up x:yy] (áp dụng cho win XP)**

- **Tham số -m\\ip** : ra lệnh cho một máy tính từ xa thực hiên các lệnh shutdown, restart,.. 
- **Tham số -t xx** : đặt thời gian cho việc thực hiện lệnh shutdown.
- **Tham số -l** : logg off (lưu ý ko thể thực hiện khi remote)
- **Tham số -s** : shutdown 
- **Tham số -r** : shutdown và restart
- **Tham số -a** : không cho shutdown
- **Tham số -f** : shutdown mà ko cảnh báo 
- **Tham số -c "comment"** : lời cảnh báo trước khi shutdown 
- **Tham số -d up x:yy** : ko rõ Code: shutdown \\ip (áp dụng win NT) 

- Công dụng:  Shutdown máy tính. 

##**11. Lệnh DIR :**
- Cú pháp: **Code: DIR [drive:][path][filename]**
- Công dụng: + Để xem file, folder. 

##**12. Lệnh DEL :** 
- Cú pháp: **Code: DEL [drive:][path][filename]**
- Công dụng: Xóa một file, thông thường sau khi xâm nhập vào hệ thống, ta
phái tiến hành xóa dấu vết của mình để khỏi bị phát hiện.

##**13. Lệnh tạo ổ đĩa ảo trên computer :**
- Cú pháp: **Code: Net use z: \\ip\C$ ( hoặc là IPC$ )**
- Công dụng: Tạo 1 đĩa ảo trên máy tính.

##**14. Lệnh Net Time :**
- Cú pháp: **Code: Net Time \\ip**
- Công dụng: Cho ta biết thời gian của victim, sau đó dùng lệnh AT để
khởi động chương trình. (các bạn có thể tham khảo lệnh AT tại phần
basic to hacking ở phần hacking and securities trong diễn đàn dttx.org)

##**15. Lệnh AT :**
- Cú pháp: **Code: AT \\ip** 
- Công dụng: Thông thường khi xâm nhập vào máy tính victim khi rút lui thì
ta sẽ tặng quà lưu niệm lên máy tính victim, khi đã copy troj hoặc
backdoor lên máy tính rùi ta sẽ dùng lệnh at để khởi động chúng.

##**16. Lệnh Telnet :**
- Cú pháp: **Code: telnet host port** 
- Công dụng: Kết nối đến host qua port xx 

##**17. Lệnh COPY :**
- Cú pháp: **Code: COPY /?** *Dùng lệnh trên để rõ hơn!* 
- Công dụng: Copy file.
- *lưu ý* : code ở đây được hiểu là mã lệnh các bạn không nên gõ vào chữ
code, nếu gõ code thì các bạn không thực hiện được những dòng mã lệnh
phía trên đâu.  

##**18. Lệnh SET :**
- Cú pháp: **Code: SET** 
- Công dụng: Displays, sets, or removes cmd.exe enviroment variables. 

##**19. Lệnh Nbtstat :**
- Cú pháp: **Code: Nbtstat /?** *Gõ lệnh trên để rõ hơn về lệnh này* 
- Công dụng: Display protocol statistic and curent TCP/IP connections using NBT (netbios over TCP?IP).




