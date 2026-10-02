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

---

# ĐẦU RA 06 · KIỂM ĐỊNH YÊU CẦU VÀ MA TRẬN TRUY VẾT

**Nhóm:** 18  
**Người phụ trách:** Nguyễn Hồ Quang Tiến  
**Ngày rà soát:** 02/10/2026  
**Phiên bản báo cáo:** 1.2  
**Hệ thống:** Quản lý lịch khám Phòng khám An Tâm

## 6.1. Báo cáo review chéo

### 6.1.1. Tổ chức kiểm định và cách ghi nhận

| Vai trò | Phần đối chiếu | Trách nhiệm xử lý phát hiện |
| --- | --- | --- |
| Thành viên 4 | Toàn bộ chuỗi nhu cầu, stakeholder, FR/NFR, scenario, TC và CR-01 | Chủ trì đối chiếu chéo, ghi mã VR, quyết định xử lý ở mức kiểm định, lập ma trận và rà checklist. |
| Thành viên 1 | Tài liệu Vấn đề và phạm vi, Kế hoạch thu thập yêu cầu; mục 1, 2 và phụ lục Mini-SRS | Bổ sung nguồn khảo sát, xác nhận phạm vi, giả định và lịch sử phiên bản. |
| Thành viên 2 | Danh mục yêu cầu; mục 3 Mini-SRS | Thống nhất ý nghĩa Requirement ID; sửa tiêu chí kiểm chứng và phiên bản bị ảnh hưởng. |
| Thành viên 3 | Đặc tả tình huống sử dụng, bộ test và CR-01 | Đồng bộ scenario, ngoại lệ, dữ liệu và test với danh mục yêu cầu. |

Quá trình kiểm định gồm kiểm tra nguồn và phạm vi; đối chiếu FR/NFR với scenario; đối chiếu scenario với TC; kiểm tra tác động CR-01; rà ngôn ngữ và liên kết. Mỗi phát hiện được ghi mã VR, tiêu chí kiểm định, quyết định xử lý và điều kiện đóng.

**Sửa (Fix)** là quyết định cần chỉnh tài liệu hoặc bổ sung kiểm chứng. **Không sửa (No-fix)** là quyết định giữ nội dung đang có, kèm căn cứ. Một vấn đề chỉ được đóng khi phần chỉnh sửa đã xuất hiện trong tài liệu liên quan và được đối chiếu lại.

### 6.1.2. Sáu tiêu chí kiểm định

| Tiêu chí | Câu hỏi đối chiếu | Dấu hiệu để kết luận | Phát hiện tiêu biểu |
| --- | --- | --- | --- |
| Đúng đắn | Nội dung có đúng dữ kiện tình huống, nguồn yêu cầu và CR-01 không? | Không gán chính sách chưa được xác nhận cho đề bài; tính toán khung giờ đúng. | VR-09, VR-11 |
| Đầy đủ | Có đủ yêu cầu, ngoại lệ, dữ liệu và test cho phạm vi đã ghi không? | 18 yêu cầu có TC; trường hợp lỗi và nhu cầu chưa được đặc tả phải được ghi nhận. | VR-01, VR-06, VR-17, VR-22 |
| Nhất quán | Cùng một ID, trạng thái hoặc quy tắc có cùng ý nghĩa trong các tài liệu không? | FR/NFR, scenario, TC và ma trận không dùng lẫn ID hoặc ngưỡng. | VR-03, VR-04, VR-10, VR-13 |
| Khả thi | Kết quả có nằm trong khả năng kiểm soát của hệ thống và dịch vụ phụ thuộc không? | Phân biệt phát lệnh với kết quả của nhà cung cấp; có nhánh xử lý lỗi. | VR-15, VR-25, VR-26 |
| Rõ ràng | Người đọc có xác định được tác nhân, hành vi và điều kiện không? | Không dùng nhận xét chung thay cho trạng thái, quyền hoặc hành vi quan sát được. | VR-12, VR-21, VR-23 |
| Đo lường được | Có điều kiện đạt/không đạt và cách thu bằng chứng không? | Thống nhất p95, số phiên, thời hạn OTP, mốc giữ chỗ và công thức uptime. | VR-07, VR-08, VR-14, VR-20 |

### 6.1.3. Bảng Validation Report

| Mã | Vấn đề / bằng chứng đối chiếu | Tiêu chí | Mục bị ảnh hưởng | Quyết định | Lý do kỹ thuật và biện pháp xử lý | Phụ trách / điều kiện đóng |
| --- | --- | --- | --- | --- | --- | --- |
| VR-01 | Kế hoạch thu thập yêu cầu chưa có nội dung. Phụ lục PL-1 đến PL-3 của Mini-SRS còn các mục chưa hoàn thiện, chưa có kế hoạch, bộ câu hỏi hoặc nội dung khảo sát. | Đầy đủ; Đúng đắn | Kế hoạch thu thập yêu cầu; Mini-SRS, phụ lục khảo sát | **Sửa (Fix)** | Cần có kế hoạch và nội dung khảo sát trước khi xác nhận nguồn stakeholder; biên bản chưa điền không phải minh chứng đã phỏng vấn. Bổ sung kế hoạch ít nhất 2 kỹ thuật, 5 câu mở, 5 câu đóng, 5 câu ngoại lệ/NFR; ghi riêng dữ kiện, giả định và câu hỏi chưa có trả lời. | TV1; đóng khi nội dung được điền và mỗi kết luận có nguồn hoặc nhãn giả định. |
| VR-02 | Mục 2.1 và nhiều hàng mục 3 của Mini-SRS còn thiếu nội dung về môi trường vận hành, nguồn và đặc tả yêu cầu; lịch sử phiên bản chưa ghi ngày cập nhật. | Đầy đủ; Rõ ràng | Mini-SRS, mục 2, 3 và lịch sử thay đổi | **Sửa (Fix)** | Chuyển đặc tả đã có ở Danh mục yêu cầu vào Mini-SRS; điền môi trường theo dữ liệu được xác nhận hoặc ghi nhãn giả định. Ngày phiên bản phải dựa trên lần cập nhật thực tế. Bản SRS cần có nội dung đặc tả thay cho các ô chưa hoàn thiện. | TV1, TV2; đóng khi không còn ô mẫu trong bản tổng hợp. |
| VR-03 | Mini-SRS đặt NFR-03 là “Mã hóa dữ liệu y tế”, NFR-06 là “Sao lưu & Khôi phục CSDL”; Danh mục yêu cầu dùng cùng ID cho OTP và lưu trữ lịch hẹn/giao dịch. | Nhất quán | Danh mục yêu cầu; Mini-SRS, mục 3.3; ma trận | **Sửa (Fix)** | Giữ ý nghĩa ID theo Danh mục yêu cầu: NFR-03 là OTP, NFR-06 là lưu trữ và bảo toàn dữ liệu. Mã hóa hoặc sao lưu, nếu nhóm giữ trong phạm vi, phải được đặc tả bằng ID riêng; TC về OTP không chứng minh mã hóa hoặc khả năng khôi phục. | TV2; đóng khi tên, mô tả, tiêu chí và TC thống nhất. |
| VR-04 | TC-03 gắn FR-06, FR-07, trong khi FR-06 kiểm tra dữ liệu lúc đặt lịch; việc tra cứu OTP và tự hủy thuộc FR-04, FR-05. | Nhất quán; Đúng đắn | Báo cáo kiểm định và kịch bản kiểm thử, TC-03; Mini-SRS, mục 6.2 và 7 | **Sửa (Fix)** | Liên kết hiệu chỉnh là FR-04, FR-05, FR-07, NFR-03. Bỏ FR-06 khỏi TC-03; kiểm tra dữ liệu không hợp lệ bằng TC-07. | TV3, TV4; áp dụng tại mục 6.2 và 7 báo cáo này; đóng toàn bộ khi bản tổng hợp được đồng bộ. |
| VR-05 | Ma trận trước hiệu chỉnh gắn N-02/STK-02 với FR-05 và SC-01; gắn N-04 với FR-06/SC-03; các hàng NFR dùng “Toàn bộ” và TC không có bước kiểm chứng tương ứng. | Nhất quán; Rõ ràng | Mini-SRS, mục 7 | **Sửa (Fix)** | FR-05 là đổi/hủy của bệnh nhân, không phải bác sĩ xem danh sách. Tách mỗi Requirement ID thành một hàng; dùng STK, SC và TC cụ thể. Nhu cầu chưa có FR được ghi riêng, không gán vào chức năng khác để lấp ô. | TV4; ma trận hiệu chỉnh tại mục 7.3; các khoảng thiếu ở mục 7.5. |
| VR-06 | Bộ TC-01 đến TC-06 chưa có test trực tiếp cho 30 phiên đồng thời, OTP sai/hết hạn, phân quyền, uptime và truy xuất dữ liệu sau khi lịch kết thúc. | Đầy đủ; Đo lường được | NFR-02 đến NFR-06; Báo cáo kiểm định và kịch bản kiểm thử | **Sửa (Fix)** | Bổ sung TC-09, TC-11, TC-12, TC-13, TC-14. Một TC thao tác thành công không thay thế test từ chối quyền, kiểm tra uptime hoặc lưu trữ. | TV3, TV4; đã đặc tả tại mục 6.3; cần chạy khi có hệ thống. |
| VR-07 | NFR-01 yêu cầu ít nhất 95% request phản hồi trong 2 giây; TC-04 chỉ yêu cầu trung bình không quá 2 giây và p95 không quá 2,5 giây. | Nhất quán; Đo lường được | NFR-01; TC-04; Mini-SRS, mục 6.2 | **Sửa (Fix)** | Trung bình đạt không chứng minh 95% request đạt. Dùng tỷ lệ request phản hồi trong 2.000 ms ít nhất 95%, đối chiếu p95 không quá 2.000 ms. Ngưỡng 2,5 giây không dùng để nghiệm thu NFR-01. | TV2, TV3; quy tắc hiệu chỉnh tại mục 6.2.3. |
| VR-08 | TC-04 dùng 100 VU làm tải nghiệm thu; NFR-02 hiện hành đặt tối thiểu 30 phiên đồng thời và NFR-01 chưa định nghĩa tải bình thường. | Rõ ràng; Đo lường được | NFR-01, NFR-02; TC-04 | **Sửa (Fix)** | Định nghĩa tạm tải bình thường là 30 phiên trong cấu hình kiểm thử, có nhãn giả định. Bài 100 VU được giữ làm kiểm tra tải mở rộng, không suy ra đó là ngưỡng stakeholder đã chốt. | TV2, TV3; đóng khi tải nghiệm thu được xác nhận và ghi thống nhất. |
| VR-09 | SC-03 tự hoàn 100% khi bệnh nhân hủy; mục 5.2 Mini-SRS quy thay đổi này cho CR-01. CR-01 của đề bài và FR-12 chỉ bắt buộc hoàn khi bác sĩ/phòng khám hủy. | Đúng đắn; Nhất quán | SC-03; Mini-SRS, mục 4 và 5.2; FR-12 | **Sửa (Fix)** | Không suy ra chính sách hoàn khi bệnh nhân hủy từ nghĩa vụ của phòng khám. Tách thành câu hỏi cần STK-01 xác nhận. Bộ test cơ sở dùng lịch trực tiếp khi kiểm tra bệnh nhân hủy; hoàn tự động được nghiệm thu ở SC-04. | TV2, TV3; đóng khi SC-03 và bảng tác động bỏ khẳng định chưa có nguồn hoặc có chính sách được xác nhận. |
| VR-10 | FR-07 nói hủy hợp lệ thì khung giờ trở lại “Khả dụng”, nhưng FR-08 khóa ca khi bác sĩ nghỉ. Cách giải phóng vô điều kiện có thể mở lại ca đã đóng. | Nhất quán; Đúng đắn | FR-07, FR-08, FR-11; SC-03, SC-04 | **Sửa (Fix)** | Bổ sung điều kiện: chỉ mở lại nếu ca còn hoạt động và không có lý do khóa khác. Hủy lịch hoặc hết hạn giữ chỗ trong ca đã đóng không được mở ca. Kiểm tra nhánh này ở TC-15 và TC-16. | TV2, TV3; đóng khi điều kiện được thêm vào đặc tả và các luồng giải phóng. |
| VR-11 | G-01 mô tả ca 4 giờ, 15 phút/lượt nhưng cho 16-20 lượt hẹn. Nếu mỗi lượt dùng một khung giờ và không chồng lịch thì 240/15 chỉ bằng 16. | Đúng đắn; Khả thi | Mini-SRS, G-01 và thuật ngữ khung giờ; PL-4, Q-01 | **Sửa (Fix)** | Với giả định hiện có, ghi tối đa 16 lượt/ca/bác sĩ khi không có giờ nghỉ. Muốn 20 lượt phải khảo sát thời lượng lượt, số bệnh nhân/slot hoặc độ dài ca; không đồng thời giữ ba giá trị mâu thuẫn. | TV1, TV2; STK-01/STK-02 xác nhận quy tắc công suất. |
| VR-12 | G-03, G-08, G-10 tham chiếu FR-04 như chức năng tiếp nhận; G-06 tham chiếu FR-06 như đổi/hủy. Ý nghĩa các ID này đã khác trong Danh mục yêu cầu. | Nhất quán; Rõ ràng | Mini-SRS, bảng G-01 đến G-12 | **Sửa (Fix)** | G-06 tham chiếu FR-05. G-03, G-08, G-10 ghi là vấn đề phạm vi/tiếp nhận chưa có FR thay vì gắn FR-04. Mã giả định phải chỉ đúng phần chịu tác động. | TV1, TV2; đóng khi toàn bộ tham chiếu G được rà lại. |
| VR-13 | NFR-03 khóa sau 3 lần sai; ngoại lệ SC-03 dùng “sai quá 3 lần”, có thể được hiểu là cho phép lần sai thứ tư. | Nhất quán; Đo lường được | NFR-03; SC-03, ngoại lệ 3a; G-07 | **Sửa (Fix)** | Thống nhất khóa ngay sau lần nhập sai thứ ba. Làm rõ mốc hết hạn khi tuổi OTP đạt 180 giây; TC-09 kiểm tra 179 giây, 180 giây và lần sai thứ ba. Các ngưỡng vẫn thuộc G-07. | TV2, TV3; đóng khi NFR, scenario và test dùng cùng điều kiện. |
| VR-14 | TC-03 chỉ thử hủy trước 4 giờ; chưa thử đúng 120 phút, dưới 120 phút, đổi thành công và khung giờ mới bị người khác chiếm. | Đầy đủ; Đo lường được | FR-05, FR-07; SC-03 | **Sửa (Fix)** | Bổ sung TC-10 với dữ liệu biên và nhánh giữ lịch cũ khi đổi thất bại. Đo bằng thời gian máy chủ; không kết luận đạt chỉ dựa vào nút trên giao diện bị làm mờ. | TV3; đặc tả bổ sung tại mục 6.3. |
| VR-15 | Hậu điều kiện SC-04 khẳng định 100% bệnh nhân nhận thông báo; chính scenario có ngoại lệ SMS thất bại. NFR/TC còn có cách diễn đạt tiền về hoặc thông báo “lập tức”. | Khả thi; Nhất quán | SC-04; FR-09, FR-12; TC-01, TC-06 | **Sửa (Fix)** | Cam kết trong hệ thống là tạo thông báo cho 100% lịch bị ảnh hưởng, ghi kết quả gửi và đưa trường hợp thất bại vào danh sách liên hệ. Tách phát lệnh hoàn, xác nhận của cổng và ngân hàng ghi có. Không cam kết người bệnh thực sự đọc tin hoặc tiền về tức thời. | TV2, TV3; kiểm chứng bằng TC-16, TC-17 và nhật ký giao dịch. |
| VR-16 | TC-01 thiếu giới tính trong bộ dữ liệu dù FR-02/SC-01 có trường này; TC-03 dùng “hôm nay”; TC-01 đặt SMS dưới 60 giây nhưng FR-03 chưa có ngưỡng đó. | Rõ ràng; Đo lường được | TC-01, TC-03; FR-02, FR-03, FR-06 | **Sửa (Fix)** | Thêm giới tính Nam cho TC-01; cố định TC-03 vào 15/10/2026; 60 giây là ngưỡng dự thảo cần xác nhận. Khảo sát trường bắt buộc ngoài họ tên/SĐT thay vì tự quy định mọi trường đều bắt buộc. | TV2, TV3; điều chỉnh áp dụng tại mục 6.2; STK-01 xác nhận trường bắt buộc và SLA gửi tin. |
| VR-17 | FR-11 có thất bại, hủy giao dịch và hết 15 phút; TC-05 chỉ kiểm tra thanh toán thành công. | Đầy đủ | FR-03, FR-11; SC-01, ngoại lệ 10a/10b | **Sửa (Fix)** | Bổ sung TC-15 cho từng nhánh, kiểm tra không xác nhận lịch, không gửi xác nhận chính thức và giải phóng có điều kiện. | TV3; đặc tả TC-15 tại mục 6.3. |
| VR-18 | SC-01/FR-11 chưa nói cách xử lý callback thanh toán lặp, sai giao dịch hoặc đến sau khi giữ chỗ hết hạn; FR-12 chưa có kiểm chứng chống hoàn lặp. | Đầy đủ; Khả thi | FR-03, FR-11, FR-12; SC-01, SC-04; CR-01 | **Sửa (Fix)** | Kiến nghị tiêu chí xác thực thông báo theo giao thức cổng, đối chiếu mã/số tiền và xử lý một lần cho cùng giao dịch. Callback muộn không được chiếm lại slot của người khác; đưa khoản tiền vào đối soát theo chính sách cần xác nhận. TC-18 là kiểm chứng bổ sung cho các tiêu chí QA này. | TV2, TV3; đóng khi giao thức, tiêu chí và xử lý tiền đã thu được phê duyệt. |
| VR-19 | Mô hình `GiaoDich` trong CR-01 thiếu mã yêu cầu/mã giao dịch hoàn tiền và trạng thái chờ xử lý thủ công, dù SC-04 và FR-12 cần lưu/hiển thị chúng. | Đầy đủ; Nhất quán | CR-01, mô hình dữ liệu; NFR-06; SC-04 | **Sửa (Fix)** | Bổ sung trường phục vụ liên kết lệnh hoàn và phản hồi, trạng thái chờ xử lý thủ công, lỗi và thời điểm xử lý. `ThoiGianHoanTien` để trống trước khi có kết quả hoàn thành; không điền thời điểm giả để đủ cột. | TV2, TV3; kiểm tra bằng TC-14, TC-16, TC-18. |
| VR-20 | G-12 giả định lưu 5 năm, còn NFR-06 để thời gian lưu tối thiểu cần xác nhận. NFR-05 cũng chưa định nghĩa cửa sổ đo uptime và cách loại bảo trì. | Nhất quán; Đo lường được | NFR-05, NFR-06; G-12 | **Sửa (Fix)** | 5 năm tiếp tục là G-12, không biến thành cam kết chính thức. Viết công thức uptime và quy tắc loại bảo trì; thử truy xuất sau khi lịch kết thúc. Kiểm thử chính sách 5 năm chỉ là nhánh có điều kiện cho đến khi được xác nhận. | TV1, TV2; TC-13, TC-14 có phương pháp đo; thời hạn lưu cần STK-01 xác nhận. |
| VR-21 | NFR-04 mới nêu quyền đóng ca/hủy ca/hoàn tiền; chưa có quyền đọc lịch theo bác sĩ, quyền tiếp nhận hoặc quyền xem lịch bệnh nhân khác. G-11 còn nói chẩn đoán nằm ngoài phạm vi. | Đầy đủ; Rõ ràng | NFR-04; G-11; phạm vi EMR | **Sửa (Fix)** | Kiểm thử ngay các quyền quản lý đã đặc tả. Lập câu hỏi quyền đọc/sửa dữ liệu hành chính và danh sách ca; không lấy quyền với bệnh án chuyên sâu làm tiêu chí nghiệm thu hệ thống đặt lịch. | TV1, TV2; TC-12 kiểm tra quyền hiện có; bảng quyền đầy đủ phải được STK-01 xác nhận. |
| VR-22 | Phạm vi mục 1.3 Mini-SRS có bác sĩ xem danh sách, chuẩn bị hồ sơ, check-in, đến trễ và khám gấp; FR-01 đến FR-12 chưa đặc tả chức năng xem danh sách ca hoặc check-in. | Đầy đủ; Đúng đắn | N-02, N-03; Mini-SRS, mục 1.3; danh mục FR | **Sửa (Fix)** | TV1/TV2 phải quyết định bổ sung FR và scenario/test hoặc thu hẹp phạm vi với căn cứ. Không ánh xạ nhu cầu bác sĩ xem danh sách vào FR-05. Báo cáo giữ 18 ID đã có và ghi rõ khoảng thiếu tại mục 7.5. | TV1, TV2; đóng khi phạm vi và catalogue thống nhất. |
| VR-23 | Tài liệu dùng “dễ dàng”, “kịp thời”, “tức thì”, “an toàn”, “bảo mật”, “minh bạch và chính xác” mà không có điều kiện cụ thể. | Rõ ràng; Đo lường được | Tài liệu Vấn đề và phạm vi, Danh mục yêu cầu, Đặc tả tình huống sử dụng, bộ test và CR-01 | **Sửa (Fix)** | Thay câu mang tính đặc tả bằng hành vi, quyền, dữ liệu hoặc ngưỡng tại mục 8.1. Lời nói và nhu cầu stakeholder được giữ làm nguồn, nhưng phải có yêu cầu kiểm chứng riêng. | TV4 phối hợp tác giả từng phần; đóng khi bản tổng hợp áp dụng các câu thay thế. |
| VR-24 | Bảng tác động CR-01 mới nêu FR-03, FR-11, FR-12; chưa chỉ ra NFR-06 bản 1.1 và các yêu cầu liên đới. Lịch sử thay đổi chưa có ngày và nội dung theo ID. | Đầy đủ; Nhất quán | CR-01; Mini-SRS, mục 5 và lịch sử phiên bản | **Sửa (Fix)** | Bổ sung tác động dữ liệu/giao dịch lên NFR-06, quyền hoàn tiền lên NFR-04, tra cứu/đặt lịch online và đóng ca/thông báo lên FR liên đới. Chỉ tăng phiên bản yêu cầu có nội dung thay đổi; tác động hồi quy không tự làm mọi FR thành 1.1. | TV1, TV2, TV3; bảng truy vết thay đổi tại mục 7.4 làm căn cứ đồng bộ. |
| VR-25 | Cần xem xét giảm thời gian giữ chỗ 15 phút vì có thể chiếm slot lâu; tài liệu ghi giá trị này là G-05 và có nhánh giải phóng. | Khả thi | FR-11; G-05; SC-01 | **Không sửa (No-fix)** | Giữ 15 phút ở mức giả định kiểm thử. Chưa có số liệu thời gian thanh toán hoặc quy tắc hết hạn của cổng để chọn giá trị khác. Cơ chế hết hạn đã được đặc tả; kiểm chứng bằng TC-15. No-fix không có nghĩa stakeholder đã chấp thuận 15 phút. | TV2/TV3 giữ G-05; xem lại khi có số liệu hoặc cấu hình cổng. |
| VR-26 | Cần xem xét gửi SMS ngay trong giao dịch lưu lịch thay cho hàng đợi bất đồng bộ của SC-01. | Khả thi | SC-01, bước 12; FR-03, FR-09 | **Không sửa (No-fix)** | Giữ gửi bất đồng bộ. Lưu lịch không cần chờ mạng SMS; TC-17 kiểm tra lỗi gửi được ghi nhận, còn lịch/giao dịch vẫn tồn tại. Chưa có mã triển khai để kết luận cơ chế hàng đợi đã hoạt động. | TV3 giữ mô tả thiết kế; cần kiểm thử tích hợp khi có ứng dụng. |
| VR-27 | SC-01/SC-04 nói gửi SMS và Email nhưng biểu mẫu và dữ liệu TC-01/TC-05 không có địa chỉ email. FR-03/FR-09 dùng SMS/Email, chưa thống nhất gửi một kênh hay cả hai. | Nhất quán; Đầy đủ | FR-03, FR-09; SC-01, SC-04; biểu mẫu bệnh nhân | **Sửa (Fix)** | Theo dữ liệu hiện có, dùng SMS làm kênh kiểm thử cơ sở; Email chỉ kiểm tra khi có địa chỉ hợp lệ được thu thập. TV2/TV3 phải làm rõ yêu cầu một kênh hay hai kênh; không kỳ vọng gửi Email đến dữ liệu không tồn tại. | TV2, TV3; đóng khi catalogue, biểu mẫu và test thống nhất kênh. |

**Tổng hợp:** 27 vấn đề được ghi nhận, gồm **25 quyết định Fix** và **2 quyết định No-fix**. Cả 6 tiêu chí đều có nội dung đối chiếu. Các vấn đề VR-01, VR-02, VR-03, VR-09 và VR-22 phải được xử lý trong hồ sơ tổng hợp trước khi kết luận Mini-SRS đã hoàn chỉnh.

## 6.2. Hiệu chỉnh và bổ sung cho TC-01 đến TC-06

### 6.2.1. Liên kết Requirement ID dùng cho ma trận

Bảng sau thống nhất liên kết yêu cầu và tiêu chí kiểm chứng của TC-01 đến TC-06 sau review. Các điều chỉnh tập trung vào Requirement ID, dữ liệu đầu vào, trạng thái nghiệp vụ và ngưỡng kiểm chứng.

| Test ID | Requirement ID dùng khi kiểm định | Scenario | Điều chỉnh cụ thể |
| --- | --- | --- | --- |
| TC-01 | FR-01, FR-02, FR-03 | SC-01, nhánh trực tiếp | Thêm giới tính Nam; kiểm tra trạng thái cuối “Đã xác nhận”; mã lịch là duy nhất, `AT-151001` chỉ là ví dụ. Slot đã đặt không được nhận lịch mới. Ngưỡng SMS dưới 60 giây là dự thảo, không dùng để kết luận FR-03 sai khi chưa được xác nhận. |
| TC-02 | FR-10 | SC-01, ngoại lệ trùng lịch | Dùng cùng SĐT, cùng ngày và cùng khoảng 09:00-09:15; bác sĩ khác vẫn còn slot. Chỉ thử quy tắc trùng theo SĐT đang có, chưa suy ra quy tắc cho hai khoảng giờ chỉ chồng lấn một phần. |
| TC-03 | FR-04, FR-05, FR-07, NFR-03 | SC-03, nhánh hủy | Dùng lịch trực tiếp ngày 15/10/2026 lúc 14:00; thời gian máy chủ 10:00 cùng ngày. OTP `123456` do dịch vụ giả lập phát hành. Sau hủy, mở lại slot nếu ca vẫn hoạt động; kiểm tra trên lần tải lại lịch tiếp theo, không phụ thuộc màu xanh. |
| TC-04 | NFR-01 | SC-01, tra cứu và gửi đặt lịch | Dùng tải cơ sở 30 phiên theo giả định QA-01; kiểm tra riêng tỷ lệ phản hồi trong 2 giây cho từng nhóm thao tác. Bài 100 VU giữ làm kiểm thử tải mở rộng, không thay ngưỡng cơ sở. Chi tiết tại mục 6.2.3. |
| TC-05 | FR-01, FR-02, FR-03, FR-11, NFR-06 | SC-01, nhánh trực tuyến | Trước callback thanh toán hợp lệ: chưa xác nhận chính thức và chưa gửi xác nhận. Sau callback: xác nhận đúng một lịch, lưu liên kết giao dịch. 150.000 VNĐ thuộc G-04; thông tin thẻ của TC-05 là dữ liệu minh họa, có thể thay bằng tài khoản sandbox/giả lập phù hợp. |
| TC-06 | FR-08, FR-09, FR-12, NFR-06 | SC-04, nhánh thành công | Kiểm tra cả khóa ca và các slot còn lại; thống nhất trạng thái lịch “Đã hủy bởi phòng khám do bác sĩ vắng mặt”. Lưu mã phản hồi hoàn tiền và thời gian; gửi thông báo theo kết quả của cổng. Link “ưu tiên” chưa có FR nên không dùng làm tiêu chí bắt buộc. |

`CR-01` là mã thay đổi, không phải Requirement ID. TC-05, TC-06 được gắn CR-01 ở cột thay đổi; cột Requirement ID chỉ dùng FR/NFR.

### 6.2.2. Dữ liệu và ngưỡng dùng trong kiểm thử

| Mã / loại | Giá trị dùng | Căn cứ và tình trạng |
| --- | --- | --- |
| G-04 | Phí khám online 150.000 VNĐ | Giả định về mức phí; STK-01 chưa xác nhận biểu phí chính thức. |
| G-05 | Giữ chỗ thanh toán 15 phút | Giả định kỹ thuật; kiểm tra hết hạn tại thời điểm đạt 15 phút. |
| G-06 | Cho tự đổi/hủy khi còn ít nhất 120 phút | Giả định nghiệp vụ; STK-01/STK-02 cần xác nhận. |
| G-07 | OTP 6 chữ số, hiệu lực 180 giây; khóa sau 3 lần sai | Giả định về OTP; làm rõ mốc hết hạn là tuổi OTP đạt 180 giây. |
| G-12 | Thời hạn lưu dữ liệu 5 năm | Giả định đang chờ xác nhận; chỉ dùng cho nhánh kiểm tra chính sách có điều kiện của TC-14. |
| QA-01 - Giả định kiểm thử | 30 phiên là tải bình thường khi kiểm tra NFR-01 | Chọn cùng tải cơ sở của NFR-02 để hai bài có thể đối chiếu. Catalogue chưa định nghĩa tải bình thường; cần TV2/STK-01 xác nhận. |
| QA-02 - Cấu hình phép đo | Ramp-up 10 giây; đo 60 giây sau ramp-up; 6 bác sĩ, 120 lịch mẫu | Kế thừa dữ liệu TC-04, tách thời gian làm nóng khỏi thời gian đo. Đây là cấu hình test, không phải số liệu sử dụng thực tế. |
| QA-03 - Giả định kiểm thử | Một slot của một bác sĩ tiếp nhận tối đa một lịch còn hiệu lực | Theo thuật ngữ ở Mini-SRS và cách khóa slot trong SC-01. Phải đổi bài tranh chấp nếu quy tắc công suất được stakeholder chốt khác. |
| Dữ liệu bệnh nhân | Các tên, SĐT và mã AT/GD trong bộ TC | Dữ liệu kiểm thử minh họa; mỗi nhánh nạp lại dữ liệu để không bị ảnh hưởng bởi lần chạy trước. |
| Thời gian | Asia/Ho_Chi_Minh, UTC+7; ngày 15/10/2026 | Dùng thời gian máy chủ giả lập cho điều kiện nghiệp vụ; không dùng thời gian thực lúc người kiểm thử mở báo cáo. |

Các điểm làm rõ kỹ thuật ở TC-18 và các trường dữ liệu bổ sung ở TC-14 là **kiến nghị QA**, cần đưa vào đặc tả trước khi dùng làm điều kiện nghiệm thu chính thức. Không coi những đề xuất này là nội dung đã được stakeholder phê duyệt.

### 6.2.3. Tiêu chí hiệu chỉnh của TC-04

**Mục tiêu:** Kiểm tra NFR-01 cho tra cứu chuyên khoa, bác sĩ, lịch trống và gửi dữ liệu đặt lịch. Không tính thời gian bệnh nhân thao tác ở cổng thanh toán, ngân hàng ghi có hoặc nhà mạng giao SMS vào thời gian phản hồi ứng dụng.

**Chuẩn bị:** Có 6 bác sĩ, 120 lịch mẫu và đủ slot trống cho các yêu cầu tạo lịch hợp lệ. Ghi cấu hình máy chủ, CSDL, mạng và phiên bản ứng dụng khi thực thi. Địa chỉ `/api/doctors/{id}/available-slots` trong TC-04 là ví dụ; phải ánh xạ tới giao diện/API thực tế của hệ thống khi triển khai.

**Các bước:**

1. Nạp dữ liệu, làm nóng ứng dụng và khởi tạo 30 phiên.
2. Tăng tải trong 10 giây, sau đó lấy mẫu trong 60 giây.
3. Tách nhãn request theo thao tác: tra cứu chuyên khoa, tra cứu bác sĩ, tra cứu lịch, gửi đặt lịch. Dữ liệu đặt lịch dùng SĐT và slot riêng để không lẫn lỗi nghiệp vụ với lỗi tải.
4. Lưu thời gian phản hồi từng request, kết quả xử lý, số mẫu, tỷ lệ lỗi, trung bình và p95.
5. Với mỗi nhóm thao tác, tính `Tỷ lệ đạt = số request phản hồi trong <= 2.000 ms / tổng request của nhóm x 100%`.
6. Chạy riêng cấu hình 100 VU nếu cần đánh giá giới hạn tải; ghi kết quả ở phần tải mở rộng.

**Điều kiện đạt cơ sở:** Mỗi nhóm có mẫu kiểm tra và tỷ lệ đạt ít nhất 95%; p95 không quá 2.000 ms. Trung bình chỉ là số liệu bổ trợ. Request lỗi được ghi riêng; không được loại mẫu chậm hoặc thất bại khỏi báo cáo để tăng tỷ lệ đạt. Nếu một nhóm không có mẫu, chưa có kết luận cho nhóm đó.

**Bằng chứng cần thu khi chạy:** Tệp kết quả từng request, cấu hình tải, dữ liệu nạp, báo cáo theo nhóm thao tác và thông tin môi trường. Ngưỡng 2 giây và tải bình thường vẫn mang nhãn giả định cần xác nhận.

## 6.3. Test bổ sung sau review

Các test sau bổ sung những điều kiện chưa có trong TC-01 đến TC-06. Mỗi nhánh dùng dữ liệu độc lập. Kết quả dưới đây là kết quả kỳ vọng; chưa ghi Pass/Fail khi chưa thực thi.

### TC-07 · Từ chối dữ liệu đăng ký thiếu hoặc sai định dạng

**Requirement ID:** FR-02, FR-06  
**Scenario:** SC-01, ngoại lệ 6a  
**Nguồn review:** VR-04, VR-16  
**Change Request:** Không áp dụng

**Tiền điều kiện:** BS. Nguyễn Văn A có slot 08:30-08:45 ngày 15/10/2026 khả dụng. Dữ liệu hợp lệ gồm Trần Văn An, SĐT `0912345678`, ngày sinh 12/05/1990, giới tính Nam, triệu chứng “Đau đầu, sốt nhẹ 2 ngày”.

**Dữ liệu theo nhánh:** A - bỏ trống họ tên; B - bỏ trống SĐT; C - SĐT có 9 chữ số. D - SĐT 11 chữ số; E - SĐT 10 ký tự nhưng chứa chữ. Nhánh D/E kiểm tra quy tắc đề xuất làm rõ “SĐT gồm đúng 10 chữ số”, cần được TV2 thống nhất trong FR-06.

**Các bước:**

1. Nạp lại dữ liệu slot và ghi số lịch hiện có.
2. Mở biểu mẫu đặt lịch, nhập một bộ dữ liệu theo nhánh.
3. Gửi yêu cầu đặt lịch bằng giao diện; kiểm tra phía xử lý yêu cầu cũng từ chối dữ liệu tương ứng.
4. Đối chiếu bản ghi lịch, trạng thái slot và nhật ký gửi xác nhận.
5. Sửa thành dữ liệu hợp lệ và gửi lại.

**Kết quả kỳ vọng:** Nhánh A/B/C không tạo lịch, không chiếm slot, không gửi xác nhận; trường lỗi được chỉ rõ. Khi sửa hợp lệ, tạo một lịch theo FR-02. Nhánh D/E chỉ kết luận theo quy tắc làm rõ đã được chấp thuận; không tự suy ra các trường khác bắt buộc nếu catalogue chưa quy định.

**Bằng chứng:** Phản hồi lỗi, ảnh trường bị đánh dấu, số bản ghi trước/sau và nhật ký thông báo.

### TC-08 · Khung giờ hết khả dụng và tranh chấp một slot

**Requirement ID:** FR-01, FR-02  
**Scenario:** SC-01, ngoại lệ 4a; SC-02  
**Nguồn review:** VR-05, VR-06  
**Change Request:** CR-01 đối với nhánh slot đang giữ chỗ thanh toán

**Tiền điều kiện:** Hai phiên A/B mở cùng slot 09:00-09:15 của BS. Nguyễn Văn A ngày 15/10/2026. Hai bệnh nhân dùng SĐT khác nhau. Áp dụng QA-03.

**Các bước:**

1. A hoàn tất đặt slot; B gửi yêu cầu từ trang đã mở trước khi A đặt.
2. Kiểm tra B nhận phản hồi không còn khả dụng và lịch của A không bị thay đổi.
3. B chọn một slot còn trống khác, tiếp tục SC-01.
4. Lặp lại với slot bị khóa do bác sĩ nghỉ và slot đang giữ chỗ thanh toán online.
5. Nạp tình huống toàn bộ bác sĩ trong chuyên khoa kín lịch; mở lại danh sách lựa chọn.

**Kết quả kỳ vọng:** Không tạo thêm lịch vào slot đã chiếm, bị khóa hoặc còn thời hạn giữ chỗ. Theo QA-03, tại một slot chỉ có tối đa một lịch còn hiệu lực. B có thể chọn slot khác nếu tồn tại; nếu không còn slot thì được hướng dẫn chọn ngày khác hoặc liên hệ phòng khám. Số “03 gợi ý” là giả định thiết kế trong SC-02, không phải ngưỡng đã được xác nhận của FR-01.

**Bằng chứng:** Hai phản hồi của A/B, số lịch theo bác sĩ/slot, trạng thái slot và danh sách lựa chọn sau khi làm mới.

### TC-09 · OTP sai, hết hạn và khóa phiên

**Requirement ID:** FR-04, NFR-03  
**Scenario:** SC-03, bước 1-4 và ngoại lệ 1a/3a  
**Nguồn review:** VR-06, VR-13  
**Change Request:** Không áp dụng

**Tiền điều kiện:** Lịch `AT-998877`, SĐT `0987654321`; dịch vụ SMS giả lập phát OTP `123456` lúc 10:00:00 ngày 15/10/2026; áp dụng G-07. Trước xác thực, không có quyền xem chi tiết hoặc đổi/hủy lịch.

**Các bước theo nhánh:**

1. A - nhập mã lịch/SĐT không khớp và thử truy cập chi tiết.
2. B - dùng đúng mã/SĐT, nhập OTP đúng tại 10:02:59, trước mốc hết hạn.
3. C - nạp lại phiên, nhập OTP đúng tại 10:03:00, đúng mốc 180 giây.
4. D - nạp lại phiên, nhập sai lần 1, lần 2, lần 3; sau lần 3 thử gửi OTP đúng trong phiên cũ.
5. Yêu cầu OTP mới sau khi phiên cũ bị khóa; thử dùng OTP cũ rồi OTP mới.

**Kết quả kỳ vọng:** A không được xem dữ liệu; B được xác thực; C bị từ chối theo quy tắc hết hạn đã làm rõ. D khóa ngay sau lần sai thứ ba; OTP đúng cũng không mở lại phiên bị khóa. Mã cũ không dùng để xác thực phiên mới. Không thay đổi lịch khi xác thực thất bại. Quy tắc vô hiệu mã cũ khi gửi lại là kiến nghị QA cần bổ sung vào đặc tả.

**Bằng chứng:** Thời điểm phát/xác thực, phản hồi từng lần, trạng thái phiên và nhật ký không có thao tác đổi/hủy trái quyền.

### TC-10 · Đổi/hủy tại biên 120 phút và bảo toàn lịch cũ

**Requirement ID:** FR-04, FR-05, FR-07  
**Scenario:** SC-03, nhánh hủy, nhánh đổi và ngoại lệ khung giờ mới bị chiếm  
**Nguồn review:** VR-10, VR-14  
**Change Request:** Không áp dụng cho bộ dữ liệu trực tiếp này

**Tiền điều kiện:** Lịch trực tiếp `AT-998877` lúc 14:00 ngày 15/10/2026; bệnh nhân đã xác thực OTP. Slot 15:00-15:15 cùng bác sĩ còn trống; ca đang hoạt động. Áp dụng G-06 và dữ liệu độc lập cho từng nhánh.

**Các bước và kết quả kỳ vọng:**

| Nhánh | Thời gian máy chủ / thao tác | Kết quả kỳ vọng |
| --- | --- | --- |
| A | 12:00:00, hủy lịch 14:00 | Còn đúng 120 phút: cho hủy; lịch chuyển “Đã hủy bởi bệnh nhân”; mở slot cũ khi ca còn hoạt động. |
| B | 12:00:01, yêu cầu hủy | Còn 119 phút 59 giây: từ chối tự hủy, lịch và slot giữ nguyên, hướng dẫn liên hệ phòng khám. |
| C | 12:00:00, đổi từ 14:00 sang 15:00 | Cho đổi; mã lịch giữ nguyên; slot mới không còn khả dụng, slot cũ được mở; gửi thông tin giờ mới. |
| D | 12:00:01, yêu cầu đổi | Từ chối tự đổi; không tạo lịch/slot mới. |
| E | 10:00:00, chọn 15:00; một phiên khác chiếm slot trước khi lưu | Lưu đổi bị từ chối; lịch vẫn ở 14:00, slot cũ không bị mở, không có xác nhận đổi thành công. |

Với B/D, gửi lại yêu cầu trực tiếp đến chức năng xử lý để kiểm tra hệ thống vẫn từ chối khi bỏ qua trạng thái nút trên giao diện. Trường hợp đổi lịch online đã thanh toán cần chính sách giữ/chuyển giao dịch được xác nhận; bộ dữ liệu này không tự áp dụng hoàn tiền cho bệnh nhân hủy.

**Bằng chứng:** Thời gian máy chủ, phản hồi thao tác, lịch/slot trước và sau, nhật ký thông báo.

### TC-11 · Ba mươi phiên đồng thời không gây mất hoặc thừa lịch

**Requirement ID:** FR-01, FR-02, FR-10, NFR-02  
**Scenario:** SC-01, ngoại lệ trùng lịch; SC-02  
**Nguồn review:** VR-06, VR-08  
**Change Request:** CR-01 ở phần kiểm tra hồi quy slot đang giữ chỗ

**Tiền điều kiện:** 6 bác sĩ và 120 lịch mẫu; có đủ slot riêng cho các lượt đặt hợp lệ. Áp dụng ngưỡng 30 phiên của NFR-02 và QA-03.

**Các bước:**

1. Khởi tạo 30 phiên cùng hoạt động; 10 phiên tra cứu, 20 phiên gửi đặt lịch vào 20 slot riêng bằng 20 SĐT khác nhau.
2. Ghi phản hồi từng yêu cầu và đối chiếu 20 bản ghi lịch được tạo.
3. Nạp lại dữ liệu, cho nhiều SĐT gửi vào cùng một slot; xác định số yêu cầu được chấp nhận.
4. Nạp lại dữ liệu, dùng cùng SĐT đặt cùng giờ ở hai bác sĩ khác nhau để kiểm tra FR-10.
5. Lặp tranh chấp với slot đang được giữ cho giao dịch online còn hạn.

**Kết quả kỳ vọng:** Pha slot riêng có đúng 20 lịch, mỗi phản hồi thành công khớp một bản ghi, không mất bản ghi hoặc tạo thừa. Pha tranh chấp chỉ nhận tối đa một lịch theo QA-03. Pha cùng SĐT/cùng giờ không nhận hai lịch. Slot giữ chỗ không bị phiên khác chiếm. Phản hồi từ chối do hết slot hoặc trùng lịch là kết quả nghiệp vụ dự kiến, không tính là lỗi máy chủ.

**Bằng chứng:** Số phiên đồng thời, danh sách request/response, mã lịch được tạo, truy vấn đối chiếu theo SĐT và slot. Tốc độ phản hồi được kết luận bằng TC-04; TC-11 kết luận về xử lý đồng thời và bảo toàn dữ liệu.

### TC-12 · Phân quyền đóng ca, hủy ca và xử lý hoàn tiền

**Requirement ID:** FR-08, FR-12, NFR-04  
**Scenario:** SC-04, tiền điều kiện và bước 3-6  
**Nguồn review:** VR-06, VR-21  
**Change Request:** CR-01 đối với quyền kích hoạt hoàn tiền

**Tiền điều kiện:** Ca chiều 15/10/2026 của BS. Lê Thị B có lịch trực tuyến đã thanh toán. Có tài khoản quản lý, bác sĩ, tiếp nhận và phiên bệnh nhân; cổng thanh toán giả lập ghi được số lần gọi hoàn tiền.

**Các bước:**

1. Với phiên chưa đăng nhập, phiên bệnh nhân, tài khoản bác sĩ và tài khoản tiếp nhận, thử đóng ca, hủy toàn bộ lịch của ca và gọi chức năng xử lý hoàn tiền.
2. Kiểm tra cả đường gọi chức năng trực tiếp, không chỉ sự hiện diện của nút trên giao diện.
3. Đối chiếu trạng thái ca, lịch và số lệnh hoàn sau mỗi lần bị từ chối.
4. Nạp lại dữ liệu, dùng tài khoản có quyền quản lý thực hiện cùng thao tác.

**Kết quả kỳ vọng:** Các vai trò không có quyền quản lý đều bị từ chối, không làm thay đổi dữ liệu và không phát lệnh hoàn. Tài khoản có quyền quản lý thực hiện được SC-04. Bảng quyền đọc/sửa từng lịch và quyền bác sĩ xem danh sách ca chưa được đặc tả đầy đủ, nên chưa kết luận đạt cho những quyền đó.

**Bằng chứng:** Vai trò của từng phiên, phản hồi từ chối/chấp nhận, số lệnh hoàn và dữ liệu trước/sau.

### TC-13 · Đo khả dụng theo tháng

**Requirement ID:** NFR-05  
**Scenario:** SC-01, SC-03, SC-04 - kiểm tra khả dụng của các luồng đã đặc tả  
**Nguồn review:** VR-06, VR-20  
**Change Request:** Không áp dụng; dùng thêm nhánh online khi kiểm tra hồi quy

**Tiền điều kiện:** Có hệ thống triển khai và cơ chế giám sát truy cập các chức năng đặt lịch, tra cứu/quản lý lịch và màn hình quản lý ca. Quy ước đo trên cả tháng là giả định kiểm thử cần xác nhận nếu phòng khám chỉ đo trong giờ phục vụ.

**Các bước:**

1. Thiết lập kiểm tra định kỳ mỗi phút trong một tháng; đây là độ phân giải phép đo của test.
2. Lưu lần kiểm tra thành công/thất bại theo chức năng; một lần thất bại chức năng nằm trong phạm vi giám sát được ghi là mẫu không khả dụng.
3. Tách các mẫu bảo trì đã thông báo trước và nằm đúng khoảng thời gian được duyệt. Sự cố hoặc thời gian bảo trì vượt khung không được tự loại.
4. Tính `Uptime = (T - M - D) / (T - M) x 100%`, với T là tổng thời gian cửa sổ đo, M là bảo trì được loại, D là gián đoạn ngoài phần được loại.
5. Đối chiếu ngưỡng 99,5%/tháng của NFR-05; kiểm tra có khoảng trống dữ liệu giám sát hay không.

**Kết quả kỳ vọng:** Uptime ít nhất 99,5% theo giả định của NFR-05. Nếu đo cả tháng 10/2026 và không loại bảo trì: T = 44.640 phút, gián đoạn tối đa tương ứng 223,2 phút. Phép lấy mẫu mỗi phút chỉ ước lượng trong độ phân giải này; không coi mẫu thiếu là thành công. Bài thử vài phút hoặc dữ liệu giám sát giả lập chỉ kiểm tra cách tính, không chứng minh uptime thực tế cả tháng.

**Bằng chứng:** Nhật ký giám sát cả kỳ, lịch bảo trì được thông báo và bảng tính uptime. Chưa có dữ liệu thực tế thì trạng thái là Chưa chạy.

### TC-14 · Lưu và truy xuất lịch hẹn, thanh toán, hoàn tiền

**Requirement ID:** FR-11, FR-12, NFR-06  
**Scenario:** SC-01, nhánh online; SC-04, nhánh hoàn tiền  
**Nguồn review:** VR-06, VR-19, VR-20  
**Change Request:** CR-01

**Tiền điều kiện:** Một lịch online có mã giao dịch `GD-888999`, số tiền 150.000 VNĐ theo G-04; cổng giả lập trả được mã giao dịch thanh toán và mã phản hồi hoàn tiền. Tên trường được đối chiếu theo mô hình dữ liệu của CR-01.

**Các bước:**

1. Thanh toán thành công; đối chiếu `MaGiaoDich`, `MaLichHen`, `SoTien`, `PhuongThucThanhToan`, `TrangThaiThanhToan`, `MaGiaoDichCongTT`, `ThoiGianThanhToan`.
2. Trước hoàn tiền, kiểm tra `ThoiGianHoanTien` chưa có giá trị; không ghi một thời gian hoàn giả.
3. Thực hiện hủy bởi phòng khám, nhận kết quả hoàn thành; kiểm tra thời gian và mã phản hồi hoàn.
4. Kết thúc/hủy lịch, khởi động lại ứng dụng rồi tra cứu lại bằng tài khoản có quyền; đối chiếu dữ liệu với trước khi khởi động lại.
5. Với chính sách lưu 5 năm theo G-12, nạp bản ghi có tuổi dưới 5 năm, chạy tác vụ dọn dữ liệu trong môi trường giả lập và tra cứu lại. Chỉ kết luận nhánh thời hạn sau khi G-12 được xác nhận và quy tắc tính năm được thống nhất.

**Kết quả kỳ vọng:** Dữ liệu tối thiểu của NFR-06 có thể truy xuất sau khi lịch kết thúc; số tiền, mã lịch và mã giao dịch không bị mất hoặc đổi. Thời gian hoàn chỉ xuất hiện khi có kết quả hoàn thành. Các trường bổ sung như `MaYeuCauHoanTien`, `MaGiaoDichHoanTien`, trạng thái/lỗi xử lý thủ công thuộc kiến nghị VR-19, phải đưa vào mô hình trước khi nghiệm thu phần bổ sung. Thử đồng hồ giả lập không thay cho bằng chứng lưu dữ liệu trong 5 năm thực tế.

**Bằng chứng:** Bản ghi trước/sau, liên kết lịch-giao dịch, mã phản hồi cổng, log khởi động và cấu hình chính sách lưu.

### TC-15 · Thanh toán thất bại, hủy và hết hạn giữ chỗ

**Requirement ID:** FR-01, FR-03, FR-08, FR-11  
**Scenario:** SC-01, ngoại lệ 10a/10b; SC-04 khi ca bị đóng  
**Nguồn review:** VR-10, VR-17, VR-25  
**Change Request:** CR-01

**Tiền điều kiện:** Giữ slot online từ 10:00:00 ngày 15/10/2026; áp dụng G-05. Cổng thanh toán giả lập tạo phản hồi thất bại, hủy hoặc không phản hồi; dịch vụ gửi xác nhận có nhật ký kiểm tra.

**Các bước và kết quả kỳ vọng:**

| Nhánh | Thao tác | Kết quả kỳ vọng |
| --- | --- | --- |
| A | Cổng trả thanh toán thất bại | Không xác nhận lịch, không gửi xác nhận chính thức; kết thúc giữ chỗ và mở slot nếu ca còn hoạt động. |
| B | Bệnh nhân hủy ở cổng | Kết quả như A; ghi giao dịch/phiên đã hủy theo mô hình được thống nhất. |
| C | Không có phản hồi; kiểm tra 10:14:59 và 10:15:00 | Trước hạn giữ chỗ còn hiệu lực. Khi đạt hạn, lịch chưa được xác nhận; sau khi tác vụ hết hạn xử lý, slot được mở nếu ca còn hoạt động. Cần ghi thời điểm tác vụ xử lý; chưa có SLA độ trễ tác vụ nên không tự đặt ngưỡng. |
| D | Trong lúc giữ chỗ, quản lý đóng ca; sau đó phiên thanh toán hết hạn | Slot vẫn bị khóa do bác sĩ nghỉ; hết hạn không mở lại ca. |

**Bằng chứng:** Thời điểm giữ chỗ/hết hạn/xử lý tác vụ, trạng thái ca-slot-lịch-giao dịch, số xác nhận được gửi. Callback đến sau hết hạn được kiểm tra riêng ở TC-18.

### TC-16 · Hoàn tiền lỗi hoặc timeout khi phòng khám hủy

**Requirement ID:** FR-07, FR-08, FR-09, FR-12, NFR-06  
**Scenario:** SC-04, ngoại lệ hoàn tiền; điều kiện giải phóng slot liên quan SC-03  
**Nguồn review:** VR-10, VR-15, VR-19  
**Change Request:** CR-01

**Tiền điều kiện:** Ca chiều BS. Lê Thị B có lịch online đã thanh toán 150.000 VNĐ, mã `GD-888999`. Cổng giả lập trả lỗi hoặc timeout cho lệnh hoàn; dùng dữ liệu riêng cho hai trường hợp.

**Các bước:**

1. Quản lý báo nghỉ và xác nhận đóng ca.
2. Cổng trả lỗi hoặc không có kết quả trong khoảng timeout được cấu hình.
3. Kiểm tra ca, slot, lịch, giao dịch và danh sách cảnh báo.
4. Kiểm tra thông báo cho bệnh nhân; mở lại danh sách lịch trống của ca.
5. Khi có kết quả đối soát hợp lệ, cập nhật theo quyền/quy trình được đặc tả; nếu chưa có quy trình thì ghi đây là nội dung cần bổ sung, không giả lập đã xử lý xong.

**Kết quả kỳ vọng:** Ca đóng, lịch hủy bởi phòng khám, slot không mở lại. Giao dịch chuyển “Chờ xử lý hoàn tiền thủ công”, có cảnh báo và đủ liên kết để tra soát. Không ghi “Đã hoàn tiền” hoặc thời gian hoàn thành khi chưa có bằng chứng. Thông báo nêu lịch đã hủy và hoàn tiền đang được xử lý, không báo tiền đã về tài khoản. Lỗi hoàn của một lịch không làm mất danh sách các lịch bị ảnh hưởng.

**Bằng chứng:** Mã lỗi/timeout, phản hồi gọi hoàn, dữ liệu và cảnh báo sau đóng ca, nội dung thông báo.

### TC-17 · Gửi thông báo thất bại và danh sách liên hệ thay thế

**Requirement ID:** FR-03, FR-08, FR-09  
**Scenario:** SC-01, bước gửi xác nhận; SC-04, ngoại lệ SMS  
**Nguồn review:** VR-15, VR-26, VR-27  
**Change Request:** CR-01 ở phần thông báo cho lịch online bị hủy

**Tiền điều kiện:** Ca có 4 lịch còn hiệu lực: 2 trực tiếp, 2 online. Dịch vụ giả lập cho 3 SMS thành công, 1 thất bại. Không cung cấp email trong bộ dữ liệu cơ sở.

**Các bước:**

1. Quản lý đóng ca; đối chiếu danh sách 4 lịch bị ảnh hưởng với danh sách thông báo tạo ra.
2. Cho dịch vụ SMS trả kết quả theo tiền điều kiện.
3. Kiểm tra số thông báo, trạng thái từng lần gửi và danh sách cần nhân viên liên hệ.
4. Kiểm tra nội dung online phân biệt hoàn thành và chờ xử lý hoàn tiền theo dữ liệu giao dịch.
5. Nạp lại dữ liệu cho một lượt đặt trực tiếp; cho dịch vụ SMS lỗi khi gửi xác nhận sau lưu lịch.

**Kết quả kỳ vọng:** Cả 4 lịch đều có thông báo cần gửi; 3 có kết quả thành công, 1 mang cờ “Chưa gửi được SMS” và xuất hiện trong danh sách liên hệ. Số liệu tổng kết bằng số bản ghi thực tế. Không khẳng định 4 bệnh nhân đã nhận/đọc tin. Ở bước 5, lịch đã lưu không bị mất do lỗi SMS. Khi chưa có email, không kỳ vọng gửi Email; quy tắc hai kênh được xử lý theo VR-27.

**Bằng chứng:** Danh sách lịch bị ảnh hưởng, thông báo, phản hồi dịch vụ và danh sách liên hệ thay thế. Việc nhân viên đã gọi bệnh nhân cần minh chứng vận hành riêng.

### TC-18 · Thông báo giao dịch lặp, không khớp và đến muộn

**Requirement ID:** FR-03, FR-11, FR-12, NFR-06  
**Scenario:** SC-01, tiếp nhận kết quả thanh toán; SC-04, xử lý hoàn tiền  
**Nguồn review:** VR-18, VR-19  
**Change Request:** CR-01  
**Tình trạng tiêu chí:** Kiến nghị QA cần bổ sung vào đặc tả

**Tiền điều kiện:** Cổng giả lập có thể gửi cùng một sự kiện nhiều lần, sự kiện không khớp giao dịch/số tiền và phản hồi muộn. Cơ chế xác thực thông báo phải theo giao thức cổng được chọn; báo cáo không tự ấn định thuật toán hoặc tên tham số.

**Các bước và kết quả kỳ vọng đề xuất:**

| Nhánh | Thao tác | Kết quả kỳ vọng đề xuất |
| --- | --- | --- |
| A | Gửi hai lần cùng thông báo thanh toán thành công hợp lệ | Chỉ một lịch được xác nhận và một kết quả thanh toán nghiệp vụ được ghi; không tạo thêm lịch hoặc xác nhận nghiệp vụ lần hai. Log kỹ thuật có thể lưu cả hai lần nhận. |
| B | Gửi thông báo sai mã giao dịch, sai số tiền hoặc không đạt xác thực cổng | Không chuyển lịch thành “Đã xác nhận”; ghi lý do từ chối/đối soát và không gửi xác nhận chính thức. |
| C | Hết 15 phút, slot đã được bệnh nhân khác đặt; sau đó nhận thông báo thu tiền cho phiên cũ | Không ghi đè lịch mới hoặc chiếm lại slot; lưu tiền đã thu để đối soát. Quyết định hoàn hay chuyển lịch cần chính sách được STK-01 xác nhận, không tự khẳng định thuộc FR-12. |
| D | Gửi lại thao tác đóng cùng ca hoặc kết quả hoàn cho cùng giao dịch | Không phát sinh nghĩa vụ hoàn vượt số tiền đã thu; cùng giao dịch chỉ có một lần hoàn nghiệp vụ được chấp nhận. Đối soát trước khi gửi lại lệnh khi lần trước timeout mà chưa rõ kết quả. |

**Bằng chứng:** Các sự kiện gửi/nhận, kết quả xác thực, số lịch, số lệnh hoàn được cổng chấp nhận, tổng số tiền hoàn và nhật ký đối soát. Test này bổ sung chất lượng xử lý tích hợp; không thay đổi nguồn nghiệp vụ của CR-01.

## 7. Ma trận truy vết

### 7.1. Danh mục nhu cầu

Các nhu cầu N-01 đến N-07 được phân nhóm theo đặt lịch, chuẩn bị ca khám, điều phối lịch, quản lý lịch cá nhân, thanh toán và chất lượng vận hành.

| Need ID | Nội dung nhu cầu | Stakeholder / nguồn | Phần yêu cầu liên quan |
| --- | --- | --- | --- |
| N-01 | Bệnh nhân tự chọn bác sĩ/khung giờ, đăng ký và có thông tin xác nhận; giảm việc phải gọi điện để đặt lịch. | STK-04, STK-01; tài liệu Vấn đề và phạm vi, phần mục tiêu và stakeholder | FR-01, FR-02, FR-03, FR-06, FR-10 |
| N-02 | Bác sĩ biết danh sách bệnh nhân theo ca và có thông tin cần chuẩn bị trước khi khám. | STK-02; tài liệu Vấn đề và phạm vi, vấn đề 4; Mini-SRS, mục 1.3 | Catalogue hiện tại chưa có FR xem danh sách ca; phần thiếu được ghi tại mục 7.5. |
| N-03 | Nhân viên và quản lý sử dụng lịch thống nhất; theo dõi slot được giải phóng, khóa ca và xử lý lịch bị ảnh hưởng. | STK-03, STK-01; tài liệu Vấn đề và phạm vi, vấn đề 2/3 và phạm vi | FR-07, FR-08, FR-09; phần check-in chưa có FR, ghi tại mục 7.5. |
| N-04 | Bệnh nhân tra cứu, đổi hoặc hủy lịch từ xa sau khi xác thực, theo điều kiện thời gian cho phép. | STK-04; tài liệu Vấn đề và phạm vi, stakeholder; SC-03 | FR-04, FR-05, NFR-03 |
| N-05 | Lịch online chỉ xác nhận sau thanh toán; nếu bác sĩ/phòng khám hủy thì xử lý hoàn tiền và thông báo. | STK-01, STK-04; CR-01 | FR-03, FR-11, FR-12; FR-08, FR-09 và NFR-06 chịu tác động liên quan. |
| N-06 | Giới hạn thao tác theo quyền và giữ dữ liệu lịch/giao dịch để tra cứu, đối soát. | STK-01, STK-02, STK-03, STK-04; NFR-04, NFR-06, G-11/G-12 và CR-01 | NFR-04, NFR-06; quyền chi tiết/thời hạn lưu còn cần xác nhận. |
| N-07 | Các thao tác đặt/quản lý lịch có thời gian phản hồi, khả năng phục vụ đồng thời và mức khả dụng kiểm chứng được. | STK-01, STK-03, STK-04; quy mô phòng khám và các giả định NFR-01, NFR-02, NFR-05 | NFR-01, NFR-02, NFR-05; các ngưỡng vẫn là giả định. |

### 7.2. Danh mục stakeholder và quy tắc liên kết

| Stakeholder ID | Vai trò |
| --- | --- |
| STK-01 | Quản lý phòng khám |
| STK-02 | Bác sĩ |
| STK-03 | Nhân viên tiếp nhận |
| STK-04 | Bệnh nhân |

Ma trận lấy **mỗi Requirement ID hiện hành làm một hàng**. Scenario là tình huống áp dụng yêu cầu; TC phải có bước hoặc kết quả kỳ vọng kiểm tra yêu cầu đó. Với NFR về vận hành/lưu trữ, các SC liên kết là luồng nghiệp vụ được giám sát hoặc dữ liệu được kiểm tra, không phải scenario mới được tự thêm vào Đặc tả tình huống sử dụng.

“Không áp dụng” ở cột Change Request là giá trị có nghĩa: yêu cầu cơ sở không phát sinh từ CR-01. Với yêu cầu bị tác động nhưng chưa đổi mô tả, cột này ghi rõ tác động hồi quy; không đồng nghĩa mọi yêu cầu đó đã tăng phiên bản. Không dùng “Toàn bộ” thay cho ID và không dùng ô trống để biểu diễn chưa rõ.

### 7.3. Traceability Matrix

| Nhu cầu | Stakeholder | Req ID (FR/NFR) | Scenario | Test case | Change request |
| --- | --- | --- | --- | --- | --- |
| N-01, N-05 | STK-04, STK-01 | **FR-01 - Tra cứu chuyên khoa, bác sĩ và khung giờ khám** | SC-01, SC-02 | TC-01, TC-05, TC-08, TC-11, TC-15 | **CR-01:** tác động lựa chọn hình thức online và slot giữ chỗ; phần tra cứu trực tiếp là cơ sở. |
| N-01, N-05 | STK-04 | **FR-02 - Đặt lịch khám** | SC-01, SC-02 | TC-01, TC-05, TC-07, TC-08, TC-11 | **CR-01:** lịch online có hình thức khám và điều kiện thanh toán; tạo lịch trực tiếp là cơ sở. |
| N-01, N-05 | STK-04, STK-01 | **FR-03 - Xác nhận và thông báo lịch hẹn** | SC-01 | TC-01, TC-05, TC-15, TC-17, TC-18 | **CR-01:** sửa điều kiện xác nhận online; FR-03 hiện hành bản 1.1. |
| N-04 | STK-04 | **FR-04 - Tra cứu và xác thực lịch hẹn** | SC-03 | TC-03, TC-09, TC-10 | **Không áp dụng:** tra cứu/xác thực thuộc nghiệp vụ cơ sở; hồi quy với lịch online khi triển khai CR-01. |
| N-04 | STK-04 | **FR-05 - Đổi hoặc hủy lịch hẹn** | SC-03 | TC-03, TC-10 | **CR-01:** cần làm rõ xử lý lịch online đã trả tiền; không suy ra bệnh nhân hủy được hoàn tự động. |
| N-01 | STK-04 | **FR-06 - Kiểm tra và xác thực dữ liệu đặt lịch** | SC-01 | TC-07 | **Không áp dụng:** kiểm tra dữ liệu đăng ký thuộc nghiệp vụ cơ sở. |
| N-03, N-04 | STK-03, STK-04, STK-01 | **FR-07 - Giải phóng khung giờ sau khi hủy lịch** | SC-03, SC-04 | TC-03, TC-10, TC-16 | **CR-01:** hồi quy điều kiện giải phóng khi ca bị khóa; không mở ca đã đóng. |
| N-03, N-05 | STK-01, STK-03, STK-02 | **FR-08 - Xử lý bác sĩ nghỉ ca đột xuất** | SC-04 | TC-06, TC-12, TC-15, TC-16, TC-17 | **CR-01:** đóng ca có lịch online kích hoạt FR-12; phần khóa ca có trước thay đổi. |
| N-03, N-05 | STK-01, STK-03, STK-04 | **FR-09 - Thông báo khi lịch khám bị thay đổi hoặc hủy** | SC-04 | TC-06, TC-16, TC-17 | **CR-01:** thông báo online kèm kết quả xử lý hoàn tiền; phần báo hủy trực tiếp là cơ sở. |
| N-01 | STK-04, STK-03 | **FR-10 - Ngăn đặt trùng lịch** | SC-01 | TC-02, TC-11 | **Không áp dụng:** kiểm tra cùng SĐT/cùng khung giờ là quy tắc cơ sở. |
| N-05 | STK-01, STK-04 | **FR-11 - Thanh toán trước cho lịch khám trực tuyến** | SC-01 | TC-05, TC-14, TC-15, TC-18 | **CR-01:** yêu cầu mới bản 1.1. |
| N-05 | STK-01, STK-04 | **FR-12 - Tự động hoàn tiền khi hủy lịch khám trực tuyến** | SC-04 | TC-06, TC-12, TC-14, TC-16, TC-18 | **CR-01:** yêu cầu mới bản 1.1; phạm vi tác nhân hủy là bác sĩ/phòng khám. |
| N-07 | STK-01, STK-03, STK-04 | **NFR-01 - Thời gian phản hồi thao tác thông thường** | SC-01 | TC-04 | **Không áp dụng:** ngưỡng cơ sở; đo thêm các thao tác online trong cùng ứng dụng khi hồi quy CR-01. |
| N-07 | STK-01, STK-03, STK-04 | **NFR-02 - Khả năng xử lý đồng thời** | SC-01, SC-02 | TC-11 | **CR-01:** kiểm tra hồi quy tranh chấp slot đang giữ cho thanh toán; ngưỡng 30 phiên là giả định cơ sở. |
| N-04 | STK-04 | **NFR-03 - Xác thực OTP khi quản lý lịch hẹn** | SC-03 | TC-03, TC-09 | **Không áp dụng:** bảo vệ tra cứu/đổi/hủy bằng OTP là yêu cầu cơ sở. |
| N-06 | STK-01, STK-02, STK-03, STK-04 | **NFR-04 - Phân quyền truy cập dữ liệu** | SC-04 | TC-12 | **CR-01:** kiểm tra quyền kích hoạt hoàn tiền; quyền đóng/hủy ca là cơ sở. |
| N-07 | STK-01, STK-03, STK-04 | **NFR-05 - Khả dụng của hệ thống** | SC-01, SC-03, SC-04 | TC-13 | **Không áp dụng:** ngưỡng khả dụng cơ sở; thêm nhánh online vào giám sát hồi quy. |
| N-06, N-05 | STK-01, STK-03, STK-04 | **NFR-06 - Lưu trữ và bảo toàn dữ liệu lịch hẹn/giao dịch** | SC-01, SC-04 | TC-05, TC-06, TC-14, TC-16, TC-18 | **CR-01:** lưu thanh toán/hoàn tiền; NFR-06 hiện hành bản 1.1. |

TC-18 và các nhánh kiểm tra theo kiến nghị QA là liên kết bổ sung. Độ bao phủ yêu cầu hiện hành không dựa riêng vào TC-18: FR-03 có TC-01/TC-05/TC-15; FR-11 có TC-05/TC-15; FR-12 có TC-06/TC-16; NFR-06 có TC-14.

### 7.4. Truy vết tác động CR-01

| Thành phần | ID / dữ liệu bị tác động | Liên kết kiểm chứng | Quyết định đối chiếu |
| --- | --- | --- | --- |
| Yêu cầu mới | FR-11, FR-12 bản 1.1 | SC-01, SC-04; TC-05, TC-06, TC-15, TC-16 | Mọi đặc tả, scenario, dữ liệu và test mới phải ghi nguồn CR-01. |
| Yêu cầu sửa đã ghi trong catalogue | FR-03, NFR-06 bản 1.1 | TC-05, TC-06, TC-14, TC-15 | Mini-SRS và lịch sử thay đổi phải ghi đúng hai yêu cầu đã đổi nội dung này, ngoài FR mới. |
| Yêu cầu chịu tác động nghiệp vụ / hồi quy | FR-01, FR-02, FR-07, FR-08, FR-09, NFR-02, NFR-04 | TC-05, TC-08, TC-11, TC-12, TC-15, TC-16, TC-17 | Rà lại online, giữ chỗ, đóng ca, quyền hoàn và nội dung thông báo. Tăng phiên bản nếu sửa mô tả/tiêu chí; giữ phiên bản nếu chỉ thêm liên kết hồi quy. |
| Quy tắc còn cần xác nhận | FR-05/SC-03 đối với bệnh nhân đổi/hủy lịch online đã trả tiền | TC-10 là bộ trực tiếp; test hoàn khi bệnh nhân hủy chỉ lập sau xác nhận | Không gắn việc hoàn 100% khi bệnh nhân hủy vào CR-01 như chính sách bắt buộc của đề. |
| Scenario đã đổi | SC-01: chọn online, giữ chỗ, thanh toán và ngoại lệ; SC-04: hoàn tiền và lỗi hoàn | TC-05, TC-06, TC-15, TC-16, TC-17, TC-18 | Luồng chính và hậu điều kiện phải tách thành công, chờ xử lý và lỗi dịch vụ. |
| Dữ liệu lịch hẹn | `HinhThucKham`, `HanThanhToanTamGiu`, liên kết giao dịch, `LinkKhamOnline` theo mô hình đề xuất | TC-05, TC-14, TC-15 | Lịch chưa thanh toán không được mang trạng thái xác nhận chính thức; dữ liệu liên kết phải truy xuất được. |
| Dữ liệu giao dịch | `MaGiaoDich`, `MaLichHen`, `SoTien`, `PhuongThucThanhToan`, trạng thái, mã cổng, thời gian thanh toán/hoàn | TC-14, TC-16 | Mô hình phải biểu diễn được trạng thái chờ xử lý thủ công; thời gian hoàn có thể chưa phát sinh. |
| Dữ liệu QA kiến nghị bổ sung | Mã yêu cầu hoàn, mã giao dịch hoàn, thông tin lỗi và liên kết sự kiện đã xử lý | TC-14, TC-18 | Bổ sung vào mô hình dữ liệu và tiêu chí kiểm chứng trước khi nghiệm thu. |
| Test cơ sở cần hồi quy | TC-01, TC-02, TC-03, TC-04 | FR-01 đến FR-07, FR-10, NFR-01, NFR-03 theo bảng liên kết | Thay đổi online không được làm sai đặt trực tiếp, chống trùng, hủy trực tiếp hoặc xác thực OTP. |

Các câu hỏi còn mở do CR-01 được ghi cụ thể để không tự điền chính sách:

| Mã QA | Câu hỏi cần xác nhận | Người xác nhận | Phần ảnh hưởng |
| --- | --- | --- | --- |
| QA-Q01 | Bệnh nhân tự hủy lịch online thì có được hoàn không; tỷ lệ, thời hạn và trường hợp hủy trễ/vắng mặt là gì? | STK-01; tham khảo STK-02 | FR-05, FR-12; SC-03; G-06; test hủy online. |
| QA-Q02 | Callback đến sau hết hạn nhưng tiền đã thu: hoàn, chuyển lịch hay xử lý đối soát theo quy tắc nào? | STK-01 và đơn vị cổng thanh toán | FR-11; SC-01; TC-18-C. |
| QA-Q03 | Cổng được chọn có quy tắc xác thực, tra cứu kết quả, chống gửi lặp và hoàn tiền như thế nào? | TV2/TV3, đơn vị cổng và STK-01 | FR-11, FR-12, NFR-06; TC-14, TC-16, TC-18. |
| QA-Q04 | Thời gian ngân hàng ghi có được cam kết là bao lâu, và nội dung nào được phép ghi trong thông báo? | Đơn vị cổng thanh toán và STK-01 | FR-09, FR-12; SC-04; TC-06, TC-16, TC-17. |
| QA-Q05 | Nền tảng khám online nào được chọn; ai được truy cập link; xử lý thế nào khi chưa tạo được link sau thanh toán? | STK-01, STK-02 và đơn vị kỹ thuật | SC-01, bước 11; TC-05; các tiêu chí quyền truy cập cần bổ sung. |

### 7.5. Kết quả rà độ bao phủ và các khoảng thiếu

| Nội dung kiểm tra | Kết quả kiểm định | Phạm vi kết luận |
| --- | --- | --- |
| FR hiện hành có ít nhất một TC liên kết | **12/12 = 100%** | FR-01 đến FR-12 theo Danh mục yêu cầu; dùng liên kết hiệu chỉnh tại mục 6.2 và test bổ sung. |
| NFR hiện hành có ít nhất một TC liên kết | **6/6 = 100%** | NFR-01 đến NFR-06; các điều kiện chưa chốt vẫn được ghi nhãn giả định/cần xác nhận. |
| Tổng yêu cầu hiện hành có TC | **18/18 = 100%** | Độ bao phủ thiết kế test theo Requirement ID, không phải tỷ lệ test đã Pass. |
| Test có Requirement ID hợp lệ | **18/18** | TC-01 đến TC-18 đều liên kết ít nhất một FR/NFR. CR-01 được ghi ở cột thay đổi. |
| Scenario có test liên kết | **4/4** | SC-01, SC-02, SC-03, SC-04 đều xuất hiện trong ma trận và bộ TC. |
| Ô ma trận không có giá trị | **0/108** | 18 hàng x 6 cột; trường hợp không chịu CR dùng giá trị “Không áp dụng”, không để trống. |
| ID tham chiếu không có định nghĩa | **0** | N-01 đến N-07, STK-01 đến STK-04, 18 Req, SC-01 đến SC-04, TC-01 đến TC-18 và CR-01 đều được định nghĩa hoặc lấy từ nguồn hiện hành. |
| Test có kết quả thực thi | **0/18** | Chưa có kết quả thực thi hoặc nhật ký kiểm thử; trạng thái toàn bộ là Chưa chạy. |

Độ bao phủ 100% của **18 yêu cầu đã có** không chứng minh toàn bộ nhu cầu/phạm vi đã được đặc tả. Các khoảng thiếu sau phải được giải quyết trong catalogue trước khi nhóm chốt Mini-SRS:

| Nhu cầu / mục phạm vi | Khoảng thiếu | Hướng xử lý đã ghi trong review |
| --- | --- | --- |
| N-02 - STK-02 xem danh sách bệnh nhân theo ca và thông tin chuẩn bị | Nhu cầu và phạm vi đã nêu trong Mini-SRS; chưa có FR xem danh sách, quyền đọc và tiêu chí cập nhật. | VR-22: TV1/TV2 bổ sung FR, scenario và test nếu giữ phạm vi. Không gán vào FR-05. |
| N-03 - Nhân viên check-in, xử lý đến trễ/khám gấp | Phạm vi và G-08/G-10 đã nêu; chưa có FR tiếp nhận, luồng tiếp nhận và TC tương ứng. | VR-12/VR-22: làm rõ quy tắc; bổ sung đặc tả hoặc điều chỉnh phạm vi có căn cứ. |
| N-06 - Bảng quyền đọc/sửa chi tiết | NFR-04 mới xác định các thao tác quản lý ca và hoàn tiền. | VR-21: xác nhận quyền cho từng vai trò/dữ liệu; TC-12 hiện chỉ nghiệm thu quyền đã nêu. |
| N-06 - Thời hạn lưu dữ liệu | NFR-06 chưa chốt thời hạn; G-12 mới là giả định 5 năm. | VR-20: xác nhận G-12 rồi hoàn thiện nhánh chính sách của TC-14. |
| N-05 - Quyền truy cập link và lỗi nền tảng khám online | Scenario có sinh link nhưng chưa có FR/tiêu chí về truy cập hoặc tạo link thất bại. | QA-Q05: bổ sung tiêu chí sau khi chọn nền tảng; không coi từ “bảo mật” là bằng chứng đạt. |

## 8. Rà ngôn ngữ và checklist nộp bài

### 8.1. Các câu cần thay bằng điều kiện kiểm chứng

Lời nói stakeholder được giữ làm nguồn nhu cầu. Khi chuyển thành đặc tả hành vi hoặc điều kiện nghiệm thu, dùng các tiêu chí kiểm chứng dưới đây.

| Cách diễn đạt trong tài liệu | Vị trí tiêu biểu | Câu/điều kiện thay thế dùng khi kiểm định |
| --- | --- | --- |
| “Đặt lịch nhanh hơn”, “thời gian phù hợp” | Nhu cầu STK-01; NFR-01 | “Trong tải đã thống nhất, ít nhất 95% request của từng nhóm thao tác phản hồi trong 2.000 ms”; ghi nhãn giả định của NFR-01. |
| “Dễ dàng”, “thuận tiện”, “dễ dùng” | Tài liệu Vấn đề và phạm vi cùng Mini-SRS, mục tiêu và nhu cầu | “Bệnh nhân có thể tra cứu và đổi/hủy qua web sau OTP, khi còn ít nhất 120 phút theo G-06.” Nếu nhóm cần đánh giá khả năng sử dụng, phải bổ sung phép đo riêng; không tự đặt điểm usability. |
| “An toàn”, “đảm bảo an toàn thông tin” | G-07; các mô tả bảo mật | “Trước OTP hợp lệ không hiển thị chi tiết hoặc cho đổi/hủy; khóa phiên sau lần sai thứ ba theo G-07.” |
| “Lập tức hiển thị màu xanh” | TC-03 | “Sau hủy hợp lệ, lần tải lại danh sách tiếp theo cho phép đặt slot cũ nếu ca còn hoạt động.” Màu chỉ là cách trình bày, không phải trạng thái nghiệp vụ. |
| “Cập nhật tức thì theo thời gian thực” | Hậu điều kiện SC-03 | “Kết quả tra cứu sau khi cập nhật thành công phải khớp trạng thái lịch đã lưu.” Nếu cần tự cập nhật không tải lại, bổ sung SLA đồng bộ riêng. |
| “100% bệnh nhân nhận thông báo kịp thời” | Hậu điều kiện SC-04 | “Tạo thông báo cho 100% lịch bị ảnh hưởng; lưu kết quả gửi; lịch gửi thất bại xuất hiện trong danh sách cần nhân viên liên hệ.” |
| “Hoàn tiền ngay lập tức”, “minh bạch và chính xác” | SC-04; mô tả CR-01 | “Phát lệnh hoàn 100% số tiền đã thu cho lịch bị bác sĩ/phòng khám hủy; lưu mã phản hồi và trạng thái; lỗi/timeout chuyển chờ xử lý thủ công.” |
| “Tiền về trong 1-3 ngày làm việc” | SC-04; CR-01, rủi ro 1 | “Thông báo trạng thái xử lý và mã tra soát; thời gian ngân hàng ghi có chỉ nêu theo cam kết đã xác nhận của nhà cung cấp.” |
| “Link online bảo mật”, “link ưu tiên” | TC-05, TC-06; SC-01/SC-04 | “Link phòng khám online được liên kết đúng lịch đã thanh toán.” Quyền truy cập, thời hạn link và mức ưu tiên cần đặc tả riêng; chưa dùng làm điều kiện nghiệm thu. |
| “Môi trường tiệm cận thực tế”, “mạng ổn định” | TC-04; môi trường vận hành | Ghi cấu hình máy chủ/CSDL, mạng, dữ liệu, công cụ, số phiên và phiên bản khi chạy; không lấy nhận xét chung làm bằng chứng tương đương môi trường thật. |
| “Đặt lịch 24/7” | Mini-SRS, giá trị kỳ vọng | Nếu giữ, xác định đó là mục tiêu truy cập cả ngày và liên kết NFR-05 cùng bảo trì; không hiểu là cam kết không có gián đoạn. Cửa sổ đo còn cần xác nhận. |

### 8.2. Checklist kiểm định yêu cầu

| Nội dung cần kiểm tra | Kết quả | Bằng chứng trong báo cáo |
| --- | --- | --- |
| Review đủ 6 tiêu chí | **Đạt** | Mục 6.1.2 và các mã VR tương ứng. |
| Tối thiểu 8 lỗi/vấn đề | **Đạt** | 27 vấn đề tại mục 6.1.3. |
| Mỗi vấn đề có quyết định Fix/No-fix và lý do | **Đạt** | 25 Fix, 2 No-fix; mỗi hàng có căn cứ, biện pháp và điều kiện đóng. |
| Có tối thiểu 6 test liên kết Requirement ID | **Đạt về đặc tả** | TC-01 đến TC-06 được đối chiếu tại mục 6.2; TC-07 đến TC-18 bổ sung tại mục 6.3; tổng 18 TC. |
| Tất cả FR/NFR hiện hành có test | **Đạt về truy vết** | 12/12 FR, 6/6 NFR; ma trận mục 7.3. |
| Ma trận có đủ 6 cột và không để ô trống | **Đạt** | 18 hàng, 108 ô có giá trị. |
| Không gán TC sai ý nghĩa FR/NFR | **Đạt trong phần hiệu chỉnh** | TC-03 không còn dùng FR-06; NFR dùng test có bước kiểm chứng tương ứng. |
| CR-01 có liên kết yêu cầu, scenario, dữ liệu và test | **Đạt về phân tích** | Mục 7.3/7.4; câu hỏi còn mở được ghi cụ thể. |
| Từ mơ hồ được rà và có câu thay thế | **Đạt về rà soát** | VR-23 và mục 8.1; bản tổng hợp còn phải áp dụng chỉnh sửa. |
| Không tự ghi test đã Pass hoặc stakeholder đã phê duyệt | **Đạt** | Test được ghi Chưa chạy; số liệu chưa xác nhận giữ nhãn giả định. |
| Khoảng thiếu của catalogue/phạm vi được nêu | **Đạt** | VR-21/VR-22 và mục 7.5; không dùng liên kết sai để lấp khoảng thiếu. |

### 8.3. Checklist hồ sơ nộp bài

| Nội dung nộp chung | Trạng thái kiểm định | Công việc phải hoàn tất trước khi nộp |
| --- | --- | --- |
| Phát biểu vấn đề, stakeholder và tối thiểu 3 mục ngoài phạm vi | **Có** | Giữ nội dung tài liệu Vấn đề và phạm vi; đồng bộ phạm vi trực tuyến và các nội dung còn thiếu theo VR-22. |
| Kế hoạch thu thập yêu cầu và bộ câu hỏi | **Chưa đạt** | TV1 hoàn thiện Kế hoạch thu thập yêu cầu và phụ lục theo VR-01. |
| Minh chứng khảo sát/biên bản và vấn đề chưa rõ | **Chưa đủ minh chứng** | TV1 bổ sung nội dung thực tế; biên bản mẫu không được trình bày như đã phỏng vấn. |
| 10 FR cơ sở, 2 FR CR-01, 6 NFR thuộc ít nhất 3 nhóm | **Có trong Danh mục yêu cầu** | TV2 đưa vào Mini-SRS và xử lý các mâu thuẫn/thiếu đã ghi trong Validation Report. |
| Mỗi yêu cầu có ID, nguồn, ưu tiên, phiên bản và kiểm chứng | **Có, cần đối chiếu nguồn** | Giữ cấu trúc Danh mục yêu cầu; xác nhận các ngưỡng/nguồn giả định và không dùng scenario làm nguồn stakeholder duy nhất khi thiếu dữ kiện. |
| Bốn scenario có đủ tác nhân, điều kiện, kích hoạt, luồng và hậu điều kiện | **Có, cần sửa** | TV3 xử lý OTP, hoàn khi bệnh nhân hủy, trạng thái slot và thông báo theo VR-09/10/13/15/27. |
| Mini-SRS không còn ô mẫu | **Chưa đạt** | TV1/TV2 điền mục 2/3 và phụ lục; thống nhất NFR-03/NFR-06. |
| Lịch sử phiên bản và phân tích tác động CR-01 | **Có khung, cần đồng bộ** | Điền ngày thực tế, ghi các ID thay đổi và dữ liệu/test chịu tác động theo mục 7.4. |
| Validation report, test và ma trận | **Có** | Đối chiếu các điều chỉnh và ma trận với Mini-SRS trước khi chốt hồ sơ; giữ đúng trạng thái chưa thực thi kiểm thử. |
| Giả định và câu hỏi chưa trả lời | **Có, cần thống nhất** | Ghi cùng ý nghĩa ID, giữ nhãn G-04/05/06/07/12; xác nhận các câu hỏi QA trước khi chốt tiêu chí liên quan. |
| Văn bản không dùng từ mơ hồ làm tiêu chí nghiệm thu | **Cần áp dụng chỉnh sửa** | Tác giả từng phần thay bằng các điều kiện ở mục 8.1 và rà lại bản tổng hợp. |
| Hồ sơ bàn giao | **Cần tổng hợp** | Hoàn thiện Mini-SRS sau review và CR-01; kèm minh chứng khảo sát, Validation Report và Traceability Matrix theo quy cách nộp bài. |

**Kết luận kiểm định:** Báo cáo ghi nhận 27 vấn đề, gồm 25 quyết định Fix và 2 quyết định No-fix. Toàn bộ 18 FR/NFR hiện hành có liên kết kiểm thử; ma trận không có ô trống. Hồ sơ cần hoàn thiện phần khảo sát và xử lý các nội dung đặc tả còn thiếu trước khi chốt Mini-SRS. Các việc cần xử lý được ghi theo mã VR và người phụ trách.
