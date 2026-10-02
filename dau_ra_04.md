## PHẦN 1: ĐẶC TẢ TÌNH HUỐNG SỬ DỤNG (ĐẦU RA 04 · SCENARIOS)

### SC-01 · Bệnh nhân đặt lịch khám thành công (Tích hợp CR-01)
* **Mã kịch bản:** `SC-01`
* **Tác nhân chính:** Bệnh nhân (`STK-04`)
* **Tiền điều kiện:** 
  * Hệ thống web hoạt động bình thường, kết nối cơ sở dữ liệu ổn định.
  * Bác sĩ thuộc chuyên khoa yêu cầu có ít nhất 01 khung giờ khám (time slot) ở trạng thái "Khả dụng".
* **Kích hoạt:** Bệnh nhân truy cập trang web phòng khám và chọn nút "Đặt lịch khám".
* **Luồng sự kiện chính (Main Flow):**
  1. Bệnh nhân lựa chọn hình thức khám mong muốn: "Khám trực tiếp tại phòng khám" hoặc "Khám trực tuyến (Telemedicine)".
  2. Bệnh nhân chọn Chuyên khoa và chọn Bác sĩ phụ trách từ danh mục.
  3. Hệ thống hiển thị lịch làm việc trong tuần và các khung giờ còn trống của bác sĩ đã chọn.
  4. Bệnh nhân bấm chọn 01 khung giờ khám phù hợp.
  5. Hệ thống hiển thị biểu mẫu thu thập thông tin đăng ký khám bệnh.
  6. Bệnh nhân nhập đầy đủ thông tin: Họ và tên, Số điện thoại liên hệ, Ngày tháng năm sinh, Giới tính và Mô tả tóm tắt triệu chứng bệnh lý ban đầu.
  7. Hệ thống hiển thị bảng tóm tắt thông tin đăng ký khám: Bác sĩ, Chuyên khoa, Ngày giờ khám, Hình thức khám và Mức viện phí niêm yết (Khám trực tiếp: Miễn phí đặt trước, thanh toán tại quầy tiếp nhận; Khám trực tuyến: 150.000 VNĐ [Giả định G-04: Mức phí khám online minh họa – Cần Ban Quản lý xác nhận biểu phí chính thức] cần thanh toán trước theo CR-01).
  8. Bệnh nhân kiểm tra thông tin, tích chọn đồng ý điều khoản dịch vụ và nhấn nút "Xác nhận đặt lịch".
  9. Hệ thống rà soát tính hợp lệ của dữ liệu, kiểm tra trạng thái khóa của khung giờ và rẽ nhánh theo hình thức khám:
     * *Nhánh A – Khám trực tiếp tại phòng khám:* Hệ thống ghi nhận lịch hẹn vào cơ sở dữ liệu ở trạng thái "Đã đặt", khóa khung giờ đã chọn thành "Không khả dụng".
     * *Nhánh B – Khám trực tuyến (theo CR-01):* Hệ thống tạm khóa khung giờ trong thời hạn tối đa 15 phút [Giả định kỹ thuật G-05: Thời gian giữ chỗ phiên giao dịch cổng thanh toán], tạo phiên giao dịch và chuyển hướng trình duyệt của bệnh nhân sang cổng thanh toán điện tử (VNPay/Momo).
  10. *(Dành riêng cho khám trực tuyến):* Bệnh nhân thực hiện xác thực và thanh toán thành công phí khám trên giao diện cổng thanh toán trung gian. Cổng thanh toán gửi mã phản hồi giao dịch thành công (IPN/Webhook) về hệ thống phòng khám.
  11. Hệ thống tạo mã lịch hẹn duy nhất (dạng `AT-XXXXXX`), tự sinh đường link phòng khám trực tuyến (nếu khám online) và lưu trạng thái lịch hẹn là "Đã xác nhận".
  12. Hệ thống hoàn tất lưu trữ dữ liệu vào CSDL và tự động kích hoạt tiến trình gửi tin nhắn SMS Brandname và Email xác nhận (chạy bất đồng bộ qua hàng đợi ngầm, đảm bảo tính toàn vẹn ngay cả khi mạng viễn thông trễ) chứa đầy đủ: Mã lịch hẹn, Tên bác sĩ, Chuyên khoa, Thời gian khám, Số phòng khám/Link khám trực tuyến đến bệnh nhân.
  13. Hệ thống hiển thị màn hình thông báo hoàn tất đặt lịch thành công kèm hướng dẫn chuẩn bị trước khi khám bệnh.
* **Luồng thay thế và ngoại lệ (Alternative & Exception Flows):**
  * *Ngoại lệ 4a (Khung giờ vừa bị người dùng khác đặt trước):* Khi bệnh nhân bấm chọn, hệ thống kiểm tra và phát hiện khung giờ vừa chuyển sang trạng thái kín chỗ ở một phiên khác -> Chuyển hướng xử lý sang kịch bản `SC-02`.
  * *Ngoại lệ 6a (Nhập sai định dạng hoặc thiếu thông tin bắt buộc):* Bệnh nhân bỏ trống Họ tên/SĐT hoặc nhập số điện thoại không đủ 10 chữ số -> Hệ thống dừng quy trình, đánh dấu đỏ các trường dữ liệu vi phạm và hiển thị thông báo lỗi cụ thể để bệnh nhân chỉnh sửa.
  * *Ngoại lệ 8a (Phát hiện trùng lịch hẹn - Vi phạm FR-10):* Hệ thống quét cơ sở dữ liệu thấy số điện thoại của bệnh nhân đã có một lịch hẹn khác trong cùng khung giờ khám -> Hệ thống từ chối tạo lịch, hiển thị cảnh báo: *"Số điện thoại này đã có lịch hẹn trong khung giờ được chọn. Vui lòng kiểm tra lại!"*
  * *Ngoại lệ 10a (Thanh toán online thất bại hoặc người dùng hủy giao dịch - CR-01):* Cổng thanh toán trả về mã lỗi giao dịch hoặc người dùng bấm nút hủy -> Hệ thống hủy phiên tạm giữ, mở lại khung giờ thành "Khả dụng" trên toàn hệ thống và hiển thị thông báo: *"Giao dịch thanh toán không thành công. Khung giờ khám chưa được ghi nhận, vui lòng thử lại"*.
  * *Ngoại lệ 10b (Quá hạn thời gian chờ thanh toán 15 phút - CR-01):* Bệnh nhân không hoàn tất thanh toán trong vòng 15 phút [Giả định G-05] -> Tiến trình nền của hệ thống tự động hủy đơn đặt, giải phóng khung giờ về trạng thái "Khả dụng".
* **Hậu điều kiện (Post-conditions):**
  * Khung giờ đã chọn chuyển sang trạng thái "Không khả dụng" trên lịch làm việc của bác sĩ.
  * Bản ghi lịch hẹn được lưu thành công trong CSDL.
  * Bác sĩ phụ trách thấy tên bệnh nhân xuất hiện trên danh sách ca khám tương ứng.
  * Bệnh nhân nhận được tin nhắn SMS/Email xác nhận hợp lệ.

---

### SC-02 · Khung giờ hoặc bác sĩ không còn khả dụng
* **Mã kịch bản:** `SC-02`
* **Tác nhân chính:** Bệnh nhân (`STK-04`)
* **Tiền điều kiện:** Bệnh nhân đang truy cập màn hình chọn thời gian khám bệnh của một bác sĩ cụ thể.
* **Kích hoạt:** Bệnh nhân nhấn chọn một khung giờ vừa bị người khác đăng ký giữ chỗ trước đó vài giây hoặc bác sĩ vừa được quản lý đánh dấu khóa lịch đột xuất.
* **Luồng sự kiện chính (Main Flow):**
  1. Bệnh nhân bấm chọn khung giờ khám và nhấn nút "Tiếp tục".
  2. Hệ thống gửi truy vấn kiểm tra trạng thái khóa thực tế (real-time lock) của khung giờ trong cơ sở dữ liệu.
  3. Hệ thống phát hiện khung giờ đã chuyển sang trạng thái "Đã kín" (Unavailable) hoặc "Bị khóa".
  4. Hệ thống hiển thị hộp thoại thông báo nổi (Modal popup): *"Rất tiếc! Khung giờ [Giờ:Phút - Ngày] bạn vừa chọn hiện không còn khả dụng do đã có người đặt trước hoặc bác sĩ có lịch đột xuất"*.
  5. Hệ thống kích hoạt thuật toán gợi ý phương án thay thế:
     * Tự động quét và hiển thị 03 khung giờ còn trống gần nhất [Giả định thiết kế UI] trong cùng ngày của chính bác sĩ đó.
     * Hiển thị danh sách các bác sĩ khác thuộc cùng chuyên khoa có lịch khám còn trống trong cùng ngày.
  6. Bệnh nhân quan sát các phương án gợi ý và bấm chọn 01 khung giờ thay thế phù hợp.
  7. Hệ thống làm mới giao diện, tạm giữ khung giờ mới được chọn và điều hướng bệnh nhân sang bước điền thông tin cá nhân (tiếp tục Bước 5 của kịch bản `SC-01`).
* **Luồng thay thế và ngoại lệ (Alternative & Exception Flows):**
  * *Ngoại lệ 5a (Bác sĩ đã kín toàn bộ lịch trong ngày):* Hệ thống kiểm tra thấy bác sĩ không còn bất kỳ khung giờ trống nào trong ngày -> Hệ thống hiển thị thông báo: *"Bác sĩ đã kín lịch khám trong ngày hôm nay"*, đồng thời tự động tải và hiển thị lịch khám còn trống của ngày làm việc tiếp theo gần nhất.
  * *Ngoại lệ 5b (Toàn bộ chuyên khoa đã kín lịch trong ngày):* Tất cả bác sĩ trong chuyên khoa đều kín lịch -> Hệ thống gợi ý bệnh nhân chọn ngày khám khác hoặc cung cấp số hotline phòng khám để được nhân viên lễ tân tư vấn hỗ trợ xếp lịch trực tiếp.
  * *Ngoại lệ 6a (Bệnh nhân từ chối các gợi ý):* Bệnh nhân đóng hộp thoại gợi ý và không chọn khung giờ mới -> Hệ thống đưa người dùng quay lại màn hình tổng quan chọn chuyên khoa/bác sĩ ban đầu.
* **Hậu điều kiện (Post-conditions):**
  * Không phát sinh bất kỳ bản ghi rác hay lịch hẹn trùng lặp nào trong cơ sở dữ liệu phòng khám.
  * Giao diện lịch khám được làm mới đồng bộ với trạng thái khả dụng thực tế của cơ sở dữ liệu.

---

### SC-03 · Bệnh nhân đổi hoặc hủy lịch hẹn
* **Mã kịch bản:** `SC-03`
* **Tác nhân chính:** Bệnh nhân (`STK-04`)
* **Tiền điều kiện:** 
  * Bệnh nhân đã có lịch hẹn được xác nhận trên hệ thống và còn lưu giữ Mã lịch hẹn cùng Số điện thoại đã đăng ký.
  * Lịch hẹn đang ở trạng thái "Đã đặt" hoặc "Đã xác nhận" (chưa diễn ra và chưa bị hủy).
* **Kích hoạt:** Bệnh nhân truy cập trang "Tra cứu & Quản lý lịch hẹn", nhập thông tin tra cứu và nhấn nút "Tra cứu lịch hẹn".
* **Luồng sự kiện chính (Main Flow):**
  1. Bệnh nhân nhập Mã lịch hẹn và Số điện thoại đăng ký, sau đó nhấn nút "Tiếp tục".
  2. Hệ thống kiểm tra tính hợp lệ của mã và số điện thoại, tự động sinh mã xác thực OTP gồm 6 chữ số gửi qua tin nhắn SMS đến số điện thoại của bệnh nhân (thời hạn hiệu lực 3 phút [Giả định an toàn thông tin G-07]).
  3. Bệnh nhân nhập mã OTP và nhấn nút "Xác thực".
  4. Hệ thống xác thực OTP thành công và hiển thị chi tiết thông tin ca khám: Bác sĩ, Chuyên khoa, Ngày khám, Khung giờ, Hình thức khám, Trạng thái thanh toán viện phí (đối với khám trực tuyến) kèm 02 nút hành động: "Đổi khung giờ khám" và "Hủy lịch hẹn".
  5. **Trường hợp A – Bệnh nhân chọn "Hủy lịch hẹn":**
     * 5a.1. Hệ thống tính toán khoảng thời gian chênh lệch giữa thời điểm hiện tại và giờ hẹn khám.
     * 5a.2. Hệ thống xác nhận thời gian chênh lệch đạt điều kiện hợp lệ ($\ge 2$ tiếng tức $\ge 120$ phút trước giờ khám [Giả định nghiệp vụ G-06: Quy định thời hạn hủy tối thiểu – Cần Phòng khám chốt chính sách]).
     * 5a.3. Hệ thống hiển thị hộp thoại xác nhận hủy kèm danh sách lý do để bệnh nhân chọn (Lý do cá nhân, Đã khỏi bệnh, Thay đổi kế hoạch...).
     * 5a.4. Bệnh nhân chọn lý do và nhấn "Xác nhận hủy lịch".
     * 5a.5. Hệ thống chuyển trạng thái lịch hẹn sang "Đã hủy bởi bệnh nhân", ghi nhận thời gian và lý do hủy.
     * 5a.6. *(Xử lý hoàn tiền khám online theo CR-01):* Nếu là ca khám trực tuyến đã thanh toán trước, hệ thống tự động phát lệnh gọi API cổng thanh toán (VNPay/Momo) để hoàn trả 100% tiền viện phí về tài khoản/thẻ ban đầu của bệnh nhân, ghi nhận mã giao dịch hoàn trả và cập nhật trạng thái bảng `GiaoDich` thành "Đã hoàn tiền".
     * 5a.7. Hệ thống kích hoạt cơ chế tự động giải phóng khung giờ (theo `FR-07`), đổi trạng thái slot tương ứng trở lại "Khả dụng" trên toàn hệ thống.
     * 5a.8. Hệ thống tự động gửi SMS thông báo xác nhận hủy lịch hẹn thành công (kèm thông báo lệnh hoàn tiền 100% viện phí đối với ca khám online) đến số điện thoại của bệnh nhân.
  6. **Trường hợp B – Bệnh nhân chọn "Đổi khung giờ khám":**
     * 6b.1. Hệ thống kiểm tra điều kiện thời gian ($\ge 2$ tiếng trước giờ khám [Giả định nghiệp vụ G-06]).
     * 6b.2. Hệ thống mở bảng lịch công tác của bác sĩ phụ trách và hiển thị các khung giờ còn trống khác.
     * 6b.3. Bệnh nhân chọn 01 khung giờ khám mới và nhấn "Lưu thay đổi".
     * 6b.4. Hệ thống cập nhật thời gian khám mới vào bản ghi lịch hẹn (giữ nguyên trạng thái thanh toán nếu cùng bác sĩ/chuyên khoa), khóa khung giờ mới.
     * 6b.5. Hệ thống giải phóng khung giờ cũ trở về trạng thái "Khả dụng".
     * 6b.6. Hệ thống gửi SMS thông báo cập nhật lịch hẹn mới thành công cho bệnh nhân.
* **Luồng thay thế và ngoại lệ (Alternative & Exception Flows):**
  * *Ngoại lệ 1a (Sai thông tin tra cứu):* Mã lịch hẹn hoặc số điện thoại không khớp với bản ghi nào trong hệ thống -> Hệ thống hiển thị cảnh báo: *"Không tìm thấy thông tin lịch hẹn hợp lệ. Vui lòng kiểm tra lại mã lịch hẹn hoặc số điện thoại"*.
  * *Ngoại lệ 3a (Nhập sai hoặc hết hạn mã OTP):* Bệnh nhân nhập sai OTP quá 3 lần hoặc để quá hạn 3 phút [Giả định G-07] -> Hệ thống khóa phiên xác thực, hiển thị nút yêu cầu gửi lại mã OTP mới.
  * *Ngoại lệ 5a.2 / 6b.1 (Yêu cầu đổi/hủy quá trễ - Vi phạm quy định < 2 tiếng):* Bệnh nhân thực hiện đổi/hủy khi thời gian đến giờ hẹn còn dưới 120 phút [Giả định G-06] -> Hệ thống làm mờ (disable) chức năng tự hủy/đổi và hiển thị thông báo: *"Đã quá thời hạn cho phép tự đổi hoặc hủy lịch trực tuyến (quy định trước tối thiểu 2 tiếng [Giả định G-06]). Quý khách vui lòng liên hệ trực tiếp hotline lễ tân phòng khám qua số điện thoại 028.xxxx.xxxx để được hỗ trợ xử lý"*. (Lưu ý: Đối với ca khám trực tuyến hủy trễ, phòng khám không hỗ trợ hoàn tiền tự động nhằm đảm bảo quyền lợi ca trực của bác sĩ [Vấn đề cần Stakeholder xác nhận]).
  * *Ngoại lệ 5a.6a (Lỗi kết nối cổng thanh toán khi hoàn tiền - CR-01):* Cổng thanh toán timeout hoặc lỗi hệ thống -> Hệ thống tự động chuyển trạng thái sang "Chờ đối soát hoàn tiền thủ công" và tạo cảnh báo để kế toán phòng khám đối soát hoàn tiền thủ công cho bệnh nhân.
  * *Ngoại lệ 6b.3a (Khung giờ mới vừa bị người khác chọn trước):* Khung giờ mới chọn bị trùng -> Hệ thống giữ nguyên lịch hẹn cũ và yêu cầu bệnh nhân chọn lại một khung giờ khác.
* **Hậu điều kiện (Post-conditions):**
  * Khung giờ cũ được mở lại ở trạng thái "Khả dụng", sẵn sàng cho các bệnh nhân khác đặt chỗ.
  * Danh sách khám của bác sĩ và màn hình điều phối của nhân viên tiếp nhận được cập nhật tức thì theo thời gian thực.
  * Nghĩa vụ hoàn tiền (nếu hủy lịch online hợp lệ) được thực thi minh bạch.

---

### SC-04 · Bác sĩ nghỉ ca đột xuất & Xử lý hoàn tiền khám online (CR-01)
* **Mã kịch bản:** `SC-04`
* **Tác nhân chính:** Quản lý phòng khám (`STK-01`)
* **Tiền điều kiện:** 
  * Quản lý phòng khám đã đăng nhập thành công vào hệ thống với vai trò Quản trị viên (Admin).
  * Bác sĩ có lịch làm việc trong ngày phát sinh sự cố khẩn cấp (ốm đau, việc gia đình) và đã thông báo nghỉ đột xuất.
  * Đã có bệnh nhân đặt hẹn trước trong ca làm việc bị ảnh hưởng.
* **Kích hoạt:** Quản lý phòng khám chọn ca trực của bác sĩ trên giao diện điều hành và nhấn nút "Báo nghỉ đột xuất / Hủy ca trực".
* **Luồng sự kiện chính (Main Flow):**
  1. Quản lý chọn Bác sĩ, Ngày khám và Ca trực cần báo nghỉ (Ca sáng/Ca chiều), sau đó chọn hoặc nhập lý do nghỉ đột xuất.
  2. Hệ thống truy vấn cơ sở dữ liệu và hiển thị danh sách tổng hợp toàn bộ các bệnh nhân đã đặt hẹn trong ca trực đó. Bảng danh sách phân tách rõ 02 nhóm đối tượng:
     * Nhóm 1: Bệnh nhân đăng ký khám trực tiếp tại phòng khám.
     * Nhóm 2: Bệnh nhân đăng ký khám trực tuyến (đã thanh toán viện phí trước).
  3. Quản lý kiểm tra thông tin và nhấn nút "Xác nhận đóng ca trực & Kích hoạt xử lý sự cố".
  4. Hệ thống tự động chuyển trạng thái của toàn bộ các khung giờ còn lại trong ca trực của bác sĩ đó sang trạng thái "Đã khóa do bác sĩ nghỉ đột xuất" (theo `FR-08`) để ngăn chặn phát sinh lịch hẹn mới.
  5. Hệ thống chuyển đổi trạng thái của toàn bộ lịch hẹn thuộc ca trực sang trạng thái "Đã hủy bởi phòng khám do bác sĩ vắng mặt".
  6. **Quy trình hoàn tiền tự động cho các ca khám trực tuyến (Tích hợp theo CR-01):**
     * 6.1. Hệ thống lọc danh sách các bệnh nhân thuộc Nhóm 2 có trạng thái giao dịch là "Đã thanh toán".
     * 6.2. Hệ thống tự động tạo mã yêu cầu hoàn tiền và gọi API sang cổng thanh toán điện tử tương ứng (VNPay/Momo) để phát lệnh hoàn trả 100% số tiền đã thu về tài khoản/thẻ ban đầu của bệnh nhân.
     * 6.3. Cổng thanh toán tiếp nhận lệnh và trả về mã xác nhận hoàn tiền thành công.
     * 6.4. Hệ thống cập nhật trạng thái bản ghi trong bảng `GiaoDich` thành "Đã hoàn tiền", ghi nhận thời gian và mã giao dịch hoàn trả.
  7. **Tiến trình gửi thông báo hàng loạt (theo FR-09):**
     * 7.1. Hệ thống tự động kích hoạt dịch vụ gửi tin nhắn SMS Brandname và Email đồng loạt đến 100% bệnh nhân bị ảnh hưởng trong ca khám.
     * 7.2. Đối với bệnh nhân khám trực tiếp: Nội dung thông báo nêu rõ lời xin lỗi vì sự cố đột xuất của bác sĩ, kèm theo một đường dẫn (link) ưu tiên đặc biệt cho phép bệnh nhân tự chọn đặt lại lịch hẹn sang ca khác hoặc bác sĩ khác mà không bị tính phí dịch vụ.
     * 7.3. Đối với bệnh nhân khám trực tuyến: Nội dung thông báo gồm lời xin lỗi, lý do hủy ca, xác nhận lệnh hoàn tiền 100% viện phí (kèm mã tra soát và thông báo tiền sẽ về tài khoản trong 1–3 ngày làm việc [Giả định thỏa thuận cổng thanh toán ngân hàng] tùy chính sách ngân hàng) cùng link ưu tiên dời lịch.
  8. Hệ thống xuất báo cáo tổng kết trên màn hình Quản lý: Tổng số lịch hẹn đã hủy, số lượt gửi tin nhắn thành công, số giao dịch hoàn tiền online đã xử lý thành công.
* **Luồng thay thế và ngoại lệ (Alternative & Exception Flows):**
  * *Ngoại lệ 6.3a (Lỗi kết nối cổng thanh toán hoặc giao dịch hoàn tiền thất bại - CR-01):* Cổng thanh toán bị timeout hoặc trả về lỗi không thể hoàn tiền tự động -> Hệ thống ghi log cảnh báo màu đỏ, tự động chuyển trạng thái giao dịch sang "Chờ xử lý hoàn tiền thủ công" và hiển thị cảnh báo ngay trên màn hình Quản lý kèm danh sách các giao dịch lỗi để bộ phận kế toán/lễ tân liên hệ đối soát thủ công trực tiếp.
  * *Ngoại lệ 7.1a (Lỗi dịch vụ mạng gửi tin nhắn SMS thất bại):* Tin nhắn SMS gửi đến một số thuê bao bị lỗi mạng -> Hệ thống đánh dấu cờ (flag) "Chưa gửi được SMS" trên danh sách bệnh nhân và thông báo cho nhân viên tiếp nhận tại quầy thực hiện cuộc gọi điện thoại trực tiếp để báo cho các bệnh nhân đó.
* **Hậu điều kiện (Post-conditions):**
  * Toàn bộ ca trực bị đóng hoàn toàn, không thể tiếp nhận thêm lịch hẹn.
  * 100% bệnh nhân bị ảnh hưởng nhận được thông báo sự cố kịp thời, hạn chế tối đa việc bệnh nhân di chuyển đến phòng khám trong vô vọng.
  * Nghĩa vụ hoàn trả tài chính cho các ca khám online được xử lý minh bạch và chính xác.
