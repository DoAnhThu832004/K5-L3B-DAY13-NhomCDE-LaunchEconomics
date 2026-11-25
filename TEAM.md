# Team

## Thông tin nhóm

- Tên nhóm: NhomCDE
- Lớp: L3B
- Repo nhóm: `K5-L3B-DAY13-NhomCDE-LaunchEconomics` (xem [SUBMISSION.md](SUBMISSION.md))
- URL repo, nhánh nộp, commit chốt: https://github.com/DoAnhThu832004/K5-L3B-DAY13-NhomCDE-LaunchEconomics, main, bb6d1d1

## Thành viên

| STT | Họ tên         | MSSV | Email | GitHub         | Vai trò                                                    |
| --: |----------------| ---- | ----- |----------------|------------------------------------------------------------|
|   1 | Đỗ Anh Thư     | 2A202603815 | adugarux4@gmail.com | DoAnhThu832004 | Người viết code (CP1, CP4) & Giữ hồ sơ & Người kiểm số CP4 |
|   2 | Võ Thanh Huy   | 2A202603879 | huyvo180700@gmail.com | VThanh-Huy     | Người kiểm số CP1 & Người gắn nhãn 1 (CP3)                 |
|   3 | Nguyễn Long Vũ |      | | mhoo40         | Người viết code (CP2) & Kế hoạch pilot (CP4)               |
|   4 | Vũ Xuân Hiếu   | 2A202603860 | vuhieu3205@gmail.com | vuhieuvh       | Kiểm soát đặc tả (CP1–CP2), Người gắn nhãn 2 & Giữ hồ sơ (CP3–CP5) |

Bốn vai của lab:

- **Người viết code:** viết và chạy `src/lab13.py`.
- **Người kiểm số:** tính tay một con số để đối chiếu, điền bảng.
- **Người gắn nhãn 1:** đọc đề, theo dõi điều kiện "Xong khi"; gắn nhãn 20 ca độc lập ở CP3.
- **Người gắn nhãn 2, kiêm giữ hồ sơ:** điền `report/team/ho_so_launch_v0.md` từ đầu buổi; gắn nhãn 20 ca độc lập ở CP3.

Đổi người viết code sau giờ giải lao, để ít nhất hai người trong nhóm tự tay tính được chi phí.

## Cá nhân

Mỗi thành viên đồng thời tạo một báo cáo riêng trong `report/` theo dạng:

```text
report/team/MSSV_HoTen.md
```

Ví dụ: `report/team/20241234_NguyenVanAn.md`.

## DoAnhThu-2A202603815

### Phần việc phụ trách

- Trưởng nhóm, điều phối chung tiến độ 5 checkpoint và quản lý PR trên GitHub.
- Người viết code CP1 (A1–A4) và CP4 (D1), Người kiểm số CP4 .
- Trực tiếp hoàn thiện và rà soát các file `pilot_plan.yaml`, `phieu_cham.md`, `chi_so.md`, `ho_so_launch_v0.md` và `group_report.md`.

### Đóng góp cụ thể

- Hiện thực hóa 3 hàm xác suất A1, hàm `mo_hinh` A2, phân loại A3 và cố định A4 trong `src/lab13.py`, người kiểm số CP4.
- Viết code tính cỡ mẫu D1 và tỉ lệ mở lại nền trong `src/lab13.py`; điền D1, cỡ mẫu, đánh đổi, D2 và sửa ngày quyết định trong `pilot_plan.yaml`.
- Điền phiếu chấm duyệt chéo `phieu_cham.md` cho nhóm EA1125 đạt 30/30 điểm kèm câu hỏi phản biện.
- Đặc tả 10 event có `trace_id` trong `chi_so.md`, tổng hợp bảng 7 mục và 4 điều kiện trong `ho_so_launch_v0.md`.

### Bằng chứng

- Commits trên repo: `completed A1,A2,A3,A3`, `complete code and number check cp4`, `completed phieu_cham`, `hoan thien D2 va ngay quyet dinh trong pilot_plan.yaml` (`e3cdaad`), `hoan thien chi_so.md, ho_so_launch_v0.md va group_report.md`.
- Commit `c44351c` trên nhánh `DoAnhThu` (chưa vào `main`): trả lời A2–A3 và thêm nhãn `simulated` cho B1–B4 trong `bang_chi_phi.md`.
- File code `src/lab13.py` chạy qua 3 phép thử ĐẠT.

## VoThanhHuy

### Phần việc phụ trách

- Người kiểm số CP1 (đối chiếu bảng A2–A4).
- Người gắn nhãn 1 tại CP3 (nhiệm vụ C).
- Soát lỗi và đối chiếu các con số trong `bang_chi_phi.md`.

### Đóng góp cụ thể

- Tính toán kiểm tra chéo các giá trị CPS ở A2, A3 và chi phí cố định A4.
- Độc lập gắn nhãn 20 ca lỗi ở CP3, đạt đồng thuận 85% (17/20 ca) với Người gắn nhãn 2.
- Cùng thống nhất 3 quy tắc phân biệt cho ca 6, 8, 9 và hoàn thiện bảng khắc phục 5 ca trong `bang_loi.md`.

### Bằng chứng

- Commits trên repo: `kiem so(bang_chi_phi_A)`, `cp3`, `fix cp3`.
- Bảng nhãn độc lập và bảng khắc phục trong `report/team/bang_loi.md`.

## NguyenLongVu

### Phần việc phụ trách

- Người viết code CP2 (sau giải lao đổi vai).
- Soạn thảo và cấu hình các thông số ban đầu của kế hoạch pilot trong `pilot_plan.yaml` (CP4).

### Đóng góp cụ thể

- Viết kịch bản khảo sát độ nhạy B1 (9 kịch bản), cặp B2, chi phí cả hệ thống B3 và B4 xem lại 100% trong `src/lab13.py`.
- Cập nhật các bảng số liệu B1–B4 vào `bang_chi_phi.md`.
- Soạn thảo các trường thông tin cơ bản, phạm vi và luật dừng trong `pilot_plan.yaml`.

### Bằng chứng

- Commits trên repo: `CP2 code, bang_chi_phi`, `Merge branch 'Vu/CP2'`, `edit pilot_plan.yaml`.
- Kết quả chạy B1–B4 trong `src/lab13.py` và bảng B trong `bang_chi_phi.md`.

## VuXuanHieu-2A202603860

### Phần việc phụ trách

- Kiểm soát đặc tả, điều kiện "Xong khi" và rà soát số liệu, câu trả lời bảng chi phí (CP1–CP2).
- Người gắn nhãn 2 tại CP3 (nhiệm vụ C) và giữ khung hồ sơ `ho_so_launch_v0.md`.
- Chuẩn bị phản biện duyệt chéo Gate 2a và rà soát checklist trước khi nộp.

### Đóng góp cụ thể

- Xác minh đầu ra `src/lab13.py` CP1 và bổ sung 3 câu trả lời phân tích kinh tế A2, A3 trong `bang_chi_phi.md`.
- Khởi tạo khung hồ sơ Gate 2a trong `ho_so_launch_v0.md` và cập nhật nháp CP2.
- Độc lập gắn nhãn 20 ca lỗi ở CP3, đối chiếu đạt đồng thuận 85% (17/20 ca) với Võ Thanh Huy và chốt quy tắc phân biệt các ca không trùng.
- Rà soát toàn bộ hồ sơ nộp cuối buổi, sửa tên nhóm trong `phieu_cham.md` và hoàn thiện báo cáo cá nhân `2A202603860_VuXuanHieu.md`.

### Bằng chứng

- Commits trên repo: `docs(cp1): complete A2-A3 answers in bang_chi_phi and init ho_so_launch_v0` (`cfbe245`, PR `#3` merge tại `f2be525`), `docs(cp3): add annotator 2 labels and 5-case mitigation table; update ho_so_launch_v0 with CP2` (`c2ddf6b`).
- Bộ nhãn Người 2 trong `report/team/bang_loi.md` và báo cáo cá nhân `report/team/2A202603860_VuXuanHieu.md`.

