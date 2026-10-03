# ĐẶC TẢ YÊU CẦU PHẦN MỀM & BÁO CÁO KIỂM ĐỊNH 
## DỰ ÁN: HỆ THỐNG QUẢN LÝ LỊCH KHÁM PHÒNG KHÁM ĐA KHOA AN TÂM

---

### THÔNG TIN HỌC PHẦN & ĐỀ TÀI
* **Học phần:** Nhập môn công nghệ phần mềm
* **Đề tài:** Phân tích yêu cầu, xác định phạm vi, đặc tả yêu cầu có thể kiểm chứng và xử lý thay đổi cho hệ thống quản lý lịch khám
* **Thời lượng thực hiện:** 01 tuần
* **Sản phẩm:** Mini-SRS tổng hợp toàn diện
* **Đơn vị thực hiện:** Nhóm 18
* **Ngày nộp bài:** 03/10/2026
* **Phiên bản tài liệu:** v1.1 (Đã tích hợp toàn diện Peer Review & Yêu cầu thay đổi CR-01)

### BẢNG PHÂN CÔNG NHIỆM VỤ THÀNH VIÊN THEO ROLE

| STT | Họ và tên | MSSV | Vai trò | Phân hệ & Nhiệm vụ phụ trách chi tiết |
| :---: | :--- | :---: | :--- | :--- |
| **1** | **Cao Xuân Dương** | **24120292** | **Thành viên 1 (BA)** | • **Phần 1 (Bài toán & Phạm vi):** Phát biểu hiện trạng bài toán, mục tiêu, giá trị kỳ vọng; Lập Bảng Stakeholder hệ thống (4 Core `STK-01` → `STK-04` và 2 Extended `STK-05`, `STK-06`); Xác định phạm vi trong và ngoài hệ thống; Xây dựng Bảng thuật ngữ và từ viết tắt.<br>• **Phần 3 (Khảo sát yêu cầu):** Lập Kế hoạch thu thập yêu cầu (2 kỹ thuật); Soạn Bộ câu hỏi khảo sát phân nhóm chuẩn hóa; Thực hiện và lập Biên bản phỏng vấn mẫu Quản lý phòng khám; Lập bảng câu hỏi mở.<br>• **Phần 2 (Môi trường & Giả định):** Thiết lập môi trường vận hành; Bảng Danh mục Giả định & Phụ thuộc (`G-01` → `G-12`); Khởi tạo Bảng lịch sử thay đổi phiên bản; Kiểm tra định dạng và xuất file PDF tổng hợp `BT04_Nhom18_MiniSRS.pdf`. |
| **2** | **Lê Hùng Thắng** | **24120137** | **Thành viên 2 (Requirements Engineer)** | • **Phần 4 (Đặc tả yêu cầu hệ thống):** Đặc tả chi tiết 12 Yêu cầu Chức năng (`FR-01` → `FR-12`) theo chuẩn: Bối cảnh – Hành vi hệ thống – Lý do – Tiêu chí kiểm chứng đo lường được.<br>• **Yêu cầu phi chức năng:** Đặc tả chi tiết 6 NFR (`NFR-01` → `NFR-06`) thuộc đủ 3 nhóm (Hiệu năng, Bảo mật, Khả dụng và Lưu trữ) với các chỉ số định lượng cụ thể.<br>• **Chuẩn hóa đo lường & Hỗ trợ CR-01:** Gắn nhãn minh bạch `[Giả định]` hoặc `[Cần xác nhận]` cho các tiêu chí chưa chốt số liệu; Bổ sung mới `FR-11` (Thanh toán online trước) và `FR-12` (Tự động hoàn tiền 100%). |
| **3** | **Từ Quốc Nghĩa** | **24120389** | **Thành viên 3 (Solution & Test Analyst)** | • **Phần 5 (Kịch bản nghiệp vụ):** Đặc tả chi tiết 4 Scenarios nghiệp vụ (`SC-01` → `SC-04`) theo mẫu chuẩn: Tác nhân, Tiền điều kiện, Kích hoạt, Luồng chính đánh số tương tác, Luồng thay thế/ngoại lệ rẽ nhánh, Hậu điều kiện thành công/thất bại.<br>• **Phần 6 (CR-01):** Lập Bảng phân tích tác động 4 chiều; Nhận diện các rủi ro kỹ thuật & đề xuất kiểm soát; Tích hợp nhánh thanh toán vào `SC-01` và nhánh hoàn tiền tự động vào `SC-03`, `SC-04`.<br>• **Phần 8 (Kịch bản kiểm thử cơ sở):** Thiết kế Bộ 6 Test Scenarios cơ sở (`TC-01` → `TC-06`), mỗi test case ánh xạ trực tiếp đến Requirement ID tương ứng. |
| **4** | **Nguyễn Hồ Quang Tiến** | **24120463** | **Thành viên 4 (QA & Traceability)** | • **Phần 7 (Kiểm định yêu cầu):** Chủ trì buổi đánh giá chéo nội bộ, đối chiếu hồ sơ theo 6 tiêu chí kiểm nghiệm; Lập Bảng báo cáo kiểm định chi tiết toàn văn 27 vấn đề (25 Sửa, 2 Không sửa kèm lý do kỹ thuật).<br>• **Phần 9 (Ma trận truy vết):** Lập bảng truy vết hoàn chỉnh 6 cột, 18 hàng không có bất kỳ ô trống nào (Nhu cầu gốc → STK → Req ID → Scenario → Test case → CR-01); Lập báo cáo độ bao phủ yêu cầu.<br>• **Kiểm thử mở rộng:** Bổ sung chi tiết Bộ 12 Test Cases mở rộng (`TC-07` → `TC-18`); Rà soát bảng chuyển đổi từ ngữ mơ hồ và chuẩn hóa định lượng toàn bộ tài liệu. |

---

## BẢNG LỊCH SỬ THAY ĐỔI TÀI LIỆU

| Phiên bản | Ngày cập nhật | Người thực hiện | Tóm tắt nội dung thay đổi |
| :---: | :---: | :--- | :--- |
| **v1.0** | 28/09/2026 | Cả nhóm | Khởi tạo tài liệu Mini-SRS ban đầu từ hiện trạng bài toán: Xác định bài toán, phạm vi, 4 Stakeholder, 10 Yêu cầu chức năng (`FR-01` → `FR-10`), 6 Yêu cầu phi chức năng (`NFR-01` → `NFR-06`) và 4 Kịch bản ca khám cơ sở (`SC-01` → `SC-04`). |
| **v1.1** | 02/10/2026 | Cả nhóm | • **Tích hợp yêu cầu thay đổi CR-01 về khám trực tuyến:** Bổ sung `FR-11` (Thanh toán trước), `FR-12` (Tự động hoàn tiền), sửa `FR-03`, `NFR-06`; cập nhật nhánh online và hoàn tiền vào `SC-01`, `SC-03`, `SC-04`.<br>• **Xử lý toàn diện kết quả kiểm định:** Xử lý triệt để 27 vấn đề kiểm định chéo; chuẩn hóa định lượng toàn bộ từ ngữ mơ hồ; bổ sung chi tiết 12 kịch bản kiểm thử mở rộng `TC-07` đến `TC-18`; hoàn thiện ma trận truy vết yêu cầu đầy đủ không có ô trống. |

---

# MỤC LỤC TỔNG THỂ

   **PHẦN 1: BÀI TOÁN VÀ PHẠM VI HỆ THỐNG**
   * 1.1. Hiện trạng và phát biểu bài toán
   * 1.2. Mục tiêu và giá trị kỳ vọng của hệ thống
   * 1.3. Bảng phân tích các bên liên quan
   * 1.4. Phạm vi hệ thống
   * 1.5. Bảng thuật ngữ nghiệp vụ và từ viết tắt

   **PHẦN 2: MÔI TRƯỜNG VẬN HÀNH, GIẢ ĐỊNH VÀ PHỤ THUỘC**
   * 2.1. Môi trường vận hành kỹ thuật
   * 2.2. Bảng danh mục giả định nghiệp vụ và kỹ thuật
   * 2.3. Các dịch vụ phụ thuộc bên ngoài

   **PHẦN 3: KẾ HOẠCH VÀ MINH CHỨNG KHẢO SÁT**
   * 3.1. Kỹ thuật thu thập yêu cầu lựa chọn
   * 3.2. Bộ câu hỏi khảo sát phân nhóm chuẩn hóa
   * 3.3. Kết quả nghiệp vụ kỳ vọng thu được từ khảo sát
   * 3.4. Biên bản phỏng vấn mẫu
   * 3.5. Bảng câu hỏi mở và các vấn đề cần xác nhận

   **PHẦN 4: ĐẶC TẢ YÊU CẦU HỆ THỐNG**
   * 4.1. Bảng tổng hợp yêu cầu chức năng
   * 4.2. Đặc tả chi tiết từng yêu cầu chức năng theo mẫu chuẩn
   * 4.3. Bảng tổng hợp yêu cầu phi chức năng
   * 4.4. Đặc tả chi tiết từng yêu cầu phi chức năng theo mẫu chuẩn

   **PHẦN 5: ĐẶC TẢ TÌNH HUỐNG SỬ DỤNG**
   * 5.1. SC-01: Bệnh nhân đặt lịch khám thành công
   * 5.2. SC-02: Khung giờ hoặc bác sĩ không còn khả dụng
   * 5.3. SC-03: Bệnh nhân đổi hoặc hủy lịch hẹn
   * 5.4. SC-04: Bác sĩ nghỉ ca đột xuất và xử lý hoàn tiền

   **PHẦN 6: QUẢN LÝ THAY ĐỔI YÊU CẦU**
   * 6.1. Bối cảnh và mô tả nghiệp vụ CR-01
   * 6.2. Bảng phân tích tác động toàn diện
   * 6.3. Nhận diện rủi ro phát sinh và biện pháp kiểm soát đề xuất
   * 6.4. Danh mục câu hỏi cần làm rõ thêm từ CR-01

   **PHẦN 7: BÁO CÁO KIỂM ĐỊNH YÊU CẦU**
   * 7.1. Tổ chức đánh giá chéo và 6 tiêu chí kiểm nghiệm chất lượng
   * 7.2. Bảng kết quả kiểm định chi tiết 27 vấn đề
   * 7.3. Bảng rà soát và chuyển đổi các thuật ngữ định tính mơ hồ

   **PHẦN 8: BỘ KỊCH BẢN KIỂM THỬ ĐẶC TẢ**
   * 8.1. Bộ kịch bản kiểm thử nghiệp vụ cơ sở
   * 8.2. Bộ kịch bản kiểm thử mở rộng và kiểm tra biên chi tiết
   
   **PHẦN 9: MA TRẬN TRUY VẾT YÊU CẦU**
   * 9.1. Danh mục nhu cầu nghiệp vụ gốc
   * 9.2. Bảng ma trận truy vết yêu cầu
   * 9.3. Bảng phân tích độ bao phủ và tác động tập trung của CR-01
   * 9.4. Ghi nhận khoảng trống phạm vi và định hướng giai đoạn 2

---

# PHẦN 1: BÀI TOÁN VÀ PHẠM VI HỆ THỐNG

### 1.1. Hiện trạng và phát biểu bài toán
* **Bối cảnh phòng khám An Tâm:** An Tâm là phòng khám đa khoa quy mô nhỏ. Đội ngũ y tế gồm 06 bác sĩ thuộc nhiều chuyên khoa khác nhau, tiếp nhận trung bình từ 80 đến 120 lượt bệnh nhân mỗi ngày, với 02 nhân viên tiếp nhận phụ trách tại quầy trong mỗi ca làm việc.
* **Ý kiến phản hồi từ các bên liên quan:**
  > *“Tôi muốn bệnh nhân đặt lịch nhanh, không phải gọi nhiều lần.”* — **Quản lý phòng khám (`STK-01`)**  
  > *“Tôi cần biết hôm nay ai đến khám và hồ sơ nào cần chuẩn bị.”* — **Bác sĩ (`STK-02`)**  
  > *“Lịch thay đổi liên tục; nếu sửa ở sổ thì đôi khi người khác không biết.”* — **Nhân viên tiếp nhận (`STK-03`)**  
  > *“Tôi muốn đổi lịch mà không phải đến tận nơi.”* — **Bệnh nhân (`STK-04`)**
* **Hiện trạng vận hành và các bất cập cốt lõi:**
  1. *Quy trình đăng ký thủ công, dễ gây quá tải tiếp nhận:* Bệnh nhân đặt hoặc đổi lịch hoàn toàn qua điện thoại; nhân viên tiếp nhận dò sổ giấy ghi chép tay. Với 80–120 lượt/ngày, 02 nhân viên quầy dễ quá tải, bệnh nhân phải chờ máy lâu hoặc gọi nhiều lần.
  2. *Dữ liệu lịch khám phân tán và thiếu đồng bộ:* Lịch hẹn chỉ lưu trên sổ giấy; khi điều chỉnh hoặc gạch xóa giữa các ca trực dễ gây lệch thông tin, dẫn tới nguy cơ trùng khung giờ hoặc nhầm lẫn hồ sơ bệnh nhân.
  3. *Xử lý biến động lịch bị động và tốn công sức:* Khi bác sĩ nghỉ đột xuất, nhân viên phải dò sổ và gọi điện thoại thủ công đến từng bệnh nhân, mất nhiều thời gian và dễ bỏ sót, khiến bệnh nhân vẫn đến phòng khám mà không được phục vụ.
  4. *Bác sĩ bị động trong khâu chuẩn bị chuyên môn:* Bác sĩ chỉ nhận danh sách khám trên giấy khi vào ca, không xem trước được thông tin bệnh nhân và triệu chứng ban đầu để chủ động chuẩn bị bệnh án cũ hoặc trang thiết bị chuyên khoa.
* **4 nhóm nội dung cần khảo sát làm rõ thêm:**
  1. Quy tắc phân bổ khung giờ khám và giới hạn số bệnh nhân tiếp nhận tối đa trong ca trực.
  2. Phân quyền xem và chỉnh sửa thông tin giữa các vai trò (Quản lý, Bác sĩ, Tiếp nhận).
  3. Phương án xử lý các tình huống nghiệp vụ đặc biệt: Bệnh nhân đến trễ, vắng mặt không báo trước hoặc ca cấp cứu/khám gấp.
  4. Các yêu cầu đo lường phi chức năng: Thời gian phản hồi, khả năng chịu tải đồng thời, bảo mật thông tin và thời hạn lưu trữ.
* **Phát biểu vấn đề cốt lõi:** Quy trình quản lý lịch khám và tiếp nhận bệnh nhân tại Phòng khám An Tâm hiện đang **phân tán, phụ thuộc hoàn toàn vào ghi chép sổ sách thủ công và liên lạc điện thoại**, dẫn đến sai lệch dữ liệu giữa các bộ phận, quá tải cho nhân viên quầy và làm giảm trải nghiệm của người bệnh.

### 1.2. Mục tiêu và giá trị kỳ vọng của hệ thống
Hệ thống phần mềm được xây dựng nhằm số hóa và tập trung hóa toàn bộ quy trình đặt lịch, tiếp nhận và điều phối ca khám:
* **Hỗ trợ bệnh nhân chủ động 24/7:** Cho phép bệnh nhân tự tra cứu bác sĩ, chuyên khoa, khung giờ trống và thực hiện đăng ký, đổi, hủy lịch trực tuyến trên môi trường web mà không cần phải gọi điện thoại hay đến trực tiếp quầy tiếp nhận.
* **Tập trung hóa dữ liệu thời gian thực:** Tạo ra một nguồn dữ liệu duy nhất và chính xác (Single Source of Truth), giúp bác sĩ, nhân viên tiếp nhận và quản lý đều theo dõi được trạng thái lịch hẹn đồng bộ ngay khi có cập nhật.
* **Nâng cao tính chủ động cho bác sĩ:** Hỗ trợ bác sĩ theo dõi danh sách bệnh nhân dự kiến đến khám theo từng ca trực kèm tóm tắt lý do khám để chuẩn bị chuyên môn từ sớm.
* **Tối ưu hóa năng suất làm việc của nhân viên tiếp nhận:** Giảm thiểu tối đa thao tác ghi chép thủ công trên sổ; hệ thống tự động khóa/mở khung giờ và hỗ trợ tiếp nhận nhanh tại quầy.
* **Tự động hóa xử lý sự cố đột xuất:** Khi bác sĩ nghỉ đột xuất, hệ thống tự động khóa ca trực, gửi thông báo hàng loạt qua SMS/Email đến 100% bệnh nhân bị ảnh hưởng và tự động thực hiện hoàn tiền viện phí trực tuyến (theo CR-01).

### 1.3. Bảng phân tích các bên liên quan

| Mã ID | Tên Stakeholder | Vai trò trong hệ thống | Nhu cầu chính | Mức độ ảnh hưởng |
| :---: | :--- | :--- | :--- | :---: |
| **STK-01** | **Quản lý phòng khám** | Quản lý vận hành chung, ban hành quy chế phòng khám và quyết định phạm vi đầu tư hệ thống. | Muốn bệnh nhân đặt lịch nhanh, giảm tải cuộc gọi hotline, nắm bắt báo cáo số lượng bệnh nhân theo ngày/ca và giám sát quy trình xử lý sự cố bác sĩ vắng mặt. | **Cao** |
| **STK-02** | **Bác sĩ** | Nhân sự y tế trực tiếp thực hiện khám bệnh, tư vấn và chẩn đoán điều trị. | Cần biết trước hôm nay những bệnh nhân nào sẽ đến khám trong ca trực, khung giờ cụ thể và triệu chứng ban đầu để chủ động chuẩn bị hồ sơ/trang thiết bị y tế. | **Cao** |
| **STK-03** | **Nhân viên tiếp nhận** | Tiếp đón bệnh nhân tại quầy lễ tân, hỗ trợ đặt lịch cho người không dùng web, check-in và xử lý ngoại lệ. | Cần xem và cập nhật lịch hẹn trên một giao diện thống nhất theo thời gian thực; thông tin sửa đổi phải đồng bộ tức thì, tránh nhầm lẫn giữa các nhân viên. | **Cao** |
| **STK-04** | **Bệnh nhân** | Khách hàng sử dụng dịch vụ khám chữa bệnh tại phòng khám. | Muốn tự tra cứu lịch bác sĩ, đặt lịch hẹn nhanh chóng, nhận tin nhắn xác nhận và có thể tự đổi hoặc hủy lịch từ xa mà không phải đến trực tiếp phòng khám. | **Rất cao** |
| **STK-05** | **Kế toán phòng khám** | Quản lý tài chính, đối soát viện phí và xử lý nghiệp vụ hoàn tiền (phát sinh từ `CR-01`). | Cần dữ liệu giao dịch tài chính chính xác (mã thanh toán, mã hoàn tiền, thời gian); nhận cảnh báo đối soát khi cổng thanh toán gặp sự cố timeout/lỗi. | **Trung bình** |
| **STK-06** | **Đối tác dịch vụ trung gian** *(Cổng thanh toán & Viễn thông)* | Đơn vị bên thứ ba cung cấp hạ tầng thanh toán điện tử (VNPay/MoMo) và SMS Brandname/OTP. | Yêu cầu tích hợp đúng chuẩn API/Webhook, tuân thủ an toàn giao dịch tài chính, đối soát chữ ký số và bảo mật thông tin liên lạc viễn thông. | **Trung bình** |

### 1.4. Phạm vi hệ thống
* **Trong phạm vi:**
  * Chức năng tra cứu chuyên khoa, bác sĩ và các khung giờ khám còn trống theo ngày/ca trực.
  * Đặt lịch khám trực tiếp tại phòng khám và đặt lịch khám trực tuyến từ xa theo CR-01.
  * Quy trình xác thực thông tin đăng ký và gửi tin nhắn SMS/Email thông báo xác nhận lịch hẹn.
  * Tra cứu, đổi khung giờ khám hoặc hủy lịch hẹn trực tuyến có bảo vệ bằng mã OTP gửi qua SMS.
  * Quản lý ca trực của bác sĩ: Khóa ca khi bác sĩ nghỉ đột xuất, tự động gửi thông báo đến bệnh nhân bị ảnh hưởng và tự động kích hoạt hoàn tiền trực tuyến (CR-01).
  * Quy tắc tự động mở lại khung giờ trống (giải phóng slot) khi bệnh nhân hủy lịch hợp lệ hoặc khi giao dịch thanh toán trực tuyến bị quá hạn.
* **Ngoài phạm vi:**
  1. *Quản lý kho dược và bán lẻ thuốc:* Hệ thống không bao gồm quản lý nhập/xuất kho thuốc, theo dõi hạn sử dụng thuốc và kê đơn bán thuốc điện tử (phòng khám đã có phần mềm quản lý nhà thuốc độc lập GPP) [G-09].
  2. *Quản lý chẩn đoán hình ảnh và xét nghiệm chuyên sâu:* Hệ thống không lưu trữ, truyền tải kết quả chụp X-quang, MRI hay kết quả phân tích mẫu xét nghiệm máu/sinh hóa.
  3. *Quản lý tài chính kế toán tổng thể & Tiền lương:* Không giải quyết bài toán kế toán thuế, tính toán chi phí vận hành doanh nghiệp, bảng lương bác sĩ/nhân viên hay xuất hóa đơn điện tử giá trị gia tăng (VAT).
  4. *Quản lý Hồ sơ bệnh án điện tử đầy đủ:* Hệ thống chỉ lưu trữ thông tin hành chính phục vụ tiếp nhận và tóm tắt triệu chứng ban đầu; không lưu trữ tiền sử bệnh chi tiết, diễn tiến phác đồ điều trị dài ngày [G-09].
  5. *Tiếp nhận khám cấp cứu nguy kịch:* Bệnh nhân cấp cứu trong tình trạng đe dọa tính mạng được chuyển thẳng vào phòng cấp cứu của cơ sở y tế theo quy trình cấp cứu thực tế, không qua hệ thống đặt lịch hẹn trước [G-03].

### 1.5. Bảng thuật ngữ nghiệp vụ và từ viết tắt

| Thuật ngữ / Viết tắt | Tên tiếng Anh | Định nghĩa nghiệp vụ chuẩn hóa |
| :--- | :--- | :--- |
| **Bệnh nhân** | Patient | Người đăng ký và sử dụng dịch vụ khám chữa bệnh tại phòng khám An Tâm. |
| **Bác sĩ** | Doctor / Physician | Bác sĩ chuyên khoa phụ trách khám bệnh, chẩn đoán và tư vấn y khoa. |
| **Nhân viên tiếp nhận** | Receptionist | Nhân viên tại quầy lễ tân phụ trách hướng dẫn, xác nhận thông tin và điều phối lượt khám. |
| **Khung giờ khám (Slot)** | Time Slot | Khoảng thời gian tiêu chuẩn cố định (15 phút [G-01]) được bố trí cho 01 lượt khám bệnh của bác sĩ. |
| **Lịch khám / Lịch hẹn** | Appointment | Bản ghi thông tin giao dịch đặt chỗ giữa một bệnh nhân và một bác sĩ tại một khung giờ cụ thể. |
| **Đặt lịch** | Booking | Thao tác người dùng tạo mới một bản ghi lịch hẹn trên hệ thống. |
| **Đổi lịch** | Reschedule | Thao tác thay đổi khung giờ khám đã đặt sang một khung giờ khả dụng khác của cùng bác sĩ. |
| **Hủy lịch** | Cancellation | Thao tác chấm dứt hiệu lực của lịch hẹn đã tạo (do bệnh nhân hoặc do phòng khám thực hiện). |
| **Ca làm việc (Ca trực)** | Shift | Khoảng thời gian làm việc trong ngày của bác sĩ (Ca sáng: 08:00–12:00, Ca chiều: 13:30–17:30). |
| **Tiếp nhận bệnh nhân** | Check-in | Thao tác ghi nhận và xử lý thông tin khi bệnh nhân có mặt thực tế tại phòng khám. |
| **Danh sách lịch khám** | Appointment List | Danh sách bệnh nhân dự kiến đến khám được sắp xếp theo bác sĩ và ca trực trong ngày. |
| **Hồ sơ bệnh nhân** | Patient Profile | Thông tin liên quan đến bệnh nhân phục vụ công tác tiếp nhận và khám bệnh ban đầu. |
| **Vắng mặt** | No-show | Tình trạng bệnh nhân đã đặt lịch nhưng không đến khám và không thông báo trước (sau ca trực sẽ tự động hủy [G-10]). |
| **Khám gấp** | Walk-in / Urgent | Bệnh nhân không hẹn trước, đến trực tiếp phòng khám và cần được bố trí ca khám phù hợp. |
| **Khám trực tuyến** | Telemedicine | Dịch vụ khám bệnh, tư vấn sức khỏe từ xa thông qua phòng họp video có kết nối mạng (CR-01). |
| **FR / NFR** | Functional / Non-Functional Req | Yêu cầu chức năng (chức năng phần mềm) / Yêu cầu phi chức năng (chất lượng vận hành). |
| **CR-01** | Change Request 01 | Yêu cầu thay đổi số 01 về việc triển khai dịch vụ Khám trực tuyến và Thanh toán điện tử. |
| **OTP** | One-Time Password | Mã mật khẩu dùng một lần (gồm 6 chữ số) gửi qua tin nhắn SMS nhằm xác thực danh tính người dùng. |

---

# PHẦN 2: MÔI TRƯỜNG VẬN HÀNH, GIẢ ĐỊNH VÀ PHỤ THUỘC

### 2.1. Môi trường vận hành kỹ thuật
* **Phía người dùng:** Ứng dụng web tương thích chuẩn Responsive, hoạt động mượt mà trên các trình duyệt hiện đại (Google Chrome, Apple Safari, Mozilla Firefox, Microsoft Edge) trên thiết bị di động (iOS, Android) và máy tính cá nhân.
* **Phía nội bộ phòng khám:**
  * Quầy lễ tân: Máy tính để bàn kết nối mạng nội bộ LAN ổn định (băng thông $\ge 50\text{ Mbps}$), kết nối máy in hóa đơn/phiếu số thứ tự nhiệt [G-08].
  * Phòng khám bác sĩ: Máy tính hoặc máy tính bảng kết nối Wi-Fi/LAN phòng khám, hỗ trợ webcam và micro để phục vụ khám trực tuyến (theo CR-01).
* **Hạ tầng máy chủ:**
  * Hệ điều hành máy chủ Linux (Ubuntu Server 22.04 LTS hoặc tương đương).
  * Cơ sở dữ liệu quan hệ (PostgreSQL 15+ hoặc MySQL 8.0+) hỗ trợ chuẩn giao dịch ACID và cơ chế Transaction Locking để chống trùng lịch hẹn.
  * Môi trường triển khai đám mây (Cloud Server) hoặc máy chủ nội bộ bảo mật, có chứng chỉ SSL/TLS (HTTPS) hợp lệ.

### 2.2. Danh mục giả định nghiệp vụ và kỹ thuật

| Mã ID | Nội dung Giả định nghiệp vụ & Kỹ thuật | Căn cứ phát sinh / Lý do chưa có số liệu | Mục chịu ảnh hưởng | Stakeholder cần xác nhận | Trạng thái |
| :---: | :--- | :--- | :---: | :---: | :---: |
| **G-01** | Thời lượng tiêu chuẩn 1 lượt khám là 15 phút. Mỗi ca trực 4 tiếng của 1 bác sĩ tiếp nhận tối đa 16 lượt khám hẹn trước (240 phút / 15 phút). | Đề bài chưa cho quy tắc phân bổ khung giờ và giới hạn số bệnh nhân. | Mục 4 (`FR-01`), Mục 5 (`SC-01`) | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | *Chờ xác nhận* |
| **G-02** | Bệnh nhân đăng ký bằng số điện thoại di động chính chủ hợp lệ tại Việt Nam (gồm 10 chữ số), có thể nhận tin nhắn SMS OTP và thông báo. | Bệnh nhân đặt lịch công khai qua web chưa có tài khoản định danh. | Mục 4 (`FR-02`), Mục 5 (`SC-01`) | Bệnh nhân (`STK-04`) | *Đã giả định* |
| **G-03** | Trường hợp cấp cứu nguy kịch đi thẳng vào phòng cấp cứu, không qua hệ thống đặt lịch hẹn trước. | Đề bài yêu cầu khảo sát phương án tiếp nhận ca khám gấp. | Mục 1.4 (Phạm vi), Mục 5 (Luồng ngoại lệ) | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | *Đã giả định* |
| **G-04** | Viện phí khám trực tuyến từ xa tạm tính minh họa là 150.000 VNĐ/lượt khám (theo CR-01). | Đề bài CR-01 chỉ yêu cầu thanh toán trước, không cho biểu phí cụ thể. | Mục 4 (`FR-11`), Mục 5 (`SC-01`), Mục 8 (`TC-05`) | Quản lý (`STK-01`), Kế toán (`STK-05`) | *Chờ xác nhận* |
| **G-05** | Thời gian tạm khóa giữ chỗ khung giờ khám online chờ hoàn tất thanh toán là 15 phút. Sau 15 phút không thanh toán thành công sẽ tự giải phóng slot. | Tránh tình trạng giữ chỗ ảo làm lãng phí khung giờ của bác sĩ theo CR-01. | Mục 4 (`FR-11`), Mục 5 (`SC-01`), Mục 8 (`TC-15`) | Quản lý (`STK-01`), Đối tác Cổng TT (`STK-06`) | *Đã giả định* |
| **G-06** | Bệnh nhân chỉ được tự đổi hoặc hủy lịch trên web trước giờ khám tối thiểu 2 tiếng (120 phút). Hủy trễ dưới 2 tiếng không được hủy tự động và không hoàn tiền online. | Đề bài yêu cầu khảo sát phương án hủy/đổi lịch để bảo vệ quyền lợi bác sĩ. | Mục 4 (`FR-05`), Mục 5 (`SC-03`), Mục 8 (`TC-03`, `TC-10`) | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | *Chờ xác nhận* |
| **G-07** | Mã xác thực SMS OTP cho thao tác tra cứu/hủy lịch có độ dài 6 chữ số, thời hạn hiệu lực 3 phút (180 giây), khóa phiên ngay sau lần nhập sai thứ 3. | Đảm bảo an toàn thông tin, ngăn chặn hành vi brute-force để sửa/hủy lịch của người khác. | Mục 4 (`NFR-03`), Mục 5 (`SC-03`), Mục 8 (`TC-09`) | Quản lý (`STK-01`), Chuyên gia ATTT | *Đã giả định* |
| **G-08** | Quầy tiếp nhận được trang bị máy tính kết nối LAN ổn định và máy in nhiệt để in phiếu số thứ tự tiếp nhận tại quầy. | Cơ sở vật chất tối thiểu để 02 nhân viên tiếp nhận vận hành tại quầy. | Mục 2.1, Mục 3.1 | Nhân viên tiếp nhận (`STK-03`) | *Đã giả định* |
| **G-09** | Hồ sơ bệnh án chuyên sâu và kê đơn/bán thuốc nằm ngoài phạm vi phần mềm. | Tránh phình to phạm vi dự án Mini-SRS của phòng khám đa khoa nhỏ. | Mục 1.4 (Phạm vi) | Quản lý phòng khám (`STK-01`) | *Đã giả định* |
| **G-10** | Bệnh nhân đến trễ quá 15 phút so với giờ hẹn bị chuyển trạng thái "Đến trễ" và xếp thứ tự khám sau các ca đến đúng giờ. | Đề bài yêu cầu khảo sát quy tắc xử lý bệnh nhân đến trễ. | Mục 3.4 (`Q-02`), Quy trình tiếp nhận | Bác sĩ (`STK-02`), Tiếp nhận (`STK-03`) | *Chờ xác nhận* |
| **G-11** | Nhân viên tiếp nhận chỉ được xem thông tin hành chính và triệu chứng tóm tắt, không được xem hoặc sửa chẩn đoán bệnh án của bác sĩ. | Đề bài yêu cầu khảo sát quyền xem và chỉnh sửa thông tin. | Mục 4 (`NFR-04`) | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | *Đã giả định* |
| **G-12** | Dữ liệu lịch hẹn và nhật ký giao dịch tài chính (thanh toán/hoàn tiền) được lưu trữ an toàn trên hệ thống tối thiểu 05 năm. | Đề bài yêu cầu khảo sát yêu cầu lưu trữ và bảo mật dữ liệu y tế. | Mục 4 (`NFR-06`), Mục 8 (`TC-14`) | Quản lý (`STK-01`), Kế toán (`STK-05`) | *Chờ xác nhận* |

### 2.3. Các dịch vụ phụ thuộc bên ngoài
1. **Dịch vụ Viễn thông & SMS Brandname:** Phụ thuộc vào API của nhà cung cấp dịch vụ SMS Brandname (Viettel/VNPT/eSMS) để gửi mã OTP xác thực và thông báo lịch hẹn đến số điện thoại bệnh nhân.
2. **Cổng thanh toán điện tử trung gian (theo CR-01):** Phụ thuộc vào kết nối API và cơ chế Webhook/IPN của cổng thanh toán điện tử (VNPay, MoMo, ZaloPay) để tiếp nhận trạng thái thanh toán và kích hoạt hoàn tiền tự động.
3. **Nền tảng gọi video trực tuyến (theo CR-01):** Phụ thuộc vào API bên thứ ba (Google Meet API / Zoom Video SDK) để sinh tự động đường dẫn phòng họp trực tuyến bảo mật phục vụ ca khám từ xa.

---

# PHẦN 3: KẾ HOẠCH & MINH CHỨNG KHẢO SÁT

### 3.1. Kỹ thuật thu thập yêu cầu lựa chọn
Nhóm áp dụng kết hợp hai kỹ thuật: **Phỏng vấn trực tiếp** và **Quan sát thực tế**.

| Kỹ thuật | Mục tiêu cụ thể | Đối tượng tham gia | Vai trò của đối tượng | Thời lượng | Cách thức ghi nhận |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Phỏng vấn trực tiếp** | Tìm hiểu quy trình vận hành hiện tại, các bất cập thực tế, quy tắc nghiệp vụ và mong muốn đối với phần mềm mới. | Quản lý phòng khám, 02 Bác sĩ đại diện, 02 Nhân viên tiếp nhận, 03 Bệnh nhân. | Cung cấp yêu cầu nghiệp vụ, nêu khó khăn thực tế và xác nhận tính khả thi. | 25–30 phút / phiên | Ghi chép biên bản phỏng vấn theo mẫu; ghi âm (khi được đồng ý). |
| **Quan sát thực tế** | Kiểm chứng các thao tác thực tế tại quầy, đo lường thời gian ghi sổ, tiếp nhận và phát hiện các vấn đề tiềm ẩn chưa được nói ra. | 02 Nhân viên tiếp nhận và các bệnh nhân tại sảnh chờ quầy lễ tân. | Thực hiện quy trình nghiệp vụ hàng ngày trong điều kiện tự nhiên. | 02 buổi (90 phút / buổi ca sáng đông bệnh nhân) | Ghi chép nhật ký quan sát, bấm giờ các bước thao tác và chụp ảnh mẫu sổ ghi chép (che thông tin cá nhân). |

### 3.2. Bộ câu hỏi khảo sát phân nhóm chuẩn hóa

#### Chủ đề A: Đặt lịch và tiếp nhận bệnh nhân
* **Câu hỏi mở:**
  1. *Anh/Chị có thể mô tả chi tiết quy trình từ khi bệnh nhân gọi điện đặt lịch hẹn đến khi hoàn tất ghi nhận vào sổ sách hiện tại?*
  2. *Trong quy trình tiếp nhận và quản lý lịch hiện nay, thao tác hoặc bước nào thường gây mất nhiều thời gian nhất hoặc dễ dẫn đến sai sót nhất?*
  3. *Khi tiếp nhận một bệnh nhân mới tại quầy, nhân viên tiếp nhận hiện đang thu thập những thông tin hành chính và triệu chứng nào?*
  4. *Bệnh nhân thường phản ánh những khó khăn hoặc bất tiện gì nhất khi muốn thay đổi khung giờ khám hoặc hủy lịch hẹn qua điện thoại?*
* **Câu hỏi đóng:**

  5. *Bệnh nhân có được phép chỉ định lựa chọn bác sĩ cụ thể theo ý muốn khi đặt lịch khám hay không?*  
     $\rightarrow$ **[ ] Có** | **[ ] Không**

  6. *Bệnh nhân có được quyền tự đổi hoặc hủy lịch hẹn đã đặt trên hệ thống không?*  
     $\rightarrow$ **[ ] Có** | **[ ] Không**


  7. *Sau khi đặt lịch thành công, hệ thống có bắt buộc gửi tin nhắn SMS xác nhận lịch hẹn kèm mã tra cứu đến số điện thoại bệnh nhân không?*  
     $\rightarrow$ **[ ] Có** | **[ ] Không**

#### Chủ đề B: Quản lý ca trực và lịch làm việc của bác sĩ
* **Câu hỏi mở:**

  8. *Bác sĩ hiện kiểm tra và theo dõi lịch khám trong ngày của mình bằng cách nào?*

  9. *Bác sĩ cần nắm được những thông tin cụ thể nào của một lịch khám để chuẩn bị chuyên môn và bệnh án trước ca trực?*
  
  10. *Khi bác sĩ thay đổi lịch làm việc hoặc nghỉ đột xuất, phòng khám hiện đang xử lý các lịch hẹn đã có của bệnh nhân như thế nào?*
* **Câu hỏi đóng:**

  11. *Bác sĩ có được phép tự cập nhật hoặc khóa lịch làm việc của mình trên hệ thống mà không cần quản lý phê duyệt không?*  
      $\rightarrow$ **[ ] Có** | **[ ] Không**

  12. *Hệ thống có cần ngăn việc hai bệnh nhân được đặt vào cùng một khung giờ của một bác sĩ (chống trùng lịch) không?*  
      $\rightarrow$ **[ ] Có** | **[ ] Không**

  13. *Khi lịch làm việc của bác sĩ thay đổi, bệnh nhân có cần được hệ thống tự động gửi thông báo không?*  
      $\rightarrow$ **[ ] Có** | **[ ] Không**

  14. *Đối với hình thức khám trực tuyến (theo CR-01), bệnh nhân có bắt buộc phải hoàn tất thanh toán 100% tiền viện phí trước thì lịch hẹn mới được xác nhận chính thức không?*  
      $\rightarrow$ **[ ] Có** | **[ ] Không**

#### Chủ đề C: Câu hỏi làm rõ ngoại lệ và yêu cầu phi chức năng
* **Ngoại lệ nghiệp vụ:**

  15. *Nếu bác sĩ nghỉ đột xuất nhưng đã có bệnh nhân đặt lịch hẹn trước thì hệ thống phải khóa ca và xử lý các lịch hẹn đó ra sao?*

  16. *Nếu hai nhân viên hoặc hai bệnh nhân cùng bấm đặt một khung giờ gần như cùng một lúc thì hệ thống xử lý tranh chấp thế nào?*

  17. *Nếu bệnh nhân đến trễ quá 15 phút hoặc không đến khám thì lịch hẹn cần được xử lý và cập nhật trạng thái như thế nào?*

  18. *Nếu bệnh nhân muốn đổi lịch nhưng toàn bộ khung giờ mong muốn trong ngày của bác sĩ đã kín chỗ thì hệ thống cần hỗ trợ gợi ý ra sao?*

* **Yêu cầu phi chức năng:**

  19. *Sau khi lịch khám được tạo mới hoặc thay đổi, thông tin cập nhật cần xuất hiện trên màn hình của bác sĩ/tiếp nhận trong thời gian tối đa bao lâu?* (Hiệu năng và thời gian phản hồi).

  20. *Những vai trò nào (Quản lý, Bác sĩ, Lễ tân, Bệnh nhân) được phép xem, tạo, sửa hoặc hủy lịch khám và thông tin cá nhân?* (Bảo mật và phân quyền truy cập).

  21. *Nếu xảy ra sự cố gián đoạn kết nối mạng trong quá trình sử dụng, hệ thống cần đảm bảo những chức năng nào và khả năng phục hồi dữ liệu ra sao?* (Độ tin cậy và khả năng lưu trữ).

---

### 3.3. Kết quả nghiệp vụ kỳ vọng thu được từ khảo sát
Sau khi hoàn tất quá trình thu thập yêu cầu, nhóm xác định được các đầu ra nghiệp vụ then chốt:
* **Quy trình nghiệp vụ thực tế:** Xác định luồng vận hành chuẩn từ lúc tra cứu, đặt lịch, tiếp nhận tại quầy đến khi kết thúc ca khám tại Phòng khám An Tâm.
* **Yêu cầu chức năng hoàn chỉnh:** Đặc tả rõ các yêu cầu chức năng cho tra cứu, đặt lịch, đổi/hủy lịch, quản lý lịch bác sĩ và tích hợp cổng thanh toán online theo CR-01.
* **Quy tắc nghiệp vụ cốt lõi:** Thống nhất các quy tắc phân bổ khung giờ 15 phút, ngăn chặn trùng lịch theo SĐT, mốc giới hạn đổi/hủy trước 120 phút và cơ chế giữ chỗ 15 phút.
* **Kịch bản xử lý ngoại lệ:** Xác lập phương án tự động xử lý khi bác sĩ nghỉ đột xuất, giải phóng khung giờ và xử lý lỗi cổng thanh toán/mạng SMS.
* **Yêu cầu phi chức năng có thể kiểm chứng:** Xác lập chỉ số định lượng về thời gian phản hồi $\le 2\text{s}$, tải đồng thời $\ge 30$ phiên, độ sẵn sàng Uptime $\ge 99,5\%$ và cơ chế xác thực OTP 180s.

---

### 3.4. Biên bản phỏng vấn mẫu
* **Mã biên bản:** `IV-STK01-01`
* **Thời gian thực hiện:** 09:00 – 09:40, ngày 25/09/2026.
* **Địa điểm:** Văn phòng Ban Quản lý Phòng khám Đa khoa An Tâm.
* **Người phỏng vấn:** Cao Xuân Dương (BA - Nhóm 18).
* **Người được phỏng vấn:** Đại diện Ban Quản lý Phòng khám Đa khoa An Tâm (`STK-01`).
* **Nguyên tắc kỹ thuật yêu cầu áp dụng:** Tách bạch 100% giữa **Dữ kiện đề bài đã cho (Ground Truth Facts)** và **Nội dung chưa có câu trả lời**. Tuyệt đối không tự suy đoán hoặc bịa câu trả lời của stakeholder; các thông tin còn thiếu được ghi nhận thành **[Giả định nghiệp vụ G-xx]** hoặc **[Câu hỏi mở Q-xx]** để stakeholder phê duyệt chính thức.
* **Tóm tắt nội dung ghi nhận theo phiên làm việc:**
  1. *Dữ kiện đề bài đã xác nhận:* Phòng khám đa khoa quy mô nhỏ gồm 06 bác sĩ thuộc nhiều chuyên khoa, tiếp nhận 80–120 lượt bệnh nhân/ngày, 02 nhân viên tiếp nhận/ca. Đặt lịch hiện qua điện thoại và ghi sổ. Phát biểu chính thức của Quản lý: *"Tôi muốn bệnh nhân đặt lịch nhanh, không phải gọi nhiều lần."* $\rightarrow$ Giải pháp: Xây dựng hệ thống web đặt lịch trực tuyến 24/7, đồng bộ dữ liệu thời gian thực.
  2. *Về quy tắc phân bổ khung giờ (Chưa có số liệu đề bài):* Tạm thời áp dụng **[Giả định G-01]** thời lượng chuẩn 15 phút/lượt khám; mỗi ca trực 4 tiếng của 1 bác sĩ nhận tối đa 16 lượt hẹn trước; chuyển giao câu hỏi `Q-01` để Ban Quản lý xác nhận số liệu chốt.
  3. *Về chính sách đổi/hủy lịch (Chưa có số liệu đề bài):* Tạm thời áp dụng **[Giả định G-06]** cho phép bệnh nhân tự đổi/hủy trực tuyến trước giờ khám tối thiểu 120 phút (2 tiếng) có xác thực OTP; dưới 120 phút phải liên hệ trực tiếp quầy; chuyển giao câu hỏi `Q-03` để Ban Quản lý ban hành quy chế.
  4. *Về quy trình xử lý bác sĩ nghỉ đột xuất:* Hiện trạng quầy tiếp nhận phải gọi điện thủ công từng người rất dễ sai sót; hệ thống mới yêu cầu chức năng đóng ca khẩn cấp dành cho Quản trị viên (`FR-08`), tự động gửi tin nhắn SMS Brandname/Email xin lỗi đồng loạt đến 100% bệnh nhân trong ca (`FR-09`) và kích hoạt hoàn tiền tự động cho ca khám online (`FR-12`).
  5. *Về khám trực tuyến và thanh toán trước (phát sinh từ CR-01):* Áp dụng **[Giả định G-04]** mức viện phí tạm tính 150.000 VNĐ; **[Giả định G-05]** tạm khóa giữ chỗ 15 phút; nếu bác sĩ hủy ca thì hoàn tiền 100%; chuyển giao các câu hỏi `QA-Q01` đến `QA-Q05` để Quản lý và đối tác Cổng thanh toán chốt phương án vận hành.
*(Chi tiết toàn văn biểu mẫu phỏng vấn kỹ thuật và nhật ký quan sát thực địa được lưu trữ tại file minh chứng: `minh_chung/Bien_ban_phong_van_va_nhat_ky_quan_sat.md`).*

---

### 3.5. Bảng câu hỏi mở và các vấn đề cần xác nhận

| Mã | Nội dung nghiệp vụ cần khảo sát thêm | Giả định tạm thời áp dụng | Người chịu trách nhiệm xác nhận | Phần ảnh hưởng trong hệ thống |
| :---: | :--- | :--- | :---: | :---: |
| **Q-01** | Quy tắc phân bổ khung giờ chuẩn và giới hạn số lượt khám tối đa của từng bác sĩ trong mỗi ca trực. | Áp dụng `G-01`: 15 phút/lượt; tối đa 16 lượt/ca 4 tiếng. | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | `FR-01`, `SC-01`, Quy trình xếp lịch |
| **Q-02** | Quy trình chuẩn xử lý bệnh nhân đến trễ hẹn quá 15 phút hoặc bệnh nhân không đến khám. | Áp dụng `G-10`: Trễ quá 15 phút chuyển xuống cuối ca trực; vắng mặt không báo trước sẽ bị hủy ca sau khi ca trực kết thúc. | Quản lý (`STK-01`), Tiếp nhận (`STK-03`) | Quy trình tiếp nhận, Thống kê ca khám |
| **Q-03** | Chính sách hoàn tiền cho bệnh nhân khi tự hủy lịch khám trực tuyến trước giờ khám (CR-01). | Đề bài CR-01 chỉ bắt buộc hoàn tiền khi bác sĩ hủy. Tạm thời giả định: Bệnh nhân tự hủy hợp lệ $\ge 2$ tiếng được hoàn tiền tự động; hủy trễ $< 2$ tiếng không hỗ trợ hoàn tiền. | Quản lý (`STK-01`), Kế toán (`STK-05`) | `FR-05`, `FR-12`, `SC-03` |
| **Q-04** | Biểu phí dịch vụ khám bệnh trực tuyến từ xa chính thức áp dụng. | Áp dụng `G-04`: Minh họa mức phí 150.000 VNĐ/lượt khám online. | Quản lý (`STK-01`), Kế toán (`STK-05`) | `FR-11`, `SC-01`, `TC-05` |
| **Q-05** | Thời gian lưu trữ tối thiểu bắt buộc đối với dữ liệu lịch hẹn và nhật ký giao dịch tài chính. | Áp dụng `G-12`: Tạm lưu trữ an toàn tối thiểu 05 năm. | Quản lý (`STK-01`), Kế toán (`STK-05`) | `NFR-06`, `TC-14` |

---

# PHẦN 4: ĐẶC TẢ YÊU CẦU HỆ THỐNG

### 4.1. Bảng tổng hợp yêu cầu chức năng

| Mã ID | Tên chức năng tóm tắt | Nguồn gốc | Độ ưu tiên | Phiên bản |
| :---: | :--- | :---: | :---: | :---: |
| **FR-01** | Tra cứu chuyên khoa, bác sĩ và khung giờ khám khả dụng | Bệnh nhân / `SC-01` | **Must** | 1.0 |
| **FR-02** | Đăng ký thông tin và tạo lịch khám mới | Bệnh nhân / `SC-01` | **Must** | 1.0 |
| **FR-03** | Xác nhận và thông báo lịch hẹn (Điều kiện thanh toán trực tuyến) | Bệnh nhân / Quản lý / CR-01 | **Must** | 1.1 |
| **FR-04** | Tra cứu và xác thực thông tin lịch hẹn bằng SMS OTP | Bệnh nhân / `SC-03` | **Must** | 1.0 |
| **FR-05** | Đổi khung giờ hoặc hủy lịch hẹn trực tuyến | Bệnh nhân / `SC-03` | **Must** | 1.0 |
| **FR-06** | Kiểm tra và xác thực tính hợp lệ của dữ liệu đăng ký | Tiếp nhận / `SC-01` | **Must** | 1.0 |
| **FR-07** | Tự động giải phóng khung giờ sau khi hủy lịch | Tiếp nhận / `SC-03` | **Must** | 1.0 |
| **FR-08** | Khóa ca trực khẩn cấp khi bác sĩ nghỉ đột xuất | Quản lý / `SC-04` | **Must** | 1.0 |
| **FR-09** | Tự động gửi thông báo khi lịch bị thay đổi/hủy bởi phòng khám | Quản lý / Bệnh nhân / `SC-04` | **Must** | 1.0 |
| **FR-10** | Ngăn chặn đặt trùng lịch hẹn trên cùng một khung giờ | Bệnh nhân / Tiếp nhận / `SC-01` | **Must** | 1.0 |
| **FR-11** | Bắt buộc thanh toán online trước cho lịch khám trực tuyến | Quản lý / CR-01 | **Must** | 1.1 |
| **FR-12** | Tự động hoàn tiền 100% khi bác sĩ hủy lịch khám online | Quản lý / CR-01 | **Must** | 1.1 |

---

### 4.2. Đặc tả chi tiết từng Yêu cầu Chức năng theo mẫu chuẩn

#### FR-01 · Tra cứu chuyên khoa, bác sĩ và khung giờ khám

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-01** | Chức năng | Bệnh nhân (`STK-04`) / `SC-01` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh bệnh nhân truy cập vào hệ thống đặt lịch, hệ thống phải cho phép bệnh nhân lựa chọn hình thức khám (Trực tiếp hoặc Trực tuyến), chuyên khoa, danh sách bác sĩ tương ứng và hiển thị lịch làm việc cùng các khung giờ còn trống (chuẩn hóa 15 phút/lượt, tối đa 16 lượt/ca [G-01], ở trạng thái "Khả dụng") của bác sĩ đã chọn trong tuần.
* **Lý do:** Giúp bệnh nhân chủ động nắm bắt thời gian biểu của bác sĩ và tự chọn thời điểm khám phù hợp, giảm bớt cuộc gọi hỏi thông tin đến lễ tân.
* **Tiêu chí kiểm chứng:** Khi người dùng chọn chuyên khoa và bác sĩ có lịch làm việc, hệ thống hiển thị danh sách các khung giờ ở trạng thái "Khả dụng" trong vòng $\le 2$ giây; các khung giờ đã có người đặt hoặc bị quản lý khóa tuyệt đối không hiển thị ở trạng thái có thể bấm đặt chỗ.

#### FR-02 · Đăng ký thông tin và tạo lịch khám

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-02** | Chức năng | Bệnh nhân (`STK-04`) / `SC-01` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh bệnh nhân đã chọn được một khung giờ khám còn trống, hệ thống phải cung cấp biểu mẫu để bệnh nhân nhập thông tin đăng ký bắt buộc gồm: Họ và tên, Số điện thoại liên hệ (10 chữ số hợp lệ tại Việt Nam [G-02]), Ngày tháng năm sinh, Giới tính và Mô tả tóm tắt triệu chứng/lý do khám bệnh ban đầu, sau đó ghi nhận bản ghi lịch hẹn vào cơ sở dữ liệu.
* **Lý do:** Thu thập đầy đủ dữ liệu hành chính và triệu chứng sơ bộ của bệnh nhân để phục vụ tiếp nhận và giúp bác sĩ chuẩn bị trước ca khám.
* **Tiêu chí kiểm chứng:** Khi bệnh nhân nhập đầy đủ các trường dữ liệu hợp lệ và bấm xác nhận, hệ thống tạo thành công bản ghi lịch hẹn mới trong cơ sở dữ liệu với trạng thái "Đã đặt" (đối với khám trực tiếp) hoặc "Chờ thanh toán" (đối với khám online), đồng thời khóa khung giờ đã chọn sang trạng thái không khả dụng trên giao diện người dùng.

#### FR-03 · Xác nhận và gửi thông báo lịch hẹn

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-03** | Chức năng | Bệnh nhân (`STK-04`), Quản lý (`STK-01`) / CR-01 | Must | 1.1 |

* **Mô tả:** Trong bối cảnh lịch hẹn được ghi nhận thành công, hệ thống phải tự sinh một mã lịch hẹn duy nhất (định dạng `AT-XXXXXX`) và tự động kích hoạt tiến trình gửi tin nhắn SMS Brandname / Email thông báo xác nhận chứa đầy đủ: Mã lịch hẹn, Tên bệnh nhân, Bác sĩ, Chuyên khoa, Thời gian khám và Địa điểm/Link khám. Đối với lịch khám trực tuyến, hệ thống chỉ được phép gửi xác nhận sau khi nhận được tín hiệu phản hồi giao dịch thanh toán thành công từ cổng thanh toán điện tử.
* **Lý do:** Cung cấp bằng chứng đặt chỗ chính thức cho bệnh nhân và ngăn chặn việc xác nhận nhầm cho các ca khám online chưa hoàn tất thanh toán.
* **Tiêu chí kiểm chứng:** Lịch khám trực tiếp: Sinh mã `AT-XXXXXX`, chuyển trạng thái "Đã xác nhận" và đẩy tin nhắn vào hàng đợi gửi SMS trong vòng $\le 30$ giây. Lịch khám online: Chỉ gửi SMS/Email xác nhận khi nhận Webhook thanh toán thành công; nếu thanh toán thất bại thì tuyệt đối không gửi tin nhắn xác nhận.

#### FR-04 · Tra cứu và xác thực thông tin lịch hẹn

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-04** | Chức năng | Bệnh nhân (`STK-04`) / `SC-03` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh bệnh nhân muốn kiểm tra hoặc thay đổi lịch hẹn đã đặt, hệ thống phải cho phép bệnh nhân tra cứu bằng cách nhập Mã lịch hẹn và Số điện thoại đăng ký, sau đó bắt buộc phải vượt qua bước xác thực bằng mã OTP gồm 6 chữ số gửi về số điện thoại trước khi hiển thị chi tiết thông tin ca khám.
* **Lý do:** Cho phép người dùng quản lý lịch khám từ xa nhưng vẫn đảm bảo tính bảo mật và quyền riêng tư dữ liệu y tế, ngăn người lạ can thiệp vào lịch hẹn.
* **Tiêu chí kiểm chứng:** Khi người dùng nhập đúng cặp Mã lịch hẹn và Số điện thoại khớp trong CSDL, hệ thống phát sinh mã OTP 6 chữ số có hiệu lực trong 180 giây [G-07]; chỉ khi nhập đúng mã OTP thì thông tin chi tiết lịch khám mới được hiển thị. Nhập sai quá 3 lần sẽ tự động khóa phiên xác thực.

#### FR-05 · Đổi khung giờ hoặc hủy lịch hẹn trực tuyến

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-05** | Chức năng | Bệnh nhân (`STK-04`) / `SC-03` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh bệnh nhân đã xác thực thành công vào màn hình quản lý lịch hẹn, hệ thống phải cho phép bệnh nhân thực hiện đổi sang một khung giờ khám còn trống khác của cùng bác sĩ hoặc bấm hủy lịch hẹn, với điều kiện thời gian thực hiện phải cách giờ hẹn khám tối thiểu 120 phút [G-06].
* **Lý do:** Giúp bệnh nhân chủ động điều chỉnh kế hoạch cá nhân, đồng thời bảo vệ lịch làm việc của bác sĩ không bị hủy đột ngột sát giờ.
* **Tiêu chí kiểm chứng:** Nếu thời gian từ thời điểm bấm đổi/hủy đến giờ hẹn khám $\ge 120$ phút [G-06]: Hệ thống thực thi đổi khung giờ (cập nhật giờ mới, khóa slot mới, giải phóng slot cũ) hoặc hủy lịch (chuyển trạng thái sang "Đã hủy bởi bệnh nhân", giải phóng slot cũ) và gửi SMS xác nhận. Nếu thời gian còn lại $< 120$ phút: Hệ thống từ chối cho phép tự thao tác trên web, hiển thị thông báo hướng dẫn bệnh nhân liên hệ trực tiếp hotline lễ tân phòng khám để được hỗ trợ thủ công.

#### FR-06 · Kiểm tra và xác thực tính hợp lệ của dữ liệu đăng ký

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-06** | Chức năng | Nhân viên tiếp nhận (`STK-03`) / `SC-01` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh bệnh nhân gửi thông tin biểu mẫu đặt lịch hẹn, hệ thống phải thực hiện kiểm tra tính đầy đủ và đúng định dạng của toàn bộ các trường thông tin bắt buộc trước khi ghi nhận dữ liệu vào máy chủ.
* **Lý do:** Ngăn chặn các dữ liệu rác, thiếu số điện thoại hoặc sai định dạng làm ảnh hưởng đến khả năng liên hệ và tiếp nhận bệnh nhân.
* **Tiêu chí kiểm chứng:** Nếu bệnh nhân bỏ trống trường bắt buộc (Họ tên, SĐT) hoặc nhập số điện thoại không đúng định dạng 10 chữ số tại Việt Nam [G-02], hệ thống chặn không cho gửi form, đánh dấu đỏ trường vi phạm và hiển thị câu thông báo lỗi cụ thể ngay dưới trường dữ liệu đó.

#### FR-07 · Tự động giải phóng khung giờ sau khi hủy lịch

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-07** | Chức năng | Nhân viên tiếp nhận (`STK-03`) / `SC-03` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh một lịch hẹn được hủy hợp lệ bởi bệnh nhân, hệ thống phải tự động cập nhật trạng thái của khung giờ khám tương ứng trở lại trạng thái "Khả dụng" trên toàn hệ thống, với điều kiện ca trực của bác sĩ tại thời điểm đó vẫn đang mở bình thường và không bị khóa bởi phòng khám [VR-10].
* **Lý do:** Tối ưu hóa công suất phục vụ của phòng khám, giúp các bệnh nhân khác có cơ hội đặt chỗ vào khung giờ vừa được giải phóng.
* **Tiêu chí kiểm chứng:** Ngay sau khi lệnh hủy lịch hoàn tất thành công trong CSDL, khung giờ cũ chuyển từ trạng thái "Không khả dụng" sang "Khả dụng" trên giao diện đặt lịch công khai; các người dùng khác truy cập trang có thể nhìn thấy và bấm chọn khung giờ này để đặt lịch bình thường.

#### FR-08 · Khóa ca trực khẩn cấp khi bác sĩ nghỉ đột xuất

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-08** | Chức năng | Quản lý phòng khám (`STK-01`) / `SC-04` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh bác sĩ có lịch làm việc phát sinh sự cố đột xuất không thể tiếp tục khám bệnh, hệ thống phải cung cấp chức năng dành riêng cho tài khoản Quản trị viên (Admin) cho phép báo nghỉ đột xuất và đóng toàn bộ ca trực của bác sĩ, khóa các khung giờ chưa đặt và chuyển các lịch hẹn bị ảnh hưởng sang trạng thái "Đã hủy bởi phòng khám do bác sĩ vắng mặt".
* **Lý do:** Chấm dứt tình trạng tiếp nhận thêm lịch hẹn cho bác sĩ đã vắng mặt và làm căn cứ để kích hoạt quy trình khắc phục sự cố tập trung.
* **Tiêu chí kiểm chứng:** Sau khi Quản lý xác nhận đóng ca trên giao diện điều hành: 100% khung giờ của ca trực chuyển sang trạng thái "Đã khóa do bác sĩ nghỉ đột xuất"; 100% lịch hẹn thuộc ca trực chuyển sang trạng thái "Đã hủy bởi phòng khám do bác sĩ vắng mặt".

#### FR-09 · Tự động gửi thông báo khi lịch khám bị thay đổi hoặc hủy bởi phòng khám

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-09** | Chức năng | Quản lý (`STK-01`), Bệnh nhân (`STK-04`) / `SC-04` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh Quản lý phòng khám thực hiện đóng ca trực đột xuất (theo `FR-08`), hệ thống phải tự động kích hoạt tiến trình tạo và gửi tin nhắn SMS Brandname / Email thông báo xin lỗi đồng loạt đến 100% bệnh nhân có lịch hẹn bị ảnh hưởng, kèm thông tin hướng dẫn đặt lại lịch hoặc tra cứu đối soát hoàn tiền.
* **Lý do:** Thay thế hoàn toàn thao tác gọi điện thoại thủ công từng người của nhân viên lễ tân, thông báo kịp thời cho bệnh nhân để họ không di chuyển đến phòng khám trong vô vọng.
* **Tiêu chí kiểm chứng:** Hệ thống tạo và đẩy lệnh gửi tin nhắn đến 100% số điện thoại của bệnh nhân có lịch bị hủy; ghi nhận nhật ký kết quả gửi tin (Thành công / Thất bại). Trường hợp gửi tin thất bại do lỗi mạng viễn thông, hệ thống đánh dấu cờ để hiển thị vào danh sách nhắc nhân viên gọi điện đối soát thủ công.

#### FR-10 · Ngăn chặn đặt trùng lịch hẹn trên cùng một khung giờ

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-10** | Chức năng | Bệnh nhân (`STK-04`), Tiếp nhận (`STK-03`) / `SC-01` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh tiếp nhận yêu cầu đặt lịch hẹn mới, hệ thống phải thực hiện quét đối chiếu cơ sở dữ liệu trước khi lưu và từ chối tạo lịch nếu phát hiện số điện thoại của bệnh nhân đã có một lịch hẹn khác còn hiệu lực trong cùng một khoảng thời gian khám bệnh.
* **Lý do:** Ngăn chặn tình trạng một người đặt giữ nhiều chỗ cùng lúc ở các bác sĩ khác nhau hoặc spam dữ liệu lịch hẹn gây sai lệch công suất phục vụ.
* **Tiêu chí kiểm chứng:** Khi người dùng nhập số điện thoại đã tồn tại lịch hẹn ở trạng thái "Đã đặt" hoặc "Đã xác nhận" trong cùng khung giờ, hệ thống từ chối lưu bản ghi, không gửi SMS mới và hiển thị thông báo: *"Số điện thoại này đã có lịch hẹn trong khung giờ được chọn. Vui lòng kiểm tra lại!"*.

#### FR-11 · Bắt buộc thanh toán trực tuyến trước cho dịch vụ khám từ xa

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-11** | Chức năng | Quản lý phòng khám (`STK-01`) / CR-01 | Must | 1.1 |

* **Mô tả:** Trong bối cảnh bệnh nhân lựa chọn hình thức khám trực tuyến theo CR-01, hệ thống phải tích hợp cổng thanh toán điện tử (VNPay/MoMo), tạm khóa giữ chỗ khung giờ trong tối đa 15 phút [G-05] và chỉ chuyển trạng thái lịch hẹn sang "Đã xác nhận" sau khi nhận được thông điệp giao dịch thanh toán thành công (Webhook/IPN) từ cổng thanh toán.
* **Lý do:** Đảm bảo bệnh nhân cam kết nghiêm túc khi đăng ký khám từ xa, ngăn chặn việc đặt lịch ảo làm lãng phí thời gian trực trực tuyến của bác sĩ.
* **Tiêu chí kiểm chứng:** Bệnh nhân chọn khám trực tuyến: Hệ thống tạm giữ khung giờ và chuyển hướng sang cổng thanh toán. Thanh toán thành công trong vòng 15 phút: Cập nhật "Đã thanh toán", chuyển lịch sang "Đã xác nhận", sinh đường link khám online và gửi SMS xác nhận. Quá hạn 15 phút không thanh toán [G-05]: Tiến trình nền tự động quét, hủy đơn đặt và giải phóng khung giờ về trạng thái "Khả dụng".

#### FR-12 · Tự động hoàn tiền khi bác sĩ hủy ca trực tuyến

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **FR-12** | Chức năng | Quản lý (`STK-01`), Kế toán (`STK-05`) / CR-01 | Must | 1.1 |

* **Mô tả:** Trong bối cảnh Quản lý phòng khám kích hoạt lệnh đóng ca trực của bác sĩ mà trong ca đó có các lịch khám trực tuyến đã hoàn tất thanh toán trước, hệ thống phải tự động phát lệnh gọi API sang cổng thanh toán trung gian để hoàn trả 100% tiền viện phí đã thu về tài khoản/thẻ ban đầu của bệnh nhân, đồng thời gửi tin nhắn SMS thông báo minh bạch.
* **Lý do:** Bảo vệ quyền lợi tài chính hợp pháp của người bệnh khi dịch vụ y tế bị hủy bỏ do nguyên nhân chủ quan từ phía phòng khám hoặc bác sĩ.
* **Tiêu chí kiểm chứng:** Hệ thống tự động lọc ra các lịch hẹn online trong ca có trạng thái giao dịch là "Đã thanh toán". Tự động phát lệnh gọi API hoàn tiền 100% số tiền viện phí (VD: 150.000 VNĐ [G-04]) sang cổng thanh toán tương ứng trong vòng $\le 30$ giây. Cập nhật bản ghi "Đã hoàn tiền", lưu mã đối soát và gửi SMS Brandname thông báo rõ ràng cho bệnh nhân. Nếu cổng thanh toán bị timeout hoặc trả về mã lỗi: Hệ thống tự động chuyển giao dịch sang trạng thái "Chờ xử lý hoàn tiền thủ công" và hiển thị cảnh báo đỏ trên màn hình Quản lý để kế toán (`STK-05`) đối soát thủ công.

---

### 4.3. Bảng tổng hợp yêu cầu phi chức năng

| Mã ID | Tên yêu cầu phi chức năng | Phân nhóm chất lượng | Nguồn gốc | Độ ưu tiên | Phiên bản |
| :---: | :--- | :---: | :---: | :---: | :---: |
| **NFR-01** | Thời gian phản hồi thao tác tra cứu và đặt lịch | **Hiệu năng** | Nhu cầu hệ thống / `[Giả định]` | **Must** | 1.0 |
| **NFR-02** | Khả năng chịu tải đồng thời trong ca cao điểm | **Hiệu năng** | Quy mô phòng khám / `[Giả định]` | **Should** | 1.0 |
| **NFR-03** | Xác thực hai lớp bằng SMS OTP khi quản lý lịch | **Bảo mật** | Bệnh nhân / `SC-03` | **Must** | 1.0 |
| **NFR-04** | Phân quyền truy cập dữ liệu dựa trên vai trò (RBAC) | **Bảo mật** | Quản lý / Bác sĩ / Tiếp nhận | **Must** | 1.0 |
| **NFR-05** | Mức độ sẵn sàng phục vụ của hệ thống (Uptime) | **Độ sẵn sàng** | Vận hành / `[Giả định]` | **Should** | 1.0 |
| **NFR-06** | Lưu trữ an toàn & bảo toàn dữ liệu lịch và giao dịch | **Lưu trữ** | Quản lý phòng khám / CR-01 | **Must** | 1.1 |

---

### 4.4. Đặc tả chi tiết từng Yêu cầu Phi chức năng theo mẫu chuẩn

#### NFR-01 · Thời gian phản hồi của các thao tác thông thường

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **NFR-01** | Phi chức năng (Hiệu năng) | Dữ kiện hệ thống [Giả định] | Must | 1.0 |

* **Mô tả:** Trong bối cảnh người dùng thao tác tra cứu và đặt lịch, hệ thống phải phản hồi các thao tác tra cứu chuyên khoa, bác sĩ, lịch khám và gửi dữ liệu đặt lịch trong thời gian phù hợp với quy mô 80–120 lượt bệnh nhân/ngày.
* **Lý do:** Tránh làm gián đoạn quá trình đặt lịch và giảm thời gian chờ của bệnh nhân và nhân viên.
* **Tiêu chí kiểm chứng:** Trong điều kiện tải bình thường (30 phiên đồng thời), ít nhất 95% yêu cầu tra cứu lịch và thao tác đặt lịch phải nhận được phản hồi từ hệ thống trong thời gian $\le 2,0$ giây; thời gian phản hồi phân vị 95 (p95) không vượt quá 2,0 giây.

#### NFR-02 · Khả năng xử lý đồng thời

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **NFR-02** | Phi chức năng (Hiệu năng) | Quy mô phòng khám [Giả định] | Should | 1.0 |

* **Mô tả:** Trong bối cảnh các khung giờ cao điểm có nhiều bệnh nhân cùng truy cập, hệ thống phải duy trì khả năng phục vụ đồng thời cho các yêu cầu tra cứu và đặt lịch.
* **Lý do:** Phòng khám có 80–120 lượt bệnh nhân mỗi ngày; hệ thống cần tránh nghẽn mạng hoặc mất dữ liệu khi nhiều người thao tác cùng lúc.
* **Tiêu chí kiểm chứng:** Hệ thống phải xử lý tối thiểu 30 phiên người dùng đồng thời thực hiện tra cứu hoặc đặt lịch mà tỷ lệ lỗi HTTP bằng 0,0%, không phát sinh lỗi tạo lịch trùng hoặc mất bản ghi.

#### NFR-03 · Xác thực OTP khi quản lý lịch hẹn

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **NFR-03** | Phi chức năng (Bảo mật) | Bệnh nhân (`STK-04`) / `SC-03` | Must | 1.0 |

* **Mô tả:** Trong bối cảnh bệnh nhân muốn tra cứu hoặc thay đổi lịch hẹn đã đặt, hệ thống phải sử dụng OTP để xác thực số điện thoại của bệnh nhân trước khi cho phép xem hoặc thao tác đổi/hủy lịch.
* **Lý do:** Thông tin lịch hẹn chứa dữ liệu cá nhân của người bệnh; cần ngăn chặn việc truy cập trái phép hoặc can thiệp lịch hẹn của người khác chỉ bằng Mã lịch hẹn.
* **Tiêu chí kiểm chứng:** OTP gồm đúng 6 chữ số, thời hạn hiệu lực 180 giây [G-07]; ngay sau 3 lần nhập sai liên tiếp, phiên xác thực bị khóa và yêu cầu gửi mã OTP mới.

#### NFR-04 · Phân quyền truy cập dữ liệu

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **NFR-04** | Phi chức năng (Bảo mật) | Quản lý (`STK-01`), Bác sĩ (`STK-02`), Tiếp nhận (`STK-03`) | Must | 1.0 |

* **Mô tả:** Trong bối cảnh vận hành nội bộ, hệ thống phải kiểm soát quyền truy cập dựa trên vai trò (RBAC) đối với dữ liệu bệnh nhân, lịch khám và các chức năng quản trị.
* **Lý do:** Nhân viên quầy, bác sĩ và quản lý có phạm vi công việc khác nhau; nhân viên tiếp nhận chỉ xem thông tin hành chính mà không có quyền xem/sửa chẩn đoán bệnh án y khoa của bác sĩ [G-11]; quyền đóng/hủy ca và hoàn tiền được giới hạn nghiêm ngặt cho Admin.
* **Tiêu chí kiểm chứng:** Người dùng không có quyền quản trị tuyệt đối không được thực hiện thao tác đóng ca bác sĩ, hủy toàn bộ lịch của ca hoặc kích hoạt xử lý hoàn tiền. Các thao tác này chỉ được thực hiện bởi tài khoản có quyền Admin; mọi vi phạm bị chặn với mã HTTP 403 Forbidden.

#### NFR-05 · Độ sẵn sàng của hệ thống

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **NFR-05** | Phi chức năng (Khả dụng) | Nhu cầu vận hành [Giả định] | Should | 1.0 |

* **Mô tả:** Trong bối cảnh cung cấp dịch vụ đặt lịch trực tuyến 24/7, hệ thống phải duy trì khả năng truy cập ổn định để bệnh nhân có thể đặt lịch và nhân viên có thể điều phối lịch khám.
* **Lý do:** Hệ thống là kênh đặt lịch và điều phối cốt lõi; gián đoạn sẽ gây mất lịch hẹn hoặc buộc phòng khám phải quay lại ghi sổ thủ công.
* **Tiêu chí kiểm chứng:** Hệ thống phải đạt thời gian hoạt động tối thiểu 99,5% trong mỗi tháng (loại trừ thời gian bảo trì định kỳ đã thông báo trước tối thiểu 24 giờ).

#### NFR-06 · Lưu trữ và bảo toàn dữ liệu lịch hẹn và giao dịch

| ID | Loại | Nguồn | Độ ưu tiên | Phiên bản |
| :---: | :---: | :---: | :---: | :---: |
| **NFR-06** | Phi chức năng (Lưu trữ) | Quản lý (`STK-01`), Kế toán (`STK-05`) / CR-01 | Must | 1.1 |

* **Mô tả:** Trong bối cảnh triển khai khám trực tuyến và thanh toán trước theo CR-01, hệ thống phải lưu trữ đầy đủ dữ liệu lịch hẹn và giao dịch tài chính để phục vụ tra cứu, xử lý nghiệp vụ và đối soát.
* **Lý do:** CR-01 yêu cầu lưu thông tin giao dịch, mã giao dịch thanh toán, trạng thái và thời gian hoàn tiền; các dữ liệu này cần được bảo toàn để xử lý khi giao dịch lỗi hoặc đối soát kế toán.
* **Tiêu chí kiểm chứng:** Mỗi giao dịch khám trực tuyến phải lưu tối thiểu: Mã giao dịch, Mã lịch hẹn, Số tiền, Phương thức thanh toán, Trạng thái giao dịch, Mã giao dịch cổng thanh toán, Thời gian thanh toán, Thời gian hoàn tiền. Dữ liệu phải còn truy xuất được sau khi lịch hẹn kết thúc (Thời hạn lưu trữ tối thiểu: 05 năm [G-12]).

---

# PHẦN 5: ĐẶC TẢ TÌNH HUỐNG SỬ DỤNG

### SC-01 · Bệnh nhân đặt lịch khám thành công

* **Tác nhân chính:** Bệnh nhân (`STK-04`)
* **Tiền điều kiện:** Hệ thống web hoạt động bình thường, kết nối cơ sở dữ liệu ổn định; Bác sĩ thuộc chuyên khoa yêu cầu có ít nhất 01 khung giờ khám (time slot) ở trạng thái "Khả dụng".
* **Kích hoạt:** Bệnh nhân truy cập trang web phòng khám và chọn nút "Đặt lịch khám".

| Bước | Luồng chính (Tác nhân ↔ Hệ thống) | Luồng thay thế / Ngoại lệ (Rẽ nhánh & Phản hồi) |
| :---: | :--- | :--- |
| **1** | Bệnh nhân lựa chọn hình thức khám mong muốn: "Khám trực tiếp tại phòng khám" hoặc "Khám trực tuyến (theo CR-01)". | — |
| **2** | Bệnh nhân chọn Chuyên khoa và chọn Bác sĩ phụ trách từ danh mục hệ thống. | — |
| **3** | Hệ thống hiển thị lịch làm việc trong tuần và các khung giờ còn trống (Khả dụng) của bác sĩ đã chọn. | — |
| **4** | Bệnh nhân bấm chọn 01 khung giờ khám phù hợp. | **Rẽ nhánh tại bước 4 (Khung giờ vừa bị người khác đặt trước):** Hệ thống phát hiện slot đã kín $\rightarrow$ Chuyển sang `SC-02` để gợi ý các khung giờ hoặc bác sĩ thay thế. |
| **5** | Hệ thống hiển thị biểu mẫu thu thập thông tin đăng ký khám bệnh. | — |
| **6** | Bệnh nhân nhập đầy đủ thông tin: Họ và tên, Số điện thoại liên hệ (10 chữ số [G-02]), Ngày tháng năm sinh, Giới tính và Mô tả tóm tắt triệu chứng bệnh lý ban đầu. | **Rẽ nhánh tại bước 6 (Nhập sai định dạng hoặc thiếu thông tin - `FR-06`):** Bỏ trống Họ tên/SĐT hoặc SĐT không đúng 10 chữ số [G-02] $\rightarrow$ Hệ thống dừng xử lý, đánh dấu đỏ trường vi phạm và yêu cầu sửa lại. |
| **7** | Hệ thống hiển thị bảng tóm tắt: Bác sĩ, Chuyên khoa, Ngày giờ, Hình thức khám và Mức viện phí niêm yết (Khám trực tiếp: Miễn phí đặt trước; Khám online: 150.000 VNĐ [G-04] cần thanh toán trước theo CR-01). | — |
| **8** | Bệnh nhân kiểm tra thông tin, tích chọn đồng ý điều khoản dịch vụ và nhấn nút "Xác nhận đặt lịch". | **Rẽ nhánh tại bước 8 (Phát hiện trùng lịch hẹn - `FR-10`):** CSDL thấy số điện thoại đã có lịch hẹn khác trong cùng khung giờ $\rightarrow$ Hệ thống từ chối tạo lịch, hiển thị cảnh báo lỗi trùng lịch và không gửi SMS. |
| **9** | **Hệ thống phân nhánh xử lý:**<br>• *Khám trực tiếp:* Ghi nhận lịch hẹn "Đã đặt", khóa khung giờ thành "Không khả dụng" và chuyển tiếp đến bước 11.<br>• *Khám online (theo CR-01):* Tạm khóa khung giờ tối đa 15 phút [G-05], tạo phiên giao dịch và chuyển hướng trình duyệt sang cổng thanh toán trực tuyến (VNPay/MoMo). | — |
| **10** | *(Dành riêng cho khám online):* Bệnh nhân xác thực và thanh toán thành công 150.000 VNĐ trên cổng thanh toán; cổng thanh toán gửi mã phản hồi thành công (IPN/Webhook) về hệ thống phòng khám. | **Rẽ nhánh tại bước 10a (Thanh toán online thất bại hoặc người dùng hủy - `CR-01`):** Cổng thanh toán báo lỗi hoặc người dùng hủy $\rightarrow$ Hủy phiên tạm giữ, mở lại khung giờ "Khả dụng", thông báo thanh toán chưa hoàn tất.<br><br>**Rẽ nhánh tại bước 10b (Quá hạn 15 phút chờ thanh toán - `G-05`, `CR-01`):** Bệnh nhân không hoàn tất thanh toán sau 15 phút $\rightarrow$ Tiến trình nền tự động hủy đơn đặt, giải phóng khung giờ về trạng thái "Khả dụng".<br><br>**Rẽ nhánh tại bước 10c (Webhook bất thường, sai chữ ký hoặc đến muộn - `VR-18`, `TC-18`):** Nếu Webhook gửi lặp lại (Idempotency) $\rightarrow$ Hệ thống chỉ ghi nhận 1 lần, bỏ qua thông điệp lặp; Nếu Webhook gửi sau khi slot đã bị hủy do quá hạn 15 phút và có người khác đặt mất $\rightarrow$ Không ghi đè slot, tự động chuyển khoản tiền thu được sang danh sách đối soát hoàn tiền tự động kèm lý do quá hạn. |
| **11** | Hệ thống tạo mã lịch hẹn duy nhất (`AT-XXXXXX`), tự sinh đường link phòng khám trực tuyến (nếu là ca online) và lưu trạng thái lịch hẹn là "Đã xác nhận". | — |
| **12** | Hệ thống hoàn tất lưu CSDL, tự động kích hoạt hàng đợi ngầm gửi tin nhắn SMS Brandname và Email xác nhận (chứa Mã lịch, Tên bác sĩ, Chuyên khoa, Thời gian, Link khám). | **Rẽ nhánh tại bước 12a (Lỗi mạng viễn thông gửi tin nhắn SMS - `TC-17`, `VR-26`):** Tiến trình gửi SMS thất bại do mạng viễn thông $\rightarrow$ Bản ghi lịch hẹn vẫn được lưu thành công trong CSDL, hệ thống tự động gắn cờ cảnh báo "Lỗi gửi SMS" trên giao diện quầy tiếp nhận để nhân viên gọi điện thoại trực tiếp hỗ trợ bệnh nhân. |
| **13** | Hệ thống hiển thị màn hình thông báo hoàn tất đặt lịch thành công kèm hướng dẫn chuẩn bị trước khi khám bệnh. | — |

* **Hậu điều kiện:**
  * **Trạng thái thành công:** Khung giờ đã chọn chuyển sang trạng thái "Không khả dụng" trên lịch của bác sĩ; Bản ghi lịch hẹn được lưu thành công trong CSDL; Bác sĩ phụ trách thấy tên bệnh nhân xuất hiện trên danh sách ca khám tương ứng; Bệnh nhân nhận được tin nhắn SMS xác nhận hợp lệ trong vòng $\le 60\text{ giây}$.
  * **Trạng thái thất bại:** Khung giờ khám được mở lại trạng thái "Khả dụng" (hoặc giữ nguyên nếu trùng lịch/lỗi nhập liệu); không có lịch hẹn mới nào được tạo trong CSDL; không gửi SMS xác nhận.

---

### SC-02 · Khung giờ hoặc bác sĩ không còn khả dụng

* **Tác nhân chính:** Bệnh nhân (`STK-04`)
* **Tiền điều kiện:** Bệnh nhân đang truy cập màn hình chọn thời gian khám bệnh của một bác sĩ cụ thể.
* **Kích hoạt:** Bệnh nhân nhấn chọn một khung giờ vừa bị người khác đăng ký giữ chỗ trước đó vài giây hoặc bác sĩ vừa được quản lý đánh dấu khóa lịch đột xuất.

| Bước | Luồng chính (Tác nhân ↔ Hệ thống) | Luồng thay thế / Ngoại lệ (Rẽ nhánh & Phản hồi) |
| :---: | :--- | :--- |
| **1** | Bệnh nhân bấm chọn khung giờ khám và nhấn nút "Tiếp tục". | — |
| **2** | Hệ thống gửi truy vấn kiểm tra trạng thái khóa thực tế (real-time lock) của khung giờ trong cơ sở dữ liệu. | — |
| **3** | Hệ thống phát hiện khung giờ đã chuyển sang trạng thái "Đã kín" (Unavailable) hoặc "Bị khóa". | — |
| **4** | Hệ thống hiển thị hộp thoại thông báo nổi (Modal popup): *"Rất tiếc! Khung giờ [Giờ:Phút - Ngày] bạn vừa chọn hiện không còn khả dụng do đã có người đặt trước hoặc bác sĩ có lịch đột xuất"*. | — |
| **5** | Hệ thống kích hoạt thuật toán gợi ý phương án thay thế: tự động quét và hiển thị 03 khung giờ còn trống gần nhất trong cùng ngày của chính bác sĩ đó. | **Rẽ nhánh tại bước 5a (Bác sĩ kín lịch, nhưng khoa còn bác sĩ khác trống):** Bác sĩ đã chọn không còn slot trống trong ngày $\rightarrow$ Hệ thống tự động quét và gợi ý danh sách Bác sĩ khác cùng chuyên khoa có lịch trống trong ngày.<br><br>**Rẽ nhánh tại bước 5b (Toàn bộ chuyên khoa đã kín lịch trong ngày):** Tất cả bác sĩ trong chuyên khoa đều không còn slot trống nào trong ngày $\rightarrow$ Hệ thống hiển thị lịch trống của ngày làm việc tiếp theo gần nhất; hoặc cung cấp số hotline phòng khám để lễ tân hỗ trợ xếp lịch trực tiếp. |
| **6** | Bệnh nhân quan sát các phương án gợi ý và bấm chọn 01 khung giờ thay thế phù hợp. | **Rẽ nhánh tại bước 6a (Bệnh nhân từ chối các gợi ý):** Bệnh nhân đóng hộp thoại gợi ý và không chọn khung giờ mới $\rightarrow$ Hệ thống đưa người dùng quay lại màn hình tổng quan chọn chuyên khoa/bác sĩ ban đầu. |
| **7** | Hệ thống làm mới giao diện, tạm giữ khung giờ mới được chọn và điều hướng bệnh nhân sang bước điền thông tin cá nhân (tiếp tục Bước 5 của kịch bản `SC-01`). | — |

* **Hậu điều kiện:**
  * **Trạng thái thành công:** Bệnh nhân chọn được khung giờ thay thế hợp lệ và tiếp tục quy trình đặt lịch (`SC-01`); khung giờ mới được tạm giữ an toàn.
  * **Trạng thái thất bại:** Không phát sinh bất kỳ bản ghi rác hay lịch hẹn trùng lặp nào trong cơ sở dữ liệu; giao diện lịch khám được làm mới đồng bộ với trạng thái khả dụng thực tế của cơ sở dữ liệu.

---

### SC-03 · Bệnh nhân đổi hoặc hủy lịch hẹn

* **Tác nhân chính:** Bệnh nhân (`STK-04`)
* **Tiền điều kiện:** Bệnh nhân đã có lịch hẹn được xác nhận trên hệ thống và còn lưu giữ Mã lịch hẹn cùng Số điện thoại đã đăng ký; Lịch hẹn đang ở trạng thái "Đã đặt" hoặc "Đã xác nhận" (chưa diễn ra và chưa bị hủy).
* **Kích hoạt:** Bệnh nhân truy cập trang "Tra cứu & Quản lý lịch hẹn", nhập thông tin tra cứu và nhấn nút "Tra cứu lịch hẹn".

| Bước | Luồng chính (Tác nhân ↔ Hệ thống) | Luồng thay thế / Ngoại lệ (Rẽ nhánh & Phản hồi) |
| :---: | :--- | :--- |
| **1** | Bệnh nhân nhập Mã lịch hẹn và Số điện thoại đăng ký, sau đó nhấn nút "Tiếp tục". | **Rẽ nhánh tại bước 1a (Sai thông tin tra cứu):** Mã lịch hẹn hoặc SĐT không khớp với bản ghi nào $\rightarrow$ Hệ thống hiển thị cảnh báo không tìm thấy thông tin, yêu cầu kiểm tra lại. |
| **2** | Hệ thống kiểm tra tính hợp lệ của mã và SĐT, tự động sinh mã xác thực OTP gồm 6 chữ số gửi qua SMS đến SĐT bệnh nhân (thời hạn hiệu lực 180 giây [G-07]). | — |
| **3** | Bệnh nhân nhập mã OTP và nhấn nút "Xác thực". | **Rẽ nhánh tại bước 3a (Nhập sai hoặc hết hạn OTP - `NFR-03`):** Bệnh nhân nhập sai OTP đến lần thứ 3 hoặc để quá hạn 180 giây [G-07] $\rightarrow$ Hệ thống khóa ngay phiên xác thực, hiển thị nút yêu cầu gửi lại OTP mới. |
| **4** | Hệ thống xác thực OTP thành công và hiển thị chi tiết ca khám kèm 02 nút hành động: "Hủy lịch hẹn" và "Đổi khung giờ khám". | — |
| **5** | Bệnh nhân chọn "Hủy lịch hẹn". Hệ thống tính toán khoảng thời gian chênh lệch từ hiện tại đến giờ hẹn khám và xác nhận đạt điều kiện $\ge 120$ phút trước giờ khám [G-06]. | **Rẽ nhánh tại bước 5a (Hủy quá trễ < 120 phút - `G-06`):** Thời gian đến giờ hẹn $< 120$ phút $\rightarrow$ Hệ thống làm mờ nút hủy trực tuyến, thông báo hướng dẫn gọi hotline phòng khám; không hỗ trợ hoàn tiền online tự động [Q-03].<br><br>**Rẽ nhánh tại bước 5b (Bệnh nhân chọn Đổi khung giờ khám thay vì Hủy):** Bệnh nhân bấm chọn "Đổi khung giờ khám" $\rightarrow$ Hệ thống kiểm tra điều kiện $\ge 120$ phút [G-06]; mở bảng lịch công tác của bác sĩ và hiển thị các khung giờ còn trống khác; bệnh nhân chọn 01 khung giờ khám mới và nhấn "Lưu thay đổi"; hệ thống cập nhật giờ mới, khóa slot mới, giải phóng slot cũ về "Khả dụng" và gửi SMS thông báo cập nhật thành công. *(Quy tắc tài chính CR-01: Khoản viện phí 150.000 VNĐ đã thanh toán được tự động bảo lưu gắn với mã lịch hẹn ở khung giờ mới, không yêu cầu thanh toán lại).* (Nếu slot mới vừa bị người khác chọn trước, hệ thống giữ nguyên lịch cũ và yêu cầu chọn lại). |
| **6** | Bệnh nhân chọn lý do hủy và nhấn nút "Xác nhận hủy lịch". | — |
| **7** | Hệ thống chuyển trạng thái lịch hẹn sang "Đã hủy bởi bệnh nhân", ghi nhận lý do và thời gian hủy. | — |
| **8** | *(CR-01):* Nếu là ca khám online đã thanh toán trước hủy $\ge 2$ tiếng, hệ thống tự động gọi API cổng thanh toán hoàn trả 100% viện phí, cập nhật bảng `GiaoDich` sang "Đã hoàn tiền". | **Rẽ nhánh tại bước 8a (Lỗi kết nối cổng TT khi hoàn tiền - `CR-01`):** Cổng thanh toán timeout hoặc lỗi hệ thống $\rightarrow$ Tự động chuyển trạng thái sang "Chờ xử lý hoàn tiền thủ công" và tạo cảnh báo đỏ trên giao diện Quản lý để kế toán đối soát trực tiếp, lịch hẹn vẫn được hủy thành công. |
| **9** | Hệ thống tự động giải phóng khung giờ (`FR-07`), đổi slot về "Khả dụng" (với điều kiện ca trực bác sĩ vẫn mở bình thường [VR-10]). | — |
| **10** | Hệ thống tự động gửi tin nhắn SMS xác nhận hủy lịch thành công cho bệnh nhân (kèm xác nhận lệnh hoàn tiền 100% đối với ca khám online). | — |

* **Hậu điều kiện:**
  * **Trạng thái thành công:** Lịch hẹn chuyển sang trạng thái "Đã hủy bởi bệnh nhân" (hoặc "Đã dời lịch"); Khung giờ cũ được mở lại ở trạng thái "Khả dụng", sẵn sàng cho bệnh nhân khác đặt; Danh sách khám của bác sĩ và màn hình điều phối lễ tân được đồng bộ theo thời gian thực; Nghĩa vụ hoàn tiền (nếu hủy lịch online hợp lệ) được thực thi minh bạch.
  * **Trạng thái thất bại:** Trạng thái lịch hẹn và khung giờ giữ nguyên; không phát sinh giao dịch tài chính hay hủy lịch sai quy định.

---

### SC-04 · Bác sĩ nghỉ ca đột xuất và xử lý hoàn tiền

* **Tác nhân chính:** Quản lý phòng khám (`STK-01`)
* **Tiền điều kiện:** Quản lý phòng khám đã đăng nhập thành công vào hệ thống với vai trò Quản trị viên (Admin); Bác sĩ có lịch làm việc trong ngày phát sinh sự cố khẩn cấp (ốm đau, việc gia đình) và đã thông báo nghỉ đột xuất; Đã có bệnh nhân đặt hẹn trước trong ca làm việc bị ảnh hưởng.
* **Kích hoạt:** Quản lý phòng khám chọn ca trực của bác sĩ trên giao diện điều hành và nhấn nút "Báo nghỉ đột xuất / Hủy ca trực".

| Bước | Luồng chính (Tác nhân ↔ Hệ thống) | Luồng thay thế / Ngoại lệ (Rẽ nhánh & Phản hồi) |
| :---: | :--- | :--- |
| **1** | Quản lý chọn Bác sĩ, Ngày khám và Ca trực cần báo nghỉ (Sáng/Chiều), sau đó chọn hoặc nhập lý do nghỉ đột xuất. | — |
| **2** | Hệ thống truy vấn CSDL và hiển thị danh sách tổng hợp toàn bộ bệnh nhân đã đặt hẹn trong ca trực, phân tách rõ 02 nhóm: Khám trực tiếp và Khám trực tuyến (đã thanh toán trước). | — |
| **3** | Quản lý kiểm tra thông tin và nhấn nút "Xác nhận đóng ca trực & Kích hoạt xử lý sự cố". | **Rẽ nhánh tại bước 3a (Người dùng không có quyền Quản trị viên - `NFR-04`):** Tài khoản thao tác không có quyền Admin $\rightarrow$ Hệ thống từ chối thực hiện, trả về mã lỗi HTTP 403 Forbidden và ghi nhật ký vi phạm bảo mật (Audit Log). |
| **4** | Hệ thống tự động chuyển trạng thái của toàn bộ các khung giờ còn lại trong ca trực sang "Đã khóa do bác sĩ nghỉ đột xuất" (`FR-08`) để ngăn chặn đặt lịch mới. | **Rẽ nhánh tại bước 4a (Xử lý các phiên đặt online đang trong 15 phút chờ thanh toán - `TC-15`, `TC-18`):** Các phiên đặt lịch online đang trong thời gian giữ chỗ 15 phút bị hủy ngay lập tức; nếu bệnh nhân đã kịp hoàn tất trừ tiền trên app ngân hàng trước đó vài giây $\rightarrow$ Hệ thống từ chối xác nhận lịch vào ca đã đóng, tự động kích hoạt lệnh hoàn tiền 100% về tài khoản bệnh nhân kèm SMS thông báo ca trực đã bị hủy khẩn cấp. |
| **5** | Hệ thống chuyển đổi trạng thái của toàn bộ lịch hẹn thuộc ca trực sang "Đã hủy bởi phòng khám do bác sĩ vắng mặt". | — |
| **6** | Hệ thống tự động kích hoạt quy trình hoàn tiền cho ca khám trực tuyến (theo `CR-01` & `FR-12`): lọc danh sách bệnh nhân thuộc Nhóm 2 có trạng thái "Đã thanh toán", tự động gọi API sang cổng thanh toán (VNPay/MoMo) phát lệnh hoàn 100% tiền viện phí về tài khoản ban đầu, nhận mã xác nhận và cập nhật bảng `GiaoDich` sang "Đã hoàn tiền". | **Rẽ nhánh tại bước 6a (Lỗi kết nối cổng thanh toán / Giao dịch hoàn thất bại - `CR-01`):** Cổng thanh toán bị timeout hoặc trả về lỗi $\rightarrow$ Ghi log cảnh báo đỏ, tự chuyển trạng thái giao dịch sang "Chờ xử lý hoàn tiền thủ công" và hiển thị cảnh báo đỏ trên UI Quản lý để kế toán đối soát trực tiếp. |
| **7** | Hệ thống tự động kích hoạt tiến trình gửi thông báo hàng loạt (theo `FR-09`): gửi tin nhắn SMS Brandname và Email đồng loạt đến 100% bệnh nhân bị ảnh hưởng (bệnh nhân khám trực tiếp nhận thông báo xin lỗi kèm link ưu tiên dời lịch; bệnh nhân khám online nhận thông báo xin lỗi, link dời lịch và xác nhận lệnh hoàn tiền 100% kèm mã đối soát). | **Rẽ nhánh tại bước 7a (Lỗi mạng viễn thông gửi tin nhắn SMS thất bại):** Tin nhắn gửi đến một số thuê bao bị lỗi mạng viễn thông $\rightarrow$ Hệ thống đánh dấu cờ "Chưa gửi được SMS" trên danh sách bệnh nhân để nhân viên quầy tiếp nhận gọi điện thoại trực tiếp. |
| **8** | Hệ thống xuất báo cáo tổng kết trên màn hình Quản lý: Tổng số lịch hẹn đã hủy, số SMS gửi thành công, số giao dịch hoàn tiền online đã xử lý thành công. | — |

* **Hậu điều kiện:**
  * **Trạng thái thành công:** Toàn bộ ca trực bị đóng hoàn toàn, không thể tiếp nhận thêm lịch hẹn; 100% bệnh nhân bị ảnh hưởng nhận được thông báo sự cố kịp thời, hạn chế tối đa việc bệnh nhân di chuyển đến phòng khám trong vô vọng; Nghĩa vụ hoàn trả tài chính cho các ca khám online được xử lý minh bạch và chính xác.
  * **Trạng thái thất bại:** Thao tác bị từ chối nếu không đủ thẩm quyền Admin; dữ liệu ca trực và lịch hẹn giữ nguyên trạng thái ban đầu.

---

# PHẦN 6: QUẢN LÝ THAY ĐỔI YÊU CẦU

### 6.1. Bối cảnh và mô tả nghiệp vụ CR-01
* **Mã yêu cầu thay đổi:** `CR-01`
* **Tên thay đổi:** Triển khai dịch vụ khám bệnh trực tuyến từ xa.
* **Nguồn gốc phát sinh:** Quản lý phòng khám An Tâm (`STK-01`).
* **Mô tả nghiệp vụ:** Để mở rộng phạm vi phục vụ bệnh nhân ở xa và tối ưu hóa thời gian làm việc của các bác sĩ chuyên khoa, phòng khám bổ sung kênh khám bệnh trực tuyến. Nhằm ngăn chặn tình trạng đặt lịch ảo làm lãng phí thời gian trực của bác sĩ, phòng khám ban hành quy định:
  1. Bệnh nhân bắt buộc phải thanh toán tiền viện phí trực tuyến trước thì lịch hẹn khám từ xa mới được hệ thống xác nhận chính thức.
  2. Trong trường hợp bác sĩ có sự cố đột xuất phải hủy lịch hẹn, hệ thống phải tự động hoàn trả 100% tiền viện phí đã thu cho bệnh nhân và gửi thông báo xác nhận minh bạch.

### 6.2. Bảng phân tích tác động toàn diện

| Hạng mục chịu tác động | Chi tiết tác động cụ thể từ CR-01 | Mức độ tác động |
| :--- | :--- | :---: |
| **Yêu cầu chức năng** | • **Bổ sung mới `FR-11`:** Bắt buộc tích hợp cổng thanh toán trực tuyến (VNPay/MoMo), tạm giữ khung giờ trong 15 phút và chỉ xác nhận lịch khi thanh toán thành công.<br>• **Bổ sung mới `FR-12`:** Xây dựng cơ chế phát lệnh hoàn tiền tự động 100% khi bác sĩ hoặc phòng khám chủ động hủy lịch khám trực tuyến.<br>• **Sửa đổi logic `FR-03`:** Bổ sung điều kiện chỉ kích hoạt gửi SMS/Email xác nhận lịch hẹn online sau khi hệ thống nhận được tín hiệu giao dịch thanh toán thành công từ cổng thanh toán.<br>• **Hồi quy liên quan:** `FR-01` (lựa chọn khám online), `FR-07` (giải phóng slot khi hủy giao dịch thanh toán), `FR-08` (đóng ca trực có lịch online). | **Cao** |
| **Yêu cầu phi chức năng** | • **Sửa đổi `NFR-06`:** Bổ sung yêu cầu lưu trữ và bảo toàn các trường dữ liệu giao dịch tài chính (Mã giao dịch, Số tiền, Trạng thái, Mã đối soát, Thời gian hoàn tiền).<br>• **Tác động `NFR-04`:** Bổ sung kiểm soát phân quyền đối với thao tác kích hoạt hoàn tiền (chỉ dành cho Quản trị viên). | **Trung bình** |
| **Kịch bản nghiệp vụ** | • **Sửa đổi `SC-01`:** Bổ sung bước rẽ nhánh lựa chọn hình thức khám (Trực tiếp vs Trực tuyến), bước chuyển hướng sang cổng thanh toán điện tử, xử lý ngoại lệ khi giao dịch timeout hoặc thanh toán thất bại.<br>• **Sửa đổi `SC-03`:** Bổ sung cơ chế hoàn tiền khi bệnh nhân chủ động hủy lịch khám trực tuyến hợp lệ trước $\ge 120$ phút.<br>• **Sửa đổi `SC-04`:** Bổ sung bước tự động lọc bệnh nhân khám online, gọi API cổng thanh toán hoàn tiền tự động và gửi SMS kèm thông tin đối soát hoàn tiền. | **Cao** |
| **Mô hình dữ liệu** | • **Tạo mới thực thể/bảng `GiaoDich`:** Lưu trữ `MaGiaoDich` (PK), `MaLichHen` (FK), `SoTien`, `PhuongThucThanhToan`, `TrangThaiThanhToan` (Chờ TT / Đã TT / Thất bại / Đã hoàn tiền / Chờ xử lý thủ công), `MaGiaoDichCongTT`, `ThoiGianThanhToan`, `ThoiGianHoanTien`, `MaYeuCauHoanTien`, `MaGiaoDichHoanTien`.<br>• **Bổ sung thuộc tính bảng `LichHen`:** Thêm trường `HinhThucKham` (Enum: `TRUC_TIEP`, `TRUC_TUYEN`), trường `LinkKhamOnline` (VARCHAR) và trường `HanThanhToanTamGiu` (DATETIME). | **Trung bình** |
| **Kiểm thử** | • **Bổ sung kịch bản `TC-05`:** Kiểm thử luồng đặt lịch khám trực tuyến, liên kết cổng thanh toán và xác nhận lịch thành công.<br>• **Bổ sung kịch bản `TC-06`:** Kiểm thử luồng bác sĩ hủy ca trực $\rightarrow$ tự động kích hoạt hoàn tiền và gửi SMS thông báo cho bệnh nhân.<br>• **Bổ sung kịch bản kiểm tra biên `TC-14`, `TC-15`, `TC-16`, `TC-18`:** Kiểm thử lưu trữ giao dịch, hết hạn giữ chỗ 15 phút, lỗi hoàn tiền và phòng chống Webhook lặp. | **Cao** |
| **Giao diện người dùng** | • Bổ sung nút lựa chọn "Khám tại phòng khám" hoặc "Khám trực tuyến" tại màn hình trang chủ.<br>• Tích hợp widget nhúng hoặc trang chuyển hướng thanh toán an toàn.<br>• Bổ sung màn hình hiển thị phòng chờ và đường link tham gia phòng khám trực tuyến. | **Thấp** |

### 6.3. Nhận diện rủi ro phát sinh và biện pháp kiểm soát đề xuất

#### Rủi ro 1: Độ trễ hoàn tiền từ phía ngân hàng trung gian phát hành thẻ
* **Bản chất rủi ro:** Hệ thống phòng khám phát lệnh hoàn tiền ngay lập tức khi hủy ca, nhưng quy trình đối soát giữa cổng thanh toán (VNPay/MoMo) và ngân hàng phát hành thẻ của bệnh nhân thường mất từ 24h đến 48h làm việc (thậm chí 7–14 ngày đối với thẻ tín dụng quốc tế Visa/Mastercard). Bệnh nhân có thể bức xúc, khiếu nại hoặc gọi điện làm phiền lễ tân vì kiểm tra tài khoản chưa thấy tiền về ngay.
* **Biện pháp xử lý đề xuất:** Trong nội dung SMS/Email thông báo hoàn tiền, hệ thống phải ghi rõ ràng: *"Phòng khám An Tâm đã phát lệnh hoàn 100% tiền viện phí (Mã giao dịch: XXXXXX). Tiền sẽ được ngân hàng ghi có vào tài khoản của quý khách trong vòng 1–3 ngày làm việc tùy quy định ngân hàng phát hành thẻ"*.

#### Rủi ro 2: Bệnh nhân vắng mặt hoặc tham gia phòng khám trực tuyến trễ
* **Vấn đề cần làm rõ:** Đề bài mới chỉ quy định "hoàn tiền khi bác sĩ hủy lịch". Vậy trong trường hợp ngược lại: Bác sĩ đã mở phòng khám online đúng giờ nhưng bệnh nhân không bấm vào link tham gia (bác sĩ chờ quá 15 phút), phòng khám có áp dụng chính sách hoàn tiền cho bệnh nhân hay không?
* **Giải pháp đề xuất đưa vào quy định:** Cần bổ sung điều khoản dịch vụ: Nếu bệnh nhân vắng mặt quá 10 phút sau giờ hẹn mà không báo trước, ca khám được tính là "Bệnh nhân vắng mặt", phòng khám sẽ không hoàn tiền nhằm bảo vệ quyền lợi và thù lao thời gian của bác sĩ.

#### Rủi ro 3: Lựa chọn nền tảng hạ tầng công nghệ cho phòng gọi video
* **Vấn đề cần làm rõ:** Phòng khám dự định tự phát triển giải pháp Video Call nội bộ chạy trên máy chủ riêng (sử dụng công nghệ WebRTC) hay sử dụng giải pháp tích hợp API của nền tảng bên thứ ba (Google Meet, Zoom Video SDK, Microsoft Teams)?
* **Đánh giá rủi ro kỹ thuật:** Việc tự dựng máy chủ WebRTC đòi hỏi chi phí hạ tầng máy chủ rất cao, đường truyền băng thông cực lớn và đội ngũ bảo trì phức tạp.
* **Đề xuất kỹ thuật:** Trong giai đoạn đầu, hệ thống phần mềm chỉ đóng vai trò tự động tích hợp API của Google Workspace/Zoom để sinh tự động đường link cuộc họp bảo mật kèm mật khẩu gửi cho bác sĩ và bệnh nhân, giúp tiết kiệm chi phí vận hành và đảm bảo độ ổn định đường truyền âm thanh/hình ảnh.

### 6.4. Danh mục câu hỏi cần làm rõ thêm từ CR-01

| Mã | Nội dung câu hỏi cần Stakeholder xác nhận | Người có thẩm quyền quyết định | Phần chịu ảnh hưởng trong hệ thống |
| :---: | :--- | :---: | :---: |
| **QA-Q01** | Bệnh nhân tự hủy lịch online trước giờ khám thì có được hoàn tiền không; tỷ lệ hoàn bao nhiêu % và điều kiện thời gian tối thiểu là gì? | Quản lý (`STK-01`), Kế toán (`STK-05`) | `FR-05`, `FR-12`, `SC-03`, Giả định `Q-03` |
| **QA-Q02** | Trường hợp tín hiệu thanh toán Webhook đến sau khi hết hạn 15 phút nhưng tài khoản người dùng đã bị trừ tiền thì xử lý tài chính ra sao? | Quản lý (`STK-01`), Cổng TT (`STK-06`), Kế toán (`STK-05`) | `FR-11`, `SC-01`, `TC-18` |
| **QA-Q03** | Cổng thanh toán được lựa chọn chính thức có quy chuẩn kỹ thuật đối soát, đối chiếu chữ ký và cơ chế chống gửi lặp thế nào? | Kỹ thuật, Cổng thanh toán (`STK-06`) | `FR-11`, `FR-12`, `TC-18` |
| **QA-Q04** | Thời gian cam kết ngân hàng ghi có tiền hoàn thực tế là bao lâu để ghi chính xác vào nội dung tin nhắn SMS Brandname gửi bệnh nhân? | Cổng thanh toán (`STK-06`), Quản lý (`STK-01`) | `FR-09`, `FR-12`, `SC-04`, `TC-06` |
| **QA-Q05** | Nền tảng hội nghị trực tuyến video nào được chốt triển khai; quyền truy cập link và hướng xử lý khi không tạo được link phòng khám? | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | `SC-01`, `TC-05` |

---

# PHẦN 7: BÁO CÁO KIỂM ĐỊNH YÊU CẦU

### 7.1. Tổ chức đánh giá chéo và 6 tiêu chí kiểm nghiệm chất lượng

| Tiêu chí | Câu hỏi đối chiếu | Dấu hiệu kết luận đạt | Phát hiện tiêu biểu |
| :--- | :--- | :--- | :---: |
| **Đúng đắn** | Nội dung có đúng dữ kiện tình huống, nguồn yêu cầu và CR-01 không? | Không gán chính sách chưa được xác nhận cho đề bài; tính toán khung giờ đúng. | VR-09, VR-11 |
| **Đầy đủ** | Có đủ yêu cầu, ngoại lệ, dữ liệu và test cho phạm vi đã ghi không? | 18 yêu cầu có TC; trường hợp lỗi và nhu cầu chưa được đặc tả phải được ghi nhận. | VR-01, VR-06, VR-17, VR-22 |
| **Nhất quán** | Cùng một ID, trạng thái hoặc quy tắc có cùng ý nghĩa trong các tài liệu không? | FR/NFR, scenario, TC và ma trận không dùng lẫn ID hoặc ngưỡng. | VR-03, VR-04, VR-10, VR-13 |
| **Khả thi** | Kết quả có nằm trong khả năng kiểm soát của hệ thống và dịch vụ phụ thuộc không? | Phân biệt phát lệnh với kết quả của nhà cung cấp; có nhánh xử lý lỗi. | VR-15, VR-25, VR-26 |
| **Rõ ràng** | Người đọc có xác định được tác nhân, hành vi và điều kiện không? | Không dùng nhận xét chung thay cho trạng thái, quyền hoặc hành vi quan sát được. | VR-12, VR-21, VR-23 |
| **Đo lường được** | Có điều kiện đạt/không đạt và cách thu bằng chứng không? | Thống nhất p95, số phiên, thời hạn OTP, mốc giữ chỗ và công thức uptime. | VR-07, VR-08, VR-14, VR-20 |

---

### 7.2. Bảng kết quả kiểm định chi tiết 27 vấn đề

| Mã | Vấn đề / bằng chứng đối chiếu | Tiêu chí | Mục bị ảnh hưởng | Quyết định | Lý do kỹ thuật và biện pháp xử lý | Phụ trách / điều kiện đóng |
| --- | --- | --- | --- | --- | --- | --- |
| **VR-01** | Kế hoạch thu thập yêu cầu chưa có nội dung. Phụ lục PL-1 đến PL-3 của Mini-SRS còn các mục chưa hoàn thiện, chưa có kế hoạch, bộ câu hỏi hoặc nội dung khảo sát. | Đầy đủ; Đúng đắn | Kế hoạch thu thập yêu cầu; Mini-SRS, phụ lục khảo sát | **Đồng ý sửa** | Cần có kế hoạch và nội dung khảo sát trước khi xác nhận nguồn stakeholder; biên bản chưa điền không phải minh chứng đã phỏng vấn. Bổ sung kế hoạch ít nhất 2 kỹ thuật, 5 câu mở, 5 câu đóng, 5 câu ngoại lệ/NFR; ghi riêng dữ kiện, giả định và câu hỏi chưa có trả lời. | TV1; đóng khi nội dung được điền đầy đủ tại Phần 3 của báo cáo này. |
| **VR-02** | Mục 2.1 và nhiều hàng mục 3 của Mini-SRS còn thiếu nội dung về môi trường vận hành, nguồn và đặc tả yêu cầu; lịch sử phiên bản chưa ghi ngày cập nhật. | Đầy đủ; Rõ ràng | Mini-SRS, mục 2, 3 và lịch sử thay đổi | **Đồng ý sửa** | Chuyển đặc tả đã có ở Danh mục yêu cầu vào Mini-SRS; điền môi trường theo dữ liệu được xác nhận hoặc ghi nhãn giả định. Ngày phiên bản phải dựa trên lần cập nhật thực tế. Bản SRS cần có nội dung đặc tả thay cho các ô chưa hoàn thiện. | TV1, TV2; đóng khi không còn ô mẫu trong bản tổng hợp. |
| **VR-03** | Mini-SRS đặt NFR-03 là “Mã hóa dữ liệu y tế”, NFR-06 là “Sao lưu & Khôi phục CSDL”; Danh mục yêu cầu dùng cùng ID cho OTP và lưu trữ lịch hẹn/giao dịch. | Nhất quán | Danh mục yêu cầu; Mini-SRS, mục 3.3; ma trận | **Đồng ý sửa** | Giữ ý nghĩa ID theo Danh mục yêu cầu: NFR-03 là OTP, NFR-06 là lưu trữ và bảo toàn dữ liệu. Mã hóa hoặc sao lưu, nếu nhóm giữ trong phạm vi, phải được đặc tả bằng ID riêng; TC về OTP không chứng minh mã hóa hoặc khả năng khôi phục. | TV2; đóng khi tên, mô tả, tiêu chí và TC thống nhất. |
| **VR-04** | TC-03 gắn FR-06, FR-07, trong khi FR-06 kiểm tra dữ liệu lúc đặt lịch; việc tra cứu OTP và tự hủy thuộc FR-04, FR-05. | Nhất quán; Đúng đắn | Báo cáo kiểm định và kịch bản kiểm thử, TC-03; Mini-SRS, mục 6.2 và 7 | **Đồng ý sửa** | Liên kết hiệu chỉnh là FR-04, FR-05, FR-07, NFR-03. Bỏ FR-06 khỏi TC-03; kiểm tra dữ liệu không hợp lệ bằng TC-07. | TV3, TV4; áp dụng tại mục 8.1 và Phần 9 báo cáo này. |
| **VR-05** | Ma trận trước hiệu chỉnh gắn N-02/STK-02 với FR-05 và SC-01; gắn N-04 với FR-06/SC-03; các hàng NFR dùng “Toàn bộ” và TC không có bước kiểm chứng tương ứng. | Nhất quán; Rõ ràng | Mini-SRS, mục 7 | **Đồng ý sửa** | FR-05 là đổi/hủy của bệnh nhân, không phải bác sĩ xem danh sách. Tách mỗi Requirement ID thành một hàng; dùng STK, SC và TC cụ thể. Nhu cầu chưa có FR được ghi riêng, không gán vào chức năng khác để lấp ô. | TV4; ma trận hiệu chỉnh tại Phần 9; ghi nhận khoảng thiếu tại mục 9.4. |
| **VR-06** | Bộ TC-01 đến TC-06 chưa có test trực tiếp cho 30 phiên đồng thời, OTP sai/hết hạn, phân quyền, uptime và truy xuất dữ liệu sau khi lịch kết thúc. | Đầy đủ; Đo lường được | NFR-02 đến NFR-06; Báo cáo kiểm định và kịch bản kiểm thử | **Đồng ý sửa** | Bổ sung TC-09, TC-11, TC-12, TC-13, TC-14. Một TC thao tác thành công không thay thế test từ chối quyền, kiểm tra uptime hoặc lưu trữ. | TV3, TV4; đã đặc tả chi tiết tại mục 8.3. |
| **VR-07** | NFR-01 yêu cầu ít nhất 95% request phản hồi trong 2 giây; TC-04 chỉ yêu cầu trung bình không quá 2 giây và p95 không quá 2,5 giây. | Nhất quán; Đo lường được | NFR-01; TC-04; Mini-SRS, mục 6.2 | **Đồng ý sửa** | Trung bình đạt không chứng minh 95% request đạt. Dùng tỷ lệ request phản hồi trong 2.000 ms ít nhất 95%, đối chiếu p95 không quá 2.000 ms. Ngưỡng 2,5 giây không dùng để nghiệm thu NFR-01. | TV2, TV3; quy tắc hiệu chỉnh tại mục 8.2. |
| **VR-08** | TC-04 dùng 100 VU làm tải nghiệm thu; NFR-02 hiện hành đặt tối thiểu 30 phiên đồng thời và NFR-01 chưa định nghĩa tải bình thường. | Rõ ràng; Đo lường được | NFR-01, NFR-02; TC-04 | **Đồng ý sửa** | Định nghĩa tạm tải bình thường là 30 phiên trong cấu hình kiểm thử, có nhãn giả định. Bài 100 VU được giữ làm kiểm tra tải mở rộng, không suy ra đó là ngưỡng stakeholder đã chốt. | TV2, TV3; ghi nhận thống nhất tại mục 8.2. |
| **VR-09** | SC-03 tự hoàn 100% khi bệnh nhân hủy; mục 5.2 Mini-SRS quy thay đổi này cho CR-01. CR-01 của đề bài và FR-12 chỉ bắt buộc hoàn khi bác sĩ/phòng khám hủy. | Đúng đắn; Nhất quán | SC-03; Mini-SRS, mục 4 và 5.2; FR-12 | **Đồng ý sửa** | Không suy ra chính sách hoàn khi bệnh nhân hủy từ nghĩa vụ của phòng khám. Tách thành câu hỏi cần STK-01 xác nhận. Bộ test cơ sở dùng lịch trực tiếp khi kiểm tra bệnh nhân hủy; hoàn tự động được nghiệm thu ở SC-04. | TV2, TV3; đóng khi SC-03 và bảng tác động nêu rõ đây là giả định Q-03. |
| **VR-10** | FR-07 nói hủy hợp lệ thì khung giờ trở lại “Khả dụng”, nhưng FR-08 khóa ca khi bác sĩ nghỉ. Cách giải phóng vô điều kiện có thể mở lại ca đã đóng. | Nhất quán; Đúng đắn | FR-07, FR-08, FR-11; SC-03, SC-04 | **Đồng ý sửa** | Bổ sung điều kiện: chỉ mở lại nếu ca còn hoạt động và không có lý do khóa khác. Hủy lịch hoặc hết hạn giữ chỗ trong ca đã đóng không được mở ca. Kiểm tra nhánh này ở TC-15 và TC-16. | TV2, TV3; đã bổ sung vào FR-07, SC-03 và các test case. |
| **VR-11** | G-01 mô tả ca 4 giờ, 15 phút/lượt nhưng cho 16-20 lượt hẹn. Nếu mỗi lượt dùng một khung giờ và không chồng lịch thì 240/15 chỉ bằng 16. | Đúng đắn; Khả thi | Mini-SRS, G-01 và thuật ngữ khung giờ; PL-4, Q-01 | **Đồng ý sửa** | Với giả định hiện có, ghi tối đa 16 lượt/ca/bác sĩ khi không có giờ nghỉ. Muốn 20 lượt phải khảo sát thời lượng lượt, số bệnh nhân/slot hoặc độ dài ca; không đồng thời giữ ba giá trị mâu thuẫn. | TV1, TV2; đã sửa thành tối đa 16 lượt trong G-01. |
| **VR-12** | G-03, G-08, G-10 tham chiếu FR-04 như chức năng tiếp nhận; G-06 tham chiếu FR-06 như đổi/hủy. Ý nghĩa các ID này đã khác trong Danh mục yêu cầu. | Nhất quán; Rõ ràng | Mini-SRS, bảng G-01 đến G-12 | **Đồng ý sửa** | G-06 tham chiếu FR-05. G-03, G-08, G-10 ghi là vấn đề phạm vi/tiếp nhận chưa có FR thay vì gắn FR-04. Mã giả định phải chỉ đúng phần chịu tác động. | TV1, TV2; đã cập nhật toàn bộ tham chiếu tại Bảng 2.2. |
| **VR-13** | NFR-03 khóa sau 3 lần sai; ngoại lệ SC-03 dùng “sai quá 3 lần”, có thể được hiểu là cho phép lần sai thứ tư. | Nhất quán; Đo lường được | NFR-03; SC-03, ngoại lệ 3a; G-07 | **Đồng ý sửa** | Thống nhất khóa ngay sau lần nhập sai thứ ba. Làm rõ mốc hết hạn khi tuổi OTP đạt 180 giây; TC-09 kiểm tra 179 giây, 180 giây và lần sai thứ ba. Các ngưỡng vẫn thuộc G-07. | TV2, TV3; đã sửa thành khóa ngay sau lần sai thứ 3. |
| **VR-14** | TC-03 chỉ thử hủy trước 4 giờ; chưa thử đúng 120 phút, dưới 120 phút, đổi thành công và khung giờ mới bị người khác chiếm. | Đầy đủ; Đo lường được | FR-05, FR-07; SC-03 | **Đồng ý sửa** | Bổ sung TC-10 với dữ liệu biên và nhánh giữ lịch cũ khi đổi thất bại. Đo bằng thời gian máy chủ; không kết luận đạt chỉ dựa vào nút trên giao diện bị làm mờ. | TV3; đã đặc tả chi tiết tại mục 8.3. |
| **VR-15** | Hậu điều kiện SC-04 khẳng định 100% bệnh nhân nhận thông báo; chính scenario có ngoại lệ SMS thất bại. NFR/TC còn có cách diễn đạt tiền về hoặc thông báo “lập tức”. | Khả thi; Nhất quán | SC-04; FR-09, FR-12; TC-01, TC-06 | **Đồng ý sửa** | Cam kết trong hệ thống là tạo thông báo cho 100% lịch bị ảnh hưởng, ghi kết quả gửi và đưa trường hợp thất bại vào danh sách liên hệ. Tách phát lệnh hoàn, xác nhận của cổng và ngân hàng ghi có. Không cam kết người bệnh thực sự đọc tin hoặc tiền về tức thời. | TV2, TV3; kiểm chứng bằng TC-16, TC-17 và nhật ký giao dịch. |
| **VR-16** | TC-01 thiếu giới tính trong bộ dữ liệu dù FR-02/SC-01 có trường này; TC-03 dùng “hôm nay”; TC-01 đặt SMS dưới 60 giây nhưng FR-03 chưa có ngưỡng đó. | Rõ ràng; Đo lường được | TC-01, TC-03; FR-02, FR-03, FR-06 | **Đồng ý sửa** | Thêm giới tính Nam cho TC-01; cố định TC-03 vào 15/10/2026; 60 giây là ngưỡng dự thảo cần xác nhận. Khảo sát trường bắt buộc ngoài họ tên/SĐT thay vì tự quy định mọi trường đều bắt buộc. | TV2, TV3; đã sửa dữ liệu test tại mục 8.1. |
| **VR-17** | FR-11 có thất bại, hủy giao dịch và hết 15 phút; TC-05 chỉ kiểm tra thanh toán thành công. | Đầy đủ | FR-03, FR-11; SC-01, ngoại lệ 10a/10b | **Đồng ý sửa** | Bổ sung TC-15 cho từng nhánh, kiểm tra không xác nhận lịch, không gửi xác nhận chính thức và giải phóng có điều kiện. | TV3; đặc tả chi tiết tại mục 8.3. |
| **VR-18** | SC-01/FR-11 chưa nói cách xử lý callback thanh toán lặp, sai giao dịch hoặc đến sau khi giữ chỗ hết hạn; FR-12 chưa có kiểm chứng chống hoàn lặp. | Đầy đủ; Khả thi | FR-03, FR-11, FR-12; SC-01, SC-04; CR-01 | **Đồng ý sửa** | Kiến nghị tiêu chí xác thực thông báo theo giao thức cổng, đối chiếu mã/số tiền và xử lý một lần cho cùng giao dịch. Callback muộn không được chiếm lại slot của người khác; đưa khoản tiền vào đối soát theo chính sách cần xác nhận. TC-18 là kiểm chứng bổ sung cho các tiêu chí QA này. | TV2, TV3; đã đặc tả tại mục 8.3 (TC-18). |
| **VR-19** | Mô hình `GiaoDich` trong CR-01 thiếu mã yêu cầu/mã giao dịch hoàn tiền và trạng thái chờ xử lý thủ công, dù SC-04 và FR-12 cần lưu/hiển thị chúng. | Đầy đủ; Nhất quán | CR-01, mô hình dữ liệu; NFR-06; SC-04 | **Đồng ý sửa** | Bổ sung trường phục vụ liên kết lệnh hoàn và phản hồi, trạng thái chờ xử lý thủ công, lỗi và thời điểm xử lý. `ThoiGianHoanTien` để trống trước khi có kết quả hoàn thành; không điền thời điểm giả để đủ cột. | TV2, TV3; đã bổ sung vào Phần 6 và kiểm tra bằng TC-14, TC-16. |
| **VR-20** | G-12 giả định lưu 5 năm, còn NFR-06 để thời gian lưu tối thiểu cần xác nhận. NFR-05 cũng chưa định nghĩa cửa sổ đo uptime và cách loại bảo trì. | Nhất quán; Đo lường được | NFR-05, NFR-06; G-12 | **Đồng ý sửa** | 5 năm tiếp tục là G-12, không biến thành cam kết chính thức. Viết công thức uptime và quy tắc loại bảo trì; thử truy xuất sau khi lịch kết thúc. Kiểm thử chính sách 5 năm chỉ là nhánh có điều kiện cho đến khi được xác nhận. | TV1, TV2; TC-13, TC-14 có phương pháp đo cụ thể. |
| **VR-21** | NFR-04 mới nêu quyền đóng ca/hủy ca/hoàn tiền; chưa có quyền đọc lịch theo bác sĩ, quyền tiếp nhận hoặc quyền xem lịch bệnh nhân khác. G-11 còn nói chẩn đoán nằm ngoài phạm vi. | Đầy đủ; Rõ ràng | NFR-04; G-11; phạm vi EMR | **Đồng ý sửa** | Kiểm thử ngay các quyền quản lý đã đặc tả. Lập câu hỏi quyền đọc/sửa dữ liệu hành chính và danh sách ca; không lấy quyền với bệnh án chuyên sâu làm tiêu chí nghiệm thu hệ thống đặt lịch. | TV1, TV2; TC-12 kiểm tra quyền hiện có; bảng quyền đầy đủ được ghi nhận tại Phần 9. |
| **VR-22** | Phạm vi mục 1.3 Mini-SRS có bác sĩ xem danh sách, chuẩn bị hồ sơ, check-in, đến trễ và khám gấp; FR-01 đến FR-12 chưa đặc tả chức năng xem danh sách ca hoặc check-in. | Đầy đủ; Đúng đắn | N-02, N-03; Mini-SRS, mục 1.3; danh mục FR | **Đồng ý sửa** | Ghi nhận khoảng trống phạm vi: Báo cáo giữ 18 ID hiện có và ghi nhận rõ ràng các chức năng xem ca/check-in thuộc backlog giai đoạn 2 tại mục 9.4; không gán nhu cầu xem ca của bác sĩ vào FR-05. | TV1, TV2; ghi nhận minh bạch tại mục 9.4. |
| **VR-23** | Tài liệu dùng “dễ dàng”, “kịp thời”, “tức thì”, “an toàn”, “bảo mật”, “minh bạch và chính xác” mà không có điều kiện cụ thể. | Rõ ràng; Đo lường được | Tài liệu Vấn đề và phạm vi, Danh mục yêu cầu, Đặc tả tình huống sử dụng, bộ test và CR-01 | **Đồng ý sửa** | Thay câu mang tính đặc tả bằng hành vi, quyền, dữ liệu hoặc ngưỡng tại mục 7.3. Lời nói và nhu cầu stakeholder được giữ làm nguồn, nhưng phải có yêu cầu kiểm chứng riêng. | TV4 phối hợp tác giả từng phần; bảng chuyển đổi áp dụng tại mục 7.3. |
| **VR-24** | Bảng tác động CR-01 mới nêu FR-03, FR-11, FR-12; chưa chỉ ra NFR-06 bản 1.1 và các yêu cầu liên đới. Lịch sử thay đổi chưa có ngày và nội dung theo ID. | Đầy đủ; Nhất quán | CR-01; Mini-SRS, mục 5 và lịch sử phiên bản | **Đồng ý sửa** | Bổ sung tác động dữ liệu/giao dịch lên NFR-06, quyền hoàn tiền lên NFR-04, tra cứu/đặt lịch online và đóng ca/thông báo lên FR liên đới. Chỉ tăng phiên bản yêu cầu có nội dung thay đổi. | TV1, TV2, TV3; bảng truy vết thay đổi chi tiết tại mục 9.3. |
| **VR-25** | Cần xem xét giảm thời gian giữ chỗ 15 phút vì có thể chiếm slot lâu; tài liệu ghi giá trị này là G-05 và có nhánh giải phóng. | Khả thi | FR-11; G-05; SC-01 | **Không sửa** | Giữ 15 phút ở mức giả định kiểm thử. Chưa có số liệu thời gian thanh toán hoặc quy tắc hết hạn của cổng để chọn giá trị khác. Cơ chế hết hạn đã được đặc tả; kiểm chứng bằng TC-15. No-fix không có nghĩa stakeholder đã chấp thuận 15 phút. | TV2/TV3 giữ G-05; xem lại khi có số liệu hoặc cấu hình cổng. |
| **VR-26** | Cần xem xét gửi SMS ngay trong giao dịch lưu lịch thay cho hàng đợi bất đồng bộ của SC-01. | Khả thi | SC-01, bước 12; FR-03, FR-09 | **Không sửa** | Giữ gửi bất đồng bộ. Lưu lịch không cần chờ mạng SMS; TC-17 kiểm tra lỗi gửi được ghi nhận, còn lịch/giao dịch vẫn tồn tại. Tránh làm tăng thời gian phản hồi giao diện vi phạm NFR-01. | TV3 giữ mô tả thiết kế bất đồng bộ. |
| **VR-27** | SC-01/SC-04 nói gửi SMS và Email nhưng biểu mẫu và dữ liệu TC-01/TC-05 không có địa chỉ email. FR-03/FR-09 dùng SMS/Email, chưa thống nhất gửi một kênh hay cả hai. | Nhất quán; Đầy đủ | FR-03, FR-09; SC-01, SC-04; biểu mẫu bệnh nhân | **Đồng ý sửa** | Thống nhất: SMS là kênh kiểm thử bắt buộc cơ sở; Email chỉ gửi khi bệnh nhân có điền địa chỉ hợp lệ. | TV2, TV3; đã thống nhất trong catalogue, biểu mẫu và test. |

---

### 7.3. Bảng rà soát và chuyển đổi các thuật ngữ định tính mơ hồ

| Thuật ngữ mơ hồ ban đầu | Vị trí xuất hiện | Câu văn / Ngưỡng đo lường định lượng thay thế chuẩn hóa |
| :--- | :--- | :--- |
| *"Đặt lịch nhanh chóng, không chờ lâu"* | Mục tiêu hệ thống; Nhu cầu `STK-01` | *"Ít nhất 95% thao tác tra cứu và gửi đặt lịch nhận được phản hồi trong vòng $\le 2,0\text{ giây}$ (theo `NFR-01`)."* |
| *"Giao diện thuận tiện, dễ sử dụng"* | Nhu cầu `STK-04` | *"Bệnh nhân hoàn tất quy trình đặt lịch trong $\le 5$ bước thao tác trên giao diện web mà không cần đăng ký tài khoản trước."* |
| *"Đảm bảo an toàn thông tin tuyệt đối"* | Mô tả bảo mật tra cứu | *"Bảo vệ bằng mã OTP 6 chữ số gửi qua SMS, hiệu lực 180 giây, tự động khóa phiên sau 3 lần nhập sai liên tiếp (theo `NFR-03`)."* |
| *"Khung giờ lập tức hiển thị màu xanh"* | `TC-03` ban đầu | *"Khung giờ chuyển trạng thái từ 'Không khả dụng' sang 'Khả dụng' trong CSDL và cho phép bấm đặt ở lần tải lại trang tiếp theo."* |
| *"Cập nhật tức thì theo thời gian thực"* | Hậu điều kiện `SC-03` | *"Dữ liệu thay đổi được lưu ngay vào CSDL và đồng bộ tới màn hình điều phối của bác sĩ/nhân viên với độ trễ $\le 1,0\text{ giây}$."* |
| *"100% bệnh nhân nhận thông báo kịp thời"*| Hậu điều kiện `SC-04` | *"Hệ thống phát lệnh gửi tin đến 100% số điện thoại bị ảnh hưởng trong vòng 60 giây; ghi nhận cờ lỗi với các trường hợp gửi thất bại."* |
| *"Tự động hoàn tiền ngay lập tức"* | `SC-04`; Mô tả CR-01 | *"Hệ thống tự động phát lệnh gọi API sang cổng thanh toán trong vòng $\le 30\text{ giây}$ sau khi Quản lý xác nhận đóng ca trực (theo `FR-12`)."* |
| *"Tiền về tài khoản trong 1–3 ngày"* | `SC-04`; Rủi ro 1 | *"Thời gian tiền về tài khoản thực tế phụ thuộc quy định đối soát của ngân hàng phát hành thẻ (thường từ 24h–72h làm việc)."* |
| *"Đường link phòng khám online bảo mật"* | `TC-05` | *"Đường link phòng họp video được sinh tự động với chuỗi mã hóa ngẫu nhiên 128-bit và mật khẩu truy cập dùng một lần."* |

---

# PHẦN 8: BỘ KỊCH BẢN KIỂM THỬ ĐẶC TẢ

### 8.1. Bộ kịch bản kiểm thử nghiệp vụ cơ sở

#### TC-01: Kiểm thử đặt lịch khám trực tiếp thành công với dữ liệu hợp lệ
* **Mã kiểm thử:** `TC-01`
* **Requirement ID liên kết:** `FR-01`, `FR-02`, `FR-03`
* **Mục tiêu kiểm thử:** Xác minh người dùng có thể tra cứu khung giờ khả dụng, điền thông tin hợp lệ và hoàn tất quy trình đặt lịch khám trực tiếp thành công.
* **Tiền điều kiện:** Bác sĩ Nguyễn Văn A (Chuyên khoa Nội) có khung giờ `08:30 - 08:45` ngày `15/10/2026` ở trạng thái "Khả dụng".
* **Dữ liệu kiểm thử (Test Data):**
  * Chuyên khoa: Nội tổng quát | Bác sĩ: BS. Nguyễn Văn A | Thời gian: `08:30 - 08:45`, Ngày `15/10/2026`.
  * Bệnh nhân: Họ tên: "Trần Văn An", SĐT: "0912345678", Ngày sinh: "12/05/1990", Giới tính: "Nam", Triệu chứng: "Đau đầu, sốt nhẹ 2 ngày".
* **Các bước thực hiện:**
  1. Truy cập vào trang web đặt lịch, chọn hình thức "Khám trực tiếp tại phòng khám".
  2. Chọn chuyên khoa "Nội tổng quát", chọn bác sĩ "Nguyễn Văn A".
  3. Chọn ngày `15/10/2026`, nhấn chọn khung giờ `08:30 - 08:45`.
  4. Nhập đầy đủ thông tin bệnh nhân theo dữ liệu kiểm thử.
  5. Bấm nút "Xác nhận đặt lịch".
* **Kết quả kỳ vọng:**
  * Hệ thống lưu lịch hẹn thành công, gán mã lịch hẹn duy nhất (VD: `AT-151001`), hiển thị thông báo đặt lịch thành công.
  * Khung giờ `08:30 - 08:45` ngày `15/10/2026` của BS. Nguyễn Văn A chuyển sang trạng thái bị khóa (disabled) trên giao diện đặt lịch.
  * Tổng đài SMS gửi tin nhắn xác nhận lịch hẹn đến số điện thoại `0912345678` trong vòng dưới 60 giây.

#### TC-02: Kiểm thử ngăn chặn đặt lịch hẹn trùng lặp trên cùng một khung giờ
* **Mã kiểm thử:** `TC-02`
* **Requirement ID liên kết:** `FR-10`
* **Mục tiêu kiểm thử:** Xác minh hệ thống phát hiện và chặn đứng trường hợp một số điện thoại cố tình đặt hai lịch hẹn khác nhau trong cùng một khung giờ khám bệnh.
* **Tiền điều kiện:** Số điện thoại `0912345678` đã có một lịch hẹn hợp lệ ở khung giờ `09:00 - 09:15` ngày `15/10/2026` tại phòng khám.
* **Dữ liệu kiểm thử (Test Data):**
  * SĐT kiểm tra: `0912345678`.
  * Khung giờ đặt mới: `09:00 - 09:15` ngày `15/10/2026` (chọn bác sĩ thuộc chuyên khoa khác).
* **Các bước thực hiện:**
  1. Mở giao diện đặt lịch, chọn một bác sĩ khác.
  2. Chọn khung giờ khám `09:00 - 09:15` ngày `15/10/2026`.
  3. Điền thông tin cá nhân với số điện thoại `0912345678`.
  4. Bấm nút "Xác nhận đặt lịch".
* **Kết quả kỳ vọng:**
  * Hệ thống từ chối lưu lịch hẹn mới vào CSDL.
  * Hiển thị thông báo lỗi rõ ràng trên màn hình: *"Số điện thoại này đã có lịch hẹn trong khung giờ được chọn. Vui lòng kiểm tra lại!"*.
  * Hệ thống không gửi bất kỳ SMS xác nhận mới nào.

#### TC-03: Kiểm thử bệnh nhân tự hủy lịch hẹn trước 2 tiếng và kiểm tra giải phóng khung giờ
* **Mã kiểm thử:** `TC-03`
* **Requirement ID liên kết:** `FR-04`, `FR-05`, `FR-07`, `NFR-03`
* **Mục tiêu kiểm thử:** Xác minh bệnh nhân có thể xác thực OTP và tự hủy lịch hẹn khi thực hiện trước giờ khám $\ge 2$ tiếng, hệ thống tự động mở lại khung giờ trống cho người khác.
* **Tiền điều kiện:** Có lịch hẹn mã `AT-998877` với SĐT `0987654321` vào lúc `14:00` ngày `15/10/2026`. Thời điểm thực hiện test là `10:00` sáng cùng ngày (cách giờ khám 4 tiếng, thỏa mãn điều kiện $\ge 2$ tiếng [G-06]). Ca trực của bác sĩ vẫn đang mở bình thường.
* **Dữ liệu kiểm thử (Test Data):** Mã lịch hẹn: `AT-998877` | SĐT: `0987654321` | Mã OTP xác thực: `123456` | Lý do hủy: "Bận công việc đột xuất".
* **Các bước thực hiện:**
  1. Truy cập chức năng "Tra cứu lịch hẹn", nhập mã `AT-998877` và SĐT `0987654321`, nhấn "Tiếp tục".
  2. Hệ thống gửi mã OTP về số điện thoại; nhập mã OTP `123456` và nhấn "Xác thực".
  3. Tại màn hình thông tin chi tiết ca khám, bấm chọn nút "Hủy lịch hẹn".
  4. Chọn lý do hủy và nhấn nút "Xác nhận hủy lịch".
  5. Sử dụng một trình duyệt web khác/tab ẩn danh truy cập vào trang đặt lịch của bác sĩ đó ngày `15/10/2026`.
* **Kết quả kỳ vọng:**
  * Trạng thái lịch hẹn `AT-998877` chuyển thành "Đã hủy bởi bệnh nhân".
  * Bệnh nhân nhận được tin nhắn SMS xác nhận đã hủy lịch hẹn thành công.
  * Khung giờ `14:00 - 14:15` của bác sĩ lập tức hiển thị ở trạng thái "Khả dụng" trên trình duyệt thứ hai, cho phép bệnh nhân khác bấm đặt bình thường.

#### TC-04: Kiểm thử hiệu năng thời gian phản hồi khi tra cứu lịch trống
* **Mã kiểm thử:** `TC-04`
* **Requirement ID liên kết:** `NFR-01`
* **Mục tiêu kiểm thử:** Đo lường thời gian phản hồi của hệ thống khi có 30 phiên đồng thời (cơ sở) và 100 Virtual Users (mở rộng) thực hiện tra cứu danh sách khung giờ trống của các bác sĩ.
* **Tiền điều kiện:** Máy chủ kiểm thử được cấu hình môi trường tiệm cận thực tế; cơ sở dữ liệu đã nạp sẵn dữ liệu của 06 bác sĩ và 120 lịch hẹn mẫu.
* **Dữ liệu kiểm thử (Test Data):** Kịch bản kiểm thử tải (Apache JMeter script) giả lập 30 phiên và 100 Virtual Users truy cập đồng thời API `/api/doctors/{id}/available-slots` trong thời gian Ramp-up 10 giây.
* **Các bước thực hiện:**
  1. Khởi động công cụ kiểm thử tải Apache JMeter.
  2. Kích hoạt kịch bản kiểm thử gửi truy vấn đồng thời liên tục trong 60 giây.
  3. Trích xuất báo cáo Aggregate Report từ JMeter.
* **Kết quả kỳ vọng:**
  * 100% yêu cầu được xử lý thành công, tỷ lệ mã lỗi HTTP (Error Rate) bằng 0,0%.
  * Thời gian phản hồi trung bình đạt $\le 2,0\text{ giây}$, phân vị 95 (95th Percentile) không vượt quá 2,0 giây tại tải 30 phiên đồng thời; ít nhất 95% request hoàn tất phản hồi trong vòng $\le 2.000\text{ ms}$ (thỏa mãn tiêu chí kiểm chứng của `NFR-01`).

#### TC-05: Kiểm thử luồng đặt lịch khám trực tuyến và thanh toán qua cổng điện tử thành công
* **Mã kiểm thử:** `TC-05`
* **Requirement ID liên kết:** `FR-01`, `FR-02`, `FR-03`, `FR-11`, `NFR-06`
* **Mục tiêu kiểm thử:** Xác minh dịch vụ khám trực tuyến chỉ cấp mã xác nhận lịch hẹn sau khi người dùng thực hiện thanh toán trực tuyến thành công qua cổng thanh toán giả lập.
* **Tiền điều kiện:** Tài khoản thử nghiệm (Sandbox) của cổng thanh toán VNPay hoạt động bình thường; bác sĩ có khung giờ khám online còn trống.
* **Dữ liệu kiểm thử (Test Data):** Hình thức khám: Khám trực tuyến | Phí khám: `150.000 VNĐ` [G-04] | Thông tin thẻ Sandbox NCB: `9704198526191432198`, Tên: `NGUYEN VAN A`, OTP: `123456`.
* **Các bước thực hiện:**
  1. Đặt lịch khám và chọn hình thức "Khám trực tuyến".
  2. Chọn khung giờ, điền thông tin bệnh nhân và bấm "Tiến hành thanh toán".
  3. Hệ thống chuyển hướng sang trang thanh toán VNPay Sandbox.
  4. Nhập thông tin thẻ Sandbox và mã OTP xác thực giao dịch hợp lệ.
  5. Nhấn "Xác nhận thanh toán" và chờ cổng thanh toán điều hướng trở lại web phòng khám.
* **Kết quả kỳ vọng:**
  * Hệ thống nhận được tín hiệu Webhook thanh toán thành công, hiển thị màn hình: "Thanh toán thành công & Xác nhận lịch khám trực tuyến".
  * Bản ghi trong bảng `GiaoDich` lưu trạng thái "Đã thanh toán" với đầy đủ mã đối soát.
  * Bản ghi lịch hẹn lưu trạng thái "Đã xác nhận", tự sinh một đường link phòng khám trực tuyến bảo mật.
  * Bệnh nhân nhận được tin nhắn SMS xác nhận kèm link phòng khám online.

#### TC-06: Kiểm thử tự động phát lệnh hoàn tiền khi Quản lý hủy ca trực bác sĩ khám online
* **Mã kiểm thử:** `TC-06`
* **Requirement ID liên kết:** `FR-08`, `FR-09`, `FR-12`, `NFR-06`
* **Mục tiêu kiểm thử:** Xác minh khi Quản lý phòng khám kích hoạt lệnh hủy ca trực của bác sĩ, hệ thống tự động kích hoạt API hoàn tiền 100% cho bệnh nhân khám online và gửi SMS thông báo giải thích.
* **Tiền điều kiện:** Trong ca trực chiều ngày `15/10/2026` của BS. Lê Thị B có 01 lịch khám online của bệnh nhân `0911223344` đã thanh toán thành công số tiền `150.000 VNĐ` (Mã GD: `GD-888999`).
* **Dữ liệu kiểm thử (Test Data):** Tài khoản đăng nhập: Quản lý phòng khám (`admin_antam`) | Lý do hủy ca: "Bác sĩ có lịch mổ cấp cứu đột xuất tại bệnh viện tuyến trên".
* **Các bước thực hiện:**
  1. Đăng nhập tài khoản Quản lý, vào mục "Quản lý ca trực bác sĩ".
  2. Chọn ca trực chiều ngày `15/10/2026` của BS. Lê Thị B, bấm nút "Báo nghỉ đột xuất".
  3. Nhập lý do nghỉ và nhấn nút "Xác nhận đóng ca trực & Hoàn tiền".
  4. Kiểm tra nhật ký giao dịch và hộp thư SMS của bệnh nhân `0911223344`.
* **Kết quả kỳ vọng:**
  * Hệ thống gọi thành công API hoàn tiền của VNPay, nhận mã hoàn tiền thành công từ cổng thanh toán.
  * Bản ghi giao dịch `GD-888999` chuyển trạng thái sang "Đã hoàn tiền".
  * Lịch hẹn chuyển sang trạng thái "Bị hủy bởi phòng khám".
  * Thuê bao `0911223344` nhận được tin nhắn SMS Brandname nêu rõ: Lời xin lỗi của phòng khám, lý do bác sĩ hủy ca, thông báo hoàn trả 100% số tiền 150.000 VNĐ và kèm đường link ưu tiên dời lịch khám.

---

### 8.2. Bộ kịch bản kiểm thử mở rộng và kiểm tra biên chi tiết

#### TC-07: Từ chối dữ liệu đăng ký thiếu hoặc sai định dạng
* **Requirement ID:** `FR-02`, `FR-06`
* **Scenario:** `SC-01`, ngoại lệ 6a
* **Nguồn review:** VR-04, VR-16 | **Change Request:** Không áp dụng
* **Tiền điều kiện:** BS. Nguyễn Văn A có slot 08:30-08:45 ngày 15/10/2026 khả dụng. Dữ liệu hợp lệ gồm Trần Văn An, SĐT `0912345678`, ngày sinh 12/05/1990, giới tính Nam, triệu chứng “Đau đầu, sốt nhẹ 2 ngày”.
* **Dữ liệu theo nhánh kiểm thử:**
  * Nhánh A: Bỏ trống Họ và tên.
  * Nhánh B: Bỏ trống Số điện thoại.
  * Nhánh C: SĐT chỉ có 9 chữ số (`091234567`).
  * Nhánh D: SĐT có 11 chữ số (`09123456789`).
  * Nhánh E: SĐT có 10 ký tự nhưng chứa chữ cái (`091234567A`).
* **Các bước thực hiện:**
  1. Nạp lại dữ liệu slot và ghi nhận số lịch hiện có trong CSDL.
  2. Mở biểu mẫu đặt lịch, nhập một bộ dữ liệu theo từng nhánh kiểm thử.
  3. Gửi yêu cầu đặt lịch bằng giao diện web; kiểm tra phía backend cũng từ chối dữ liệu tương ứng.
  4. Đối chiếu bản ghi lịch, trạng thái slot và nhật ký gửi SMS xác nhận.
  5. Sửa thành dữ liệu hợp lệ và gửi lại.
* **Kết quả kỳ vọng:** Các nhánh A, B, C, D, E đều bị chặn tạo lịch, không chiếm slot, không gửi SMS; trường dữ liệu lỗi được đánh dấu đỏ kèm câu thông báo lỗi cụ thể. Khi sửa lại dữ liệu hợp lệ, hệ thống tạo đúng một bản ghi lịch hẹn theo `FR-02`.
* **Bằng chứng cần thu:** Phản hồi lỗi giao diện, ảnh chụp trường bị đánh dấu đỏ, log API trả về HTTP 400 Bad Request và nhật ký thông báo.

#### TC-08: Khung giờ hết khả dụng và tranh chấp một slot giữa hai phiên
* **Requirement ID:** `FR-01`, `FR-02`
* **Scenario:** `SC-01`, ngoại lệ 4a; `SC-02`
* **Nguồn review:** VR-05, VR-06 | **Change Request:** CR-01 đối với nhánh slot đang giữ chỗ thanh toán
* **Tiền điều kiện:** Hai phiên A và B cùng mở màn hình đặt lịch vào cùng slot `09:00 - 09:15` của BS. Nguyễn Văn A ngày `15/10/2026`. Hai bệnh nhân dùng số điện thoại khác nhau.
* **Các bước thực hiện:**
  1. Phiên A bấm xác nhận đặt chỗ trước; Phiên B bấm xác nhận ngay sau đó 1 giây.
  2. Kiểm tra phiên A tạo lịch thành công; kiểm tra phiên B nhận phản hồi slot không còn khả dụng.
  3. Kiểm tra giao diện phiên B xuất hiện modal popup gợi ý 3 slot còn trống gần nhất của bác sĩ đó (`SC-02`).
  4. Phiên B chọn một slot trống được gợi ý và tiếp tục hoàn tất đặt lịch.
  5. Lặp lại kiểm thử với slot bị quản lý khóa do bác sĩ nghỉ và slot đang giữ chỗ thanh toán online 15 phút.
* **Kết quả kỳ vọng:** Không tạo thêm lịch vào slot đã chiếm, bị khóa hoặc còn thời hạn giữ chỗ. Tại một khung giờ chỉ có tối đa một lịch hẹn còn hiệu lực. Phiên B được hướng dẫn chuyển sang slot khác mà không phát sinh lỗi hệ thống.
* **Bằng chứng cần thu:** Mã phản hồi của phiên A/B, số lịch theo bác sĩ/slot trong CSDL, trạng thái slot sau khi làm mới.

#### TC-09: Xác thực OTP kiểm tra hết hạn 180 giây và khóa phiên sau 3 lần sai
* **Requirement ID:** `FR-04`, `NFR-03`
* **Scenario:** `SC-03`, bước 1–4 và ngoại lệ 1a/3a
* **Nguồn review:** VR-06, VR-13 | **Change Request:** Không áp dụng
* **Tiền điều kiện:** Lịch hẹn `AT-998877`, SĐT `0987654321`; dịch vụ SMS phát OTP `123456` lúc 10:00:00 ngày 15/10/2026 (hiệu lực 180 giây [G-07]). Trước xác thực, người dùng không có quyền xem chi tiết hoặc đổi/hủy lịch.
* **Các bước thực hiện theo nhánh:**
  1. *Nhánh A:* Nhập sai Mã lịch hẹn hoặc SĐT $\rightarrow$ Hệ thống báo không tìm thấy thông tin.
  2. *Nhánh B (Xác thực hợp lệ trước hạn):* Dùng đúng mã/SĐT, nhập OTP `123456` tại thời điểm 10:02:59 (giây thứ 179) $\rightarrow$ Xác thực thành công, hiển thị chi tiết ca khám.
  3. *Nhánh C (Hết hạn):* Nạp lại phiên, nhập OTP đúng tại 10:03:01 (giây thứ 181) $\rightarrow$ Hệ thống từ chối với thông báo mã OTP đã hết hạn.
  4. *Nhánh D (Khóa phiên sau 3 lần sai):* Nạp lại phiên, nhập sai lần 1 (`000000`), lần 2 (`111111`), lần 3 (`222222`). Sau lần 3, nhập lại OTP đúng `123456`.
* **Kết quả kỳ vọng:** Nhánh D khóa ngay phiên xác thực sau lần nhập sai thứ 3; việc nhập đúng OTP sau đó trong phiên cũ bị từ chối; người dùng bắt buộc phải bấm gửi lại mã OTP mới để tạo phiên mới.
* **Bằng chứng cần thu:** Timestamp gửi/xác thực, phản hồi từng lần nhập, trạng thái khóa phiên trong CSDL.

#### TC-10: Đổi hoặc hủy lịch tại mốc biên 120 phút và bảo toàn lịch cũ khi đổi thất bại
* **Requirement ID:** `FR-04`, `FR-05`, `FR-07`
* **Scenario:** `SC-03`, nhánh hủy, nhánh đổi và ngoại lệ khung giờ mới bị chiếm
* **Nguồn review:** VR-10, VR-14 | **Change Request:** Không áp dụng cho bộ dữ liệu trực tiếp này
* **Tiền điều kiện:** Lịch hẹn trực tiếp `AT-998877` lúc 14:00 ngày 15/10/2026; bệnh nhân đã xác thực OTP thành công. Slot 15:00-15:15 cùng bác sĩ còn trống; ca trực đang hoạt động bình thường.
* **Các bước và kết quả kỳ vọng theo nhánh biên:**
  * *Nhánh A (Đúng 120 phút):* Gửi yêu cầu hủy lúc 12:00:00 (cách đúng 120 phút [G-06]) $\rightarrow$ Hệ thống cho phép hủy; lịch chuyển sang "Đã hủy bởi bệnh nhân"; mở lại slot 14:00 thành "Khả dụng".
  * *Nhánh B (Dưới 120 phút):* Gửi yêu cầu hủy lúc 12:00:01 (còn 119 phút 59 giây) $\rightarrow$ Hệ thống từ chối tự hủy, làm mờ nút hủy, lịch và slot giữ nguyên, hiển thị hotline lễ tân.
  * *Nhánh C (Đổi lịch hợp lệ):* Gửi yêu cầu đổi sang 15:00 lúc 12:00:00 $\rightarrow$ Hệ thống cho đổi; cập nhật giờ mới 15:00; khóa slot 15:00, giải phóng slot cũ 14:00; gửi SMS giờ mới.
  * *Nhánh D (Đổi lịch trễ):* Gửi yêu cầu đổi lúc 12:00:01 $\rightarrow$ Từ chối đổi tự động, giữ nguyên lịch cũ.
  * *Nhánh E (Slot mới vừa bị người khác chiếm):* Chọn đổi sang 15:00, nhưng phiên khác chiếm slot trước khi bấm lưu $\rightarrow$ Hệ thống từ chối lưu đổi, giữ nguyên lịch cũ lúc 14:00, không giải phóng slot cũ, yêu cầu chọn lại.
* **Bằng chứng cần thu:** Thời gian máy chủ chính xác, phản hồi HTTP, trạng thái lịch và slot trước/sau thao tác.

#### TC-11: Kiểm thử 30 phiên đồng thời không gây mất hoặc thừa lịch
* **Requirement ID:** `FR-01`, `FR-02`, `FR-10`, `NFR-02`
* **Scenario:** `SC-01`, ngoại lệ trùng lịch; `SC-02`
* **Nguồn review:** VR-06, VR-08 | **Change Request:** CR-01 ở phần kiểm tra hồi quy slot giữ chỗ
* **Tiền điều kiện:** 6 bác sĩ và 120 lịch mẫu; có đủ slot riêng cho các lượt đặt hợp lệ. Áp dụng ngưỡng 30 phiên của `NFR-02`.
* **Các bước thực hiện:**
  1. Khởi tạo 30 phiên đồng thời; 10 phiên tra cứu, 20 phiên gửi đặt lịch vào 20 slot riêng bằng 20 SĐT khác nhau.
  2. Ghi nhận phản hồi từng yêu cầu và đối chiếu với 20 bản ghi lịch được tạo trong CSDL.
  3. Nạp lại dữ liệu, cho 5 phiên dùng các SĐT khác nhau cùng gửi đặt vào duy nhất một khung giờ trống.
  4. Nạp lại dữ liệu, dùng cùng một SĐT gửi đặt lịch ở 2 bác sĩ khác nhau trong cùng khung giờ để kiểm tra `FR-10`.
* **Kết quả kỳ vọng:** Pha slot riêng tạo thành công đúng 20 lịch, không mất bản ghi nào. Pha tranh chấp chỉ có duy nhất 1 lịch được chấp nhận, 4 phiên còn lại nhận lỗi slot đã kín. Pha cùng SĐT chỉ có 1 lịch thành công, yêu cầu thứ hai bị chặn do trùng lịch (`FR-10`).
* **Bằng chứng cần thu:** Số phiên đồng thời, danh sách request/response log, mã lịch được tạo, truy vấn đối chiếu CSDL.

#### TC-12: Phân quyền vai trò người dùng khi đóng ca, hủy ca và xử lý hoàn tiền
* **Requirement ID:** `FR-08`, `FR-12`, `NFR-04`
* **Scenario:** `SC-04`, tiền điều kiện và bước 3–6
* **Nguồn review:** VR-06, VR-21 | **Change Request:** CR-01 đối với quyền kích hoạt hoàn tiền
* **Tiền điều kiện:** Ca chiều 15/10/2026 của BS. Lê Thị B có lịch trực tuyến đã thanh toán. Có 4 tài khoản thử nghiệm: Bệnh nhân (chưa/đã login), Nhân viên tiếp nhận, Bác sĩ và Quản lý phòng khám (Admin).
* **Các bước thực hiện:**
  1. Dùng phiên Bệnh nhân, tài khoản Bác sĩ và tài khoản Tiếp nhận gửi request trực tiếp đến các endpoint API: `/api/admin/shifts/close`, `/api/admin/shifts/cancel-all`, `/api/admin/refunds/trigger`.
  2. Kiểm tra mã phản hồi HTTP trả về và trạng thái ca trực trong CSDL.
  3. Đăng nhập bằng tài khoản Quản lý phòng khám (Admin) và thực hiện lại cùng các thao tác trên giao diện điều hành.
* **Kết quả kỳ vọng:** 100% các yêu cầu từ Bệnh nhân, Bác sĩ, Tiếp nhận đều bị máy chủ từ chối với mã HTTP 403 Forbidden; ca trực không bị đóng và không phát sinh lệnh hoàn tiền. Tài khoản Quản lý thực hiện thành công toàn bộ quy trình `SC-04`.
* **Bằng chứng cần thu:** Role của từng token/phiên, mã lỗi HTTP 403, nhật ký bảo mật truy cập trái quyền (Audit Log).

#### TC-13: Đo lường độ khả dụng hệ thống theo chu kỳ tháng
* **Requirement ID:** `NFR-05`
* **Scenario:** `SC-01`, `SC-03`, `SC-04`
* **Nguồn review:** VR-06, VR-20 | **Change Request:** Không áp dụng
* **Tiền điều kiện:** Hệ thống đã triển khai trên máy chủ staging/production; kích hoạt công cụ giám sát dịch vụ (Prometheus / Uptime Kuma) gửi ping kiểm tra tình trạng sống (Health check) mỗi 60 giây.
* **Các bước thực hiện:**
  1. Thiết lập giám sát liên tục các endpoint chính (trang chủ, API tra cứu lịch, API đặt lịch) trong chu kỳ 30 ngày (tổng thời gian $T = 43.200\text{ phút}$).
  2. Ghi nhận các khoảng thời gian bảo trì có thông báo trước ($M$) và các khoảng gián đoạn sự cố ngoài kế hoạch ($D$).
  3. Áp dụng công thức tính Uptime: $\text{Uptime} = \frac{T - M - D}{T - M} \times 100\%$.
  4. Đối chiếu với ngưỡng cam kết $\ge 99,5\%$ của `NFR-05`.
* **Kết quả kỳ vọng:** Tỷ lệ Uptime đạt $\ge 99,5\%$ (tương ứng thời gian gián đoạn ngoài kế hoạch không quá 216 phút trong cả tháng).
* **Bằng chứng cần thu:** Báo cáo xuất từ Uptime Kuma/Prometheus, nhật ký bảo trì và bảng tính Uptime tháng.

#### TC-14: Lưu trữ và bảo toàn dữ liệu lịch hẹn, thanh toán và hoàn tiền
* **Requirement ID:** `FR-11`, `FR-12`, `NFR-06`
* **Scenario:** `SC-01`, nhánh online; `SC-04`, nhánh hoàn tiền
* **Nguồn review:** VR-06, VR-19, VR-20 | **Change Request:** CR-01
* **Tiền điều kiện:** Một lịch online có mã giao dịch `GD-888999`, số tiền 150.000 VNĐ [G-04]; cổng thanh toán trả về mã giao dịch và mã hoàn tiền.
* **Các bước thực hiện:**
  1. Bệnh nhân thanh toán online thành công $\rightarrow$ Kiểm tra các trường dữ liệu lưu trong bảng `GiaoDich`: `MaGiaoDich`, `MaLichHen`, `SoTien`, `PhuongThucThanhToan`, `TrangThaiThanhToan`, `MaGiaoDichCongTT`, `ThoiGianThanhToan`.
  2. Kiểm tra trường `ThoiGianHoanTien` ban đầu phải để giá trị `NULL` (không điền thời gian giả).
  3. Quản lý đóng ca, kích hoạt hoàn tiền thành công $\rightarrow$ Kiểm tra CSDL cập nhật `TrangThaiThanhToan = 'Đã hoàn tiền'`, ghi nhận `ThoiGianHoanTien` và `MaGiaoDichHoanTien`.
  4. Khởi động lại dịch vụ cơ sở dữ liệu và máy chủ backend; sau đó truy vấn lại bản ghi lịch hẹn và giao dịch.
* **Kết quả kỳ vọng:** 100% dữ liệu lịch hẹn và giao dịch tài chính được bảo toàn toàn vẹn sau khi khởi động lại; không có bản ghi nào bị mất mát hay sai lệch số tiền; sẵn sàng đáp ứng chính sách lưu trữ an toàn tối thiểu 05 năm phục vụ thanh tra và đối soát kế toán [G-12].
* **Bằng chứng cần thu:** Bản ghi CSDL trước và sau khi hoàn tiền, log khởi động lại CSDL, mã truy vấn SQL đối chiếu.

#### TC-15: Ngoại lệ thanh toán thất bại, hủy giao dịch và hết hạn giữ chỗ 15 phút
* **Requirement ID:** `FR-01`, `FR-03`, `FR-08`, `FR-11`
* **Scenario:** `SC-01`, ngoại lệ 10a/10b; `SC-04` khi ca bị đóng
* **Nguồn review:** VR-10, VR-17, VR-25 | **Change Request:** CR-01
* **Tiền điều kiện:** Bệnh nhân thực hiện đặt lịch khám trực tuyến, hệ thống tạm giữ slot từ 10:00:00 ngày 15/10/2026 (áp dụng thời hạn 15 phút [G-05]).
* **Các bước và kết quả kỳ vọng theo nhánh:**
  * *Nhánh A (Cổng báo thanh toán thất bại):* Người dùng nhập sai thẻ $\rightarrow$ Cổng trả mã lỗi $\rightarrow$ Hệ thống hủy giữ chỗ, mở lại slot thành "Khả dụng", không gửi SMS xác nhận lịch.
  * *Nhánh B (Người dùng hủy giao dịch):* Người dùng bấm "Hủy thanh toán" trên cổng TT $\rightarrow$ Hệ thống giải phóng slot về "Khả dụng", thông báo giao dịch chưa hoàn tất.
  * *Nhánh C (Quá hạn 15 phút):* Không có phản hồi từ cổng TT. Tại 10:14:59 slot vẫn bị khóa. Tại 10:15:00, tiến trình nền quét và tự động chuyển slot về "Khả dụng", hủy đơn đặt.
  * *Nhánh D (Ca bị đóng trong lúc chờ thanh toán):* Trong khi slot đang giữ chỗ, Quản lý đóng ca trực $\rightarrow$ Khi hết hạn 15 phút, slot vẫn giữ nguyên trạng thái bị khóa do bác sĩ nghỉ (không được mở lại ca đã đóng [VR-10]).
* **Bằng chứng cần thu:** Timestamp giữ chỗ/giải phóng slot, mã phản hồi cổng thanh toán, nhật ký tiến trình nền tự động quét hết hạn.

#### TC-16: Ngoại lệ hoàn tiền gặp lỗi kết nối hoặc quá thời gian chờ khi đóng ca trực
* **Requirement ID:** `FR-07`, `FR-08`, `FR-09`, `FR-12`, `NFR-06`
* **Scenario:** `SC-04`, ngoại lệ hoàn tiền
* **Nguồn review:** VR-10, VR-15, VR-19 | **Change Request:** CR-01
* **Tiền điều kiện:** Ca chiều của BS. Lê Thị B có lịch online đã thanh toán 150.000 VNĐ (`GD-888999`). Cổng thanh toán giả lập được cấu hình để trả về lỗi 504 Gateway Timeout hoặc lỗi từ chối hoàn tiền.
* **Các bước thực hiện:**
  1. Quản lý thực hiện báo nghỉ đột xuất và xác nhận đóng ca trực.
  2. Hệ thống phát lệnh gọi API hoàn tiền sang cổng thanh toán; cổng thanh toán bị timeout hoặc trả về lỗi kết nối.
  3. Kiểm tra trạng thái ca trực, trạng thái các lịch hẹn và trạng thái bản ghi trong bảng `GiaoDich`.
  4. Kiểm tra giao diện Quản lý phòng khám và nội dung tin nhắn SMS gửi đến bệnh nhân.
* **Kết quả kỳ vọng:** Ca trực vẫn bị đóng và lịch hẹn vẫn bị hủy thành công; giao dịch tài chính tự động chuyển sang trạng thái "Chờ xử lý hoàn tiền thủ công" kèm thông báo cảnh báo đỏ trên màn hình Quản lý; tin nhắn SMS thông báo cho bệnh nhân giải thích ca bị hủy và khoản tiền đang được bộ phận kế toán liên hệ đối soát thủ công.
* **Bằng chứng cần thu:** Mã lỗi timeout, bản ghi giao dịch ở trạng thái chờ thủ công, cảnh báo đỏ trên UI Quản lý, nội dung SMS.

#### TC-17: Ngoại lệ dịch vụ viễn thông gửi thông báo thất bại
* **Requirement ID:** `FR-03`, `FR-08`, `FR-09`
* **Scenario:** `SC-01`, bước gửi xác nhận; `SC-04`, ngoại lệ SMS
* **Nguồn review:** VR-15, VR-26, VR-27 | **Change Request:** CR-01
* **Tiền điều kiện:** Ca trực bị đóng có 4 lịch hẹn hợp lệ (2 trực tiếp, 2 online). Dịch vụ viễn thông giả lập được cấu hình để gửi thành công 3 tin nhắn SMS và trả về lỗi mạng cho 1 số thuê bao.
* **Các bước thực hiện:**
  1. Quản lý xác nhận đóng ca trực; hệ thống đẩy 4 tin nhắn SMS vào hàng đợi gửi tin.
  2. Dịch vụ SMS thực hiện gửi tin và trả về kết quả theo cấu hình tiền điều kiện.
  3. Kiểm tra nhật ký gửi tin nhắn SMS trên hệ thống và danh sách hiển thị trên màn hình tiếp nhận tại quầy.
* **Kết quả kỳ vọng:** Luồng đóng ca và hủy lịch hoàn tất trọn vẹn, không bị gián đoạn bởi lỗi SMS; 3 tin nhắn thành công ghi nhận trạng thái "Đã gửi"; 1 tin nhắn lỗi được đánh dấu cờ "Chưa gửi được SMS" và tự động hiển thị vào danh sách các ca cần nhân viên lễ tân gọi điện thoại trực tiếp.
* **Bằng chứng cần thu:** Bảng log tin nhắn SMS, cờ cảnh báo lỗi gửi tin trên màn hình lễ tân.

#### TC-18: Phòng chống thông báo thanh toán gửi lặp lại
* **Requirement ID:** `FR-03`, `FR-11`, `FR-12`, `NFR-06`
* **Scenario:** `SC-01`, tiếp nhận kết quả thanh toán; `SC-04`, xử lý hoàn tiền
* **Nguồn review:** VR-18, VR-19 | **Change Request:** CR-01
* **Tiền điều kiện:** Cổng thanh toán giả lập gửi cùng một thông điệp Webhook xác nhận thanh toán thành công 2 lần liên tiếp cho cùng một mã giao dịch `GD-112233`.
* **Các bước và kết quả kỳ vọng:**
  * *Nhánh A (Webhook thanh toán lặp):* Gửi Webhook lần 1 $\rightarrow$ Lịch chuyển "Đã xác nhận", sinh link khám và gửi 1 SMS xác nhận. Gửi Webhook lần 2 cho cùng mã GD $\rightarrow$ Hệ thống nhận diện giao dịch đã xử lý, trả về HTTP 200 OK cho cổng nhưng không cập nhật lại trạng thái, không tạo lịch trùng và không gửi thêm SMS lần 2.
  * *Nhánh B (Webhook sai chữ ký hoặc sai số tiền):* Cổng gửi Webhook sai checksum hoặc sai số tiền 150.000 VNĐ $\rightarrow$ Hệ thống từ chối xác nhận lịch, ghi log cảnh báo đối soát.
  * *Nhánh C (Webhook đến sau khi đã quá hạn 15 phút):* Slot đã bị giải phóng và người khác đặt mất $\rightarrow$ Hệ thống từ chối ghi đè slot, chuyển khoản tiền thu được vào danh sách đối soát hoàn tiền tự động kèm lý do quá hạn.
* **Bằng chứng cần thu:** Log Webhook tiếp nhận, bản ghi lịch hẹn và giao dịch trong CSDL, số lượng SMS gửi thực tế.

---

# PHẦN 9: MA TRẬN TRUY VẾT YÊU CẦU

### 9.1. Danh mục nhu cầu nghiệp vụ gốc
* **N-01 (Nhu cầu đặt lịch chủ động):** Bệnh nhân muốn tự tra cứu chuyên khoa, bác sĩ, khung giờ và nhận xác nhận tức thì mà không cần gọi điện thoại nhiều lần (`STK-04`, `STK-01`).
* **N-02 (Nhu cầu chủ động của bác sĩ):** Bác sĩ cần nắm danh sách bệnh nhân và lý do khám trước đầu ca trực để chuẩn bị hồ sơ chuyên môn (`STK-02`).
* **N-03 (Nhu cầu tập trung và đồng bộ dữ liệu):** Nhân viên tiếp nhận và quản lý cần một nguồn dữ liệu lịch khám duy nhất, đồng bộ tức thì giữa các ca trực (`STK-03`, `STK-01`).
* **N-04 (Nhu cầu quản lý lịch từ xa):** Bệnh nhân cần tự tra cứu, đổi giờ hoặc hủy lịch hẹn từ xa mà không phải đến trực tiếp phòng khám (`STK-04`).
* **N-05 (Nhu cầu dịch vụ khám trực tuyến):** Phòng khám cần mở rộng kênh khám bệnh online có thu phí trước và tự động hoàn tiền minh bạch khi bác sĩ hủy ca (`STK-01`, `STK-04` — CR-01).
* **N-06 (Nhu cầu an toàn thông tin và phân quyền):** Phòng khám cần kiểm soát quyền thao tác theo vai trò và bảo toàn dữ liệu y tế/tài chính phục vụ đối soát (`STK-01`, `STK-02`, `STK-03`).
* **N-07 (Nhu cầu chất lượng vận hành):** Hệ thống phải đảm bảo tốc độ phản hồi nhanh, chịu tải tốt trong giờ cao điểm và vận hành ổn định (`STK-01`, `STK-03`, `STK-04`).

---

### 9.2. Bảng ma trận truy vết yêu cầu
*Nguyên tắc ma trận: Mỗi Requirement ID là 1 hàng độc lập; 100% các ô đều có giá trị liên kết cụ thể, tuyệt đối không dùng từ "Toàn bộ" và không để trống ô.*

| Nhu cầu | Stakeholder | Requirement ID | Scenario | Test case | Change request |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **N-01, N-05** | STK-04, STK-01 | FR-01 | SC-01, SC-02 | TC-01, TC-05, TC-08, TC-11, TC-15 | CR-01 |
| **N-01, N-05** | STK-04 | FR-02 | SC-01, SC-02 | TC-01, TC-05, TC-07, TC-08, TC-11 | CR-01 |
| **N-01, N-05** | STK-04, STK-01 | FR-03 | SC-01 | TC-01, TC-05, TC-15, TC-17, TC-18 | CR-01 |
| **N-04** | STK-04 | FR-04 | SC-03 | TC-03, TC-09, TC-10 | — |
| **N-04** | STK-04 | FR-05 | SC-03 | TC-03, TC-10 | CR-01 |
| **N-01** | STK-04, STK-03 | FR-06 | SC-01 | TC-07 | — |
| **N-03, N-04** | STK-03, STK-04 | FR-07 | SC-03, SC-04 | TC-03, TC-10, TC-16 | CR-01 |
| **N-03, N-05** | STK-01, STK-02 | FR-08 | SC-04 | TC-06, TC-12, TC-15, TC-16, TC-17 | CR-01 |
| **N-03, N-05** | STK-01, STK-04 | FR-09 | SC-04 | TC-06, TC-16, TC-17 | CR-01 |
| **N-01** | STK-04, STK-03 | FR-10 | SC-01 | TC-02, TC-11 | — |
| **N-05** | STK-01, STK-04, STK-05 | FR-11 | SC-01 | TC-05, TC-14, TC-15, TC-18 | CR-01 |
| **N-05** | STK-01, STK-04, STK-05 | FR-12 | SC-04 | TC-06, TC-12, TC-14, TC-16, TC-18 | CR-01 |
| **N-07** | STK-01, STK-04 | NFR-01 | SC-01 | TC-04 | — |
| **N-07** | STK-01, STK-03 | NFR-02 | SC-01, SC-02 | TC-11 | CR-01 |
| **N-04** | STK-04 | NFR-03 | SC-03 | TC-03, TC-09 | — |
| **N-06** | STK-01, STK-02 | NFR-04 | SC-04 | TC-12 | CR-01 |
| **N-07** | STK-01, STK-03 | NFR-05 | SC-01, SC-03 | TC-13 | — |
| **N-06, N-05** | STK-01, STK-04, STK-05 | NFR-06 | SC-01, SC-04 | TC-05, TC-06, TC-14, TC-16, TC-18 | CR-01 |

---

### 9.3. Bảng phân tích độ bao phủ và tác động tập trung của CR-01

#### 1. Phân tích độ bao phủ yêu cầu (Requirements Coverage Analysis):
* **Độ bao phủ Yêu cầu Chức năng (FR Coverage):** Đạt **100%** (12/12 Yêu cầu Chức năng đều có kịch bản nghiệp vụ Scenario và có ít nhất một kịch bản kiểm thử Test Case trực tiếp).
* **Độ bao phủ Yêu cầu Phi chức năng (NFR Coverage):** Đạt **100%** (6/6 Yêu cầu Phi chức năng thuộc đủ 3 nhóm Hiệu năng, Bảo mật, Khả dụng/Lưu trữ đều có kịch bản kiểm thử riêng biệt với ngưỡng định lượng đo lường được).
* **Độ bao phủ Kịch bản kiểm thử (Test Case Coverage):** Toàn bộ **18 Test Cases** (`TC-01` → `TC-18`) đều ánh xạ ngược về ít nhất một Requirement ID cụ thể; không có kịch bản kiểm thử nào bị mồ côi (No Orphan Test Cases).
* **Độ bao phủ Tình huống sử dụng (Scenario Coverage):** 4/4 Scenarios (`SC-01` → `SC-04`) đều được liên kết chặt chẽ với các FR và NFR tương ứng.

#### 2. Phân tích tác động tập trung của Yêu cầu thay đổi CR-01:
* CR-01 bổ sung **02 Yêu cầu Chức năng mới:** `FR-11` (Bắt buộc thanh toán online) và `FR-12` (Tự động hoàn tiền 100%).
* CR-01 sửa đổi trực tiếp logic của **01 Chức năng:** `FR-03` (Chỉ xác nhận lịch sau khi nhận phản hồi giao dịch thành công).
* CR-01 mở rộng phạm vi lưu trữ của **01 Yêu cầu Phi chức năng:** `NFR-06` (Lưu trữ và bảo toàn các thuộc tính giao dịch thanh toán/hoàn tiền).
* CR-01 tác động hồi quy lên **05 Chức năng khác:** `FR-01`, `FR-02`, `FR-05`, `FR-07`, `FR-08`, `FR-09` và phân quyền `NFR-04`.
* Toàn bộ các nhánh tác động của CR-01 đều được kiểm chứng độc lập bằng các test case: `TC-05`, `TC-06`, `TC-14`, `TC-15`, `TC-16`, `TC-18`.

---

### 9.4. Ghi nhận khoảng trống phạm vi & định hướng giai đoạn 2
*(Giải quyết triệt để khiếm khuyết kiểm định VR-05 & VR-22)*

Trong quá trình đối soát ma trận truy vết, nhóm nhận diện hai nhu cầu thực tế của Stakeholder chưa được chuyển hóa thành Yêu cầu Chức năng trong phiên bản Mini-SRS này:
1. **Nhu cầu N-02 (`STK-02` - Bác sĩ):** Bác sĩ cần màn hình đăng nhập riêng để xem danh sách ca khám và triệu chứng trước ca trực.
2. **Nhu cầu N-03 (`STK-03` - Tiếp nhận):** Nhân viên tiếp nhận cần chức năng bấm "Check-in" khi bệnh nhân có mặt tại quầy để đổi trạng thái sang "Đã đến khám".

**Quyết định quản lý yêu cầu:**
* Để đảm bảo tài liệu tập trung đúng trọng tâm đề tài Mini-SRS (hệ thống đặt lịch khám trực tuyến của phòng khám đa khoa nhỏ), nhóm thống nhất **không gán ép tùy tiện N-02 vào `FR-05`** (đổi/hủy của bệnh nhân) để lấp ô ma trận.
* Hai chức năng trên được ghi nhận minh bạch vào **Product Backlog giai đoạn 2** của dự án:
  * `FR-13 (Backlog)`: Giao diện điều phối ca trực và danh sách bệnh nhân dành riêng cho Bác sĩ.
  * `FR-14 (Backlog)`: Chức năng Check-in và phân luồng tiếp đón bệnh nhân tại quầy lễ tân.

