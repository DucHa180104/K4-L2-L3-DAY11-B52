# QA review · B4-mid

Mã khóa: 655C-406F

| frame | object_ref | rule_id | nhận xét |
|---|---|---|---|
| adasind_261480.jpg | L2 Bike | R05 | Box chạm biên trái ảnh (x=0), vật bị khung ảnh cắt nhưng `truncated=false`; kiểm tra và đặt true nếu xác nhận phần vật tiếp tục ngoài khung. |
| adasind_261480.jpg | L4 Bike | R05 | Box chạm biên phải ảnh (x=1080), vật bị khung ảnh cắt nhưng `truncated=false`; kiểm tra và đặt true nếu xác nhận phần vật tiếp tục ngoài khung. |
| adasind_265065.jpg | L5 Pedestrian | R02 | Box chưa bám sát visible extent của người, còn dư khoảng trống quanh người; cần kiểm tra và chỉnh lại geometry. |

Ghi finding r2_qa: cell=L_only, rule_id có giá trị, why để trống.
