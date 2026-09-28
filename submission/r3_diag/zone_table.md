# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 4 | 0 | 1 | 1 | 4 | SPURIOUS (1) |
| mid | 13 | 2 | 1 | 3 | 7 | ATTRIBUTE (2) |
| edge | 2 | 1 | 1 | 1 | 1 | MISSING (1) |

## Nhận xét

1. **Phân bố theo zone**: 
   - Vùng `center` có độ khớp tốt giữa nhãn người gán (L) và tham chiếu (R).
   - Vùng `mid` là nơi tập trung nhiều đối tượng và phát sinh nhiều sai lệch nhất (thiếu sót xe/người hoặc sai lệch biên do biến dạng fisheye).
   - Vùng `edge` hầu như không có đối tượng hợp lệ do đối tượng bị cắt biên hoặc biến dạng quang học mạnh.

2. **Giả thuyết & Giới hạn**:
   - Model (M) gặp nhiều lỗi `spurious` ở cả center và mid do nhận nhầm các chi tiết nền và phương tiện ở xa dưới 40px.
   - Phân loại zone dựa trên khoảng cách tương đối tới tâm vòng kính, chỉ mang tính chất thống kê trên 3 frame của slice B4-mid chứ chưa đại diện cho toàn bộ hệ thống SVM 360 4 camera.
