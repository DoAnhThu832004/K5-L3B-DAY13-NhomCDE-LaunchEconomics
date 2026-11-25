# Báo cáo cá nhân — Vũ Xuân Hiếu — 2A202603860

## 1. Thông tin thành viên

- Họ tên: Vũ Xuân Hiếu
- MSSV: 2A202603860
- Email: 26ai.hieuvx2@vinuni.edu.vn
- Vai trong nhóm: Người kiểm soát đặc tả / điều kiện "Xong khi" (CP1–CP2); Người gắn nhãn 2 kiêm giữ hồ sơ (CP3–CP5).

## 2. Phần việc phụ trách

- CP1–CP2: Đọc đặc tả đề bài, theo dõi điều kiện "Xong khi", kiểm định đầu ra `src/lab13.py` và rà soát câu trả lời trong `report/team/bang_chi_phi.md`.
- Khởi tạo khung hồ sơ Gate 2a (`report/team/ho_so_launch_v0.md`) từ kết quả CP1 và cập nhật số CP2.
- CP3: Tự gắn nhãn độc lập 20 ca lỗi theo 5 loại của Google PAIR, đối chiếu đồng thuận với Người gắn nhãn 1 (Võ Thanh Huy) và đề xuất bảng khắc phục 5 ca.
- Duyệt chéo Gate 2a: Chuẩn bị nội dung phản biện cho các câu hỏi của hội đồng về luật dừng an toàn, quyền rollback trong 30 phút và các điều kiện để duyệt kế hoạch pilot.

## 3. Đóng góp cụ thể

- **CP1 (`bang_chi_phi.md`):** Xác minh 3 phép thử A1 đạt (`1,20 · 1,25 · 1,25`), kiểm tra cờ `keep_default_na=False` và sai số 0% cho toàn bộ bảng A2–A4; bổ sung 3 câu trả lời phân tích kinh tế bị thiếu ở A2 (CPS `4.472 đ` [simulated] gấp `16,3×` hoá đơn `274,7 đ`; khoản làm lại lớn nhất chiếm `51,8%` [simulated], tổng giờ nhân viên `92,5%`) và A3 (loại `quoc_te` `1,88×`, thành công `27,3%`, chạy lại 3 lần không giúp vì tỉ lệ `ok` tụt `30,0% → 11,4% → 2,2%`; thu hẹp về `noi_dia + hang_nang`).
- **Hồ sơ launch v0 (`ho_so_launch_v0.md`):** Khởi tạo khung hồ sơ NhomCDE (L3B) từ CP1 với Mục 1 và Mục 3 đúng chuẩn nhãn `Giả lập` và người phụ trách cụ thể; rà soát tuân thủ quy chế không dùng từ cấm và không thiếu nhãn `simulated`.
- **CP3 (`bang_loi.md`):** Độc lập gắn nhãn 20 ca lỗi theo nguyên nhân gốc, so chéo với Võ Thanh Huy đạt đồng thuận **17/20 = 85%**, thống nhất quy tắc phân biệt 3 ca lệch (Ca 6, 8, 9) và soạn bảng khắc phục 5 ca có event, ngưỡng và vai trò phụ trách.
- **Duyệt chéo Gate 2a:** Tổng hợp câu trả lời phản biện có số liệu cho câu hỏi về điều kiện dừng tại bước 4 nhân viên (`rollout = 0,10`), phân quyền dừng & thời hạn rollback tối đa 30 phút khi phát sinh lệch sổ cái, và làm rõ 4 điều kiện bắt buộc của đề xuất `Go có điều kiện`; sửa tên nhóm bị nhầm trong `phieu_cham.md` (`ABC` → `NhomCDE`).

## 4. Bằng chứng

- Commit `cfbe245` (đã merge vào `main` qua PR `#3` tại commit `f2be525`): `docs(cp1): complete A2-A3 answers in bang_chi_phi and init ho_so_launch_v0`.
- Commit `c2ddf6b` trên nhánh `vuhieuvh`: `docs(cp3): add annotator 2 labels and 5-case mitigation table; update ho_so_launch_v0 with CP2`.
- Câu trả lời A2–A3 trong [bang_chi_phi.md](bang_chi_phi.md), bộ nhãn Người gắn nhãn 2 trong [bang_loi.md](bang_loi.md), khung khởi tạo [ho_so_launch_v0.md](ho_so_launch_v0.md) và chỉnh sửa [phieu_cham.md](phieu_cham.md).

## 5. Công cụ AI đã dùng

- Sử dụng Antigravity (Gemini) để tóm tắt yêu cầu từng checkpoint, xây dựng checklist QA kiểm tra điều kiện "Xong khi" (kiểm tra 3 phép thử A1, các mục còn bỏ trống, nhãn `simulated`, cú pháp YAML và từ cấm), ôn tập ranh giới 5 loại lỗi Google PAIR và rà soát câu trả lời phản biện Gate 2a.
- **Cách tự kiểm tra:** Chạy trực tiếp `python lab13.py` và `yaml.safe_load` trên máy cá nhân để đối chiếu từng con số A1–A4, B1–B4, D1 với dữ liệu CSV; tự đọc nguyên văn 20 ca lỗi trong đề và gắn nhãn độc lập trước khi đối chiếu với Võ Thanh Huy; kiểm tra lại toàn bộ điều kiện dừng, ngưỡng an toàn và ngày quyết định trong `pilot_plan.yaml`, `chi_so.md` và `ho_so_launch_v0.md`.

## 6. Tự đánh giá

- **Điểm làm tốt:** Nắm chắc nguyên tắc tính chi phí mỗi việc thành công (tử số tính mọi lần chạy kể cả lỗi và giờ nhân viên, mẫu số chỉ chia cho số yêu cầu thành công), hiểu rõ cách gắn nhãn theo nguyên nhân gốc của Google PAIR và biết bảo vệ kế hoạch pilot một cách trung thực (nêu rõ cả số liệu bất lợi như kịch bản xem lại 100% và `power = 0,64` ở mức chênh 5 điểm).
- **Điểm cần rút kinh nghiệm:** Cần đồng bộ nhánh với `origin/main` sớm hơn giữa các checkpoint và kiểm tra kỹ `base repository` khi tạo Pull Request trên repo fork để tránh mở nhầm sang repo đề bài.
