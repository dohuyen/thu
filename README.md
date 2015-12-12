#**I.Tìm hiểu các sử dụng VMWare WorkStation**

##**1. Cài đặt VMware Workstation trên Windowns**
- Đăng ký và download bản Free Trial VMware Workstation 9.0 
+Trong màn hình Welcome bạn bấm nút next.
+Trong màn hình Setup Type, bạn chọn Typical. 
+Trong màn hình Destination Folder, bạn chấp nhận vị trí cài đặt mặc định và bấm nút Next.
+Trong màn hình Software Updates, bạn bấm Next.
+Trong màn hình User Experience Improvement Program, bạn nhấn nút Next 
+Trong màn hình Shortcuts, bạn chọn vị trí tạo các shortcut cho VMware Workstation, sau đó nhấn Next:  
+Tại màn hình Ready to Perform the Requested Operations, bạn nhấn Continue. Sau bước này VMware Workstation sẽ được cài đặt. 
+Tại màn hình Enter License Key, bạn nhập Key được cấp qua Email khi bạn đăng ký tải VMware Workstation, sau đó nhấn Enter. 
+Nhấn nút Finish ở màn hình Setup Wizard Complete, sau đó khởi động lại máy để hoàn tất quá trình cài đặt.
##**2.Tạo máy ảo**
Sau khi mở phần mềm Vmware (phiên bản Vmware 9), bạn vào File, chọn New Virtual Machine.          
-Sau đó sẽ xuất hiện 1 hộp thoại: 
+ Mặc định của phần mềm là Typical: bạn sẽ tạo được ổ đĩa ảo với cái bước rất dễ. 
+ Còn ở phần Custom thì bạn có thể tạo ổ ảo với những gì mà mình thích.            
Bạn nhấn Next. Tiếp theo bảng hộp thoại xuất hiện nhằm hỏi bạn muốn tạo phần mềm gì để chạy trên hệ thống ổ đĩa ảo của mình và đường dẫn để cài đặt phần mềm đó. Ở đây chúng ta có 3 sự lựa chọn: Install from disc: bạn sẽ cài đặt phần mềm từ đĩa CD Installer disc image file (.iso): bạn sẽ cài đặt phần mềm có đuôi là .iso. File iso hiểu theo một cách thông thường thì đó là 1 dạng file nén. Có thể dùng được bằng cách giải nén hoặc chạy được trên ổ đĩa ảo. Mục còn lại thì Vmware sẽ tự động tạo 1 ổ đĩa trống và chờ bạn cài đặt phần mềm tùy thích để chạy.      

Ở đây tôi chọn mục 2 vì đã có sẵn file iso. Sau đó bạn nhấn thẻ Browse để chọn file iso cần chạy (phần mềm đó là Win8 bản Beta). Sau đó nhấn Next.   
 
-Kế đến, một hộp thoại khác sẽ xuất hiện giúp bạn chọn Hệ điều hành. Ở đây tôi chọn hệ điều hành Microsoft và phiên bản là Win8. Sau đó nhấn Next.              
 
-Một hộp thoại khác xuất hiện nhằm hỏi bạn về 2 vấn đề: Virtual Machine Name: tên của ổ đĩa ảo. Các bạn có thể đặt tên tùy theo ý thích của mình. Location: nơi sẽ lưu ổ đĩa. Vì bước tiếp theo bạn phải chọn dung lượng của ổ đĩa ảo. Nên tôi khuyến cáo các bạn nên chọn ổ đĩa nào dung lượng còn nhiều và không ảnh hưởng đến hoạt động của máy chủ thật.  Sau đó bạn nhấn Next.          
-Kế đến, Vmware sẽ hỏi bạn về dung lượng của ổ đĩa cứng trên máy ảo mà bạn muốn chia sẻ từ ổ cứng của máy chủ thật. Vmware sẽ tự động mặc định dung lượng tối thiểu là 60.0Gb, bạn có thể tùy chỉnh dung lượng theo ý thích của mình. Sau khi tùy chỉnh dung lượng tùy thích, bạn nhấn Next.             

-Bước cuối cùng, bạn sẽ điều chỉnh những thông số như: RAM, CPU, Display, Sound Card,… theo ý muốn của mình. Khuyến cáo: tạo vừa phải, đúng với các thông số của máy chủ thật của mình.             
Để tùy chỉnh, bạn nhấn thẻ Customize Hardware.             

Sau khi đã hoàn thành hết những gì theo ý muốn của mình trong bảng tùy chỉnh, bạn nhấn Close và nhấn Finish để hoàn thành việc tạo ổ đĩa ảo của mình.             
Sau khi nhấn Finish, cửa sổ Vmware của bạn sẽ như thế này.            
 
Để có thể chạy được ổ đĩa ảo vừa tạo, bạn nhấn vào nút Power on this virtual machine (có biểu tượng là một hình tam giác màu xanh lá cây) Nếu bạn chưa hài lòng với những thông số kĩ thuật mà mình vừa tạo thì nhấn vào Edit virtual machine setting để thiết lập lại những gì mong muốn.

#**II.Các chế độ card mạng trong VMWare WorkStation**
**Switch ảo** (*Virtual Switch*) cũng giống như switch vật lý, một Virtual Switch kết nối các thành phần mạng ảo lại với nhau. Những  switch ảo hay còn gọi là mạng ảo, chúng có tên là VMnet0, VMnet1, VMnet2… một số switch ảo được gắn vào mạng một cách mặc định. (Ta có thể thêm, bớt, chỉnh các option của VMnet bằng cách vào menu Edit -> Virtual Network Editor...).
Khi ta tạo các VMnet thì trên máy thật của ta sẽ tạo ra những card mạng ảo tương ứng, riêng VMnet0 kết nối trực tiếp với card mạng vật lý nên không tạo ra card VMnet.
**DHCP server ảo DHCP**(*Dynamic Host Configuration*) server ảo cung cấp địa chỉ IP cho các máy ảo trong việc kết nối máy ảo vào các Switch ảo không có tính năng Bridged (VMnet0).
Nếu bạn muốn bỏ chế độ DHCP của VMnet nào, bạn chỉ cần bỏ dấu check tại Use local DHCP service to distribute IP address to VMs
**Card mạng ảo** Khi bạn tạo một máy ảo mới (New Virtual Machine wizard), card mạng ảo được tạo ra cho máy ảo. Những card mạng này hiển thị trên hệ điều hành máy ảo như là AMD PCNET PCI hay Intel Pro/1000 MT Server Adapter. Thêm bớt card mạng bạn nhấn vào nút Add... hoặc Remove... trong Virtual Machine Setting.
**Card mạng trên máy tính ảo**  Khi cài đặt, VMWare tạo ra ở máy thật 2 card mạng ảo.
 VMWare Virtual Ethernet Adapter for VMnet1.
 VMWare Virtual Ethernet Adapter for Vmnet8.
 2 card mạng này có thể đựơc sử dụng để máy thật giao tiếp với các máy tính ảo.
 Khi “gắn” một card mạng vào một máy ảo, card mạng này có thể được chọn 1 trong 3 loại sau :
 - **Bridge :**
Card Bridge trên máy ảo chỉ có thể giao tiếp với card mạng thật trên máy thật.Nó  có thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối.
- **Host-only :**
Card Host-only chỉ có thể giao tiếp với card mạng ảo VMnet1 trên máy thật; chỉ có thể giao tiếp với các card Host-only trên các máy ảo khác.
Card Host-only không thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối.
- **NAT :**
Card NAT chỉ có thể giao tiếp với card mạng ảo VMnet8 trên máy thật; chỉ có thể giao tiếp với các card NAT trên các máy ảo khác.
Card NAT không thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối. Tuy nhiên nhờ cơ chế NAT được tích hợp trong VMWare, máy tính ảo có thể gián tiếp liên lạc với mạng vật lý bên ngoài.


#**III.Cách sử dụng trình soạn thảo vi**
##**1.Các chế độ trong vi**
###**a.Khởi động vi bằng lệnh**
vi<tên file>
	
###**b.Chế độ lệnh**
Dành cho việc biên tập và điều khển.Các lện thường gồm 1 ký tự như là: y,d,j,...
Nếu muốn thực hiện lệnh n lần, ta đặt n trước lệnh. 
-Ví dụ :5dw – xóa 5 từ.
	
###**c.Chế độ hai chấm (tìm kiếm)**
Gõ dấu hai chấm ":" từ chế độ lệnh.
Trong chế độ này, ta có thể thực hiện: tìm kiếm, lưu trữ, thoát hoặc chạy một lệnh của **shell**.
Gõ phím"Esc" để trở về chế độ lệnh.
	
###**d.Chế độ soạn thảo**
Gõ"i" hoặc"a" từ chế độ lệnh để vào chế độ này. 
Gõ "Esc" để trở về chế độ lệnh. 
Dùng chế độ này để soạn thảo văn bản.
	
##**2.Các phần tử văn bản(*text items*)**
Các phần tử như :ký tự,từ, đoạn được định nghĩa trong chế độ lệnh cho phép áp dụng các lệnh soạn thảo lên tài liệu văn bản không cần sử dụng chuột.
**b/e** :di chuyển về đầu/cuối từ hiện hành.
**(/)** :di chuyển về đầu/cuối câu hiện hành.
**{/}** :di chuyển về đầu/cuối đoạn hiện hành.
**w** :tương tự lệnh b nhưng bao gồm cả các khoảng trắng sau từ.
**^** :di chuyển về đầu hàng.
**$** :di chuyển về cuối hàng.
**1G** :di chuyển về đầu tập tin.
**G** :di chuyển về cuối tập tin(chú ý G in hoa).
Có thể sử dụng các phần tử này để thực hiện lệnh, ví dụ như xóa, sao chép,...

##**3.Soạn thảo văn bản**
**a** :Vào chế độ soạn tahor, con trỏ năm ở ký tự cuối hàng.
**A** :Vào chế độ soạn thảo, con trỏ nằm ở sau ki tự cuối hàng.
**i** :Vào chế độ soạn thảo, con trỏ nằm ở vị trí hiện hành.
**o** :Thêm một hàng mới dưới hàng hiện hành.
**O** :Thêm một hàng mới trên hảng hiện hành.
**s** :Xóa ký tự hiện hành và vào chế độ soạn thảo.
**S** :Xóa dòng hiện hành và vào chế độ soạn thảo.
	
##**4.Xóa văn bản**
Trong chế độ lệnh, gõ **x** để xóa 1 ký tự, **d** để xóa 1 hàng.
Có thể áp dụng lệnh d với các phần tử văn bản .
-Ví dụ :
**dw** :xóa 1 từ.
**d$** :xóa từ vị trí hiện hành đến cuối hàng.
**d}** : xóa từ vị trí hiện hành đến cuối đoạn.
Để xóa 1 phần tử và chuyển sang chế độ soạn thảo, dùng lệnh **c**.
	
##**5.Sao chép/dán**
Trong chế độ lệnh :
**y** :sao chép(yank)
**p** :dán(paste)
Nếu cả một dòng được sao chép và dán thì nó sẽ được đặt dưới dòng có con trỏ.
Có thể sử dụng với các phần tử văn bản.
-Ví dụ :
**y$** :sao chép từ vị trí hiện hành đến cuối hàng.
**yy** :sao chép cả hàng hiện hành.
**3yy** :sao chép 3 hàng liên tiếp.

##**6.Tìm kiếm**
Để tìm kiếm, ta phải chuyển sang chế độ "**hai chấm**"
"/" để tìm xuôi, "?" để tìm ngược .
Có thể tìm kiếm, thay thế tương tự như lệnh **sed**. 
-Ví dụ :
**/\<comp** :tìm những từ bắt đầu bằng comp.
**/^z** :tìm những hàng bắt đầu bằng z.
**:%s/VAR/var** :Thay thế VAR bằng var.
**:g/XX/s/YY/** :Thay thế XX bằng YY.
	
##**7.Lưu trữ & các lệnh khác**
Từ chế độ lệnh hoặc hai chấm, gõ :
**:w** :lưu văn bản lại.
**:w new_file** :Lưu văn bản với tên mới new_file.
**:w 12,15 extract** : lưu các hàng từ 12 đến 5 vào tập tin extract.
**:r extract** :đọc tập tin extract vào xem nó tại vị trí con trỏ.
**:q** :thoát khỏi vi.
**:q!** :thoát khồng cần hỏi.
**"wq** :save và thoát.
**:x** :tương tự :wq
**u** : hủy bỏ thao tác vừa thực hiện(undo) trong chế độ lệnh.
	
#**IV.Một số lệnh cấu hình Network trên Ubuntu**
##**1.Các câu lệnh kiểm tra thông tin mạng trong Ubuntu**
LỆNH LINUX	  &  MỤC ĐÍCH / MIÊU TẢ
ifconfig -a       : Kiểm tra máy có bao nhiêu card mạng
  grep eth	  
  ifconfig	  : Xem thông tin cấu hình các card mạng (MAC, địa chỉ IP, gateway..)  của tất cả các card mạng trong máy (tương tự                       lệnh ipconfig của Windows)
  ifconfig        : Xem thông tin cấu hình của card mạng có tên là card-name (ví dụ: ifconfìg eth0)
  card-name 
  route -n	  : Kiểm tra đường đi của gói tin (tương tự lệnh route trong Windows).
##**2.Các câu lệnh cấu hình mạng trong Ubuntu**
LỆNH LINUX	                      & MỤC ĐÍCH / MIÊU TẢ
sudo ifconfig eth0 up             : Enable card mạng eth0 trong Ubuntu
  sudo ifconfig eth0 down    	    : Disable card mạng eth0 trong Ubuntu
 ifconfig card IP1 netmask IP2    : Cấu hình mạng cho Ubuntu, ví dụ: để thiết lập IP cho card eth0 IP là 192.168.1.100, netmask là                                        255.255.255.0 thì ta dùng lệnh sau: ifconfig eth0 192.168.1.2 netmask 255.255.255.0
                                   Lưu ý: Cách cấu hình này sẽ bị mất giá trị khi máy khởi động lại
 vi /etc/network/interfaces	      : Thiết lập file cấu hình mạng trong Ubuntu
 /etc/init.d/networking restart   : Khởi động lại card mạng trong Ubuntu (để thay đổi có hiệu lực)
  vi /etc/resolv	                  Thiết lập name server cho Ubuntu. Ví dụ, nhập vào nội dung file là:
                                    nameserver 8.8.8.8
                                    nameserver 8.8.8.4
 route add default gw 192.168.1.1	: Đặt địa chỉ IP 192.168.1.1 làm default gateway trong Ubuntu. Ngược lại với add ta dùng lệnh delete                                     (ví dụ: route delete default gw 192.168.1.1)
route add -net 192.168.5.0 mask   : Để add một routing tĩnh đến mạng (cho card mạng eth0). Ngược lại với add ta dùng lệnh delete.
255.255.255.0 dev eth0            	
##**3. Các câu lệnh Command Line khác về mạng trong Ubuntu**
LỆNH LINUX          &	MỤC ĐÍCH / MIÊU TẢ
 netstat    	      : Hiển thị các kết nối mạng (tương tự trong Windows)
 traceroute maychu  : Trace gói định tuyến tới máy chủ
 nslookup	          : Truy vấn máy chủ tên miền
 rlogin maychu	    : Kết nối với một hệ thống ở xa
  telnet maychu	    : Kết nối tới một hệ thống ở xa (tương tác tốt hơn lệnh rlogin)
 rcp taptin maytuxa : Sao chép taptin từ một máy tính maytuxa
 ftp	              : Truyền tập tin giữa các hệ thống trên một mạng
 rsh lenh	          : Chạy một lệnh trên một hệ thống ở xa mà không cần đăng nhập
 ping maychu	      : Kiểm tra kết nối tới một hệ thống ở xa (tương tự trong Windows)
 lcd path	          : Thay đổi thư mục máy cục bộ khi đã đăng nhập ở trên máy ở xa
 mesg y/n	          : Đặt tùy chọn để các người dùng khác viết thông điệp cho bạn
 write user	        : Gửi tin nhắn cho người dùng khác
 talk user	        : Cho phép 2 người chat với nhau.

#**V.Phân tích gói tin IP datagram**

![Cấu trúc gói tin IP](https://kysudien.files.wordpress.com/2014/12/1e56a-capture.png?w=665.png)

**VERS (4 bit):** chỉ ra phiên bản hiện hành của IP đang được dùng, có 4 bit. Nếu trường này khác với phiên bản IP của thiết bị nhận,                   thiết bị nhận sẽ từ chối và loại bỏ các gói tin này.

**HLEN (4 bit):** chỉ độ dài phần tiêu đề (Internet Header Length) của datagram, tính theo đơn vị word (32 bits). Nếu không có trường                   này thì độ dài mặc định của phần tiêu đề là 5 từ.
**Service Type (8 bits):** cho biết các thông tin về loại dịch vụ và mức ưu tiên của gói IP, có dạng cụ thể như sau:
**Precedence (3 bits):** chỉ thị về quyền ưu tiên gửi datagram, cụ thể là:

- 111 Network Control (cao nhất)
- 011- flash
- 110 Internetwork Control
- 010 Immediate
- 101 CRITIC/ECP
- 001 Priority
- 100 Flas Override
- 000 Routine (thấp nhất)

**D** (delay)  (1 bit) : chỉ độ trễ yêu cầu
- D = 0 độ trễ bình thường,
- D = 1 độ trễ thấp

**T** (Throughput) (1 bit) : chỉ số thông lượng yêu cầu
- T = 0 thông lượng bình thường
- T = 1 thông lượng cao

**R** (Reliability) (1 bit): chỉ độ tin cậy yêu cầu
- R = 0 độ tin cậy bình thường
- R = 1 độ tin cậy cao

**– Total Length (16 bits):** chỉ độ dài toàn bộ datagram, kể cả phần header (tính theo đơn vị bytes), vùng dữ liệu của datagram có                                 thể dài tới 65535 bytes. Để biết chiều dài của dữ liệu chỉ cần lấy tổng chiều dài này trừ đi HLEN.
**– Identification (16 bit):**cùng với các tham số khác như (Source Address và Destination Address) tham số này dùng để định danh duy                               nhất cho một datagram trong khoảng thời gian nó vẫn còn trên liên mạng. Đây là 1 số nguyên.
**– Flags (3 bits):**        Liên quan đến sự phân đoạn (Fragment) của datagram. cụ thể:
**0**        **DF**        **MF**
**Bit 0**: reserved chưa sử dụng luôn lấy giá trị 0
**Bit 1**:
- DF = 1: Gói tin bị phân đoạn, có nhiều hơn 1 đoạn
- DF = 0: Gói tin ko bị phân đoạn.
**Bit 2**:
- MF = 0: Đây là đoạn cuối cùng
- MF = 1: Đây chưa phải là đoạn cuối cùng, còn đoạn khác phía sau nữa

**Fragment Offset (13 bits):** chỉ vị trí của đoạn (fragment) ở trong datagram, tính theo đơn vị 64 bits, có nghĩa là mỗi đoạn (trừ                                  đoạn cuối cùng) phải chứa một vùng dữ liệu có độ dài là bội của 64 bits. Nó được dùng để ghép các mảnh                                Datagram lai với nhau
**Time To Live (TTL – 8 bit):**giá trị này được đặt lúc bắt đầu gửi gói tin. Và nó sẽ giảm dần khi đi qua 1 router. gói tin sẽ bị hủy                                nếu giá trị này = 0 khi chưa đến đích. Việc làm này nhằm giải quyết vấn đề gói tin bị lặp vô hạn trên                                 mạng.
**Protocol (8 bits):** Chỉ ra giao thức lớp trên, chẳng hạn như TCP hay UDP
**Header Checksum:** Mã kiểm soát lỗi sử dụng phương pháp CRC (Cyclic Redundancy Check) dùng để đảm bảo thông tin về gói dữ liệu được                     truyền đi một cách chính xác (mặc dù dữ liệu có thể bị lỗi). Nếu như việc kiểm tra này thất bại, gói dữ liệu sẽ bị                     huỷ bỏ tại nơi xác định được lỗi. Cần chú ý là IP không cung cấp một phương tiện truyền tin cậy bởi nó không cung                     cấp cho ta một cơ chế để xác nhận dữ liệu truyền tại điểm nhận hoặc tại những điểm trung gian. Giao thức IP không                     có cơ chế Error Control cho dữ liệu truyền đi, không có cơ chế  kiểm soát luồng dữ liệu (flow control).
**Source Address (32 bits):** Địa chỉ của trạm nguồn.
**Destination Address (32 bits):** Địa chỉ của trạm đích.
**Option (có độ dài thay đổi):** sử dụng trong một số trường hợp, nhưng thực tế chúng rất ít dùng. Option bao gồm bảo mật, chức năng                                   định tuyến đặc biệt
**Padding (độ dài thay đổi):** Các số 0 được bổ sung vào field này để đảm bảo IP Header luôn la bội số của 32 bit.
**Data (độ dài thay đổi):** Vùng dữ liệu có độ dài là bội của 8 bits, tối đa là 65535 bytes.

