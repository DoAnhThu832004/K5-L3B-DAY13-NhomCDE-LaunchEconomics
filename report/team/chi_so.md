# Đặc tả chỉ số, event và rủi ro kinh tế · Nhiệm vụ E1, E2

## E1 · Đặc tả chỉ số

| Loại | Chỉ số | Công thức | Tính thử trên 1.200 yêu cầu |
| --- | --- | --- | --- |
| Chính (kết quả) | % yêu cầu đóng trong 24 giờ và không mở lại trong 7 ngày | `dong_trong_24h` bằng 1 và `mo_lai_trong_7_ngay` bằng 0, chia tổng số yêu cầu | **82,83%** (994/1.200 yêu cầu) |
| Dùng | Tỉ lệ bỏ qua gợi ý | `quyet_dinh_xem_lai` là `sua` hoặc `bo`, chia số yêu cầu được xem lại | **27,12%** (48/177 yêu cầu được xem lại) |
| An toàn | Tỉ lệ lỗi lọt đến khách | `mo_lai_trong_7_ngay` bằng 1, chia tổng số yêu cầu | **4,25%** (51/1.200 yêu cầu; trong phạm vi `noi_dia + hang_nang` là 3,97%) |
| Dùng | Nhóm tự đề xuất: % yêu cầu thuộc nhóm can thiệp được nhân viên mở bằng trợ lý | Số yêu cầu nhóm can thiệp có gọi trợ lý ÷ Tổng số yêu cầu nhóm can thiệp tiếp nhận | Không cần tính |
| An toàn | Nhóm tự đề xuất: % đơn hoàn sai tiền qua kiểm toán mẫu hằng tuần | Số đơn sai lệch tiền qua đối soát kiểm toán mẫu hằng tuần ÷ Tổng số đơn được chọn kiểm toán (100 ca/tuần) | Không cần tính |

*Chỉ số trong đợt chạy thử là 82,83% (chưa có nhóm đối chứng, không viết trợ lý đã nâng chỉ số).*

## Danh sách event

Ít nhất sáu event, mỗi event có `trace_id` để nối với trace của agent.

| Event | Ai tạo | Thuộc tính chính | Thời điểm |
| --- | --- | --- | --- |
| `refund_request_created` | App khách / Hệ thống CRM | `request_id`, `loai`, `so_tien`, `arm`, `trace_id` | Khi khách gửi yêu cầu |
| `agent_run_completed` | Agent | `attempt`, `tokens_in`, `tokens_out`, `tool_calls`, `status`, `trace_id` | Sau mỗi lần chạy agent, kể cả khi lỗi |
| `agent_suggestion_shown` | Giao diện nhân viên | `staff_id`, `so_tien_de_xuat`, `trace_id` | Khi gợi ý của agent hiển thị trên màn hình |
| `staff_review_decision` | Nhân viên CSKH | `decision` (giu/sua/bo), `phut_xem_lai` (đo thật), `trace_id` | Khi nhân viên xác nhận duyệt/sửa/bỏ gợi ý |
| `staff_rework_completed` | Nhân viên CSKH | `phut_lam_lai`, `ly_do_lam_lai`, `trace_id` | Khi nhân viên hoàn thành xử lý lại ca bị sai |
| `refund_ledger_write` | Dịch vụ sổ cái | `idempotency_key`, `so_tien_hoan`, `ket_qua`, `trace_id` | Khi ghi nhận lệnh hoàn tiền thành công vào sổ cái |
| `handoff_to_staff` | Agent | `reason`, `tom_tat_ngu_canh`, `trace_id` | Khi agent chạy quá giới hạn hoặc thiếu dữ liệu, chuyển cho người |
| `ticket_closed` | Hệ thống ticket | `closed_at`, `closed_by`, `trace_id` | Khi ticket khiếu nại hoàn phí được đóng |
| `ticket_reopened` | Khách hàng | `reopened_at`, `reason`, `trace_id` | Khi khách mở lại ticket trong vòng 7 ngày |
| `audit_sample_checked` | Kế toán / Kiểm toán nội bộ | `sample_id`, `so_tien_da_hoan`, `so_tien_dung`, `trace_id` | Định kỳ hằng tuần khi kiểm tra mẫu 100 ca |

**Kiểm tra chéo:**
- **Chỉ số chính:** Tính từ `ticket_closed` (xác định `closed_at <= 24h`) kết hợp không có event `ticket_reopened` trong vòng 7 ngày trên cùng `trace_id`.
- **Chỉ số dùng:** Tính từ `staff_review_decision` (đếm số lần `decision` là `sua` hoặc `bo` chia cho tổng event `staff_review_decision`).
- **Chỉ số an toàn:** Tính từ event `ticket_reopened` phát sinh trong vòng 7 ngày sau `ticket_closed` trên cùng `trace_id`.
- **Chỉ số dùng đề xuất:** Tính từ tỉ lệ event `agent_suggestion_shown` xuất hiện trên tổng số `refund_request_created` của nhóm can thiệp.
- **Chỉ số an toàn đề xuất:** Tính từ event `audit_sample_checked` có `so_tien_da_hoan != so_tien_dung`.

## E2 · Rủi ro kinh tế

Ít nhất hai dòng, số lấy từ bảng độ nhạy (`bang_chi_phi.md`).

| Rủi ro | Tác động đã tính | Dấu hiệu theo dõi | Hành động | Người phụ trách |
| --- | --- | --- | --- | --- |
| Số ca làm lại tăng gấp đôi | CPS tăng **+51,8%** lên **6.787 đ** [simulated] | Tỉ lệ ca phải làm lại theo tuần vượt quá 7% (đợt chạy thử: 4,9% trong phạm vi) | Thu hẹp phạm vi về riêng `noi_dia`, rà soát 20 trace làm lại gần nhất để sửa prompt/tool | PM trợ lý hoàn phí |
| Phải xem lại 100% kéo dài | CPS tăng lên **11.743–12.414 đ** (gồm cố định: **12.928–13.600 đ = 1,08×–1,13×** [simulated], đắt hơn người tự làm) | Tỉ lệ yêu cầu được xem lại vẫn > 50% ở cuối bước rollout 0.25 | Kích hoạt lộ trình giảm xem lại theo bậc (100% → 50% → 25%) khi tỉ lệ sửa+bỏ < 15% | Trưởng nhóm CSKH |
| Khối lượng xử lý thực tế giảm một nửa | Chi phí cố định mỗi đơn tăng gấp đôi từ **1.185 đ** lên **2.370 đ**; CPS có cố định tăng lên **5.784 đ = 0,48×** [simulated] | Số lượng yêu cầu thành công theo tuần đạt dưới 50% kế hoạch (dưới 3.800 ca/tuần) | Không mở rộng quy mô pilot, đàm phán lại gói cước chi phí cố định hạ tầng với nhà cung cấp | PM trợ lý hoàn phí |

