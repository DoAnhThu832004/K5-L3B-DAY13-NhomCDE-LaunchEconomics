# Báo cáo nhóm

Báo cáo ngắn, tối đa 2 trang. Số liệu chi tiết nằm trong các file hồ sơ; ở đây chỉ dẫn lại con số chính.

## 1. Thông tin nhóm

- Tên nhóm: NhomCDE
- Lớp: L3B
- Thành viên: xem `TEAM.md` (Đỗ Anh Thư, Võ Thanh Huy, Vũ Hiếu và các thành viên nhóm)

## 2. Mục tiêu và cách tiếp cận

Xây dựng bộ hồ sơ thẩm định Gate 2a hoàn chỉnh cho Trợ lý hoàn phí tự động tại công ty vận tải giả định LogiX-VN (quy mô 12 depot, 40 nhân viên CSKH, 45.000 yêu cầu/tháng). Nhóm tiếp cận toàn diện qua 4 khía cạnh:
1. **Kinh tế học Agent (CPS & Kinh tế học thử lại):** Đánh giá chi phí thật cho mỗi việc thành công từ dữ liệu trace, bóc tách giờ nhân viên xem lại và làm lại.
2. **Quản trị rủi ro & Phân loại lỗi:** Phân loại 20 ca lỗi theo chuẩn Google PAIR, đạt đồng thuận độc lập và thiết kế cơ chế phát hiện tự động.
3. **Thiết kế thử nghiệm Pilot chuẩn khoa học:** Tính toán cỡ mẫu có điều chỉnh hiệu ứng cụm (cluster randomization), kiểm soát hiện tượng tràn tác động và ban hành luật dừng an toàn viết trước.
4. **Hồ sơ ra quyết định:** Tổng hợp các bằng chứng để hội đồng Gate 2a thẩm định minh bạch, nêu rõ đánh đổi và điều kiện triển khai.

## 3. Giải pháp

- **Nhiệm vụ A — Mô hình chi phí ([bang_chi_phi.md](bang_chi_phi.md)):** Hoàn thiện 3 hàm xác suất A1, hàm `mo_hinh` A2 tính tổng chi phí gồm token, tool, phút xem lại và làm lại chia cho số việc thành công. Phân tích A3 theo 4 loại đơn và tính chi phí cố định 40 triệu đ/tháng ở A4.
- **Nhiệm vụ B — Bảng độ nhạy ([bang_chi_phi.md](bang_chi_phi.md)):** Khảo sát 9 kịch bản đơn lẻ B1, chứng minh tính cộng tuyến tính khi đổi cặp B2, phân tích chi phí toàn hệ thống theo số lần chạy B3 và kịch bản xem lại 100% ở B4.
- **Nhiệm vụ C — Bảng lỗi và cách khắc phục ([bang_loi.md](bang_loi.md)):** Hai thành viên dán nhãn độc lập 20 ca lỗi theo 5 nhóm của Google PAIR đạt đồng thuận **85%** (17/20 ca). Xây dựng quy tắc phân biệt cho 3 ca không trùng và lập bảng khắc phục cho 5 ca tiêu biểu với event và ngưỡng phát hiện đo được.
- **Nhiệm vụ D — Kế hoạch pilot ([pilot_plan.yaml](pilot_plan.yaml)):** Tính toán 5 bài toán cỡ mẫu D1; chọn cách chia ngẫu nhiên 20 + 20 nhân viên phân tầng depot; chấp nhận đánh đổi MDE 6 điểm (`n = 859`, `m ≥ 299`); thiết lập 3 luật dừng đủ 4 vế NẾU–TRONG–THÌ–KHÔNG THÌ và cờ rollback tắt trong 30 phút.
- **Nhiệm vụ E — Đặc tả chỉ số và Hồ sơ launch v0 ([chi_so.md](chi_so.md), [ho_so_launch_v0.md](ho_so_launch_v0.md)):** Đặc tả 3 chỉ số chạy thử, đề xuất 2 chỉ số mới, liệt kê 10 event có `trace_id` và 3 dòng rủi ro kinh tế. Hoàn thiện hồ sơ 1 trang và thẩm định chéo nhóm bạn ([phieu_cham.md](phieu_cham.md)).

## 4. Kết quả

- **Chi phí mỗi việc thành công (CPS):** Toàn mẫu là **4.472 đ** [simulated] (gấp 16,3× hoá đơn token+tool). Giờ nhân viên chiếm **92,5%** tổng chi phí (Làm lại: 51,8%, Xem lại: 40,7%).
- **Phạm vi triển khai tối ưu:** Thu hẹp về `noi_dia` (2.696 đ = 0,22×) và `hang_nang` (8.221 đ = 0,69×). Loại bỏ `quoc_te` (22.515 đ = **1,88×** [simulated], tỉ lệ thành công chỉ 27,3%) và `doi_tac` (10.215 đ = 0,85×).
- **Giới hạn số lần chạy:** Giới hạn tối đa **2 lần chạy** mang lại chi phí cả hệ thống rẻ nhất cho công ty (**3.980.391 đ/982 yêu cầu** trong phạm vi, hoặc 6.901.220 đ trên toàn mẫu [simulated]). CPS gồm cố định là **4.447 đ = 0,37×** ở mức 45.000 yêu cầu/tháng [simulated].
- **Con số bất lợi:** Nếu phải xem lại 100%, chi phí cộng cố định vọt lên **12.928–13.600 đ = 1,08×–1,13×** [simulated], đắt hơn nhân viên tự làm.
- **Đề xuất cuối cùng:** **Go có điều kiện** cho kế hoạch pilot `noi_dia + hang_nang`, tối đa 2 lần chạy, kèm 4 điều kiện kiểm tra trước ngày 30/11/2026.
- **Kết quả duyệt chéo:** Nhóm hoàn thành chấm hồ sơ nhóm EA1125 đạt **30/30 điểm** (Go có điều kiện) với đầy đủ đối chứng số liệu và câu hỏi phản biện tại lớp.

## 5. Khó khăn và cách xử lý

- *Bẫy tối ưu cục bộ chi phí:* Ban đầu mức 1 lần chạy cho CPS thấp nhất (4.111 đ), nhưng khi tính chi phí cả hệ thống thì đẩy thêm 85 ca sang nhân viên xử lý thủ công (tốn 12.000 đ/ca). Nhóm đã chọn mức 2 lần chạy tối ưu toàn diện.
- *Thiếu hụt cỡ mẫu theo cụm:* Với 40 nhân viên và ICC = 0,02, không thể phát hiện mức chênh 5 điểm. Nhóm đã giải phương trình thống kê chấp nhận MDE 6 điểm và nêu rõ độ nhạy power còn 0,64 nếu hiệu ứng thật là 5 điểm.
- *Ngưỡng an toàn bị kích hoạt sớm:* Tỉ lệ mở lại hiện tại là 4,25% (3,97% trong phạm vi). Nhóm tránh bẫy đặt ngưỡng tuyệt đối 3% (sẽ dừng pilot ngay tuần 1), thay bằng ngưỡng so với đối chứng chênh ≥ 2 điểm kèm trần tuyệt đối 6%.

## 6. Tổng hợp đóng góp

Chi tiết vai trò, cam kết và bằng chứng của từng thành viên được ghi nhận cụ thể trong `TEAM.md` và các báo cáo cá nhân `MSSV_HoTen.md`.

## 7. Hạn chế và hướng cải thiện

- Toàn bộ thời gian xem lại và làm lại hiện dựa trên dữ liệu giả lập `_simulated`. Cần thay thế bằng số đo phút thật ngay sau tuần đầu tiên của bước rollout 0.10.
- Cần hoàn tất triển khai đối soát sổ cái tự động theo `trace_id` trước thông báo để loại bỏ hoàn toàn nguy cơ hoàn tiền trùng (ca 7, ca 20).
- Cần nghiên cứu cơ chế giảm xem lại theo bậc an toàn nhằm tránh rơi vào kịch bản xem lại 100% gây lỗ chi phí.

## 8. Tài liệu tham khảo

1. Erol et al., *Cost-of-Pass: An Economic Framework for Evaluating Language Models*, arXiv:2504.13359.
2. Google PAIR, *People + AI Guidebook: Errors + Graceful Failure*.
3. Thư viện `statsmodels.stats.power.NormalIndPower` cho tính toán Cluster Randomization.
4. Tài liệu hướng dẫn Lab 13 — AI20K K5, Viện Công nghệ VinUni.

