# ĐẦU RA 03 --- ĐẶC TẢ YÊU CẦU HỆ THỐNG

> **Phạm vi:** Phòng khám An Tâm\
> **Nguồn xây dựng:** Case Study, CR-01 và SC-01 → SC-04.\
> **Lưu ý:** Các số liệu chưa được phòng khám xác nhận được đánh dấu
> `[Giả định]` hoặc `[Cần xác nhận]`.

------------------------------------------------------------------------

# A. YÊU CẦU CHỨC NĂNG

## FR-01 --- Tra cứu chuyên khoa, bác sĩ và khung giờ khám

  ID          Loại        Nguồn               Độ ưu tiên   Phiên bản
  ----------- ----------- ------------------- ------------ -----------
  **FR-01**   Chức năng   Bệnh nhân / SC-01   **Must**     1.0

**Mô tả:** Hệ thống phải cho phép bệnh nhân lựa chọn hình thức khám,
chuyên khoa, bác sĩ và xem lịch làm việc cùng các khung giờ còn trống
của bác sĩ đã chọn.

**Lý do:** Giúp bệnh nhân chủ động lựa chọn bác sĩ và thời gian khám
thay vì phải liên hệ trực tiếp với nhân viên phòng khám để hỏi lịch.

**Tiêu chí kiểm chứng:** Khi bệnh nhân chọn một chuyên khoa và bác sĩ có
lịch làm việc, hệ thống phải hiển thị các khung giờ đang ở trạng thái
**"Khả dụng"**; các khung giờ đã bị khóa/đã đặt không được hiển thị là
có thể đặt.

------------------------------------------------------------------------

## FR-02 --- Đặt lịch khám

  ID          Loại        Nguồn               Độ ưu tiên   Phiên bản
  ----------- ----------- ------------------- ------------ -----------
  **FR-02**   Chức năng   Bệnh nhân / SC-01   **Must**     1.0

**Mô tả:** Hệ thống phải cho phép bệnh nhân tạo lịch hẹn bằng cách chọn
khung giờ và cung cấp các thông tin đăng ký gồm họ tên, số điện thoại,
ngày tháng năm sinh, giới tính và mô tả tóm tắt triệu chứng.

**Lý do:** Số hóa quy trình đặt lịch hiện đang được thực hiện bằng sổ và
điện thoại, đồng thời giúp phòng khám có trước thông tin cơ bản của bệnh
nhân.

**Tiêu chí kiểm chứng:** Khi bệnh nhân nhập đầy đủ thông tin hợp lệ và
xác nhận đặt lịch, hệ thống phải tạo bản ghi lịch hẹn tương ứng với bác
sĩ, chuyên khoa, ngày giờ và hình thức khám đã chọn.

------------------------------------------------------------------------

## FR-03 --- Xác nhận và thông báo lịch hẹn

  ID          Loại        Nguồn                       Độ ưu tiên   Phiên bản
  ----------- ----------- --------------------------- ------------ -----------
  **FR-03**   Chức năng   Bệnh nhân / SC-01 / CR-01   **Must**     1.1

**Mô tả:** Hệ thống phải tạo mã lịch hẹn duy nhất và gửi SMS/Email xác
nhận cho bệnh nhân sau khi lịch hẹn được xác nhận. Đối với lịch khám
trực tuyến, hệ thống chỉ được gửi xác nhận sau khi nhận được tín hiệu
thanh toán thành công từ cổng thanh toán.

**Lý do:** Bệnh nhân cần có thông tin xác nhận chính thức và phòng khám
cần tránh việc xác nhận lịch khám trực tuyến trước khi nhận được thanh
toán.

**Tiêu chí kiểm chứng:** - Lịch trực tiếp được xác nhận → hệ thống tạo
mã lịch hẹn và gửi SMS/Email. - Lịch trực tuyến nhưng thanh toán thất
bại/chưa hoàn tất → hệ thống không gửi xác nhận lịch chính thức. - Lịch
trực tuyến thanh toán thành công → hệ thống tạo mã lịch, lưu trạng thái
**"Đã xác nhận"** và kích hoạt gửi SMS/Email.

------------------------------------------------------------------------

## FR-04 --- Tra cứu và xác thực lịch hẹn

  ID          Loại        Nguồn               Độ ưu tiên   Phiên bản
  ----------- ----------- ------------------- ------------ -----------
  **FR-04**   Chức năng   Bệnh nhân / SC-03   **Must**     1.0

**Mô tả:** Hệ thống phải cho phép bệnh nhân tra cứu lịch hẹn bằng Mã
lịch hẹn và Số điện thoại đăng ký, sau đó xác thực bằng mã OTP trước khi
hiển thị thông tin chi tiết.

**Lý do:** Cho phép bệnh nhân quản lý lịch hẹn mà không cần trực tiếp
đến phòng khám, đồng thời hạn chế người không có quyền truy cập thông
tin lịch hẹn.

**Tiêu chí kiểm chứng:** Với Mã lịch hẹn và số điện thoại hợp lệ, hệ
thống gửi OTP gồm **6 chữ số**; OTP có hiệu lực **3 phút \[Giả định
G-07\]**. Chỉ sau khi OTP hợp lệ, hệ thống mới hiển thị thông tin lịch
hẹn và các thao tác được phép.

------------------------------------------------------------------------

## FR-05 --- Đổi hoặc hủy lịch hẹn

  ID          Loại        Nguồn               Độ ưu tiên   Phiên bản
  ----------- ----------- ------------------- ------------ -----------
  **FR-05**   Chức năng   Bệnh nhân / SC-03   **Must**     1.0

**Mô tả:** Hệ thống phải cho phép bệnh nhân đã xác thực lịch hẹn thực
hiện đổi khung giờ hoặc hủy lịch khi đáp ứng điều kiện thời gian do
phòng khám quy định.

**Lý do:** Giúp bệnh nhân chủ động điều chỉnh lịch và giảm khối lượng xử
lý thủ công của nhân viên tiếp nhận.

**Tiêu chí kiểm chứng:** Khi bệnh nhân yêu cầu đổi/hủy lịch, hệ thống
phải kiểm tra thời gian còn lại trước giờ khám. Điều kiện tối thiểu
**120 phút \[Giả định G-06 -- Cần phòng khám xác nhận\]**; nếu không
đạt, hệ thống phải từ chối thao tác tự động và hướng dẫn bệnh nhân liên
hệ phòng khám.

------------------------------------------------------------------------

## FR-06 --- Kiểm tra và xác thực dữ liệu đặt lịch

  ID          Loại        Nguồn               Độ ưu tiên   Phiên bản
  ----------- ----------- ------------------- ------------ -----------
  **FR-06**   Chức năng   Bệnh nhân / SC-01   **Must**     1.0

**Mô tả:** Hệ thống phải kiểm tra tính đầy đủ và hợp lệ của dữ liệu bệnh
nhân trước khi tạo lịch hẹn.

**Lý do:** Ngăn dữ liệu thiếu hoặc sai định dạng làm ảnh hưởng đến việc
liên hệ bệnh nhân và xử lý lịch khám.

**Tiêu chí kiểm chứng:** Nếu bệnh nhân bỏ trống trường bắt buộc hoặc
nhập số điện thoại không đủ **10 chữ số**, hệ thống không được tạo lịch
và phải đánh dấu trường dữ liệu lỗi kèm thông báo để bệnh nhân sửa lại.

------------------------------------------------------------------------

## FR-07 --- Giải phóng khung giờ sau khi hủy lịch

  --------------------------------------------------------------------------
  ID             Loại           Nguồn          Độ ưu tiên     Phiên bản
  -------------- -------------- -------------- -------------- --------------
  **FR-07**      Chức năng      Nhân viên tiếp **Must**       1.0
                                nhận / Bệnh                   
                                nhân / SC-03                  

  --------------------------------------------------------------------------

**Mô tả:** Khi một lịch hẹn được hủy hợp lệ, hệ thống phải tự động
chuyển khung giờ tương ứng về trạng thái **"Khả dụng"** để có thể tiếp
tục được đặt.

**Lý do:** Tránh giữ lại các khung giờ không còn được sử dụng và tối ưu
số lượt khám trong ngày.

**Tiêu chí kiểm chứng:** Sau khi lịch hẹn được hủy thành công, trạng
thái khung giờ cũ phải chuyển thành **"Khả dụng"** và có thể được bệnh
nhân khác lựa chọn.

------------------------------------------------------------------------

## FR-08 --- Xử lý bác sĩ nghỉ ca đột xuất

  ID          Loại        Nguồn                        Độ ưu tiên   Phiên bản
  ----------- ----------- ---------------------------- ------------ -----------
  **FR-08**   Chức năng   Quản lý phòng khám / SC-04   **Must**     1.0

**Mô tả:** Hệ thống phải cho phép quản lý phòng khám đóng ca trực của
bác sĩ khi bác sĩ nghỉ đột xuất, khóa các khung giờ chưa được đặt và
chuyển các lịch hẹn bị ảnh hưởng sang trạng thái hủy bởi phòng khám.

**Lý do:** Ngăn bệnh nhân tiếp tục đặt lịch với bác sĩ không thể khám và
hỗ trợ phòng khám xử lý tập trung khi có sự cố nhân sự.

**Tiêu chí kiểm chứng:** Sau khi quản lý xác nhận đóng ca, toàn bộ khung
giờ còn lại của ca phải chuyển sang trạng thái **"Đã khóa do bác sĩ nghỉ
đột xuất"**; các lịch hẹn thuộc ca bị ảnh hưởng phải được chuyển sang
trạng thái **"Đã hủy bởi phòng khám do bác sĩ vắng mặt"**.

------------------------------------------------------------------------

## FR-09 --- Thông báo khi lịch khám bị thay đổi hoặc hủy

  --------------------------------------------------------------------------
  ID             Loại           Nguồn          Độ ưu tiên     Phiên bản
  -------------- -------------- -------------- -------------- --------------
  **FR-09**      Chức năng      Quản lý phòng  **Must**       1.0
                                khám / Bệnh                   
                                nhân / SC-04                  

  --------------------------------------------------------------------------

**Mô tả:** Hệ thống phải gửi SMS/Email thông báo cho bệnh nhân khi lịch
khám bị hủy hoặc thay đổi do phòng khám, đồng thời cung cấp thông tin
cần thiết để bệnh nhân biết trạng thái mới của lịch.

**Lý do:** Giảm tình trạng bệnh nhân đến phòng khám khi lịch đã bị hủy
và giảm số cuộc gọi thông báo thủ công của nhân viên.

**Tiêu chí kiểm chứng:** Khi quản lý đóng ca có bệnh nhân bị ảnh hưởng,
hệ thống phải tạo và gửi thông báo đến **100% bệnh nhân thuộc ca bị ảnh
hưởng**; trường hợp SMS thất bại phải được đánh dấu để nhân viên tiếp
nhận thực hiện liên hệ thay thế.

------------------------------------------------------------------------

## FR-10 --- Ngăn đặt trùng lịch

  ID          Loại        Nguồn               Độ ưu tiên   Phiên bản
  ----------- ----------- ------------------- ------------ -----------
  **FR-10**   Chức năng   Bệnh nhân / SC-01   **Must**     1.0

**Mô tả:** Hệ thống phải kiểm tra các lịch hẹn hiện có của bệnh nhân
trước khi tạo lịch mới và từ chối đặt lịch nếu bệnh nhân đã có lịch
trong cùng khung giờ.

**Lý do:** Tránh phát sinh lịch hẹn trùng, gây sai lệch danh sách bệnh
nhân và ảnh hưởng đến khả năng phục vụ của phòng khám.

**Tiêu chí kiểm chứng:** Khi hệ thống phát hiện số điện thoại của bệnh
nhân đã có lịch hẹn trong cùng khung giờ, hệ thống phải **không tạo lịch
mới** và hiển thị thông báo yêu cầu bệnh nhân kiểm tra lại lịch hiện có.

------------------------------------------------------------------------

# B. YÊU CẦU CHỨC NĂNG BỔ SUNG TỪ CR-01

## FR-11 --- Thanh toán trước cho lịch khám trực tuyến

  ID          Loại        Nguồn                        Độ ưu tiên   Phiên bản
  ----------- ----------- ---------------------------- ------------ -----------
  **FR-11**   Chức năng   Quản lý phòng khám / CR-01   **Must**     1.1

**Mô tả:** Đối với hình thức khám trực tuyến, hệ thống phải tích hợp
cổng thanh toán điện tử và yêu cầu bệnh nhân thanh toán trước khi lịch
hẹn được xác nhận chính thức. Hệ thống phải tạm giữ khung giờ trong **15
phút \[Giả định kỹ thuật G-05\]** trong thời gian chờ thanh toán.

**Lý do:** Ngăn tình trạng đặt lịch trực tuyến nhưng không thanh toán,
gây lãng phí khung giờ làm việc của bác sĩ.

**Tiêu chí kiểm chứng:** 1. Bệnh nhân chọn khám trực tuyến → hệ thống
giữ khung giờ và chuyển sang cổng thanh toán. 2. Thanh toán thành công →
hệ thống nhận phản hồi giao dịch và xác nhận lịch. 3. Thanh toán thất
bại/hủy → lịch không được xác nhận và khung giờ được giải phóng. 4.
Không thanh toán trong **15 phút \[Giả định G-05\]** → hệ thống tự động
hủy phiên giữ chỗ và chuyển khung giờ về **"Khả dụng"**.

------------------------------------------------------------------------

## FR-12 --- Tự động hoàn tiền khi hủy lịch khám trực tuyến

  ID          Loại        Nguồn                        Độ ưu tiên   Phiên bản
  ----------- ----------- ---------------------------- ------------ -----------
  **FR-12**   Chức năng   Quản lý phòng khám / CR-01   **Must**     1.1

**Mô tả:** Khi bác sĩ hoặc phòng khám chủ động hủy một lịch khám trực
tuyến đã thanh toán, hệ thống phải tự động phát lệnh hoàn **100% tiền
viện phí** thông qua cổng thanh toán và gửi thông báo cho bệnh nhân.

**Lý do:** Bệnh nhân đã thanh toán trước nhưng không thể sử dụng dịch vụ
do nguyên nhân từ phía phòng khám/bác sĩ, vì vậy hệ thống phải xử lý
nghĩa vụ hoàn tiền và thông báo minh bạch.

**Tiêu chí kiểm chứng:** 1. Xác định các giao dịch ở trạng thái **"Đã
thanh toán"**. 2. Phát lệnh hoàn tiền **100%** qua cổng thanh toán. 3.
Nhận mã xác nhận hoàn tiền. 4. Cập nhật giao dịch thành **"Đã hoàn
tiền"**, lưu mã giao dịch và thời gian hoàn tiền. 5. Gửi SMS/Email cho
bệnh nhân kèm thông tin đối soát.

Nếu cổng thanh toán lỗi/timeout, hệ thống phải chuyển giao dịch sang
trạng thái **"Chờ xử lý hoàn tiền thủ công"** và cảnh báo cho bộ phận
phụ trách.

> **Lưu ý:** Khoảng thời gian 1--3 ngày làm việc để tiền thực tế về tài
> khoản là **\[Giả định\]**, không phải cam kết của hệ thống.

------------------------------------------------------------------------

# C. YÊU CẦU PHI CHỨC NĂNG

## Nhóm 1 --- Hiệu năng

### NFR-01 --- Thời gian phản hồi thao tác thông thường

  --------------------------------------------------------------------------
  ID             Loại           Nguồn          Độ ưu tiên     Phiên bản
  -------------- -------------- -------------- -------------- --------------
  **NFR-01**     Phi chức năng  Nhu cầu hệ     **Must**       1.0
                 --- Hiệu năng  thống / \[Giả                 
                                định\]                        

  --------------------------------------------------------------------------

**Mô tả:** Hệ thống phải phản hồi các thao tác tra cứu chuyên khoa, bác
sĩ, lịch khám và gửi dữ liệu đặt lịch trong thời gian phù hợp với quy mô
80--120 lượt bệnh nhân/ngày.

**Lý do:** Tránh làm gián đoạn quá trình đặt lịch và giảm thời gian chờ
của bệnh nhân/nhân viên.

**Tiêu chí kiểm chứng:** Trong điều kiện tải bình thường, **ít nhất
95%** yêu cầu tra cứu lịch và thao tác đặt lịch phải nhận được phản hồi
từ hệ thống trong **≤ 2 giây \[Giả định -- Cần xác nhận\]**.

------------------------------------------------------------------------

### NFR-02 --- Khả năng xử lý đồng thời

  --------------------------------------------------------------------------
  ID             Loại           Nguồn          Độ ưu tiên     Phiên bản
  -------------- -------------- -------------- -------------- --------------
  **NFR-02**     Phi chức năng  Quy mô phòng   **Should**     1.0
                 --- Hiệu năng  khám / \[Giả                  
                                định\]                        

  --------------------------------------------------------------------------

**Mô tả:** Hệ thống phải duy trì khả năng phục vụ khi có nhiều bệnh nhân
đồng thời thực hiện tra cứu và đặt lịch.

**Lý do:** Phòng khám có 80--120 lượt bệnh nhân mỗi ngày; hệ thống cần
tránh lỗi hoặc mất dữ liệu khi nhiều người thao tác gần cùng thời điểm.

**Tiêu chí kiểm chứng:** Hệ thống phải xử lý tối thiểu **30 phiên người
dùng đồng thời \[Giả định -- Cần xác nhận\]** thực hiện tra cứu/đặt lịch
mà không phát sinh lỗi tạo lịch trùng hoặc mất bản ghi.

------------------------------------------------------------------------

## Nhóm 2 --- Bảo mật

### NFR-03 --- Xác thực OTP khi quản lý lịch hẹn

  --------------------------------------------------------------------------
  ID             Loại           Nguồn          Độ ưu tiên     Phiên bản
  -------------- -------------- -------------- -------------- --------------
  **NFR-03**     Phi chức năng  Bệnh nhân /    **Must**       1.0
                 --- Bảo mật    SC-03                         

  --------------------------------------------------------------------------

**Mô tả:** Hệ thống phải sử dụng OTP để xác thực bệnh nhân trước khi cho
phép xem hoặc thay đổi thông tin lịch hẹn.

**Lý do:** Thông tin lịch hẹn có dữ liệu cá nhân của bệnh nhân và không
được để người khác truy cập chỉ bằng Mã lịch hẹn.

**Tiêu chí kiểm chứng:** OTP phải gồm **6 chữ số**, có thời hạn **3 phút
\[Giả định G-07\]**; sau **3 lần nhập sai**, phiên xác thực phải bị khóa
và yêu cầu gửi OTP mới.

------------------------------------------------------------------------

### NFR-04 --- Phân quyền truy cập dữ liệu

  --------------------------------------------------------------------------
  ID             Loại           Nguồn          Độ ưu tiên     Phiên bản
  -------------- -------------- -------------- -------------- --------------
  **NFR-04**     Phi chức năng  Quản lý phòng  **Must**       1.0
                 --- Bảo mật    khám / Bác sĩ                 
                                / Nhân viên /                 
                                \[Cần xác                     
                                nhận\]                        

  --------------------------------------------------------------------------

**Mô tả:** Hệ thống phải kiểm soát quyền truy cập theo vai trò đối với
dữ liệu bệnh nhân, lịch khám và chức năng quản lý.

**Lý do:** Nhân viên, bác sĩ và quản lý có phạm vi công việc khác nhau;
dữ liệu bệnh nhân cần được giới hạn theo quyền.

**Tiêu chí kiểm chứng:** Người dùng không có quyền quản trị không được
thực hiện thao tác **đóng ca bác sĩ, hủy toàn bộ lịch của ca hoặc kích
hoạt xử lý hoàn tiền**. Các thao tác này chỉ được thực hiện bởi tài
khoản có quyền quản lý **\[Cần xác nhận danh sách vai trò và quyền chi
tiết\]**.

------------------------------------------------------------------------

## Nhóm 3 --- Khả dụng / Lưu trữ

### NFR-05 --- Khả dụng của hệ thống

  --------------------------------------------------------------------------
  ID             Loại           Nguồn          Độ ưu tiên     Phiên bản
  -------------- -------------- -------------- -------------- --------------
  **NFR-05**     Phi chức năng  Nhu cầu vận    **Should**     1.0
                 --- Khả dụng   hành / \[Giả                  
                                định\]                        

  --------------------------------------------------------------------------

**Mô tả:** Hệ thống phải duy trì khả năng truy cập để bệnh nhân có thể
đặt lịch và nhân viên có thể quản lý lịch khám trong thời gian phục vụ.

**Lý do:** Hệ thống là kênh đặt lịch và điều phối lịch khám; việc gián
đoạn có thể làm mất lịch hẹn hoặc buộc phòng khám quay lại quy trình thủ
công.

**Tiêu chí kiểm chứng:** Hệ thống phải đạt thời gian hoạt động tối thiểu
**99,5% trong mỗi tháng \[Giả định -- Cần xác nhận\]**, không tính thời
gian bảo trì đã được thông báo trước.

------------------------------------------------------------------------

### NFR-06 --- Lưu trữ và bảo toàn dữ liệu lịch hẹn/giao dịch

  --------------------------------------------------------------------------
  ID             Loại           Nguồn          Độ ưu tiên     Phiên bản
  -------------- -------------- -------------- -------------- --------------
  **NFR-06**     Phi chức năng  CR-01 / SC-01  **Must**       1.1
                 --- Lưu trữ    / SC-04                       

  --------------------------------------------------------------------------

**Mô tả:** Hệ thống phải lưu trữ đầy đủ dữ liệu lịch hẹn và giao dịch
thanh toán/hoàn tiền để phục vụ tra cứu, xử lý nghiệp vụ và đối soát.

**Lý do:** CR-01 yêu cầu lưu thông tin giao dịch, mã giao dịch thanh
toán, trạng thái và thời gian hoàn tiền; các dữ liệu này cần được bảo
toàn để xử lý khi giao dịch lỗi hoặc cần đối soát.

**Tiêu chí kiểm chứng:** Mỗi giao dịch khám trực tuyến phải lưu tối
thiểu các thông tin: **Mã giao dịch, Mã lịch hẹn, Số tiền, Phương thức
thanh toán, Trạng thái giao dịch, Mã giao dịch cổng thanh toán, Thời
gian thanh toán và Thời gian hoàn tiền**. Dữ liệu phải còn truy xuất
được sau khi lịch hẹn kết thúc **\[Thời gian lưu trữ tối thiểu: Cần xác
nhận\]**.

------------------------------------------------------------------------

# D. CÁC SỐ LIỆU CẦN XÁC NHẬN

Các số liệu dưới đây chưa được phòng khám chốt:

1.  **NFR-01:** 95% yêu cầu có thời gian phản hồi ≤ 2 giây.
2.  **NFR-02:** 30 người dùng đồng thời.
3.  **NFR-05:** Uptime 99,5%/tháng.
4.  **NFR-06:** Thời gian lưu trữ tối thiểu.
5.  **G-04:** Phí khám online 150.000 VNĐ.
6.  **G-05:** Thời gian giữ chỗ thanh toán 15 phút.
7.  **G-06:** Thời hạn đổi/hủy tối thiểu 120 phút.
8.  **G-07:** OTP 6 chữ số, hiệu lực 3 phút.
9.  Thời gian tiền hoàn thực tế về tài khoản 1--3 ngày làm việc.

Các số liệu thuộc nhóm giả định cần được stakeholder/phòng khám xác nhận
trước khi xem là yêu cầu chính thức.
