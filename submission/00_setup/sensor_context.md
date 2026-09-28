# Sensor context

- **Rig**: Camera fisheye góc rộng gắn phía trước/sau ở vị trí thấp quanh xe phục vụ hệ thống SVM; dữ liệu ADASIND không kèm tài liệu rig chi tiết nên xác định vị trí theo quan sát góc nhìn thực tế trên ảnh.
- **`ego_body`**: Nhìn thấy một phần cản xe (bumper) / nắp capo ở mép dưới khung hình, cần đưa vào ignore_region khi bị che khuất.
- **Vòng kính (lens circle)**: Vòng tròn quang học nằm ở trung tâm ảnh, 4 góc khung hình bị bo đen (lens_border) chiếm khoảng 10-15% diện tích ảnh và không chứa bằng chứng cảnh quan thực tế.