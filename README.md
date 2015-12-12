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
	
