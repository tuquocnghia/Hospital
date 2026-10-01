📋 PHÂN CHIA NHIỆM VỤ CHI TIẾT NHÓM 18 (CHUẨN 100% ĐỀ BÀI)

👤 THÀNH VIÊN 1 (Lead / BA) — Phụ trách Scope & Khảo sát:
• Đầu ra 01:
  - Phát biểu bài toán hiện tại, mục tiêu, giá trị kỳ vọng.
  - Bảng 4 Stakeholder (STK-01 -> STK-04): vai trò, nhu cầu, mức ảnh hưởng.
  - Phạm vi: In-scope và tối thiểu 3 Out-of-scope (kho thuốc, bệnh án EMR, kế toán).
  - Bảng thuật ngữ nghiệp vụ (Glossary) & từ viết tắt.
• Đầu ra 02 & Hồ sơ Minh chứng khảo sát:
  - Kế hoạch thu thập (chọn 2 kỹ thuật: Phỏng vấn sâu & Khảo sát).
  - Bộ 15 câu hỏi: 5 câu mở, 5 câu đóng, 5 ngoại lệ/NFR.
  - Soạn 1 Biên bản phỏng vấn mẫu (gặp Quản lý phòng khám).
  - Lập Bảng các vấn đề chưa rõ / Câu hỏi stakeholder chưa trả lời.
• Khung Mini-SRS & Hồ sơ nộp:
  - Tạo khung Google Docs tổng, viết mục Môi trường vận hành & Giả định/phụ thuộc.
  - Tạo Bảng lịch sử thay đổi phiên bản (v1.0 -> v1.1 do CR-01).
  - Cuối ngày: Gom bài cả nhóm, kiểm tra định dạng và xuất file PDF BT04_Nhom18_MiniSRS.pdf.

👤 THÀNH VIÊN 2 (Requirements Engineer) — Phụ trách Yêu cầu hệ thống:
• Đầu ra 03:
  - Đặc tả tối thiểu 10 FR (FR-01 -> FR-10) theo đúng mẫu bảng: ID, Loại, Nguồn, Độ ưu tiên (MoSCoW), Phiên bản, Mô tả ngữ cảnh, Lý do, Tiêu chí kiểm chứng.
  - Đặc tả tối thiểu 6 NFR (NFR-01 -> NFR-06) thuộc đủ 3 nhóm: Hiệu năng, Bảo mật, Khả dụng/Lưu trữ (có số đo định lượng, tuyệt đối không dùng từ mơ hồ).
  - Gắn nhãn rõ ràng: [Giả định] hoặc [Cần xác nhận] vào các tiêu chí chưa có số liệu chốt (thời gian khám trễ, xử lý khám gấp).
• Hỗ trợ CR-01:
  - Bổ sung 2 yêu cầu mới cho khám trực tuyến: FR-11 (Thanh toán trước) và FR-12 (Tự động hoàn tiền).

👤 THÀNH VIÊN 3 (Solution & Test Analyst) — Phụ trách Nghiệp vụ & Kịch bản:
• Đầu ra 04:
  - Đặc tả chi tiết 4 Scenarios theo mẫu (Actor, Pre-cond, Trigger, Main flow, Exception flow, Post-cond):
    + SC-01: Bệnh nhân đặt lịch thành công.
    + SC-02: Khung giờ hoặc bác sĩ không còn khả dụng.
    + SC-03: Bệnh nhân đổi hoặc hủy lịch.
    + SC-04 (Tự chọn): Xử lý bác sĩ nghỉ đột xuất / Tiếp nhận ca khám gấp.
• Đầu ra 06 (Phần Test):
  - Viết tối thiểu 6 Test Scenarios (TC-01 -> TC-06), mỗi test case phải ánh xạ trực tiếp đến Requirement ID tương ứng.
• Xử lý trọn gói CR-01 (Khám trực tuyến):
  - Bảng Phân tích tác động (Impact Analysis) đến 4 yếu tố: Yêu cầu, Kịch bản, Dữ liệu, Test case.
  - Nêu tối thiểu 3 rủi ro / câu hỏi mới cần làm rõ.
  - Cập nhật nhánh rẽ thanh toán vào SC-01 và nhánh rẽ hoàn tiền vào SC-04.

👤 THÀNH VIÊN 4 (QA & Traceability Lead) — Phụ trách Kiểm định & Truy vết:
• Đầu ra 06 (Phần Review):
  - Chủ trì buổi Peer Review nội bộ, đối chiếu chéo theo 6 tiêu chí: Đúng đắn, Đầy đủ, Nhất quán, Khả thi, Rõ ràng, Đo lường được.
  - Lập Bảng Validation Report ghi nhận tối thiểu 8 lỗi/vấn đề phát hiện.
  - Ghi nhận quyết định cho từng lỗi: Sửa (Fix) hoặc Không sửa (No-fix) kèm lý do kỹ thuật.
• Ma trận truy vết (Traceability Matrix):
  - Lập bảng kết nối xuyên suốt các cột: Nhu cầu -> Stakeholder -> Req ID (FR/NFR) -> Scenario -> Test case -> Change request (CR-01).
  - Rà soát đảm bảo 100% yêu cầu đều được test và không có ô nào bị bỏ trống liên kết.
• Soát Checklist nộp bài:
  - Rà soát toàn bộ văn bản để loại bỏ các từ ngữ mơ hồ ("nhanh chóng", "dễ dùng", "an toàn").