## DANH MỤC KỊCH BẢN KIỂM THỬ (ĐẦU RA 06 · TEST SCENARIOS)

### TC-01 · Kiểm thử đặt lịch khám trực tiếp thành công với dữ liệu hợp lệ
* **Mã kiểm thử:** `TC-01`
* **Requirement ID liên kết:** `FR-01`, `FR-02`, `FR-03`
* **Mục tiêu kiểm thử:** Xác minh người dùng có thể tra cứu khung giờ khả dụng, điền thông tin hợp lệ và hoàn tất quy trình đặt lịch khám trực tiếp thành công.
* **Tiền điều kiện:** Bác sĩ Nguyễn Văn A (Chuyên khoa Nội) có khung giờ `08:30 - 08:45` ngày `15/10/2026` ở trạng thái "Khả dụng".
* **Dữ liệu kiểm thử (Test Data):**
  * Chuyên khoa: Nội tổng quát.
  * Bác sĩ: BS. Nguyễn Văn A.
  * Thời gian: `08:30 - 08:45`, Ngày `15/10/2026`.
  * Thông tin bệnh nhân: Họ tên: "Trần Văn An", SĐT: "0912345678", Ngày sinh: "12/05/1990", Triệu chứng: "Đau đầu, sốt nhẹ 2 ngày".
* **Các bước thực hiện (Test Steps):**
  1. Truy cập vào trang web đặt lịch, chọn hình thức "Khám trực tiếp tại phòng khám".
  2. Chọn chuyên khoa "Nội tổng quát", chọn bác sĩ "Nguyễn Văn A".
  3. Chọn ngày `15/10/2026`, nhấn chọn khung giờ `08:30 - 08:45`.
  4. Nhập đầy đủ thông tin bệnh nhân theo dữ liệu kiểm thử.
  5. Bấm nút "Xác nhận đặt lịch".
* **Kết quả kỳ vọng (Expected Results):**
  * Hệ thống lưu lịch hẹn thành công, gán mã lịch hẹn (VD: `AT-151001`), hiển thị thông báo đặt lịch thành công.
  * Khung giờ `08:30 - 08:45` ngày `15/10/2026` của BS. Nguyễn Văn A chuyển sang trạng thái bị khóa (disabled) trên giao diện đặt lịch.
  * Tổng đài SMS gửi tin nhắn xác nhận lịch hẹn đến số điện thoại `0912345678` trong vòng dưới 60 giây.

---

### TC-02 · Kiểm thử ngăn chặn đặt lịch hẹn trùng lặp trên cùng một khung giờ
* **Mã kiểm thử:** `TC-02`
* **Requirement ID liên kết:** `FR-10`
* **Mục tiêu kiểm thử:** Xác minh hệ thống phát hiện và chặn đứng trường hợp một số điện thoại cố tình đặt hai lịch hẹn khác nhau trong cùng một khung giờ khám bệnh.
* **Tiền điều kiện:** Số điện thoại `0912345678` đã có một lịch hẹn hợp lệ ở khung giờ `09:00 - 09:15` ngày `15/10/2026` tại phòng khám.
* **Dữ liệu kiểm thử (Test Data):**
  * SĐT kiểm tra: `0912345678`.
  * Khung giờ đặt mới: `09:00 - 09:15` ngày `15/10/2026` (chọn bác sĩ thuộc chuyên khoa khác).
* **Các bước thực hiện (Test Steps):**
  1. Mở giao diện đặt lịch, chọn một bác sĩ khác.
  2. Chọn khung giờ khám `09:00 - 09:15` ngày `15/10/2026`.
  3. Điền thông tin cá nhân với số điện thoại `0912345678`.
  4. Bấm nút "Xác nhận đặt lịch".
* **Kết quả kỳ vọng (Expected Results):**
  * Hệ thống từ chối lưu lịch hẹn mới vào CSDL.
  * Hiển thị thông báo lỗi rõ ràng trên màn hình: *"Số điện thoại này đã có lịch hẹn trong khung giờ được chọn. Vui lòng kiểm tra lại!"*
  * Hệ thống không gửi bất kỳ SMS xác nhận mới nào.

---

### TC-03 · Kiểm thử bệnh nhân tự hủy lịch hẹn trước 2 tiếng và kiểm tra giải phóng khung giờ
* **Mã kiểm thử:** `TC-03`
* **Requirement ID liên kết:** `FR-06`, `FR-07`
* **Mục tiêu kiểm thử:** Xác minh bệnh nhân có thể xác thực OTP và tự hủy lịch hẹn khi thực hiện trước giờ khám $\ge 2$ tiếng, hệ thống tự động mở lại khung giờ trống cho người khác.
* **Tiền điều kiện:** Có lịch hẹn mã `AT-998877` với SĐT `0987654321` vào lúc `14:00` ngày hôm nay. Thời điểm thực hiện test là `10:00` sáng cùng ngày (cách giờ khám 4 tiếng, thỏa mãn điều kiện $\ge 2$ tiếng).
* **Dữ liệu kiểm thử (Test Data):**
  * Mã lịch hẹn: `AT-998877`.
  * SĐT: `0987654321`.
  * Mã OTP xác thực: `123456`.
  * Lý do hủy: "Bận công việc đột xuất".
* **Các bước thực hiện (Test Steps):**
  1. Truy cập chức năng "Tra cứu lịch hẹn", nhập mã `AT-998877` và SĐT `0987654321`, nhấn "Tiếp tục".
  2. Hệ thống gửi mã OTP về số điện thoại; nhập mã OTP `123456` và nhấn "Xác thực".
  3. Tại màn hình thông tin chi tiết ca khám, bấm chọn nút "Hủy lịch hẹn".
  4. Chọn lý do hủy và nhấn nút "Xác nhận hủy lịch".
  5. Sử dụng một trình duyệt web khác/tab ẩn danh truy cập vào trang đặt lịch của bác sĩ đó.
* **Kết quả kỳ vọng (Expected Results):**
  * Trạng thái lịch hẹn `AT-998877` chuyển thành "Đã hủy bởi bệnh nhân".
  * Bệnh nhân nhận được tin nhắn SMS xác nhận đã hủy lịch hẹn thành công.
  * Khung giờ `14:00 - 14:15` của bác sĩ lập tức hiển thị màu xanh ở trạng thái "Khả dụng" trên trình duyệt thứ hai, cho phép bệnh nhân khác bấm đặt bình thường.

---

### TC-04 · Kiểm thử hiệu năng thời gian phản hồi khi tra cứu lịch trống (Performance Testing)
* **Mã kiểm thử:** `TC-04`
* **Requirement ID liên kết:** `NFR-01`
* **Mục tiêu kiểm thử:** Đo lường thời gian phản hồi của hệ thống khi có 100 người dùng đồng thời thực hiện tra cứu danh sách khung giờ trống của các bác sĩ.
* **Tiền điều kiện:** Máy chủ kiểm thử được cấu hình môi trường tiệm cận thực tế; cơ sở dữ liệu đã nạp sẵn dữ liệu của 06 bác sĩ và 120 lịch hẹn mẫu.
* **Dữ liệu kiểm thử (Test Data):**
  * Kịch bản kiểm thử tải (Apache JMeter script) giả lập 100 Virtual Users (VU) truy cập đồng thời API `/api/doctors/{id}/available-slots` trong thời gian Ramp-up 10 giây.
* **Các bước thực hiện (Test Steps):**
  1. Khởi động công cụ kiểm thử tải Apache JMeter.
  2. Kích hoạt kịch bản kiểm thử gửi 100 truy vấn đồng thời liên tục trong 60 giây.
  3. Trích xuất báo cáo Aggregate Report từ JMeter.
* **Kết quả kỳ vọng (Expected Results):**
  * 100% yêu cầu được xử lý thành công, tỷ lệ mã lỗi HTTP (Error Rate) bằng 0,0%.
  * Thời gian phản hồi trung bình (Average Response Time) đạt $\le 2,0\text{ giây}$ (thỏa mãn tiêu chí kiểm chứng của `NFR-01`).
  * Thời gian phản hồi phân vị 95 (95th Percentile) không vượt quá 2,5 giây.

---

### TC-05 · Kiểm thử luồng đặt lịch khám trực tuyến và thanh toán qua cổng điện tử thành công (CR-01)
* **Mã kiểm thử:** `TC-05`
* **Requirement ID liên kết:** `FR-11`, `CR-01`
* **Mục tiêu kiểm thử:** Xác minh dịch vụ khám trực tuyến chỉ cấp mã xác nhận lịch hẹn sau khi người dùng thực hiện thanh toán trực tuyến thành công qua cổng thanh toán giả lập.
* **Tiền điều kiện:** Tài khoản thử nghiệm (Sandbox) của cổng thanh toán VNPay hoạt động bình thường; bác sĩ có khung giờ khám online còn trống.
* **Dữ liệu kiểm thử (Test Data):**
  * Hình thức khám: Khám trực tuyến.
  * Phí khám: `150.000 VNĐ`.
  * Thông tin thẻ Sandbox: Ngân hàng NCB, Số thẻ: `9704198526191432198`, Tên chủ thẻ: `NGUYEN VAN A`, OTP: `123456`.
* **Các bước thực hiện (Test Steps):**
  1. Đặt lịch khám và chọn hình thức "Khám trực tuyến".
  2. Chọn khung giờ, điền thông tin bệnh nhân và bấm "Tiến hành thanh toán".
  3. Hệ thống chuyển hướng sang trang thanh toán VNPay Sandbox.
  4. Nhập thông tin thẻ Sandbox và mã OTP xác thực giao dịch hợp lệ.
  5. Nhấn "Xác nhận thanh toán" và chờ cổng thanh toán điều hướng trở lại web phòng khám.
* **Kết quả kỳ vọng (Expected Results):**
  * Hệ thống nhận được tín hiệu Webhook thanh toán thành công, hiển thị màn hình: "Thanh toán thành công & Xác nhận lịch khám trực tuyến".
  * Bản ghi trong bảng `GiaoDich` lưu trạng thái "Đã thanh toán" với đầy đủ mã đối soát.
  * Bản ghi lịch hẹn lưu trạng thái "Đã xác nhận", tự sinh một đường link phòng khám trực tuyến bảo mật.
  * Bệnh nhân nhận được tin nhắn SMS xác nhận kèm link phòng khám online.

---

### TC-06 · Kiểm thử tự động phát lệnh hoàn tiền khi Quản lý hủy ca trực bác sĩ khám online (CR-01)
* **Mã kiểm thử:** `TC-06`
* **Requirement ID liên kết:** `FR-12`, `FR-09`, `CR-01`
* **Mục tiêu kiểm thử:** Xác minh khi Quản lý phòng khám kích hoạt lệnh hủy ca trực của bác sĩ, hệ thống tự động kích hoạt API hoàn tiền 100% cho bệnh nhân khám online và gửi SMS thông báo giải thích.
* **Tiền điều kiện:** Trong ca trực chiều ngày `15/10/2026` của BS. Lê Thị B có 01 lịch khám online của bệnh nhân `0911223344` đã thanh toán thành công số tiền `150.000 VNĐ` (Mã GD: `GD-888999`).
* **Dữ liệu kiểm thử (Test Data):**
  * Tài khoản đăng nhập: Quản lý phòng khám (`admin_antam`).
  * Lý do hủy ca: "Bác sĩ có lịch mổ cấp cứu đột xuất tại bệnh viện tuyến trên".
* **Các bước thực hiện (Test Steps):**
  1. Đăng nhập tài khoản Quản lý, vào mục "Quản lý ca trực bác sĩ".
  2. Chọn ca trực chiều ngày `15/10/2026` của BS. Lê Thị B, bấm nút "Báo nghỉ đột xuất".
  3. Nhập lý do nghỉ và nhấn nút "Xác nhận đóng ca trực & Hoàn tiền".
  4. Kiểm tra nhật ký giao dịch và hộp thư SMS của bệnh nhân `0911223344`.
* **Kết quả kỳ vọng (Expected Results):**
  * Hệ thống gọi thành công API hoàn tiền của VNPay, nhận mã hoàn tiền thành công từ cổng thanh toán.
  * Bản ghi giao dịch `GD-888999` chuyển trạng thái sang "Đã hoàn tiền".
  * Lịch hẹn chuyển sang trạng thái "Bị hủy bởi phòng khám".
  * Thuê bao `0911223344` nhận được tin nhắn SMS Brandname nêu rõ: Lời xin lỗi của phòng khám, lý do bác sĩ hủy ca, thông báo hoàn trả 100% số tiền 150.000 VNĐ và kèm đường link ưu tiên dời lịch khám.