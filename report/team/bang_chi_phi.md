# Bảng chi phí · Nhiệm vụ A và B

Số tính bằng `src/lab13.py`. Mọi con số tính từ cột `_simulated` ghi nhãn `simulated`. Mỗi câu trả lời không quá ba dòng, có ít nhất một con số.

## A1 · Ba phép thử đáp án biết trước

| Phép thử (p = 0,8) | Kết quả của nhóm |
| --- | --- |
| Số lần chạy trung bình, tối đa 2 lần | 1,20 |
| Số lần chạy trung bình, chạy đến khi đúng | 1,25 |
| Hệ số chi phí mỗi việc thành công, tối đa 3 lần | 1,25 |

## A2 · Mô hình chi phí từ trace

| Khoản | Số tiền (đ) | Nguồn | Nhãn |
| --- | ---: | --- | --- |
| Token | 245.585 | `logix_runs.csv` | đo từ trace |
| Tool | 84.000 | `logix_runs.csv` (5.600 lượt × 15 đ) | đo từ trace |
| Trong đó, phần của lần chạy thứ 2 và 3 | 93.804 | `attempt > 1`, đã nằm trong token và tool | đo từ trace |
| Xem lại | 1.780.000 | `phut_xem_lai_simulated` (890 phút × 2.000 đ) | simulated |
| Làm lại | 2.264.000 | `phut_lam_lai_simulated` (1.132 phút × 2.000 đ) | simulated |
| Tổng chi phí | 4.373.585 | Token + tool + xem lại + làm lại | simulated |
| Số việc thành công | 978 yêu cầu | `ket_qua == thanh_cong` | đếm từ dữ liệu |
| Chi phí mỗi việc thành công | 4.472 | Tổng chi phí ÷ 978 việc thành công | simulated |
| Hoá đơn token và tool chia cho số yêu cầu | 274,7 | (Token + tool) ÷ 1.200 yêu cầu | đo từ trace |

- Chi phí mỗi việc thành công gấp bao nhiêu lần "hoá đơn chia số yêu cầu"? Gấp **16,3 lần** (`4.472 đ` [simulated] ÷ `274,7 đ`).
- Khoản nào chiếm tỉ trọng lớn nhất trong tổng chi phí, bao nhiêu phần trăm? **Làm lại**, chiếm **51,8%** tổng chi phí (`2.264.000 đ / 4.373.585 đ`, simulated; theo sau là xem lại **40,7%**, giờ nhân viên chiếm tổng cộng **92,5%**).

## A3 · Tách theo loại yêu cầu

| Loại | Số yêu cầu | Tỉ lệ thành công | Số lần chạy mỗi yêu cầu | Chi phí mỗi việc thành công | So với 12.000 đ |
| --- | ---: | ---: | ---: | ---: | ---: |
| noi_dia | 824 | 95,0% | 1,11 | 2.696 đ (simulated) | 0,22× (simulated) |
| hang_nang | 158 | 74,1% | 1,47 | 8.221 đ (simulated) | 0,69× (simulated) |
| quoc_te | 150 | 27,3% | 2,32 | 22.515 đ (simulated) | 1,88× (simulated) |
| doi_tac | 68 | 54,4% | 1,88 | 10.215 đ (simulated) | 0,85× (simulated) |

- Loại nào không đáng để trợ lý xử lý? Với loại đó, cho chạy lại tới 3 lần có giúp không? Loại **`quoc_te`** (**22.515 đ = 1,88×** mốc 12.000 đ, simulated; thành công chỉ **27,3%**). Chạy lại tới 3 lần **không giúp** vì tỉ lệ `ok` tụt từ **30,0% → 11,4% → 2,2%**; nên thu hẹp pilot về `noi_dia + hang_nang` (loại thêm `doi_tac` sát ngưỡng 0,85×).

## A4 · Chi phí cố định (phạm vi noi_dia + hang_nang)

| Khối lượng | Việc thành công mỗi tháng | Chi phí cố định mỗi việc | Chi phí mỗi việc thành công + cố định | So với 12.000 đ |
| --- | ---: | ---: | ---: | ---: |
| 45.000 yêu cầu/tháng | 33.750 | 1.185 đ | 4.599 đ (simulated) | 0,38× (simulated) |
| Một nửa khối lượng (22.500 yêu cầu/tháng) | 16.875 | 2.370 đ | 5.784 đ (simulated) | 0,48× (simulated) |

- Ở cả hai mức khối lượng, chi phí mỗi việc thành công sau khi cộng chi phí cố định vẫn dưới mốc **12.000 đ**. Khi khối lượng giảm một nửa, khoản cố định trên mỗi việc tăng từ **1.185 đ** lên **2.370 đ**.

## B1 · Đổi từng yếu tố

| Kịch bản | Cách tính | Chi phí mỗi việc thành công | Thay đổi (%) |
| --- | --- | ---: | ---: |
| Giá token gấp đôi | 52 đ và 260 đ cho 1.000 token; giá tool giữ nguyên | 4.723 đ (simulated) | +5,6% |
| Giá token giảm một nửa | 13 đ và 65 đ | 4.346 đ (simulated) | −2,8% |
| Tỉ lệ xem lại gấp đôi | Tiền xem lại × 2 | 6.292 đ (simulated) | +40,7% |
| Tỉ lệ xem lại giảm một nửa | Tiền xem lại ÷ 2 | 3.562 đ (simulated) | −20,3% |
| Số ca làm lại gấp đôi | Tiền làm lại × 2 | 6.787 đ (simulated) | +51,8% |
| Số ca làm lại giảm một nửa | Tiền làm lại ÷ 2 | 3.315 đ (simulated) | −25,9% |
| Lương nhân viên tăng 25% | 2.500 đ mỗi phút | 5.506 đ (simulated) | +23,1% |
| Chỉ cho chạy tối đa 2 lần | Bỏ lần chạy có attempt > 2; yêu cầu có so_lan_chay > 2 coi là chuyen_nhan_vien | 4.237 đ (simulated) | −5,2% |
| Chỉ cho chạy 1 lần | Như trên với giới hạn 1 | 4.111 đ (simulated) | −8,1% |

## B2 · Đổi một cặp và xếp hạng

- Giá token gấp đôi cùng lúc tỉ lệ xem lại gấp đôi: **6.543 đ (simulated, +46,3%)**, đúng bằng tổng hai tác động riêng lẻ (+5,6% và +40,7%) vì mô hình chi phí là hàm cộng tuyến tính.
- Xếp hạng ba yếu tố ảnh hưởng mạnh nhất: **1. Số ca làm lại (+51,8% / −25,9%) · 2. Tỉ lệ xem lại (+40,7% / −20,3%) · 3. Lương nhân viên (+23,1%)**.

## B3 · Giới hạn chạy lại có thật sự rẻ hơn

| Giới hạn | Tổng chi phí trợ lý | Số yêu cầu không thành công | Chi phí cả hệ thống | Chi phí mỗi việc thành công |
| --- | ---: | ---: | ---: | ---: |
| 1 lần | 3.621.781 đ (simulated) | 319 | 7.449.781 đ (simulated) | 4.111 đ (simulated) |
| 2 lần | 4.093.220 đ (simulated) | 234 | 6.901.220 đ (simulated) | 4.237 đ (simulated) |
| 3 lần | 4.373.585 đ (simulated) | 222 | 7.037.585 đ (simulated) | 4.472 đ (simulated) |

- Giới hạn nào rẻ nhất cho công ty? Có trùng với giới hạn cho chi phí mỗi việc thành công thấp nhất không? Giới hạn tối đa **2 lần chạy** rẻ nhất cho cả công ty (**6.901.220 đ**, simulated), không trùng với giới hạn cho chi phí mỗi việc thành công thấp nhất là **1 lần chạy** (**4.111 đ**, simulated) vì chặn ở 1 lần sẽ đẩy thêm **85 việc** sang nhân viên tự làm (tốn 12.000 đ/việc).

## B4 · Nếu phải xem lại tất cả

- Chi phí mỗi việc thành công khi xem lại 100% (`noi_dia` + `hang_nang`), so với 12.000 đ: Chi phí là **11.743 đ = 0,98×** mức 12.000 đ (simulated, nếu tính 9 phút làm lại/ca) và tăng lên **12.414 đ = 1,03×** (simulated) nếu tính theo mức làm lại trung bình thực tế trong dữ liệu là **15,3 phút/ca** (đắt hơn nhân viên tự làm).

- Kết quả này nói gì về thứ pilot cần học được? Xem lại 100% gần như không tiết kiệm được chi phí (tiền xem lại chiếm ~90% tổng chi phí), nên pilot bắt buộc phải xác định được ngưỡng giảm tỉ lệ xem lại an toàn và rút ngắn thời gian mỗi lần xem lại xuống mức hoà vốn (**$\le$ 4,8 – 5,1 phút/ca**).

