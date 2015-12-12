#**V.Phân tích gói tin IP datagram**

![Cấu trúc gói tin IP](https://kysudien.files.wordpress.com/2014/12/1e56a-capture.png?w=665.png)

- **VERS (4 bit):** chỉ ra phiên bản hiện hành của IP đang được dùng, có 4 bit. Nếu trường này khác với phiên bản IP của thiết bị nhận, thiết bị nhận sẽ từ chối và loại bỏ các gói tin này.

- **HLEN (4 bit):** chỉ độ dài phần tiêu đề (Internet Header Length) của datagram, tính theo đơn vị word (32 bits). Nếu không có trường này thì độ dài mặc định của phần tiêu đề là 5 từ.
- **Service Type (8 bits):** cho biết các thông tin về loại dịch vụ và mức ưu tiên của gói IP, có dạng cụ thể như sau:
- **Precedence (3 bits):** chỉ thị về quyền ưu tiên gửi datagram, cụ thể là:

- 111 Network Control (cao nhất)
- 011- flash
- 110 Internetwork Control
- 010 Immediate
- 101 CRITIC/ECP
- 001 Priority
- 100 Flas Override
- 000 Routine (thấp nhất)

- **D** (delay)  (1 bit) : chỉ độ trễ yêu cầu
+ D = 0 độ trễ bình thường,
+ D = 1 độ trễ thấp

- **T** (Throughput) (1 bit) : chỉ số thông lượng yêu cầu
+ T = 0 thông lượng bình thường
+ T = 1 thông lượng cao

- **R** (Reliability) (1 bit): chỉ độ tin cậy yêu cầu
+ R = 0 độ tin cậy bình thường
+ R = 1 độ tin cậy cao

- **– Total Length (16 bits):** chỉ độ dài toàn bộ datagram, kể cả phần header (tính theo đơn vị bytes), vùng dữ liệu của datagram có                                 thể dài tới 65535 bytes. Để biết chiều dài của dữ liệu chỉ cần lấy tổng chiều dài này trừ đi HLEN.
- **– Identification (16 bit):**cùng với các tham số khác như (Source Address và Destination Address) tham số này dùng để định danh                                   duy nhất cho một datagram trong khoảng thời gian nó vẫn còn trên liên mạng. Đây là 1 số nguyên.
- **– Flags (3 bits):** Liên quan đến sự phân đoạn (Fragment) của datagram. cụ thể:

**0**        **DF**        **MF**
- **Bit 0**: reserved chưa sử dụng luôn lấy giá trị 0
- **Bit 1**:
+ DF = 1: Gói tin bị phân đoạn, có nhiều hơn 1 đoạn
+ DF = 0: Gói tin ko bị phân đoạn.
- **Bit 2**:
+ MF = 0: Đây là đoạn cuối cùng
+ MF = 1: Đây chưa phải là đoạn cuối cùng, còn đoạn khác phía sau nữa

- **Fragment Offset (13 bits):** chỉ vị trí của đoạn (fragment) ở trong datagram, tính theo đơn vị 64 bits, có nghĩa là mỗi đoạn (trừ                                  đoạn cuối cùng) phải chứa một vùng dữ liệu có độ dài là bội của 64 bits. Nó được dùng để ghép các                                    mảnh Datagram lai với nhau
- **Time To Live (TTL – 8 bit):**giá trị này được đặt lúc bắt đầu gửi gói tin. Và nó sẽ giảm dần khi đi qua 1 router. gói tin sẽ bị                                  hủy nếu giá trị này = 0 khi chưa đến đích. Việc làm này nhằm giải quyết vấn đề gói tin bị lặp vô hạn                                  trên mạng.
- **Protocol (8 bits):** Chỉ ra giao thức lớp trên, chẳng hạn như TCP hay UDP
- **Header Checksum:** Mã kiểm soát lỗi sử dụng phương pháp CRC (Cyclic Redundancy Check) dùng để đảm bảo thông tin về gói dữ liệu                           được truyền đi một cách chính xác (mặc dù dữ liệu có thể bị lỗi). Nếu như việc kiểm tra này thất bại, gói dữ                          liệu sẽ bị huỷ bỏ tại nơi xác định được lỗi. Cần chú ý là IP không cung cấp một phương tiện truyền tin cậy bởi                        nó không cung cấp cho ta một cơ chế để xác nhận dữ liệu truyền tại điểm nhận hoặc tại những điểm trung gian.                         Giao thức IP không có cơ chế Error Control cho dữ liệu truyền đi, không có cơ chế  kiểm soát luồng dữ liệu (flow                      control).
- **Source Address (32 bits):** Địa chỉ của trạm nguồn.
- **Destination Address (32 bits):** Địa chỉ của trạm đích.
- **Option (có độ dài thay đổi):** sử dụng trong một số trường hợp, nhưng thực tế chúng rất ít dùng. Option bao gồm bảo mật, chức năng                                   định tuyến đặc biệt
- **Padding (độ dài thay đổi):** Các số 0 được bổ sung vào field này để đảm bảo IP Header luôn la bội số của 32 bit.
- **Data (độ dài thay đổi):** Vùng dữ liệu có độ dài là bội của 8 bits, tối đa là 65535 bytes.
