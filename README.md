# BTLComputerVision
Phát hiện bất thường (trái cây lỗi, vật thể lạ) trên băng chuyền thu hoạch nông sản bằng xử lý ảnh cơ bản
📌 1. Mục tiêu đề tài
Xây dựng một hệ thống thị giác máy tính đơn giản, không dùng AI, nhằm giám sát quá trình thu hoạch nông sản (ví dụ: táo, cam...) trên băng chuyền và phát hiện các bất thường, bao gồm:

Trái cây bị hỏng, méo mó, sai màu.

Vật thể lạ như lá cây, cành, bao bì, đá...

🧠 2. Ý tưởng triển khai
Sử dụng video .mp4 hoặc camera trực tiếp mô phỏng băng chuyền thu hoạch.

Mỗi khung hình từ video được xử lý như sau:

Color Thresholding: Phát hiện vùng màu đỏ (nếu là táo).

Phát hiện hình dạng (Contour hoặc Hough Circle): Kiểm tra độ tròn đều.

So sánh đặc trưng hình ảnh:

Sai màu → vật thể lạ.

Méo nhiều, không tròn → trái cây lỗi.

Kích thước bất thường → loại trừ hoặc cảnh báo.

🧰 3. Công cụ và kỹ thuật
Ngôn ngữ :	Python
Thư viện :	OpenCV, NumPy (nếu cần), matplotlib (tùy chọn giao diện)
Video mẫu	: video.mp4 quay cảnh băng chuyền có trái cây thật hoặc mô phỏng
Thuật toán	Xử lý ảnh cơ bản: chuyển màu, thresholding, morphology, contours, hình tròn (Hough Circle)

🛠️ 4. Chức năng chính
Đọc video .mp4 làm đầu vào hệ thống.

Xử lý khung hình theo thời gian thực (hoặc mô phỏng).

Phát hiện trái cây và phân loại:

Màu hợp lệ + hình tròn → táo đạt chuẩn.

Màu hợp lệ + hình méo → táo lỗi.

Màu khác → vật thể lạ.

Hiển thị kết quả lên từng khung hình (bounding box + nhãn).

(Tùy chọn) Ghi log hoặc đếm số lượng trái đạt/không đạt.

📊 5. Tiêu chí đánh giá sản phẩm
Xử lý đúng và phân biệt được 3 loại: táo tốt – táo lỗi – vật thể lạ.

Hiển thị hình ảnh kết quả rõ ràng, trực quan.

Giao diện đơn giản, dễ dùng (nếu có).

Tài liệu báo cáo phân tích rõ quy trình xử lý và đánh giá kết quả.

🌱 6. Mở rộng (nếu có thời gian)
Đếm số lượng từng loại đối tượng.

Gửi cảnh báo khi phát hiện bất thường.

Kết nối với mô hình điều khiển (relay, gạt trái lỗi).

Tạo giao diện GUI đơn giản bằng PyQt5 hoặc Tkinter.

📘 7. Hướng phát triển
Ứng dụng trong hệ thống kiểm tra chất lượng tự động trong dây chuyền nông sản.

Có thể kết hợp học sâu (CNN) để nâng cấp độ chính xác khi có đủ dữ liệu.
