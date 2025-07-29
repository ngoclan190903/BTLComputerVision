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

```bash
git clone https://github.com/ten-user/apple_vs_defect.git
cd apple_vs_defect
python -m venv venv
source venv/Scripts/activate  # với Windows
pip install -r requirements.txt
