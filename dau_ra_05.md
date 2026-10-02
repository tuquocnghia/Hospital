# TÀI LIỆU ĐẶC TẢ YÊU CẦU PHẦN MỀM (MINI-SRS)


## LỊCH SỬ THAY ĐỔI TÀI LIỆU (REVISION HISTORY)
<!-- [THÀNH VIÊN 1 PHỤ TRÁCH ĐIỀN] -->

| Phiên bản | Ngày cập nhật | Người thực hiện | Tóm tắt nội dung thay đổi |
| :---: | :---: | :--- | :--- |
| **v1.0** | [DD/MM/2026] | Cả nhóm | Khởi tạo tài liệu Mini-SRS từ hiện trạng (10 FR, 6 NFR, 4 Scenarios). |
| **v1.1** | [DD/MM/2026] | Cả nhóm | Cập nhật phản hồi sau Peer Review và tích hợp CR-01 (Khám trực tuyến). |

---

## 1. GIỚI THIỆU & PHẠM VI HỆ THỐNG
<!-- [THÀNH VIÊN 1 PHỤ TRÁCH ĐIỀN TOÀN BỘ MỤC 1] -->

### 1.1. Phát biểu bài toán hiện tại (Problem Statement)
* **Hiện trạng phòng khám:** [TV 1 điền: Mô tả quy mô 6 bác sĩ, 80-120 lượt/ngày, 2 lễ tân/ca, đặt lịch bằng sổ và gọi điện...]
* **Các vấn đề tồn đọng:** [TV 1 điền: Nêu 3-4 khó khăn: nhầm lịch sổ sách, nghẽn cuộc gọi, bác sĩ bị động hồ sơ, mất đồng bộ khi đổi ca...]
* **Mục tiêu hệ thống:** [TV 1 điền: Mục tiêu xây dựng phần mềm hỗ trợ đặt lịch trực tuyến, check-in tại quầy và theo dõi lịch khám...]
* **Giá trị kỳ vọng:** [TV 1 điền: Giảm cuộc gọi thủ công, xóa bỏ trùng lịch, chuẩn bị trước hồ sơ bệnh nhân...]

### 1.2. Danh sách Stakeholder (Tối thiểu 4 Stakeholder)

| Stakeholder ID | Tên Stakeholder | Vai trò trong hệ thống | Nhu cầu chính | Mức độ ảnh hưởng |
| :---: | :--- | :--- | :--- | :---: |
| **STK-01** | Quản lý phòng khám | [TV 1 điền vai trò] | [TV 1 điền nhu cầu] | [Cao / TB / Thấp] |
| **STK-02** | Bác sĩ | [TV 1 điền vai trò] | [TV 1 điền nhu cầu] | [Cao / TB / Thấp] |
| **STK-03** | Nhân viên tiếp nhận | [TV 1 điền vai trò] | [TV 1 điền nhu cầu] | [Cao / TB / Thấp] |
| **STK-04** | Bệnh nhân | [TV 1 điền vai trò] | [TV 1 điền nhu cầu] | [Cao / TB / Thấp] |

### 1.3. Phạm vi hệ thống (Scope)
* **Trong phạm vi (In-Scope):**
  * [TV 1 liệt kê các phân hệ chính: đặt lịch online, check-in tại quầy, quản lý lịch bác sĩ, hủy/đổi lịch, thông báo...]
* **Ngoài phạm vi (Out-of-Scope - Tối thiểu 3 nội dung):**
  1. [TV 1 điền Out-of-scope 1: VD: Quản lý kho dược và bán thuốc]
  2. [TV 1 điền Out-of-scope 2: VD: Hồ sơ bệnh án chuyên sâu EMR / PACS]
  3. [TV 1 điền Out-of-scope 3: VD: Kế toán tài chính phòng khám và xuất hóa đơn đỏ]

### 1.4. Bảng thuật ngữ nghiệp vụ (Glossary) & Từ viết tắt

| Thuật ngữ / Viết tắt | Tên tiếng Anh | Định nghĩa nghiệp vụ |
| :--- | :--- | :--- |
| **Khung giờ khám** | Time slot | [TV 1 định nghĩa] |
| **Tiếp nhận** | Check-in | [TV 1 định nghĩa] |
| **Vắng mặt** | No-show | [TV 1 định nghĩa] |
| **Khám gấp** | Walk-in / Urgent | [TV 1 định nghĩa] |
| **FR / NFR** | Functional / Non-Functional Req | [TV 1 định nghĩa] |
| **CR-01** | Change Request 01 | [TV 1 định nghĩa] |

---

## 2. MÔI TRƯỜNG VẬN HÀNH & GIẢ ĐỊNH
<!-- [THÀNH VIÊN 1 PHỤ TRÁCH ĐIỀN TOÀN BỘ MỤC 2] -->

### 2.1. Môi trường vận hành
* **Phía người dùng (Bệnh nhân & Bác sĩ):** [TV 1 điền: Trình duyệt hỗ trợ, thiết bị di động, desktop...]
* **Phía quầy tiếp nhận:** [TV 1 điền: Máy tính quầy lễ tân, mạng LAN, máy in số thứ tự...]
* **Hạ tầng máy chủ:** [TV 1 điền: Môi trường cloud/server, hệ điều hành, CSDL...]

### 2.2. Giả định & Phụ thuộc (Assumptions & Dependencies)

#### 2.2.1. Bảng Danh mục Giả định nghiệp vụ & Kỹ thuật (Assumptions Log)
<!-- Nhóm quy ước: Mọi thông tin chưa có trong đề bài đều được ghi nhận minh bạch thành mã G-xx để phục vụ truy vết -->

| Mã ID | Nội dung Giả định nghiệp vụ & Kỹ thuật | Căn cứ phát sinh / Lý do chưa có số liệu | Phân hệ / Mục ảnh hưởng | Stakeholder cần xác nhận | Trạng thái |
| :---: | :--- | :--- | :---: | :---: | :---: |
| **G-01** | Thời lượng 1 lượt khám chuẩn là 15 phút; mỗi ca trực 4 tiếng của 1 bác sĩ tiếp nhận tối đa 16–20 lượt khám hẹn trước. | Đề bài chưa cho quy tắc phân bổ khung giờ và giới hạn số bệnh nhân. | Mục 3 (`FR-01`), Mục 4 (`SC-01`) | Bác sĩ (`STK-02`), Quản lý (`STK-01`) | *Chờ xác nhận* |
| **G-02** | Bệnh nhân đăng ký bằng số điện thoại di động chính chủ hợp lệ tại VN, có khả năng nhận tin nhắn SMS OTP và thông báo. | Bệnh nhân đặt lịch qua web công khai chưa có tài khoản định danh. | Mục 3 (`FR-02`), Mục 4 (`SC-01`, `SC-03`) | Bệnh nhân (`STK-04`) | *Đã giả định* |
| **G-03** | Trường hợp cấp cứu khẩn cấp (Walk-in nguy kịch) đi thẳng vào phòng cấp cứu, không qua hệ thống đặt lịch hẹn trước. | Đề bài yêu cầu khảo sát phương án tiếp nhận ca khám gấp. | Mục 1.3 (Scope), Mục 3 (`FR-04`) | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | *Đã giả định* |
| **G-04** | Viện phí khám trực tuyến từ xa (Telemedicine) tạm tính minh họa là 150.000 VNĐ/lượt khám (theo CR-01). | Đề bài CR-01 chỉ yêu cầu thanh toán trước, không cho biểu phí cụ thể. | Mục 3 (`FR-11`), Mục 4 (`SC-01`), Mục 6 (`TC-05`) | Quản lý phòng khám (`STK-01`) | *Chờ xác nhận* |
| **G-05** | Thời gian tạm khóa giữ chỗ khung giờ khám online chờ hoàn tất thanh toán là 15 phút. Sau 15 phút tự động giải phóng. | Tránh tình trạng giữ chỗ ảo làm lãng phí khung giờ của bác sĩ theo CR-01. | Mục 3 (`FR-11`), Mục 4 (`SC-01`) | Kỹ thuật / Cổng thanh toán | *Đã giả định* |
| **G-06** | Bệnh nhân chỉ được tự đổi/hủy lịch trên web trước giờ khám tối thiểu 2 tiếng (120 phút); hủy trễ không tự động hoàn tiền. | Đề bài yêu cầu khảo sát cách xử lý hủy/đổi lịch để bác sĩ chủ động ca trực. | Mục 3 (`FR-06`), Mục 4 (`SC-03`), Mục 6 (`TC-03`) | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | *Chờ xác nhận* |
| **G-07** | Mã xác thực SMS OTP cho thao tác tra cứu/hủy lịch có hiệu lực trong 3 phút (180s), nhập sai tối đa 3 lần. | Đảm bảo an toàn thông tin, ngăn chặn kẻ xấu cố tình hủy lịch của bệnh nhân khác. | Mục 3 (`NFR-03`), Mục 4 (`SC-03`) | Kỹ thuật / An toàn thông tin | *Đã giả định* |
| **G-08** | Quầy tiếp nhận được trang bị máy tính kết nối LAN ổn định và máy in nhiệt để in phiếu số thứ tự tiếp nhận. | Cơ sở vật chất tối thiểu để 02 nhân viên tiếp nhận/ca vận hành tại quầy. | Mục 2.1, Mục 3 (`FR-04`) | Nhân viên tiếp nhận (`STK-03`) | *Đã giả định* |
| **G-09** | Hồ sơ bệnh án chuyên sâu (EMR/PACS) và kê đơn/bán thuốc nằm ngoài phạm vi phần mềm (Out-of-scope). | Tránh phình to phạm vi dự án Mini-SRS của phòng khám quy mô nhỏ. | Mục 1.3 (Out-of-scope) | Quản lý phòng khám (`STK-01`) | *Đã giả định* |
| **G-10** | Bệnh nhân đến trễ quá 15 phút so với giờ hẹn bị chuyển trạng thái "Đến trễ" và xếp thứ tự khám sau các ca đúng giờ. | Đề bài yêu cầu khảo sát phương án xử lý bệnh nhân đến trễ. | Mục 3 (`FR-04`), Mục 4 (Luồng tiếp nhận) | Bác sĩ (`STK-02`), Lễ tân (`STK-03`) | *Chờ xác nhận* |
| **G-11** | Lễ tân chỉ được xem thông tin hành chính và triệu chứng tóm tắt, không được xem/sửa chẩn đoán bệnh án của bác sĩ. | Đề bài yêu cầu khảo sát quyền xem và chỉnh sửa thông tin. | Mục 3 (`NFR-04`) | Quản lý (`STK-01`), Bác sĩ (`STK-02`) | *Đã giả định* |
| **G-12** | Dữ liệu lịch hẹn và nhật ký giao dịch tài chính được lưu trữ bảo mật trên hệ thống tối thiểu 05 năm. | Đề bài yêu cầu khảo sát yêu cầu lưu trữ dữ liệu y tế. | Mục 3 (`NFR-06`) | Quản lý phòng khám (`STK-01`) | *Chờ xác nhận* |

#### 2.2.2. Sự phụ thuộc bên ngoài (Dependencies)
* **Dịch vụ viễn thông & Email:** Phụ thuộc vào tính sẵn sàng của hạ tầng tổng đài SMS Brandname (Viettel/VNPT) và dịch vụ SMTP (SendGrid/AWS SES) để gửi mã OTP và thông báo.
* **Cổng thanh toán trung gian:** Phụ thuộc vào kết nối API và cơ chế Webhook/IPN của cổng thanh toán điện tử (VNPay, MoMo) để xác nhận giao dịch thanh toán viện phí và phát lệnh hoàn tiền tự động theo CR-01.
* **Nền tảng truyền hình hội nghị:** Phụ thuộc vào API bên thứ ba (Google Meet / Zoom Video SDK) để tự động sinh đường dẫn phòng họp trực tuyến bảo mật phục vụ ca khám từ xa theo CR-01.

---

## 3. DANH MỤC YÊU CẦU PHẦN MỀM (REQUIREMENTS CATALOGUE)
<!-- [THÀNH VIÊN 2 PHỤ TRÁCH ĐIỀN TOÀN BỘ MỤC 3] -->
<!-- Lưu ý TV 2: Tiêu chí kiểm chứng phải đo lường được bằng số/điều kiện cụ thể, không dùng từ mơ hồ -->

### 3.1. Bảng tổng hợp Yêu cầu Chức năng (Functional Requirements - FR)
*(Tối thiểu 10 FR ban đầu + 2 FR từ CR-01)*

| ID | Tên chức năng tóm tắt | Nguồn | Độ ưu tiên (MoSCoW) | Phiên bản |
| :---: | :--- | :---: | :---: | :---: |
| **FR-01** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-02** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-03** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.1 |
| **FR-04** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-05** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-06** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-07** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-08** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-09** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-10** | [TV 2 điền tên chức năng] | [Nguồn] | [Must/Should/Could] | 1.0 |
| **FR-11** | [Thanh toán online trước khi khám (CR-01)] | CR-01 | Must Have | 1.1 |
| **FR-12** | [Tự động hoàn tiền khi bác sĩ hủy lịch (CR-01)] | CR-01 | Must Have | 1.1 |

### 3.2. Đặc tả chi tiết từng Yêu cầu Chức năng (Theo mẫu chuẩn)

#### FR-01: [TV 2 điền tên FR-01]
* **ID:** `FR-01` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát để kết luận Đạt/Không đạt].

#### FR-02: [TV 2 điền tên FR-02]
* **ID:** `FR-02` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-03: [TV 2 điền tên FR-03]
* **ID:** `FR-03` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.1
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-04: [TV 2 điền tên FR-04]
* **ID:** `FR-04` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-05: [TV 2 điền tên FR-05]
* **ID:** `FR-05` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-06: [TV 2 điền tên FR-06]
* **ID:** `FR-06` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-07: [TV 2 điền tên FR-07]
* **ID:** `FR-07` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-08: [TV 2 điền tên FR-08]
* **ID:** `FR-08` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-09: [TV 2 điền tên FR-09]
* **ID:** `FR-09` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-10: [TV 2 điền tên FR-10]
* **ID:** `FR-10` | **Loại:** Chức năng | **Nguồn:** [TV 2 điền] | **Độ ưu tiên:** [TV 2 điền] | **Phiên bản:** 1.0
* **Mô tả:** Trong bối cảnh [TV 2 điền ngữ cảnh], hệ thống phải [TV 2 điền hành vi hệ thống].
* **Lý do:** [TV 2 điền vấn đề hoặc nhu cầu mà FR này giải quyết].
* **Tiêu chí kiểm chứng:** [TV 2 điền điều kiện đo lường/quan sát].

#### FR-11: Bắt buộc thanh toán trực tuyến cho khám online (CR-01)
* **ID:** `FR-11` | **Loại:** Chức năng | **Nguồn:** CR-01 | **Độ ưu tiên:** Must Have | **Phiên bản:** 1.1
* **Mô tả:** Trong bối cảnh bệnh nhân đặt lịch khám trực tuyến, hệ thống phải yêu cầu thanh toán qua cổng thanh toán điện tử; chỉ khi nhận phản hồi thanh toán thành công mới xác nhận lịch hẹn chính thức.
* **Lý do:** Đảm bảo bệnh nhân giữ chỗ nghiêm túc cho dịch vụ khám từ xa theo CR-01.
* **Tiêu chí kiểm chứng:** [TV 2 điền: Điều kiện xác nhận lịch hẹn, thời gian tạm giữ slot 15 phút, hủy slot nếu timeout].

#### FR-12: Tự động hoàn tiền khi bác sĩ hủy ca khám online (CR-01)
* **ID:** `FR-12` | **Loại:** Chức năng | **Nguồn:** CR-01 | **Độ ưu tiên:** Must Have | **Phiên bản:** 1.1
* **Mô tả:** Trong bối cảnh bác sĩ hủy ca khám trực tuyến đã có bệnh nhân thanh toán, hệ thống phải tự động phát lệnh hoàn tiền 100% về tài khoản ban đầu và gửi thông báo xác nhận cho bệnh nhân.
* **Lý do:** Đảm bảo quyền lợi tài chính minh bạch cho bệnh nhân theo quy định CR-01.
* **Tiêu chí kiểm chứng:** [TV 2 điền: Lệnh hoàn tiền được tạo, chuyển trạng thái "Đã hoàn tiền", gửi SMS thông báo].

---

### 3.3. Yêu cầu phi chức năng (Non-Functional Requirements - NFR)
*(Tối thiểu 6 NFR thuộc ít nhất 3 nhóm: Hiệu năng, Bảo mật, Khả dụng/Lưu trữ)*

#### Nhóm 1: Hiệu năng (Performance)
* **NFR-01 (Thời gian phản hồi):**
  * *Mô tả:* [TV 2 điền: Ngưỡng thời gian phản hồi cho tra cứu lịch trống với số lượng người dùng đồng thời cụ thể].
  * *Tiêu chí kiểm chứng:* [TV 2 điền: Công cụ đo lường và ngưỡng đạt/không đạt].
* **NFR-02 (Thông lượng cao điểm):**
  * *Mô tả:* [TV 2 điền: Khả năng chịu tải cho 80-120 lượt/ngày và số giao dịch trong ca cao điểm].
  * *Tiêu chí kiểm chứng:* [TV 2 điền: Tỷ lệ lỗi cho phép (0%) trong bài test tải].

#### Nhóm 2: Bảo mật & Quyền riêng tư (Security)
* **NFR-03 (Mã hóa dữ liệu y tế):**
  * *Mô tả:* [TV 2 điền: Tiêu chuẩn mã hóa dữ liệu nhạy cảm lưu trữ và giao thức truyền tải mạng].
  * *Tiêu chí kiểm chứng:* [TV 2 điền: Cách kiểm tra plain text trong CSDL và chứng chỉ SSL].
* **NFR-04 (Phân quyền RBAC):**
  * *Mô tả:* [TV 2 điền: Quyền của lễ tân so với bác sĩ đối với chẩn đoán bệnh án chi tiết].
  * *Tiêu chí kiểm chứng:* [TV 2 điền: Mã lỗi HTTP trả về khi truy cập trái quyền].

#### Nhóm 3: Khả dụng & Lưu trữ dữ liệu (Availability & Retention)
* **NFR-05 (Độ sẵn sàng Uptime):**
  * *Mô tả:* [TV 2 điền: Tỷ lệ uptime cam kết trong khung giờ làm việc của phòng khám].
  * *Tiêu chí kiểm chứng:* [TV 2 điền: Thời gian downtime tối đa cho phép mỗi tháng].
* **NFR-06 (Sao lưu & Khôi phục CSDL):**
  * *Mô tả:* [TV 2 điền: Tần suất sao lưu định kỳ và thời gian phục hồi tối đa RTO].
  * *Tiêu chí kiểm chứng:* [TV 2 điền: Kết quả kịch bản phục hồi thử nghiệm].

---

## 4. ĐẶC TẢ TÌNH HUỐNG SỬ DỤNG (SCENARIOS)

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

---

## 5. QUẢN LÝ THAY ĐỔI YÊU CẦU (CHANGE MANAGEMENT · CR-01)
<!-- [THÀNH VIÊN 3 PHỤ TRÁCH ĐIỀN TOÀN BỘ MỤC 5] -->

### 5.1. Bối cảnh & Mô tả Yêu cầu Thay đổi CR-01
* **Mã yêu cầu thay đổi:** `CR-01`
* **Tên thay đổi:** Triển khai dịch vụ Khám bệnh trực tuyến từ xa (Telemedicine).
* **Nguồn gốc phát sinh:** Quản lý phòng khám An Tâm (`STK-01`).
* **Mô tả nghiệp vụ:** Để mở rộng phạm vi phục vụ bệnh nhân ở xa và tối ưu hóa thời gian làm việc của các bác sĩ chuyên khoa, phòng khám bổ sung kênh khám bệnh trực tuyến. Nhằm ngăn chặn tình trạng đặt lịch ảo làm lãng phí thời gian trực của bác sĩ, phòng khám ban hành quy định:
  1. Bệnh nhân bắt buộc phải thanh toán tiền viện phí trực tuyến trước thì lịch hẹn khám từ xa mới được hệ thống xác nhận chính thức.
  2. Trong trường hợp bác sĩ có sự cố đột xuất phải hủy lịch hẹn, hệ thống phải tự động hoàn trả 100% tiền viện phí đã thu cho bệnh nhân và gửi thông báo xác nhận minh bạch.

### 5.2. Bảng phân tích tác động toàn diện (Impact Analysis Table)

| Hạng mục chịu tác động | Chi tiết tác động cụ thể từ CR-01 | Mức độ tác động |
| :--- | :--- | :---: |
| **Yêu cầu chức năng (FR)** | • **Bổ sung mới `FR-11`:** Bắt buộc tích hợp cổng thanh toán trực tuyến (VNPay/Momo), tạm giữ khung giờ trong 15 phút và chỉ xác nhận lịch khi thanh toán thành công.<br>• **Bổ sung mới `FR-12`:** Xây dựng cơ chế phát lệnh hoàn tiền tự động 100% khi bác sĩ hoặc phòng khám chủ động hủy lịch khám trực tuyến.<br>• **Sửa đổi logic `FR-03`:** Bổ sung điều kiện chỉ kích hoạt gửi SMS/Email xác nhận lịch hẹn online sau khi hệ thống nhận được tín hiệu giao dịch thanh toán thành công từ cổng thanh toán. | **Cao** |
| **Kịch bản nghiệp vụ (Scenarios)** | • **Sửa đổi `SC-01`:** Bổ sung bước rẽ nhánh lựa chọn hình thức khám (Trực tiếp vs Trực tuyến), bước chuyển hướng sang cổng thanh toán điện tử, xử lý ngoại lệ khi giao dịch timeout hoặc thanh toán thất bại.<br>• **Sửa đổi `SC-03`:** Bổ sung cơ chế hoàn tiền khi bệnh nhân chủ động hủy lịch khám trực tuyến hợp lệ trước $\ge 2$ tiếng.<br>• **Sửa đổi `SC-04`:** Bổ sung bước tự động lọc bệnh nhân khám online, gọi API cổng thanh toán hoàn tiền tự động và gửi SMS kèm thông tin đối soát hoàn tiền. | **Trung bình** |
| **Mô hình Dữ liệu (Data Model)** | • **Tạo mới thực thể/bảng `GiaoDich`:** Lưu trữ `MaGiaoDich` (PK), `MaLichHen` (FK), `SoTien`, `PhuongThucThanhToan`, `TrangThaiThanhToan` (Chờ TT / Đã TT / Thất bại / Đã hoàn tiền), `MaGiaoDichCongTT`, `ThoiGianThanhToan`, `ThoiGianHoanTien`.<br>• **Bổ sung thuộc tính bảng `LichHen`:** Thêm trường `HinhThucKham` (Enum: `TRUC_TIEP`, `TRUC_TUYEN`), trường `LinkKhamOnline` (VARCHAR) và trường `HanThanhToanTamGiu` (DATETIME). | **Trung bình** |
| **Kiểm thử (Test Cases)** | • **Bổ sung kịch bản `TC-05`:** Kiểm thử luồng đặt lịch khám trực tuyến, liên kết cổng thanh toán và xác nhận lịch thành công.<br>• **Bổ sung kịch bản `TC-06`:** Kiểm thử luồng bác sĩ hủy ca trực -> tự động kích hoạt hoàn tiền và gửi SMS thông báo cho bệnh nhân. | **Trung bình** |
| **Giao diện người dùng (UI/UX)** | • Bổ sung nút lựa chọn "Khám tại phòng khám" hoặc "Khám trực tuyến" tại màn hình trang chủ.<br>• Tích hợp widget nhúng hoặc trang chuyển hướng thanh toán an toàn.<br>• Bổ sung màn hình hiển thị phòng chờ và đường link tham gia phòng khám trực tuyến. | **Thấp** |

### 5.3. Nhận diện Rủi ro mới & Danh mục Câu hỏi cần Stakeholder làm rõ

#### Rủi ro 1: Độ trễ hoàn tiền từ phía ngân hàng trung gian phát hành thẻ
* **Bản chất rủi ro:** Hệ thống phòng khám phát lệnh hoàn tiền ngay lập tức khi hủy ca, nhưng quy trình đối soát giữa cổng thanh toán (VNPay/Momo) và ngân hàng phát hành thẻ của bệnh nhân thường mất từ 24h đến 48h làm việc (thậm chí 7–14 ngày đối với thẻ tín dụng quốc tế Visa/Mastercard). Bệnh nhân có thể bức xúc, khiếu nại hoặc gọi điện làm phiền lễ tân vì kiểm tra tài khoản chưa thấy tiền về ngay.
* **Biện pháp xử lý đề xuất:** Trong nội dung SMS/Email thông báo hoàn tiền, hệ thống phải ghi rõ ràng: *"Phòng khám An Tâm đã phát lệnh hoàn 100% tiền viện phí (Mã giao dịch: XXXXXX). Tiền sẽ được ngân hàng ghi có vào tài khoản của quý khách trong vòng 1–3 ngày làm việc tùy quy định ngân hàng phát hành thẻ"*.

#### Rủi ro 2: Bệnh nhân vắng mặt (No-show) hoặc tham gia phòng khám trực tuyến trễ
* **Vấn đề cần làm rõ:** Đề bài mới chỉ quy định "hoàn tiền khi bác sĩ hủy lịch". Vậy trong trường hợp ngược lại: Bác sĩ đã mở phòng khám online đúng giờ nhưng bệnh nhân không bấm vào link tham gia (bác sĩ chờ quá 15 phút), phòng khám có áp dụng chính sách hoàn tiền cho bệnh nhân hay không?
* **Giải pháp đề xuất đưa vào quy định:** Cần bổ sung điều khoản dịch vụ: Nếu bệnh nhân vắng mặt quá 10 phút sau giờ hẹn mà không báo trước, ca khám được tính là "Bệnh nhân vắng mặt (No-show)", phòng khám sẽ không hoàn tiền nhằm bảo vệ quyền lợi và thù lao thời gian của bác sĩ.

#### Rủi ro 3: Lựa chọn nền tảng hạ tầng công nghệ cho phòng gọi video (Video Call)
* **Vấn đề cần làm rõ:** Phòng khám dự định tự phát triển giải pháp Video Call nội bộ chạy trên máy chủ riêng (sử dụng công nghệ WebRTC) hay sử dụng giải pháp tích hợp API của nền tảng bên thứ ba (Google Meet, Zoom Video SDK, Microsoft Teams)?
* **Đánh giá rủi ro kỹ thuật:** Việc tự dựng máy chủ WebRTC đòi hỏi chi phí hạ tầng máy chủ rất cao, đường truyền băng thông cực lớn và đội ngũ bảo trì phức tạp.
* **Đề xuất kỹ thuật:** Trong giai đoạn đầu, hệ thống phần mềm chỉ đóng vai trò tự động tích hợp API của Google Workspace/Zoom để sinh tự động đường link cuộc họp bảo mật kèm mật khẩu gửi cho bác sĩ và bệnh nhân, giúp tiết kiệm chi phí vận hành và đảm bảo độ ổn định đường truyền âm thanh/hình ảnh.

---

## 6. BÁO CÁO KIỂM NGHIỆM & TEST SCENARIOS (VALIDATION REPORT)
<!-- [THÀNH VIÊN 4 CHỦ TRÌ PEER REVIEW - THÀNH VIÊN 3 HỖ TRỢ TEST CASES] -->

### 6.1. Báo cáo kết quả Peer Review chéo (Tối thiểu 8 lỗi/vấn đề phát hiện)
<!-- Cả nhóm cùng soi bài của nhau, TV 4 lập bảng ghi nhận đủ 8 lỗi theo 6 tiêu chí: Đúng đắn, Đầy đủ, Nhất quán, Khả thi, Rõ ràng, Đo lường được -->

| STT | Vấn đề / Lỗi phát hiện | Tiêu chí vi phạm | Mục bị ảnh hưởng | Quyết định | Lý do & Biện pháp khắc phục |
| :---: | :--- | :--- | :---: | :---: | :--- |
| **1** | [TV 4 điền lỗi 1] | [Đo lường được] | [Vị trí] | **Sửa (Fix)** | [Cách khắc phục] |
| **2** | [TV 4 điền lỗi 2] | [Nhất quán] | [Vị trí] | **Sửa (Fix)** | [Cách khắc phục] |
| **3** | [TV 4 điền lỗi 3] | [Đầy đủ] | [Vị trí] | **Sửa (Fix)** | [Cách khắc phục] |
| **4** | [TV 4 điền lỗi 4] | [Rõ ràng] | [Vị trí] | **Sửa (Fix)** | [Cách khắc phục] |
| **5** | [TV 4 điền lỗi 5] | [Khả thi] | [Vị trí] | **Không sửa (No-fix)** | [Lý do kỹ thuật giữ nguyên] |
| **6** | [TV 4 điền lỗi 6] | [Đúng đắn] | [Vị trí] | **Sửa (Fix)** | [Cách khắc phục] |
| **7** | [TV 4 điền lỗi 7] | [Đầy đủ] | [Vị trí] | **Sửa (Fix)** | [Cách khắc phục] |
| **8** | [TV 4 điền lỗi 8] | [Rõ ràng] | [Vị trí] | **Sửa (Fix)** | [Cách khắc phục] |

### 6.2. Danh mục Kịch bản kiểm thử (Test Scenarios - Tối thiểu 6 Test Cases)
<!-- TV 3 phụ trách viết 6 test scenarios, mỗi test case BẮT BUỘC liên kết với ít nhất 1 Requirement ID -->

| Test ID | Tên kịch bản kiểm thử | Requirement ID liên kết | Điều kiện đầu vào | Kết quả kỳ vọng |
| :---: | :--- | :---: | :--- | :--- |
| **TC-01** | Kiểm thử đặt lịch khám trực tiếp thành công với dữ liệu hợp lệ | `FR-01`, `FR-02`, `FR-03` | BS. Nguyễn Văn A, ngày 15/10/2026, slot 08:30 khả dụng, thông tin bệnh nhân hợp lệ. | Đặt lịch thành công, sinh mã AT-151001, khóa slot, gửi SMS xác nhận trong < 60s. |
| **TC-02** | Kiểm thử ngăn chặn đặt lịch hẹn trùng lặp trên cùng một khung giờ | `FR-10` | SĐT 0912345678 đã có lịch 09:00 ngày 15/10/2026, cố tình đặt thêm 1 lịch khác cùng giờ. | Hệ thống từ chối tạo lịch, hiển thị cảnh báo trùng lặp, không phát sinh SMS mới. |
| **TC-03** | Kiểm thử bệnh nhân tự hủy lịch trước 2 tiếng và giải phóng khung giờ | `FR-06`, `FR-07` | Lịch hẹn AT-998877 lúc 14:00, thực hiện hủy lúc 10:00 (cách 4h $\ge$ 2h), nhập OTP SMS. | Lịch chuyển sang "Đã hủy bởi bệnh nhân", slot 14:00 mở lại "Khả dụng", gửi SMS hủy. |
| **TC-04** | Kiểm thử hiệu năng thời gian phản hồi khi tra cứu lịch trống (Performance) | `NFR-01` | Kịch bản JMeter 100 Virtual Users truy cập đồng thời API available-slots trong 60s. | 100% request thành công (Error 0.0%), Average Response Time $\le$ 2.0s, p95 $\le$ 2.5s. |
| **TC-05** | Kiểm thử đặt lịch khám trực tuyến và thanh toán qua cổng điện tử (CR-01) | `FR-11`, `CR-01` | Khám online, viện phí 150.000 VNĐ, nhập thẻ Sandbox NCB hợp lệ và OTP 123456. | Cổng TT trả Webhook thành công, trạng thái "Đã xác nhận", tự sinh link online và gửi SMS. |
| **TC-06** | Kiểm thử tự động phát lệnh hoàn tiền khi Quản lý hủy ca trực (CR-01) | `FR-12`, `FR-09`, `CR-01` | Ca trực chiều có lịch online đã thanh toán 150.000 VNĐ, Quản lý nhấn "Báo nghỉ đột xuất". | Gọi API hoàn 100% (150.000 VNĐ), giao dịch sang "Đã hoàn tiền", gửi SMS xin lỗi + hoàn tiền. |

---

## 7. MA TRẬN TRUY VẾT (TRACEABILITY MATRIX)
<!-- [THÀNH VIÊN 4 PHỤ TRÁCH ĐIỀN TOÀN BỘ MỤC 7] -->
<!-- Lưu ý TV 4: Rà soát không để ô trống liên kết, mã ID phải khớp 100% với các mục trên -->

| Nhu cầu (Need) | Stakeholder | Requirement ID (FR / NFR) | Scenario ID | Test Case ID | Change Request |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **N-01** | STK-04 | [FR-01, FR-02, FR-03] | [SC-01, SC-02] | [TC-01] | — |
| **N-01** | STK-04 | [FR-10] | [SC-01] | [TC-02] | — |
| **N-01** | STK-04 | [NFR-01, NFR-02] | [SC-01] | [TC-04] | — |
| **N-02** | STK-02 | [FR-05] | [SC-01] | [TC-01] | — |
| **N-03** | STK-03 | [FR-04, FR-07] | [SC-03] | [TC-03] | — |
| **N-04** | STK-04 | [FR-06] | [SC-03] | [TC-03] | — |
| **N-03** | STK-01, STK-03 | [FR-08, FR-09] | [SC-04] | [TC-06] | — |
| **N-05** | STK-04 | [FR-11] | [SC-01] | [TC-05] | **CR-01** |
| **N-05** | STK-02, STK-04 | [FR-12] | [SC-04] | [TC-06] | **CR-01** |
| [Bảo mật] | Toàn bộ | [NFR-03, NFR-04] | Toàn bộ | [TC-01, TC-05] | — |
| [Khả dụng] | Toàn bộ | [NFR-05, NFR-06] | Toàn bộ | [TC-04] | — |

---

## PHỤ LỤC: MINH CHỨNG KHẢO SÁT (ELICITATION EVIDENCE)
<!-- [THÀNH VIÊN 1 PHỤ TRÁCH ĐIỀN PHẦN NÀY] -->

### PL-1. Kế hoạch thu thập yêu cầu (Elicitation Plan)
* **Kỹ thuật 1: Phỏng vấn sâu (In-depth Interview):**
  * *Mục tiêu:* [TV 1 điền]
  * *Đối tượng tham gia:* [TV 1 điền: Quản lý, Bác sĩ, Lễ tân]
  * *Thời lượng & Cách ghi nhận:* [TV 1 điền: 30 phút/phiên, ghi âm và ghi chép biên bản]
* **Kỹ thuật 2: Bảng câu hỏi khảo sát (Online Questionnaire):**
  * *Mục tiêu:* [TV 1 điền: Đo lường hành vi đặt lịch và nhu cầu đổi lịch từ xa của bệnh nhân]
  * *Đối tượng:* [TV 1 điền: Bệnh nhân đã từng khám tại phòng khám]
  * *Cách ghi nhận:* [TV 1 điền: Google Forms, phân tích biểu đồ]

### PL-2. Bộ 15 câu hỏi khảo sát chi tiết
* **Nhóm 1: 05 câu hỏi mở (Quy trình & Nhu cầu nghiệp vụ):**
  1. [TV 1 điền câu hỏi mở 1...]
  2. [TV 1 điền câu hỏi mở 2...]
  3. [TV 1 điền câu hỏi mở 3...]
  4. [TV 1 điền câu hỏi mở 4...]
  5. [TV 1 điền câu hỏi mở 5...]
* **Nhóm 2: 05 câu hỏi đóng (Quy tắc & Giới hạn vận hành):**
  6. [TV 1 điền câu hỏi đóng 6...]
  7. [TV 1 điền câu hỏi đóng 7...]
  8. [TV 1 điền câu hỏi đóng 8...]
  9. [TV 1 điền câu hỏi đóng 9...]
  10. [TV 1 điền câu hỏi đóng 10...]
* **Nhóm 3: 05 câu hỏi ngoại lệ & Yêu cầu phi chức năng:**
  11. [TV 1 điền câu hỏi ngoại lệ bệnh nhân đến trễ...]
  12. [TV 1 điền câu hỏi ca khám cấp cứu xen kẽ ca đặt trước...]
  13. [TV 1 điền câu hỏi bác sĩ xin nghỉ đột xuất trong ca...]
  14. [TV 1 điền câu hỏi thời gian phản hồi chấp nhận được khi tra cứu lịch...]
  15. [TV 1 điền câu hỏi chính sách bảo mật dữ liệu thông tin khám bệnh...]

### PL-3. Biên bản phỏng vấn mẫu (Interview Notes)
* **Người phỏng vấn:** Thành viên 1 | **Người được phỏng vấn:** Quản lý phòng khám
* **Thời gian & Địa điểm:** [DD/MM/2026] tại Văn phòng Quản lý An Tâm.
* **Tóm tắt nội dung ghi nhận:** [TV 1 điền tóm tắt các ý trao đổi chính...]

### PL-4. Bảng câu hỏi và vấn đề chưa rõ (Open Questions Log)
*(Tuân thủ nguyên tắc không tự ý suy đoán dữ liệu của đề bài)*

| Mã | Nội dung cần khảo sát thêm | Giả định tạm thời được áp dụng | Người cần xác nhận |
| :---: | :--- | :--- | :---: |
| **Q-01** | [Quy tắc khung giờ & giới hạn số lượt/bác sĩ] | [Tạm giả định: 15 phút/lượt, tối đa 20 lượt/ca] | Quản lý, Bác sĩ |
| **Q-02** | [Quy tắc xử lý bệnh nhân đến trễ hẹn] | [Tạm giả định: Quá 15 phút chuyển xuống cuối ca] | Lễ tân, Bác sĩ |
| **Q-03** | [Quy tắc ưu tiên ca khám gấp / cấp cứu] | [Tạm giả định: Ca cấp cứu không qua web đặt lịch] | Quản lý |
| **Q-04** | [Quyền hạn chuyển bệnh nhân giữa các bác sĩ] | [Tạm giả định: Chỉ Quản lý mới có quyền chuyển] | Quản lý, Lễ tân |