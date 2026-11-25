# Báo cáo cá nhân — 2A202603842_NguyenLongVu

## 1. Thông tin thành viên

- Họ tên: Nguyễn Long Vũ
- MSSV: 2A202603842
- Email: nguyenlongvu17082004@gmail.com
- Vai trong nhóm: Người viết code (CP2 — đổi vai sau giờ giải lao 15:20) & Kế hoạch pilot (CP4)

## 2. Phần việc phụ trách

- Đổi vai Người viết code sau giờ giải lao: Viết toàn bộ code phân tích độ nhạy kinh tế CP2 (B1–B4) trong `src/lab13.py`.
- Khởi tạo khung cấu hình kế hoạch pilot, xác định đơn vị phân bổ cụm và soạn thảo dự thảo luật dừng an toàn trong `pilot_plan.yaml` (CP4).
- Phân tích và điền dữ liệu bảng độ nhạy B1–B4 vào `report/team/bang_chi_phi.md`.

## 3. Đóng góp cụ thể

- **Code phân tích độ nhạy (CP2):** Hiện thực hóa 9 kịch bản biến động đơn lẻ B1, kịch bản đổi cặp tuyến tính B2 (`+46,3%`), tính toán chi phí toàn hệ thống theo số lần thử B3 và mô hình kịch bản xem lại 100% ở B4.
- **Phát hiện kinh tế mấu chốt (B3):** Chứng minh giới hạn 2 lần chạy mang lại chi phí cả hệ thống thấp nhất cho công ty (**3.980.391 đ/982 yêu cầu** trong phạm vi, hoặc 6.901.220 đ toàn mẫu, simulated) thay vì bẫy tối ưu cục bộ 1 lần chạy (CPS 4.111 đ nhưng làm tăng chi phí toàn hệ thống lên 7.449.781 đ do đẩy thêm 85 việc sang con người).
- **Phân tích rủi ro xem lại 100% (B4):** Tính toán chi phí xem lại 100% cộng chi phí cố định vọt lên **12.928–13.600 đ = 1,08×–1,13×** (simulated), chỉ ra điểm hòa vốn thời gian xem lại phải $\le 4,2–4,6$ phút/ca để không đắt hơn con người tự làm (12.000 đ).
- **Đóng góp kế hoạch pilot (CP4):** Soạn thảo cấu trúc YAML, thiết lập thông số phân bổ ngẫu nhiên theo nhân viên (`unit: staff`, 20 can thiệp + 20 đối chứng) và đề xuất các ngưỡng kích hoạt luật dừng bảo vệ khách hàng.

## 4. Bằng chứng

- **Mã nguồn trong `src/lab13.py`:** Khối lệnh `TODO CP2` từ dòng 121 đến dòng 159 (chạy in ra kết quả B1–B4 chuẩn xác).
- **Các commit trên repo GitHub:**
  - `CP2 code, bang_chi_phi`
  - `Merge branch 'Vu/CP2'`
  - `edit pilot_plan.yaml`
- **Tài liệu hoàn thành:** Bảng B1, B2, B3, B4 trong `report/team/bang_chi_phi.md` và các trường ban đầu trong `report/team/pilot_plan.yaml`.

## 5. Công cụ AI đã dùng

- **Công cụ:** Antigravity AI Assistant.
- **Mục đích sử dụng:**
  - Hỗ trợ cú pháp tối ưu hóa vòng lặp dictionary khi truyền `**kw` vào hàm `mo_hinh` cho 9 kịch bản B1.
  - Kiểm tra cú pháp YAML bằng thư viện `pyyaml` (`yaml.safe_load`) để tránh lỗi thụt dòng khi cấu hình `pilot_plan.yaml`.
- **Cách tự kiểm tra kết quả:**
  - Chạy trực tiếp `.\.venv\Scripts\python.exe lab13.py` trên máy local, so sánh kết quả B1 và B3 với slide đáp án của giảng viên tại lớp (khớp 100%).
  - Dùng máy tính bấm tay kiểm tra chéo tính chất cộng tuyến tính ở B2: $5,6\% + 40,7\% = 46,3\%$.

## 6. Tự đánh giá

- Thực hiện nghiêm túc quy định đổi người viết code sau giờ giải lao để đảm bảo nắm vững logic tính toán kinh tế của agent.
- Phối hợp nhịp nhàng với Người kiểm số (Võ Thanh Huy) và Trưởng nhóm (Đỗ Anh Thư) để chuyển giao số liệu B1–B4 mượt mà.
- Mức độ hoàn thành: Hoàn thành xuất sắc nhiệm vụ được giao.
