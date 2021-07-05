# Những Thay đổi trong Tái bản thứ Nhất
Ở lần tái bản này có sáu mục tiêu chính:

1. Các chủ đề Học Máy bổ sung: các kỹ thuật học tập không giám sát 
(gồm phân cụm, phát hiện bất thường, ước tính mật độ, và mô hình hỗn hợp),
các kỹ thuật huấn luyện mạng sâu (gồm mạng tự chuẩn hóa), các kỹ thuật thị giác máy tính 
(gồm Xception, SENet, phát hiện vật thể với YOLO, và phân đoạn ngữ nghĩa sử dụng R-CNN),
xử lý chuỗi bằng CNN (gồm WaveNet), xử lý ngôn ngữ tự nhiên sử dụng RNN, CNN và Transformers, mạng đối sinh.
2. Các thư viện và API bổ sung: Keras, API dữ liệu, TF-Agents cho Học tăng cường, 
huấn luyện và triển khai các mô hình trên TensorFlow có quy mô sử dụng Distribution Strategies API,
TF-Serving và Google Cloud AI Platform. Đồng thời giới thiệu ngắn về TF Transform, TFLite, TF Addons/Seq2Seq, TensorFlow.js, v.v.
1. Đề cập đến một số thành quả quan trọng từ việc nghiên cứu Deep Learning.
2. Nâng cấp các chương đang sử dụng TensorFlow sang TensorFlow 2, và sử dụng Keras API để 
triển khai TensorFlow (gọi là tf.keras) bất cứ khi nào có thể, để đơn giản hóa các ví dụ trong mã lập trình.
5. Cập nhật các ví dụ mã lập trình để sử dụng phiên bản mới nhất của Scikit-Learn, NumPy, Pandas, Matplotlib, và những thư viện khác.
6. Làm rõ một số phần nội dung và sửa một số lỗi, cảm ơn nhiều phản hồi tuyệt vời từ độc giả.

Một số chương đã được thêm vào, những chương khác được viết lại và một vài chương đã được sắp xếp lại thứ tự.
Bảng sau đây sẽ ánh xạ các thay đổi giữa ấn bản đầu tiên và tái bản lần thứ nhất:

| Ấn bản đầu tiên  | Tái bản lần thứ nhất | % thay đổi | Tiêu đề của lần tái bản
|--|--|--|--|
|1|1|<10%|Toàn cảnh Học Máy
|2|2|<10%|Dự án Học Máy từ Đầu tới Cuối
|3|3|<10%|Bài toán Phân loại
|4|4|<10%|Huấn luyện Mô Hình
|5|5|<10%|Máy Vector Hỗ trợ
|6|6|<10%|Cây Quyết định
|7|7|<10%|Học Ensemble và Rừng Ngẫu nhiên
|8|8|<10%|Giảm Chiều
|Không|9|Mới 100%|Các kỹ thuật Học Không giám sát
|10|10|~75%|Giới thiệu về Mạng Nơ-ron Nhân tạo với Keras
|11|11|~50%|Huấn luyện các Mạng Nơ-ron Sâu
|9|12|Viết lại 100%|Mô hình tùy chỉnh & Huấn luyện với TensorFlow
|Một phần chương 12|13|Viết lại 100%|Tải và Tiền xử lý Dữ liệu với TensorFlow
|13|14|~50%|Thị giác Máy tính Sâu sử dụng Mạng Nơ-ron Tích chập
|Một phần chương 14|15|~75%|Xử lý Chuỗi sử dụng RNN và CNN
|Một phần chương 14|16|~90%|Xử lý Ngôn ngữ Tự nhiên với RNN và Cơ chế Tập trung
|15|17|~75%|Bộ tự Mã hóa và GAN
|16|18|~75%|Học tăng cường
|Một phần chương 12|19|Mới ~75%|Sản xuất Mô hình TensorFlow
