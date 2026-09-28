# Đề xuất gold set theo camera — tình huống giả lập

**Đầu bài:** 50.000 frame từ bốn camera SVM, ngân sách chọn 200 frame để review/gold. Đây là tình huống trên slide,
**không phải** 50.000 frame có trong repo. Phân bổ đúng 200 ở `45_sampling_plan.csv` cho bốn camera, mỗi camera có
normal và hard slice. “Gold set” ở đây là **kế hoạch tạo** reference sau kiểm chứng, không phải teaching reference
ADASIND hoặc nhãn bạn vừa vẽ. Nếu cần, dùng `notebooks/day11-svm360-colab.ipynb` để thử tổng phân bổ; notebook
không làm thay phần lý do.

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|
| front | Vùng góc nhìn hẹp phía trước, xe máy cắt ngang | Biến dạng thấu kính camera trước và điểm mù sát cản trước | Hệ tọa độ ảnh 2D camera trước và thông số camera matrix | Peer review chéo giữa các thành viên nhóm và chốt reference |
| rear | Vùng sát mép cản sau, vật cản thấp | Ánh sáng yếu, phản xạ từ gầm xe và góc camera lùi rộng | Hệ tọa độ 2D camera sau và vùng loại trừ gầm xe | Soát box thủ công qua công cụ overlay và đối chiếu model |
| left | Vùng lốp xe bên trái, vạch kẻ đường uốn cong | Biến dạng fisheye góc rộng kéo dãn vật thể theo chiều ngang | Vùng giao nhau giữa camera trái và camera trước/sau | Kiểm tra chéo độ liền mạch qua các frame liên tiếp |
| right | Vùng lốp xe bên phải, người đi bộ sát lề | Lệch cân bằng màu sắc và biến dạng quang học vùng rìa | Vùng không gian hiển thị góc nhìn camera phải | Đảm bảo không bỏ sót đối tượng ở góc khuất tầm nhìn |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): Khi hệ thống xe thay đổi góc lắp đặt camera, thay đổi thấu kính fisheye hoặc cập nhật phiên bản hướng dẫn gán nhãn mới.
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: Cần quy định rõ ngưỡng dung sai khoảng cách (pixel overlap) và xác nhận đối tượng xuất hiện đồng thời trên ít nhất hai camera trước khi thực hiện đồng bộ box.
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: Vì mỗi camera có góc nhìn (FOV) và đặc trưng quang học biến dạng khác nhau, chất lượng trên một camera không suy rộng được độ chính xác khi ghép hình toàn cảnh Surround View.