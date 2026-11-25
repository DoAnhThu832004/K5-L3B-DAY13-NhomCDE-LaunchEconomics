# Hồ sơ launch v0 · Trợ lý hoàn phí LogiX-VN · Gate 2a

Một trang. Cột trạng thái chỉ nhận: **Xong, có bằng chứng · Chưa · Giả lập**. Mục nào dựa trên cột `_simulated` ghi Giả lập. Người phụ trách là một vai trò, không ghi "cả đội". Gate 2a chỉ duyệt kế hoạch pilot: không viết như thể trợ lý đã được duyệt chạy chính thức (xem quy tắc 5 trong `README.md`).

Nhóm: NhomCDE · Lớp: L3B

| Mục | Con số chính | Trạng thái | Người phụ trách |
| --- | --- | --- | --- |
| 1 · Chi phí mỗi việc thành công | **4.472 đ** [simulated] (gấp 16,3× hoá đơn 274,7 đ); phạm vi `noi_dia + hang_nang` tối đa 2 lần chạy gồm chi phí cố định 40 triệu đ/tháng là **4.447 đ = 0,37×** của 12.000 đ ở 45.000 yc/tháng, nửa khối lượng là **5.784 đ = 0,48×** [simulated] | Giả lập | PM trợ lý hoàn phí |
| 2 · Ba yếu tố nhạy nhất | **1. Số ca làm lại (+51,8%) · 2. Tỉ lệ xem lại (+40,7%) · 3. Lương nhân viên (+23,1%)** [simulated]. Token ít nhạy nhất (+5,6%); đổi cặp token ×2 và xem lại ×2 tăng **+46,3%** (cộng tuyến tính) | Giả lập | PM trợ lý hoàn phí |
| 3 · So với nhân viên tự làm | Cả hệ thống toàn mẫu (2 lần chạy) = **6.901.220 đ** [simulated]; riêng phạm vi `noi_dia + hang_nang` = **3.980.391 đ/982 yc** [simulated] (rẻ nhất cho công ty); loại `quoc_te` (22.515 đ = **1,88×**) và `doi_tac` (**0,85×**, có điều khoản riêng). B4 xem lại 100% gồm cố định là **12.928–13.600 đ = 1,08×–1,13×** [simulated] (đắt hơn người tự làm) | Giả lập | PM trợ lý hoàn phí |
| 4 · Chỉ số chính, chỉ số dùng, chỉ số an toàn | Chạy thử trên 1.200 yc: chính **82,83%** (994/1.200, chưa có đối chứng); dùng (bỏ qua) **27,12%** (48/177); an toàn (mở lại 7 ngày) **4,25%** (51/1.200; trong phạm vi là 3,97%). Đủ đặc tả 2 chỉ số đề xuất và **10 event có trace_id** trong `chi_so.md` | Xong, có bằng chứng | Trưởng nhóm CSKH |
| 5 · Bảng lỗi và cách khắc phục | Gắn nhãn độc lập 20 ca đạt đồng thuận **17/20 = 85%**; 3 quy tắc phân biệt; bảng khắc phục 5 ca đủ 5 loại lỗi của Google PAIR có event, ngưỡng phát hiện đo được và một vai trò chịu trách nhiệm | Xong, có bằng chứng | Kỹ sư trưởng agent |
| 6 · Pilot plan | Chia ngẫu nhiên **20 + 20 nhân viên** phân tầng theo depot (seed 20261125); **MDE 6 điểm** (`n = 859`/nhóm, `m ≥ 299` yc/người, `DE = 6,96`); nếu tác động thật là 5 điểm thì `power` còn **0,64**; rollout 4→10→20 người; **3 luật dừng** đủ 4 vế NẾU–TRONG–THÌ–KHÔNG THÌ; cờ rollback tắt trong 30 phút | Xong, có bằng chứng | Giám đốc vận hành LogiX-VN |
| 7 · Rủi ro kinh tế | Đủ 3 dòng rủi ro trong `chi_so.md` (làm lại ×2 tăng CPS lên 6.787 đ; xem lại 100% gồm cố định tăng lên 12.928–13.600 đ = 1,08×–1,13× đắt hơn người; nửa khối lượng chi phí cố định tăng lên 2.370 đ/việc), mỗi rủi ro có ngưỡng kích hoạt và hành động cụ thể [simulated] | Giả lập | PM trợ lý hoàn phí |

**Đề xuất:** Go có điều kiện cho kế hoạch pilot phạm vi `noi_dia + hang_nang`, giới hạn tối đa 2 lần chạy.

**Bốn điều kiện trước khi chạy (kiểm tra ngày 30/11/2026):**
1. **PM trợ lý hoàn phí** và **Trưởng nhóm CSKH** hoàn tất các tài liệu đo lường, bật đủ event có `trace_id` để thay số phút `_simulated` bằng phút đo thật sau tuần 1.
2. **Kỹ sư trưởng agent** kiểm chứng khóa chống trùng và đối soát sổ cái tự động (chỉ báo *"đã hoàn"* khi sổ cái trả `ok`, ngưỡng 0 ca sai lệch), đồng thời bổ sung ca 7 và ca 20 vào `bang_loi.md`; **Giám đốc vận hành LogiX-VN** thử nghiệm thành công nút tắt rollback trong 30 phút.
3. **Giám đốc vận hành LogiX-VN** ký phê duyệt văn bản chấp nhận đánh đổi chia 20+20 nhân viên với mức chênh MDE 6 điểm (`n = 859`/nhóm, `m ≥ 299`), chấp nhận `power` giảm còn 0,64 nếu hiệu ứng thật là 5 điểm.
4. **Trưởng nhóm CSKH** ban hành lộ trình giảm tỉ lệ xem lại theo bậc (100% → 50% → 25%) và rút ngắn thời gian xem lại mỗi ca xuống mức hoà vốn ≤ 4,2–4,6 phút/ca.
