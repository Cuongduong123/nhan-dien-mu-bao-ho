
![123cb7d34701cf5f9610](https://github.com/user-attachments/assets/5c162d70-6433-4ccc-820a-264104a35dff)
Giới Thiệu

Tai nạn lao động tại công trường, nhà máy, xưởng sản xuất thường xuất phát từ việc công nhân không tuân thủ quy định an
toàn, đặc biệt là không đội mũ bảo hộ.

Giải pháp Nhận diện mũ bảo hộ bằng Camera AI ứng dụng Thị giác máy tính (Computer Vision) và Trí tuệ nhân tạo (AI) để:
Giám sát tự động trong thời gian thực.
Phát hiện công nhân có hoặc không đội mũ bảo hộ.
Gửi cảnh báo (âm thanh, đèn báo, email hoặc log hệ thống).
Mục tiêu: Tăng cường an toàn lao động – Giảm chi phí giám sát – Hỗ trợ chuyển đổi số trong công tác quản lý an toàn.

🎯 Mục tiêu đề tài
Phát hiện con người trong khung hình từ camera giám sát.
Phân loại nhân viên thành 2 nhóm:
✅ Có đội mũ bảo hộ.
❌ Không đội mũ bảo hộ.
Tích hợp hệ thống cảnh báo khi phát hiện vi phạm.
Hỗ trợ giám sát real-time và xuất báo cáo vi phạm.


⚙️ Công nghệ sử dụng
Ngôn ngữ: Python 3.x
Thư viện chính:
OpenCV → xử lý hình ảnh & video.
TensorFlow hoặc PyTorch → huấn luyện & triển khai mô hình AI.
YOLOv5/YOLOv8 → nhận diện đối tượng (helmet/no-helmet).
Triển khai giao diện: Flask / FastAPI / Streamlit (tùy chọn).
Phần cứng: Webcam / Camera IP.


📂 Cấu trúc thư mục (gợi ý)
helmet-detection-ai/
│── data/                # Bộ dữ liệu huấn luyện & kiểm thử
│   ├── images/          # Ảnh gốc
│   ├── labels/          # Nhãn (helmet / no-helmet)
│── models/              # Mô hình AI đã huấn luyện
│── src/                 
│   ├── train.py         # Huấn luyện mô hình
│   ├── detect.py        # Chạy nhận diện
│   ├── utils.py         # Các hàm hỗ trợ
│── requirements.txt     # Danh sách thư viện cần cài đặt
│── README.md            # Tài liệu dự án
🚀 Hướng dẫn cài đặt & chạy


1. Clone dự án
git clone https://github.com/<username>/helmet-detection-ai.git
cd helmet-detection-ai
2. Cài đặt thư viện
pip install -r requirements.txt
3. Huấn luyện mô hình (nếu cần)
python src/train.py --data data/helmet.yaml --epochs 50
4. Chạy nhận diện từ webcam
python src/detect.py --source 0
5. Chạy nhận diện từ video
python src/detect.py --source input_video.mp4



🔄 Luồng hoạt động hệ thống
Camera ghi hình → gửi dữ liệu video.
AI (YOLO) xử lý khung hình → phát hiện người + mũ bảo hộ.

So sánh kết quả:
✅ Có mũ → đánh dấu viền xanh.
❌ Không mũ → đánh dấu viền đỏ + cảnh báo.
Kết quả hiển thị trên màn hình / gửi cảnh báo ra ngoài.
🖼️ Demo (ví dụ)
🟢 Công nhân đội mũ → nhãn "Helmet" (viền xanh).
🔴 Công nhân không đội mũ → nhãn "No Helmet" (viền đỏ + cảnh báo).

📊 Kết quả mong đợi
Độ chính xác (Accuracy): >90% trên tập kiểm thử.
Tốc độ xử lý: <100ms/frame (thời gian thực).
Hệ thống hoạt động ổn định trong môi trường nhà máy/công trường.

🌟 Ưu điểm
Giám sát 24/7 tự động.
Giảm phụ thuộc vào nhân viên bảo hộ.
Mở rộng dễ dàng cho các yêu cầu khác: khẩu trang, áo phản quang, găng tay.

🔮 Hướng phát triển
Tích hợp IoT: còi báo, đèn nháy, gửi tin nhắn SMS.
Dashboard quản lý vi phạm trên Web.
Báo cáo thống kê số lần vi phạm theo thời gian.
Hỗ trợ Edge AI để chạy trực tiếp trên camera thông minh.
