# Đầu ra 02 · Elicitation Plan

## 1. Kỹ thuật thu thập yêu cầu

Nhóm sử dụng hai kỹ thuật: **Phỏng vấn trực tiếp (Interviewing)** và **Quan sát (Observing)**.

| Kỹ thuật | Mục tiêu | Đối tượng | Vai trò | Thời lượng | Cách ghi nhận |
|---|---|---|---|---|---|
| **Phỏng vấn trực tiếp** | Tìm hiểu quy trình hiện tại, khó khăn, nhu cầu và quy tắc nghiệp vụ | Quản lý phòng khám, nhân viên tiếp nhận, bác sĩ, bệnh nhân | Cung cấp yêu cầu và xác nhận cách nghiệp vụ đang được thực hiện | 20–30 phút/người | Ghi chú; ghi âm khi được đồng ý |
| **Quan sát** | Kiểm tra quy trình thực tế và phát hiện các thao tác, vấn đề có thể không được nhắc tới khi phỏng vấn | Nhân viên tiếp nhận và bệnh nhân tại quầy | Cung cấp bằng chứng về cách quy trình thực tế diễn ra | 60–90 phút/buổi | Ghi lại các bước thực hiện, thời gian xử lý và vấn đề phát sinh |

---

## 2. Bộ câu hỏi phỏng vấn
### Vấn đề: Đặt lịch và tiếp nhận bệnh nhân
#### Câu hỏi mở
1. Anh/chị có thể mô tả quy trình từ khi bệnh nhân yêu cầu đặt lịch cho đến khi lịch được xác nhận không?
2. Trong quá trình đặt lịch hiện tại, bước nào thường mất nhiều thời gian hoặc dễ xảy ra sai sót nhất?
3. Khi tiếp nhận một bệnh nhân mới, nhân viên cần thu thập những thông tin nào?

#### Câu hỏi đóng
1. Bệnh nhân có được phép lựa chọn bác sĩ khi đặt lịch không?  
   **Có / Không**
2. Bệnh nhân có thể đổi hoặc hủy lịch đã đặt không?  
   **Có / Không**
3. Sau khi đặt lịch thành công, bệnh nhân có cần nhận thông báo xác nhận không?  
   **Có / Không**

### Vấn đề Quản lý lịch bác sĩ
#### Câu hỏi mở
4. Bác sĩ hiện kiểm tra lịch khám của mình bằng cách nào?
5. Khi bác sĩ thay đổi lịch làm việc hoặc nghỉ đột xuất, phòng khám hiện xử lý các lịch hẹn đã có như thế nào?
6. Bác sĩ cần xem những thông tin nào của một lịch khám để chuẩn bị cho ca khám?

#### Câu hỏi đóng
4. Bác sĩ có được phép tự cập nhật lịch làm việc của mình không?  
   **Có / Không**
5. Hệ thống có cần ngăn việc hai bệnh nhân được đặt vào cùng một khung giờ của một bác sĩ không?  
   **Có / Không**
6. Khi lịch bác sĩ thay đổi, bệnh nhân có cần được thông báo tự động không?  
   **Có / Không**

## 3. Câu hỏi làm rõ ngoại lệ và yêu cầu phi chức năng
### Ngoại lệ

1. Nếu bác sĩ nghỉ đột xuất nhưng đã có bệnh nhân đặt lịch thì hệ thống phải xử lý các lịch hẹn đó như thế nào?
2. Nếu hai nhân viên cùng đặt một khung giờ cho hai bệnh nhân gần như cùng lúc thì hệ thống phải xử lý thế nào?
3. Nếu bệnh nhân đến trễ hoặc không đến khám thì lịch hẹn cần được xử lý và cập nhật trạng thái như thế nào?
4. Nếu bệnh nhân muốn đổi lịch nhưng khung giờ mong muốn đã đầy thì hệ thống cần hỗ trợ nhân viên ra sao?

### Yêu cầu phi chức năng
5. Sau khi lịch khám được tạo hoặc thay đổi, thông tin cần xuất hiện trên màn hình của bác sĩ trong thời gian tối đa bao lâu?  
   → Làm rõ yêu cầu về **hiệu năng và thời gian phản hồi**.
6. Những vai trò nào được phép xem, tạo, sửa hoặc hủy lịch khám và thông tin bệnh nhân?  
   → Làm rõ yêu cầu về **bảo mật và phân quyền**.
7. Nếu mất kết nối mạng trong quá trình sử dụng, hệ thống cần đảm bảo những chức năng nào vẫn có thể thực hiện hoặc phục hồi sau khi có mạng?  
   → Làm rõ yêu cầu về **độ tin cậy và khả năng phục hồi**.

## 4. Kết quả cần thu được

Sau quá trình elicitation, nhóm cần xác định được:

- Quy trình nghiệp vụ thực tế của phòng khám.
- Functional Requirements cho đặt lịch, đổi/hủy lịch, tiếp nhận và quản lý lịch bác sĩ.
- Các quy tắc nghiệp vụ như tránh trùng lịch và quyền thay đổi lịch.
- Các trường hợp ngoại lệ cần hệ thống xử lý.
- Non-functional Requirements về hiệu năng, bảo mật, phân quyền và khả năng phục hồi.
