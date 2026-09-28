# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B4 | SPURIOUS | 3 |
| center | C0 | MISSING | 1 |
| center | C0 | SPURIOUS | 2 |
| mid | B4 | ATTRIBUTE | 4 |
| mid | B4 | BOX_GEOMETRY | 1 |
| mid | B4 | MISSING | 2 |
| mid | B4 | SPURIOUS | 1 |

## Top defects
- SPURIOUS: 6 (ví dụ frame adasind_019560.jpg)
- ATTRIBUTE: 4 (ví dụ frame adasind_261480.jpg)
- MISSING: 3 (ví dụ frame adasind_019560.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: Do góc chụp fisheye bị biến dạng quang học mạnh ở vùng biên và mid, khiến các đối tượng xe máy/xe đạp (Bike) khi chạm mép khung hình hoặc bị cắt biên dễ dẫn đến nhầm lẫn thuộc tính `truncated` hoặc phát sinh box thừa (`SPURIOUS`).
- Cách sửa và ai nhận việc (`owner`): Thành viên A (gán nhãn) tiến hành kiểm tra lại các box bị cắt biên trên CVAT, cập nhật đúng thuộc tính `truncated = true` và nắn lại bounding box bám sát phần người/phương tiện.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): Thể hiện qua các ca lỗi ở frame `adasind_261480.jpg` (đối tượng L2, L4) và `adasind_265065.jpg` theo biên bản QA nhóm.
