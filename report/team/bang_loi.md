# Bảng lỗi và cách khắc phục · Nhiệm vụ C

20 ca lỗi nằm trong `docs/Ngay13_Lab13_De_bai_hoc_vien.docx`. Năm loại theo Google PAIR: **Do người dùng · Hệ thống · Ngữ cảnh · Giới hạn hệ thống · Ngầm**. Gắn nhãn theo nguyên nhân gốc, không theo chỗ cần sửa.

## Hai bộ nhãn độc lập

Người gắn nhãn 1: ... · Người gắn nhãn 2: ... (gắn trong 8 phút, không trao đổi)

| Ca | Nhãn người 1 | Nhãn người 2 | Trùng? | Nhãn thống nhất |
| --: | --- | --- | --- | --- |
| 1 | Do người dùng | Do người dùng | Trùng | Do người dùng |
| 2 | Hệ thống | Hệ thống | Trùng | Hệ thống |
| 3 | Ngữ cảnh | Ngữ cảnh | Trùng | Ngữ cảnh |
| 4 | Giới hạn hệ thống | TrùHệ thống | Trùng | Hệ thống |
| 5 | Ngầm | Ngầm | Trùng | Ngầm |
| 6 | Do người dùng | Hệ thống | Không | Do người dùng |
| 7 | Hệ thống | Hệ thống | Trùng | Hệ thống |
| 8 | Hệ thống | Ngữ cảnh | Không | Hệ thống |
| 9 | Do người dùng | Ngầm | Không | Do người dùng |
| 10 | Ngữ cảnh | Ngữ cảnh | Trùng | Ngữ cảnh |
| 11 | Giới hạn hệ thống | Hệ thống | Trùng | Hệ thống |
| 12 | Ngầm | Ngầm | Trùng | Ngầm |
| 13 | Giới hạn hệ thống | Giới hạn hệ thốn | Trùng | Giới hạn hệ thốn |
| 14 | Do người dùng | Do người dùng | Trùng | Do người dùng |
| 15 | Hệ thống | Hệ thống | Trùng | Hệ thống |
| 16 | Ngữ cảnh | Ngữ cảnh | Trùng | Ngữ cảnh |
| 17 | Ngầm | Ngầm | Trùng | Ngầm |
| 18 | Ngữ cảnh | Ngữ cảnh | Trùng | Ngữ cảnh |
| 19 | Giới hạn hệ thống| Giới hạn hệ thốn | Trùng | Giới hạn hệ thốn |
| 20 | Hệ thống | Hệ thống | Trùng | Hệ thống |

**Tỉ lệ đồng thuận:** 17 / 20 = 85%

## Quy tắc phân biệt cho các ca không trùng
D:\Document_D\Vin_AI\K5-L34-Day13-Lab\report\team\bang_loi.md
Mỗi ca không trùng một câu. Đồng thuận dưới 80% thì ghi định nghĩa đã viết lại.

- Khách chọn mục giao trễ cho ca hàng vỡ, khiến trợ lý đi theo luồng đã chọn. 
- Trợ lý viện dẫn điều khoản không có trong chính sách hiện hành, dù số tiền hoàn đúng. |
- Khách nhập mã đơn sàn vào ô mã vận đơn. Trợ lý đã báo mã không hợp lệ ngay. |
## Bảng khắc phục cho 5 ca, mỗi loại một ca

Cách phát hiện phải đo được (event, ngưỡng, tần suất). Người phụ trách là một vai trò, không ghi "cả đội".

| Ca | Loại lỗi | Phát hiện bằng gì | Khắc phục thế nào | Ai phụ trách |
|---:|---|---|---|---|
| 6 | Do người dùng | Ghi một event mỗi lần mục khách chọn mâu thuẫn với mô tả, ví dụ mục giao trễ nhưng nội dung nói hàng bị vỡ. | Hỏi khách xác nhận lại loại sự cố trước khi xử lý. | Quản lý sản phẩm luồng hoàn phí |
| 8 | Hệ thống | Kiểm tra từng điều khoản được viện dẫn với bản chính sách hiện hành. Cảnh báo khi một điều khoản không tồn tại. | Chỉ cho phép gửi căn cứ đã được đối chiếu. Nếu không xác minh được, chuyển nhân viên xem lại. | Kỹ sư phụ trách trợ lý |
| 18 | Ngữ cảnh | Đếm hằng tuần số yêu cầu mở lại vì khách cho rằng được hoàn thiếu, dù phép tính đúng. | Hiển thị phí ban đầu, tỷ lệ hoàn và phép tính ngay trong tin nhắn, ví dụ `30.000 đ × 50% = 15.000 đ`. | Quản lý sản phẩm CSKH |
| 19 | Giới hạn hệ thống | Ghi một event cho mỗi yêu cầu tra đơn quá 12 tháng và theo dõi số ca chuyển nhân viên hằng tuần. | Thông báo giới hạn tra cứu và chuyển yêu cầu cho nhân viên kèm mã đơn, ngày giao và lý do hoàn phí. | Trưởng nhóm CSKH |
| 17 | Ngầm | Đối soát hằng ngày số tiền đã hoàn với bảng giá có hiệu lực tại thời điểm tính hoàn. Cảnh báo khi phát hiện chênh lệch. | Làm mới bộ nhớ đệm khi bảng giá đổi và rà soát lại các đơn bị ảnh hưởng. | Kỹ sư phụ trách tích hợp bảng giá |