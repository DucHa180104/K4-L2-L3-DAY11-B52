# Thành viên và phân vai — Day11 SVM 360 Fisheye

## 1. Thông tin nhóm

- Khóa/lớp: L2-2a
- Tên nhóm: B52
- Repo Public: https://github.com/DucHa180104/K4-L2-L3-DAY11-B52.git
- Máy giữ hồ sơ chính / người quản lý: Nguyễn Đức Hà
- Slice chung lấy từ mode.json: B4-mid
- Tên định danh vai A dùng cho --self: LeVinhHung
- Kênh trao đổi nội bộ: Zalo
- Đại diện nộp (vai C): Nguyễn Đức Hà, MSSV: 2A202602105
- Commit chốt bài: https://github.com/DucHa180104/K4-L2-L3-DAY11-B52/tree/main/submission

## 2. Ba vai chính

| Vai | Họ và tên | MSSV | Tên định danh trong mode | Trách nhiệm | Bằng chứng đóng góp |
|---|---|---|---|---|---|
| A · Gán nhãn | Lê Vĩnh Hưng | 2A202602222 | LeVinhHung | Parking/C0/slice, self-QC, lock, rework | submission/r1_craft/annotations.xml, r1_craft/lock.txt — thực hiện gán nhãn, self-QC và khóa bản đầu. |
| B · QA độc lập | Bùi Phương Nam | 2A202602134 | BuiPhuongNam | Review trước reference, finding QA, kiểm lại ca sửa | submission/r2_qa/qa_review.md, submission/findings.csv — thực hiện QA mù và ghi các finding P3. |
| C · Chẩn đoán & điều phối | Nguyễn Đức Hà | 2A202602105 | NguyenDucHa | Báo cáo, phân xử, kế hoạch, tích hợp, check và nộp | submission/r3_diag/, decision log, manifest.json — thực hiện chẩn đoán, điều phối rework và tích hợp hồ sơ. |

Bảng này xác định vai của nhóm. Vòng QA tự sinh trong team.json thuộc quy trình nhiều hồ sơ của CLI; nhóm dùng một slice chung và quy trình A → B → C đã nêu trong hướng dẫn.

## 3. Bàn giao theo pha

| Mốc | Người giao → nhận | File / commit / mã khóa | Người nhận đã kiểm gì? | Trạng thái / vướng mắc |
|---|---|---|---|---|
| P0 · Chốt môi trường và vai | C → A, B | mode.json, slice, phân vai | Kiểm members, assignments, self, slice và phân vai A/B/C | Đã chốt |
| P2 · Khóa bản đầu | A → B, C | XML, lock.txt, slice, code, commit | B kiểm bản khóa để chuẩn bị QA mù; C nhận hồ sơ để chẩn đoán sau P3 | Đã bàn giao |
| P3 · Chốt QA mù | B → C, A | review, findings, ảnh, commit | C nhận QA review và các finding; kiểm số lượng finding, cell=L_only, rule_id; chưa xem reference/model trong lúc B QA | Đã chốt QA; có các finding cần C chẩn đoán |
| P4 · Quyết định sửa | C → A, B | finding, decision log, commit | A kiểm các quyết định liên quan đến nhãn/sửa; B nắm kết quả chẩn đoán để kiểm lại ca sửa | Đã xong |
| P5 · Kiểm bản sửa | A → B → C | v2, lock2, review kiểm lại, delta | B kiểm độc lập lại các ca đã sửa; C kiểm kết quả rework và hồ sơ | Đã xong |
| P6 · Chốt nộp | A, B → C | manifest, commit chốt | C kiểm đủ hồ sơ, failed_gates rỗng, repo Public và evidence mở được | Đã xong |

## 4. Bất đồng và phối hợp

- Một ca đã phân xử: adasind_261480.jpg / L2, L4 / R05 — A gán nhãn chưa bật truncated khi box chạm biên; B phát hiện qua QA mù; C chẩn đoán thuộc E1_annotator_error và giao A sửa rework.
- Ca còn mở: Không còn ca mở, toàn bộ các ca lỗi đã được xử lý và khóa bản rework v2.
- Đóng góp của A/B/C vào kế hoạch và exit ticket: A hoàn thiện gán nhãn và rework trên CVAT; B thực hiện QA độc lập và kiểm tra chéo; C tổng hợp chẩn đoán, hoàn thiện báo cáo và thực hiện check/nộp bài.
- Thay đổi phân công nếu có: Không thay đổi trong suốt quá trình làm bài.

## 5. Xác nhận trước khi nộp

- [x] A xác nhận nhãn và export đúng phiên bản: Lê Vĩnh Hưng / submission/r1_craft/lock.txt
- [x] B xác nhận đã QA độc lập trước reference và kiểm lại ca sửa: Bùi Phương Nam / submission/r2_qa/qa_review.md
- [x] C xác nhận báo cáo đúng bản khóa, các file đầy đủ và check exit 0: Nguyễn Đức Hà / submission/r3_diag/
- [x] manifest.json tại commit chốt có failed_gates rỗng.
- [x] Repo nhóm Public, ảnh và các bằng chứng mở được.
- [x] C đã push và gửi link repo nhóm + commit qua kênh lớp công bố.

Chỉ đánh dấu việc đã kiểm thật. Nhóm nộp một hồ sơ chung; check không tự chấm đóng góp từng người. Giữ nguyên header/các cột enum của findings.csv; tên người được ghi trong tài liệu này hoặc phần note thích hợp.