# Phiếu chấm hội đồng Gate 2a

Nhóm số n chấm nhóm số n + 1; nhóm cuối chấm nhóm 1. Chấm theo bằng chứng trong hồ sơ, không theo cách trình bày: một đề xuất No-go có lý do bằng số được điểm cao hơn một đề xuất Go bỏ qua con số bất lợi.

- Nhóm chấm (hội đồng): NhomCDE
- Nhóm được chấm: EA1125

| Tiêu chí | 0 điểm | 5 điểm | 10 điểm | Điểm | Lý do (có số) |
| --- | --- | --- | --- | ---: | --- |
| Đề xuất khớp bằng chứng | Mâu thuẫn với số của chính nhóm | Khớp nhưng bỏ qua một con số bất lợi | Khớp, nêu cả con số bất lợi và cách xử lý | 10 | Đề xuất Go có điều kiện khớp chi phí hệ thống 6.385,88 đ/yc (< 12.000 đ) và CPS có cố định 4.599,09 đ; nêu thẳng rủi ro B4 (11.742,79–12.414,50 đ), power 0,6418 ở 5 điểm và điều kiện sửa chống trùng/ghi sổ trước 30/11/2026. |
| Số giả lập và phạm vi | Không nhãn; phạm vi "mọi yêu cầu" | Có nhãn hoặc có thu hẹp phạm vi | Nhãn ở mọi số giả lập; phạm vi thu hẹp có lý do bằng số | 10 | Mọi chi phí từ `_simulated` đều có nhãn `simulated` (mục 1, 2, 3, 7); thu hẹp về `noi_dia + hang_nang` có số liệu loại `quoc_te` (22.515,16 đ, thành công 27,33%) và `doi_tac` (10.214,87 đ). |
| Pilot ra được quyết định | Không đối chứng hoặc thiếu cỡ mẫu | Đủ cỡ mẫu, luật dừng chung chung | Tách được tác động, đủ mẫu, luật dừng có ngưỡng, thời hạn, người có quyền dừng | 10 | Chia ngẫu nhiên 20+20 nhân viên phân tầng depot (seed 20261125); đủ mẫu MDE 6 điểm (n=859, m=299, DE=6,96); 4 luật dừng đủ 4 vế có ngưỡng (≥2 điểm/>6%, 0 ca hoàn trùng, >8.000 đ, >40%), thời hạn và Giám đốc vận hành tắt trong 30 phút. |
| **Tổng** | | | | **30 / 30** | |

**Quyết định của hội đồng:** Go có điều kiện

**Lý do:** Hồ sơ `EA1125` đầy đủ bằng chứng, nhất quán giữa số liệu và đề xuất: thu hẹp đúng phạm vi `noi_dia + hang_nang` tối đa 2 lần (6.385,88 đ/yc toàn công ty, simulated), gắn nhãn `simulated` đầy đủ, không giấu số bất lợi (B4 11.742,79–12.414,50 đ; power 0,6418 nếu hiệu ứng 5 điểm), có 4 luật dừng và điều kiện kỹ thuật rõ ràng trước ngày chạy. Đội trình cũng trả lời đúng câu hỏi phản biện về ngưỡng 3% vs nền 4,25% (3,97% trong phạm vi).

**Một câu hỏi cho đội trình:** Với tỉ lệ `mo_lai_trong_7_ngay` hiện tại là 4,25% (3,97% trong phạm vi), nếu đặt luật dừng an toàn là "vượt 3%" thì chuyện gì xảy ra?

**Câu trả lời của đội trình (ghi lại tại buổi):** Ngưỡng 3% thấp hơn mức nền 4,25% toàn mẫu và 3,97% trong phạm vi; nếu giữ tỷ lệ tương đương hiện tại, luật sẽ kích hoạt ngay lần đánh giá đầu tiên dù trợ lý chưa làm tình hình xấu đi. Vì vậy, nhóm đề xuất dừng khi tỷ lệ mở lại cao hơn đối chứng ít nhất 2 điểm phần trăm hoặc vượt trần 6%, kèm cửa sổ theo dõi và cỡ mẫu tối thiểu.
