# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): Các đoạn vạch sơn vàng rõ nét ở tiền cảnh góc dưới bên trái và chính giữa phía trước, dùng để phân chia ranh giới các ô đỗ xe riêng biệt.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: Các đoạn vạch sơn vàng ở hậu cảnh phía xa bị mờ và lóa sáng, hoặc dải sơn phân luồng lối đi chung không tạo ranh giới cho một ô đỗ riêng lẻ nên không gán nhãn parking_line theo quy tắc guideline.
- Polygon `free_space` dừng ở đâu; có phần bị che nào không: Polygon bao quanh phần mặt đường nhựa trống của lối xe chạy chính ở giữa bãi đỗ; ranh giới dừng lại trước thân xe ô tô đỏ đang đỗ ở phía xa và không lấn vào hàng rào/hàng cây phía sau; không có phần bị che khuất nào bị nối xuyên qua.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): không có