# TÀI LIỆU ĐẶC TẢ YÊU CẦU PHẦN MỀM (MINI-SRS)
# HỆ THỐNG QUẢN LÝ LỊCH KHÁM – PHÒNG KHÁM ĐA KHOA AN TÂM

* **Mã môn học / Bài tập:** LT04 – Kỹ nghệ phần mềm (BT04)
* **Nhóm thực hiện:** Nhóm 18 | **Lớp:** [Điền tên lớp]
* **Thành viên nhóm:**
  1. [Họ tên TV 1 - MSSV] (Lead / BA)
  2. [Họ tên TV 2 - MSSV] (Requirements Engineer)
  3. [Họ tên TV 3 - MSSV] (Solution & Test Analyst)
  4. [Họ tên TV 4 - MSSV] (QA & Traceability Lead)
* **Phiên bản:** v1.1 (Cập nhật sau Peer Review và Change Request CR-01)
* **Ngày nộp bài:** [DD/MM/2026]

---

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
* `[Giả định G-01]`: [TV 1 điền: Thời lượng 1 lượt khám chuẩn (VD: 15-20 phút), số bệnh nhân tối đa/ca...]
* `[Giả định G-02]`: [TV 1 điền: Bệnh nhân cung cấp SĐT chính chủ nhận SMS OTP/xác nhận...]
* `[Giả định G-03]`: [TV 1 điền: Ca cấp cứu khẩn cấp chuyển thẳng phòng cấp cứu không qua hệ thống đặt lịch...]
* **Sự phụ thuộc (Dependencies):** [TV 1 điền: Phụ thuộc dịch vụ SMS Brandname, cổng thanh toán ngân hàng...]

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
<!-- [THÀNH VIÊN 3 PHỤ TRÁCH ĐIỀN TOÀN BỘ MỤC 4] -->
<!-- Lưu ý TV 3: Đánh số từng bước tương tác, chỉ rõ bước rẽ nhánh ngoại lệ và phản hồi của hệ thống -->

### SC-01 · Bệnh nhân đặt lịch thành công (Tích hợp CR-01)
* **Tác nhân chính:** [TV 3 điền]
* **Tiền điều kiện:** [TV 3 điền]
* **Kích hoạt:** [TV 3 điền]
* **Luồng chính (Main Flow):**
  1. [TV 3 điền bước 1...]
  2. [TV 3 điền bước 2...]
  3. [TV 3 điền bước 3...]
  4. [TV 3 điền bước 4...]
  5. [TV 3 điền bước 5...]
  6. [TV 3 điền bước 6...]
  7. [TV 3 điền bước 7: Phân nhánh khám trực tiếp vs khám online có thanh toán...]
  8. [TV 3 điền bước 8...]
* **Luồng thay thế / Ngoại lệ (Alternative & Exception Flows):**
  * *Ngoại lệ [Bước]a:* [TV 3 điền điều kiện rẽ nhánh và phản hồi của hệ thống].
  * *Ngoại lệ [Bước]b (Thanh toán thất bại / timeout 15 phút):* [TV 3 điền xử lý].
* **Hậu điều kiện:** [TV 3 điền trạng thái hệ thống sau khi hoàn thành].

---

### SC-02 · Khung giờ hoặc bác sĩ không còn khả dụng
* **Tác nhân chính:** [TV 3 điền]
* **Tiền điều kiện:** [TV 3 điền]
* **Kích hoạt:** [TV 3 điền]
* **Luồng chính (Main Flow):**
  1. [TV 3 điền bước 1...]
  2. [TV 3 điền bước 2...]
  3. [TV 3 điền bước 3: Hệ thống phát hiện slot đã kín...]
  4. [TV 3 điền bước 4: Hệ thống cảnh báo và gợi ý 3 slot trống thay thế...]
  5. [TV 3 điền bước 5: Bệnh nhân chọn slot mới...]
* **Luồng thay thế / Ngoại lệ:**
  * *Ngoại lệ [Bước]a:* [TV 3 điền trường hợp hết lịch cả ngày].
* **Hậu điều kiện:** [TV 3 điền trạng thái hệ thống].

---

### SC-03 · Bệnh nhân đổi hoặc hủy lịch hẹn
* **Tác nhân chính:** [TV 3 điền]
* **Tiền điều kiện:** [TV 3 điền: Có mã lịch hẹn, cách giờ khám >= 2 tiếng...]
* **Kích hoạt:** [TV 3 điền]
* **Luồng chính (Main Flow):**
  1. [TV 3 điền bước tra cứu lịch...]
  2. [TV 3 điền bước chọn Đổi lịch hoặc Hủy lịch...]
  3. [TV 3 điền bước xác nhận...]
  4. [TV 3 điền bước hệ thống giải phóng khung giờ cũ và gửi SMS...]
* **Luồng thay thế / Ngoại lệ:**
  * *Ngoại lệ [Bước]a (Hủy trễ < 2 tiếng):* [TV 3 điền: Hệ thống khóa nút tự hủy và hướng dẫn gọi hotline].
* **Hậu điều kiện:** [TV 3 điền trạng thái khung giờ và CSDL sau khi đổi/hủy].

---

### SC-04 · Bác sĩ nghỉ ca đột xuất & Xử lý hoàn tiền (CR-01)
* **Tác nhân chính:** [TV 3 điền: Quản lý phòng khám]
* **Tiền điều kiện:** [TV 3 điền]
* **Kích hoạt:** [TV 3 điền]
* **Luồng chính (Main Flow):**
  1. [TV 3 điền bước Quản lý chọn ca trực và nhập lý do...]
  2. [TV 3 điền bước hệ thống hiển thị danh sách bệnh nhân bị ảnh hưởng...]
  3. [TV 3 điền bước khóa toàn bộ slot trong ca...]
  4. [TV 3 điền bước tự động phát lệnh hoàn tiền cho ca online theo CR-01...]
  5. [TV 3 điền bước gửi thông báo đồng loạt cho bệnh nhân kèm link đặt lại...]
* **Luồng thay thế / Ngoại lệ:**
  * *Ngoại lệ [Bước]a (Lỗi kết nối API hoàn tiền):* [TV 3 điền xử lý hàng đợi hoàn tiền thủ công].
* **Hậu điều kiện:** [TV 3 điền trạng thái hệ thống sau khi hủy ca].

---

## 5. QUẢN LÝ THAY ĐỔI YÊU CẦU (CHANGE MANAGEMENT · CR-01)
<!-- [THÀNH VIÊN 3 PHỤ TRÁCH ĐIỀN TOÀN BỘ MỤC 5] -->

### 5.1. Bảng phân tích tác động (Impact Analysis Table)

| Đối tượng chịu tác động | Chi tiết tác động cụ thể từ CR-01 (Khám trực tuyến) | Mức độ tác động |
| :--- | :--- | :---: |
| **Yêu cầu (Requirements)** | [TV 3 điền: FR nào thêm mới, FR nào sửa đổi] | Cao |
| **Kịch bản (Scenarios)** | [TV 3 điền: Scenario nào bổ sung bước thanh toán / hoàn tiền] | Trung bình |
| **Cơ sở dữ liệu (Data)** | [TV 3 điền: Bổ sung bảng giao dịch, trạng thái thanh toán, link phòng online] | Trung bình |
| **Kiểm thử (Test Cases)** | [TV 3 điền: Test case nào kiểm thử thanh toán và hoàn tiền] | Trung bình |

### 5.2. Danh mục Rủi ro & Câu hỏi mới cần làm rõ (Tối thiểu 3 rủi ro)
1. **Rủi ro 1:** [TV 3 điền: Vấn đề độ trễ hoàn tiền từ cổng thanh toán bên thứ ba và cách giải quyết].
2. **Rủi ro 2:** [TV 3 điền: Chính sách xử lý bệnh nhân vào trễ hoặc vắng mặt trong phòng khám online].
3. **Rủi ro 3:** [TV 3 điền: Giải pháp công nghệ video call (tự dựng WebRTC hay dùng Zoom/Meet)].

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
<!-- TV 3/4 viết 6 test scenarios, mỗi test case BẮT BUỘC liên kết với ít nhất 1 Requirement ID -->

| Test ID | Tên kịch bản kiểm thử | Requirement ID liên kết | Điều kiện đầu vào | Kết quả kỳ vọng |
| :---: | :--- | :---: | :--- | :--- |
| **TC-01** | [TV 4 điền tên test case 1] | [FR-xx] | [Dữ liệu vào] | [Kết quả mong đợi] |
| **TC-02** | [TV 4 điền tên test case 2] | [FR-xx] | [Dữ liệu vào] | [Kết quả mong đợi] |
| **TC-03** | [TV 4 điền tên test case 3] | [FR-xx] | [Dữ liệu vào] | [Kết quả mong đợi] |
| **TC-04** | [TV 4 điền tên test case 4] | [NFR-xx] | [Dữ liệu vào] | [Kết quả mong đợi] |
| **TC-05** | [TV 4 điền test thanh toán online] | [FR-11, CR-01] | [Dữ liệu vào] | [Kết quả mong đợi] |
| **TC-06** | [TV 4 điền test hoàn tiền tự động] | [FR-12, CR-01] | [Dữ liệu vào] | [Kết quả mong đợi] |

---

## 7. MA TRẬN TRUY VẾT (TRACEABILITY MATRIX)
<!-- [THÀNH VIÊN 4 PHỤ TRÁCH ĐIỀN TOÀN BỘ MỤC 7] -->
<!-- Lưu ý TV 4: Rà soát không để ô trống liên kết, mã ID phải khớp 100% với các mục trên -->

| Nhu cầu (Need) | Stakeholder | Requirement ID (FR / NFR) | Scenario ID | Test Case ID | Change Request |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **N-01** | STK-04 | [FR-01, FR-02, FR-03] | [SC-01, SC-02] | [TC-01] | — |
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