# Guideline patch

- **Rule mới đề xuất:** Bổ sung quy tắc xử lý vật thể chạm biên khung hình fisheye và chuẩn hóa biên dạng box đối tượng người đi bộ (Pedestrian).
- **Áp dụng cho:** Class `Bike`, `Pedestrian` tại vùng `mid` và `edge` của ảnh fisheye.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** Luật hiện tại chỉ định nghĩa kích thước tối thiểu ($H \geq 40px$) nhưng chưa hướng dẫn chi tiết cách xử lý khi box chạm đúng vạch biên ảnh ($x=0$ hoặc $x=1080$) dẫn đến việc bỏ sót thuộc tính `truncated`.
- **`rules_version` mới:** v1.0.0 → v1.1.0
- **Hiệu lực từ:** Round rework (`r2_rework`) trở đi trong toàn bộ nhóm.