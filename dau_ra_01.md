# SOFTWARE REQUIREMENT 

## Case Study: Phòng khám An Tâm
An Tâm là phòng khám đa khoa quy mô nhỏ. Việc đặt lịch hiện được thực hiện qua điện thoại và ghi vào sổ. Phòng khám muốn xây dựng một hệ thống hỗ trợ đặt lịch, tiếp nhận bệnh nhân và theo dõi lịch khám.

## Thông tin:
- Người thực hiện: Cao Xuân Dương
- MSSV: 24120292
- Nhóm: 18

# PROBLEM STATEMENT & SCOPE

## 1.1.  Vấn đề hiện tại
Phòng khám hiện tại quản lí đặt lịch thủ công thông qua điện thoại và ghi chép vào sổ. Nhân viên tiếp nhận phải ghi lịch hẹn, xác nhận với bệnh nhân và cập nhật các thay đổi bằng tay. Cách làm này phù hợp khi lượng lịch ít, nhưng với quy mô khoảng 80–120 lượt bệnh nhân mỗi ngày, việc quản lý thủ công bắt đầu tạo ra nhiều vấn đề:

- ***Vấn đề 1:*** Việc đặt lịch và thay đổi lịch chủ yếu được thực hiện bởi **Nhân viên tiếp nhận**, **Bệnh nhân** muốn đặt lịch phải gọi điện trực tiếp => quá trình đặt lịch khám bệnh diễn ra lâu và tạo thêm nhiều công việc cho **Nhân viên tiếp nhận** khi số lượng đặt lịch lớn.
- ***Vấn đề 2:*** Quản lí lịch khám bị phân tán vì thông tin được ghi chép trong sổ sách, khi một nhân viên thay đổi mà các bộ phận chưa kịp cập nhật dẫn đến sử dụng thông tin lịch khám không giống nhau.
- ***Vấn đề 3:*** Xử lí khi có thay đổi đột xuất như có **Bác sĩ** nghỉ đột xuất, Nhân viên phải gọi từng bệnh nhân trong ca khám đó để thông => tốn thời gian.
- ***Vấn đề 4:*** **Bác sĩ** có yêu cầu muốn biết được bệnh nhân đặt lịch khám và những hồ sơ cần chuẩn bị trước nhưng chỉ được nhận lịch khám vào đầu mỗi ca.

Tóm lại, vấn đề hiện tại là việc **quản lí đặt lịch chưa nằm trên một hệ thống tập trung duy nhất** khiến việc tiếp cận thông tin giữa các bộ phận chưa được đồng bộ và mất nhiều thời gian.

## 1.2. Mục tiêu và giá trị mong đợi của hệ thống
Hệ thống được xây dựng nhằm hỗ trợ số hóa quy trình đặt lịch, tiếp nhận và theo dõi lịch khám tại Phòng khám An Tâm. Các mục tiêu và giá trị mong đợi gồm:

- **Hỗ trợ bệnh nhân đặt và thay đổi lịch thuận tiện hơn**, từ đó giảm sự phụ thuộc vào việc gọi điện hoặc đến trực tiếp phòng khám.
- **Tập trung thông tin lịch khám**, giúp nhân viên tiếp nhận theo dõi và cập nhật lịch trên cùng một hệ thống, hạn chế tình trạng thông tin thay đổi nhưng các bên liên quan không nắm được.
- **Hỗ trợ bác sĩ chủ động theo dõi lịch khám**, giúp bác sĩ biết trước bệnh nhân dự kiến đến và chuẩn bị các thông tin cần thiết cho ca khám.
- **Giảm thao tác thủ công cho nhân viên tiếp nhận**, đặc biệt trong việc ghi lịch, cập nhật thay đổi và xử lý các trường hợp lịch bị ảnh hưởng.
- **Hỗ trợ xử lý các thay đổi đột xuất hiệu quả hơn**, chẳng hạn khi bác sĩ nghỉ và nhiều lịch khám cần được điều chỉnh hoặc thông báo.
- **Cải thiện sự phối hợp giữa bệnh nhân, nhân viên tiếp nhận và bác sĩ**, thông qua việc sử dụng một nguồn thông tin lịch khám thống nhất.

## 2. Stakeholder

| Stakeholder | Vai trò | Nhu cầu | Ảnh hưởng đến hệ thống |
|---|---|---|---|
| **Quản lý phòng khám** | Quản lý hoạt động chung và định hướng cải tiến quy trình | Muốn bệnh nhân đặt lịch nhanh hơn, giảm việc gọi điện và giảm thao tác thủ công | Ảnh hưởng đến phạm vi, mục tiêu và các quy tắc vận hành của hệ thống |
| **Nhân viên tiếp nhận** | Trực tiếp quản lý lịch, tiếp nhận bệnh nhân và xử lý thay đổi | Cần xem và cập nhật lịch dễ dàng, thông tin phải thống nhất giữa các nhân viên | Ảnh hưởng lớn đến thiết kế quy trình quản lý lịch và tiếp nhận |
| **Bác sĩ** | Trực tiếp khám bệnh | Cần biết bệnh nhân nào sẽ đến và những thông tin cần chuẩn bị | Ảnh hưởng đến chức năng xem lịch, danh sách bệnh nhân và thông tin liên quan |
| **Bệnh nhân** | Người đặt lịch và sử dụng dịch vụ khám | Muốn đặt, đổi hoặc hủy lịch thuận tiện mà không phải đến trực tiếp | Ảnh hưởng đến các chức năng phía người dùng và mức độ dễ sử dụng của hệ thống |

## 3. Phạm vi hệ thống

### Trong phạm vi

Hệ thống tập trung hỗ trợ các nghiệp vụ liên quan đến đặt lịch,
tiếp nhận bệnh nhân và theo dõi lịch khám, bao gồm:

- Đặt lịch khám.
- Đổi hoặc hủy lịch.
- Quản lý và cập nhật lịch khám.
- Bác sĩ theo dõi danh sách bệnh nhân.
- Quản lý các thông tin cần thiết cho quá trình tiếp nhận.
- Hỗ trợ xử lý các thay đổi lịch, chẳng hạn khi bác sĩ nghỉ.

### Ngoài phạm vi

Hệ thống không tập trung giải quyết các nghiệp vụ khác của phòng khám như:

- Quản lý kho và cấp phát thuốc.
- Quản lý xét nghiệm, chẩn đoán hình ảnh.
- Quản lý tài chính, kế toán và tiền lương.
- Quản lý bệnh án điện tử đầy đủ.

## Bảng thuật ngữ nghiệp vụ
| Thuật ngữ | Giải thích |
|---|---|
| **Bệnh nhân** | Người sử dụng dịch vụ khám tại phòng khám. |
| **Bác sĩ** | Người trực tiếp thực hiện khám bệnh. |
| **Nhân viên tiếp nhận** | Người tiếp nhận bệnh nhân và quản lý lịch khám. |
| **Lịch khám / Lịch hẹn** | Thông tin về một lần bệnh nhân dự kiến đến khám. |
| **Đặt lịch** | Tạo một lịch khám mới. |
| **Đổi lịch** | Thay đổi thông tin của lịch đã đặt. |
| **Hủy lịch** | Chấm dứt một lịch khám đã tạo. |
| **Khung giờ khám** | Khoảng thời gian dùng để bố trí lịch khám. |
| **Ca làm việc** | Khoảng thời gian làm việc của bác sĩ hoặc nhân viên. |
| **Tiếp nhận bệnh nhân** | Ghi nhận và xử lý thông tin khi bệnh nhân đến khám. |
| **Danh sách lịch khám** | Danh sách bệnh nhân dự kiến đến khám. |
| **Hồ sơ bệnh nhân** | Thông tin liên quan đến bệnh nhân phục vụ tiếp nhận và khám. |
