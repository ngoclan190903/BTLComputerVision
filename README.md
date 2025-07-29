# BÀI TẬP LỚN: NHẬN DIỆN VÀ THEO DÕI TÁO TRÊN BĂNG CHUYỀN BẰNG YOLOv8 KẾT HỢP BYTE-TRACK

## 📌 Giới thiệu

Đây là dự án nhận diện và theo dõi chất lượng táo trên băng chuyền sử dụng mô hình YOLOv8 kết hợp với thuật toán ByteTrack. Mục tiêu chính là phát hiện các loại táo như:
- 🍏 Táo thường
- 🧃 Táo bị dập
- ❌ Táo hỏng
- 🧽 Dị vật

Sau khi nhận diện, hệ thống sử dụng ByteTrack để gán ID và theo dõi từng quả táo trong suốt quá trình xuất hiện trên video. Dự án được xây dựng bằng ngôn ngữ Python và sử dụng mô hình huấn luyện từ Roboflow.

---

## 🛠 Công nghệ sử dụng

- [x] **Python 3.8+**
- [x] **YOLOv8** (Ultralytics)
- [x] **ByteTrack** (YOLOX tracker)
- [x] **OpenCV** để xử lý video
- [x] **NumPy** cho tính toán ma trận
- [x] **Roboflow** để gán nhãn và huấn luyện mô hình

---

## 📁 Cấu trúc thư mục
apple_vs_defect/
├── weights/
│ ├── best.pt # Mô hình YOLOv8 đã huấn luyện
│ ├── videoapple9S.mp4 # Video đầu vào
│ └── nhan_dien_qua_video.py # File chính chạy phát hiện và theo dõi
├── ByteTrack-main/
│ └── yolox/tracker/ # Thư viện ByteTrack
├── README.md # File mô tả dự án


---

## 🚀 Hướng dẫn cài đặt

### Bước 1: Clone dự án

git clone https://github.com/ten-user/apple_vs_defect.git
cd apple_vs_defect
python -m venv venv
source venv/Scripts/activate  # với Windows
pip install -r requirements.txt

## Lưu ý: Các thư viện cần thiết bao gồm ultralytics, opencv-python, numpy, scipy.

##▶️ Cách chạy chương trình
##Sau khi đã cài đặt xong, bạn có thể chạy script nhận diện như sau:
python weights/nhan_dien_qua_video.py
##Video sẽ hiển thị kết quả nhận diện và theo dõi từng quả táo với bounding box và ID tương ứng.

##📹 Video đầu vào
##Video mẫu: videoapple9S.mp4

##Độ dài: ~10s

##Độ phân giải: 1280x720

##Bối cảnh: Băng chuyền vận chuyển các quả táo

##✅ Kết quả đầu ra
##Hiển thị khung bao quanh từng quả táo

##Gán nhãn: apple, broken, damaged_apple, foreign object

## ID duy nhất cho từng đối tượng

## Tính năng đếm số lượng táo từng loại

##⚠️ Các lỗi thường gặp
## IndexError: index 4 is out of bounds

## Nguyên nhân: output của YOLO không đúng định dạng → cần kiểm tra chiều mảng kết quả

## VisibleDeprecationWarning từ NumPy

##Giải pháp: thêm dtype=object khi chuyển sang np.array nếu cần

##OpenCV hiển thị sai màu

##Kiểm tra lại chuyển đổi màu giữa BGR và RGB

##💡 Ý tưởng mở rộng
##Tích hợp phân loại chất lượng theo kích thước/đường kính táo

##Kết hợp với servo để gạt sản phẩm bị lỗi

##Thêm mô-đun báo cáo thống kê sản phẩm hàng ngày

##👨‍💻 Tác giả
##📧 Nguyễn Thị Ngọc Lan

##📍 Trường Đại học XYZ

##🧪 Bộ môn Hệ thống nhúng - Khoa CNTT

## DANH MỤC TÀI LIỆU THAM KHẢO
##[1] Ultralytics. Ultralytics YOLOv8 Documentation. Truy cập tại: https://docs.ultralytics.com
##[2] Roboflow Inc. Roboflow Documentation. Truy cập tại: https://docs.roboflow.com
##[3] Redmon, J., Divvala, S., Girshick, R., & Farhadi, A. (2016). You Only Look Once: Unified, Real-Time Object Detection. Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2016.
##[4] Ultralytics. YOLOv8 GitHub Repository. Truy cập tại: https://github.com/ultralytics/ultralytics
##[5] Rosebrock, A. (2019). Deep Learning for Computer Vision with Python. PyImageSearch.
##[6] Raspberry Pi Foundation. Raspberry Pi 4 Documentation. Truy cập tại: https://www.raspberrypi.org/documentation/
##[7] PyTorch Team. PyTorch Documentation. Truy cập tại: https://pytorch.org/docs/stable/index.html
##[8] Deng, J., Dong, W., Socher, R., Li, L.J., Li, K., & Fei-Fei, L. (2009). ImageNet: A Large-Scale Hierarchical Image Database. IEEE Conference on Computer Vision and Pattern Recognition, 2009. Dataset truy cập tại: https://www.image-net.org
##[9] NVIDIA Corporation. TensorRT Optimization Toolkit. Truy cập tại: https://developer.nvidia.com/tensorrt
[##10] Roboflow. Apple Object Detection Dataset. Truy cập tại: https://universe.roboflow.com
