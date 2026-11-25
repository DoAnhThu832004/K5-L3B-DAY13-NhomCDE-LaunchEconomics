# Báo cáo cá nhân — Võ Thanh Huy — 2A202603879

## 1. Thông tin thành viên

- Họ tên: Võ Thanh Huy
- MSSV: 2A202603879
- Email: huyvo180700@gmail.com
- Vai trong nhóm: Người kiểm số ở CP1, người gắn nhãn 1 ở CP3.

## 2. Phần việc phụ trách

- CP1: Đối chiếu kết quả A1–A4 và điền bảng chi phí của nhóm.
- CP3: Phân loại ca lỗi, đối chiếu với bộ nhãn của Vũ Hiếu và đề xuất cách phát hiện, khắc phục cho các ca đại diện.

## 3. Đóng góp cụ thể

- A1: Tính tay và đối chiếu ba kết quả 1,20, 1,25 và 1,25.
- A2: Kiểm lại số lượt gọi tool, số yêu cầu thành công và mẫu số của hai chỉ số chi phí.
- A3: So sánh bốn loại yêu cầu và kiểm tỷ lệ lượt chạy OK theo từng lần thử của `quoc_te`.
- A4: Đối chiếu chi phí cố định trên mỗi việc thành công ở hai mức khối lượng.
- CP3: Tự gán nhãn 10 ca đầu, rà nhãn tham khảo cho ca 11–20 và đối chiếu với bộ nhãn của Vũ Hiếu. Phân tích ba ca lệch 6, 8 và 9. Đề xuất event, ngưỡng phát hiện và vai trò phụ trách cho năm ca 6, 8, 18, 19 và 17.

## 4. Bằng chứng

- [Bảng chi phí A1–A4](bang_chi_phi.md). Ở A1, với 100 yêu cầu và xác suất thành công 80%, kỳ vọng có 100 lượt đầu và 20 lượt chạy lại. Trung bình là `(100 + 20) / 100 = 1,20` lượt/yêu cầu.
- Ở A2, `5.600 × 15 = 84.000 đ` tiền tool. Dữ liệu có `978/1.200` yêu cầu thành công. Kết quả được đối chiếu với output của `python lab13.py` tại commit `b85c38f`.
- [Bảng lỗi và cách khắc phục](bang_loi.md). Với ca 8, bảng đề xuất ghi event `policy_reference_invalid` khi có ít nhất một điều khoản được viện dẫn không tồn tại, sau đó chuyển đề xuất cho nhân viên xem lại.

## 5. Công cụ AI đã dùng

- ChatGPT để giải thích công thức và hỗ trợ tính lại A2–A4 từ hai CSV. Kết quả được so với output của `lab13.py`.
- Ở CP3, dùng ChatGPT để đối chiếu nhãn với đề bài và bảng tham khảo, phân tích các ca lệch và soạn event cùng ngưỡng phát hiện. Dùng mô tả gốc của từng ca và bảng nhãn nhóm để rà lại nội dung.

## 6. Tự đánh giá

- Ở CP1, học được cách kiểm mẫu số trước khi đối chiếu. Tổng chi phí tính cả các lượt chạy thất bại, còn chi phí trên mỗi việc thành công chia cho số yêu cầu thành công.
- Ở CP3, học được cách dùng chi tiết trong đề để giải thích nhãn. Ví dụ, viện dẫn điều khoản không tồn tại vẫn là lỗi hệ thống dù số tiền hoàn đúng. Khi đối chiếu, tôi cần lưu riêng hai bộ nhãn ban đầu và ghi kết quả thống nhất ở cột cuối.