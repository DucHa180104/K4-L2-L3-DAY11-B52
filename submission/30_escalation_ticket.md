# Escalation ticket

## Ticket 1

- **Frame:** adasind_261480.jpg
- **Ảnh chụp:** submission/screenshots/adasind_261480_edge.png (đường dẫn trong `submission/screenshots/`)
- **Expected impact:** Tránh sai lệch class hoặc thiếu sót thuộc tính `truncated` tại vùng biên ảnh fisheye khi scale mô hình sang bốn camera.
- **Owner:** `annotator`
- **Recommendation:** Thống nhất trong nhóm quy tắc đánh dấu `truncated = true` cho mọi đối tượng hộp chữ nhật chạm sát biên mép khung hình (`x=0` hoặc `x=1080`).