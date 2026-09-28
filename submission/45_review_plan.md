# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| B4-mid (adasind_261480.jpg) | 2 ca lỗi thuộc tính (`truncated`) | Do đối tượng cắt biên chưa được gán nhãn thuộc tính chính xác theo guideline | Overlay, XML export từ CVAT và biên bản QA |
| B4-mid (adasind_265065.jpg) | 1 ca sai hình học (`geometry`) của Pedestrian | Box gán nhãn chưa bám sát vùng người thực tế nhìn thấy trên ảnh fisheye | Ảnh chụp màn hình và dòng findings tương ứng |

Giới hạn của kết luận từ ba frame ADASIND: Chỉ phản ánh sai sót cục bộ trên một slice nhỏ, chưa đại diện cho toàn bộ hệ thống Surround View 4 camera trên 50.000 frame thực tế.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: Phân bổ đều frame theo tỷ lệ các camera (front, rear, left, right) kết hợp chọn lọc các ca khó (`hard case`) ở vùng rìa và góc khuất để lập bộ gold set kiểm chứng, tránh lấy dồn dập các frame liên tiếp nhau trong một đoạn video ngắn gây nhiễu thống kê.