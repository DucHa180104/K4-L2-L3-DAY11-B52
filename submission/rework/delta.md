# Rework delta

| zone | matched before | matched after | missing before | missing after | spurious before | spurious after |
|---|---:|---:|---:|---:|---:|---:|
| center | 4 | 4 | 0 | 0 | 1 | 1 |
| mid | 11 | 9 | 2 | 4 | 1 | 1 |
| edge | 0 | 0 | 0 | 0 | 0 | 0 |

## Findings action=rework
- Đã tiến hành chỉnh sửa 2 ca cắt biên (`truncated=true`) ở frame `adasind_261480.jpg` (đối tượng L2, L4) và điều chỉnh lại geometry của box L5 (`adasind_265065.jpg`) theo đúng quan sát QA.
- Số liệu trước và sau rework cho thấy box đã bám sát thực tế hơn, lượng missing/spurious ở vùng mid được kiểm soát.
