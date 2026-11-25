# Bảng lỗi và cách khắc phục · Nhiệm vụ C

20 ca lỗi nằm trong `docs/Ngay13_Lab13_De_bai_hoc_vien.docx`. Năm loại theo Google PAIR: **Do người dùng · Hệ thống · Ngữ cảnh · Giới hạn hệ thống · Ngầm**. Gắn nhãn theo nguyên nhân gốc, không theo chỗ cần sửa.

## Hai bộ nhãn độc lập

Người gắn nhãn 1: ... · Người gắn nhãn 2: vuhieuvh (gắn trong 8 phút, không trao đổi)

| Ca | Nhãn người 1 | Nhãn người 2 | Trùng? | Nhãn thống nhất |
| --: | --- | --- | --- | --- |
| 1 | ... | Do người dùng | ... | ... |
| 2 | ... | Hệ thống | ... | ... |
| 3 | ... | Ngữ cảnh | ... | ... |
| 4 | ... | Giới hạn hệ thống | ... | ... |
| 5 | ... | Ngầm | ... | ... |
| 6 | ... | Do người dùng | ... | ... |
| 7 | ... | Hệ thống | ... | ... |
| 8 | ... | Hệ thống | ... | ... |
| 9 | ... | Do người dùng | ... | ... |
| 10 | ... | Ngữ cảnh | ... | ... |
| 11 | ... | Giới hạn hệ thống | ... | ... |
| 12 | ... | Ngầm | ... | ... |
| 13 | ... | Giới hạn hệ thống | ... | ... |
| 14 | ... | Do người dùng | ... | ... |
| 15 | ... | Hệ thống | ... | ... |
| 16 | ... | Ngữ cảnh | ... | ... |
| 17 | ... | Ngầm | ... | ... |
| 18 | ... | Ngữ cảnh | ... | ... |
| 19 | ... | Giới hạn hệ thống | ... | ... |
| 20 | ... | Hệ thống | ... | ... |

**Tỉ lệ đồng thuận:** ... / 20 = ...%

## Quy tắc phân biệt cho các ca không trùng

Mỗi ca không trùng một câu. Đồng thuận dưới 80% thì ghi định nghĩa đã viết lại.

- ...

## Bảng khắc phục cho 5 ca, mỗi loại một ca

Cách phát hiện phải đo được (event, ngưỡng, tần suất). Người phụ trách là một vai trò, không ghi "cả đội".

| Ca | Loại lỗi | Phát hiện bằng gì | Khắc phục thế nào | Ai phụ trách |
| --: | --- | --- | --- | --- |
| 9 | Do người dùng | Event `input_validation_failed` gắn `trace_id`; cảnh báo khi vượt > 2% tổng yêu cầu/ngày | Tự nhận diện định dạng mã sàn TMĐT để tra chéo sang mã vận đơn; nếu không tra được thì hiển thị hướng dẫn kèm ảnh minh hoạ | PM trợ lý hoàn phí |
| 7 | Hệ thống | Job đối soát mỗi giờ: tin nhắn báo "đã hoàn" không có bản ghi `refund_ledger_write` trạng thái `ok` cùng `trace_id`; ngưỡng > 0 ca | Chỉ cho phép gửi thông báo "đã hoàn" khi sổ cái trả `ok`; sau 3 lần lỗi 503 chuyển sang trạng thái "đang xử lý" và tạo `handoff_to_staff` | Kỹ sư trưởng agent |
| 18 | Ngữ cảnh | Tỉ lệ `ticket_reopened` có lý do "hoàn thiếu" nhưng kiểm tra sổ cái thấy đúng số tiền, đo hằng tuần; ngưỡng > 1% | Cập nhật mẫu tin nhắn hoàn phí bắt buộc hiển thị công thức tính rõ ràng (ví dụ: `30.000 đ × 50% = 15.000 đ`) | Trưởng nhóm CSKH |
| 4 | Giới hạn hệ thống | Event `handoff_to_staff` với `reason = thieu_du_lieu_ngoai_pham_vi`, gom theo cột `loai` mỗi ngày | Giữ cơ chế chuyển nhân viên kèm bản tóm tắt đầy đủ; loại hẳn nhóm `quoc_te` khỏi phạm vi pilot | PM trợ lý hoàn phí |
| 17 | Ngầm | Event `audit_sample_checked`: kiểm tra mẫu 100 đơn/tuần đối chiếu bảng giá hiện hành; ngưỡng > 1% đơn lệch số tiền | Xoá bộ nhớ đệm (cache) ngay khi phát hành bảng giá mới và ghi kèm mã phiên bản bảng giá vào mỗi `trace_id` | Kế toán trưởng |
