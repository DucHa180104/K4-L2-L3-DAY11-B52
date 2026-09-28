# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy
   tắc riêng? Vì sao? Đây là hiện tượng phát sinh lỗi `DUPLICATE` do giao vùng nhìn giữa hai camera, cần một quy tắc hợp nhất box (cross-camera matching policy) dựa trên tọa độ không gian thực thay vì chỉ xử lý độc lập trên từng ảnh 2D.
2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera. Giữ cùng track ID khi vật thể chuyển động liên tục không bị che khuất hoàn toàn; thêm trạng thái `Outside` hoặc cắt đoạn khi vật đi ra khỏi khung hình camera. Bằng chứng cần là sự khớp về nhãn class, chiều di chuyển và vận tốc tương đối giữa các frame.
3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm? Nhóm đã mở lại ảnh gốc để đối chiếu trực tiếp phần pixel thực tế mà vật thể chiếm chỗ theo đúng guideline thay vì cãi nhau theo cảm tính. Nếu làm lại, nhóm sẽ chú ý soát kỹ các thuộc tính cắt biên ngay từ khâu gán nhãn ban đầu để giảm thiểu số ca phải rework ở pha sau.