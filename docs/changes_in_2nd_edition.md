# Những Thay đổi trong lần Tái bản thứ Nhất
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

| Ấn bản đầu tiên  | Tái bản lần thứ nhất | Ánh xạ bản tiếng Việt | % thay đổi | Tiêu đề của lần tái bản
|--|--|--|--|--|
|1|1|1, tập 1|<10%|Toàn cảnh Học Máy
|2|2|2, tập 1|<10%|Dự án Học Máy từ Đầu tới Cuối
|3|3|3, tập 1|<10%|Bài toán Phân loại
|4|4|4, tập 1|<10%|Huấn luyện Mô Hình
|5|5|5, tập 1|<10%|Máy Vector Hỗ trợ
|6|6|6, tập 1|<10%|Cây Quyết định
|7|7|7, tập 1|<10%|Học Ensemble và Rừng Ngẫu nhiên
|8|8|8, tập 1|<10%|Giảm Chiều
|Không|9|9, tập 1|Mới 100%|Các kỹ thuật Học Không giám sát
|10|10|1, tập 2|~75%|Giới thiệu về Mạng Nơ-ron Nhân tạo với Keras
|11|11|2, tập 2|~50%|Huấn luyện các Mạng Nơ-ron Sâu
|9|12|3, tập 2|Viết lại 100%|Mô hình tùy chỉnh & Huấn luyện với TensorFlow
|Một phần chương 12|13|4, tập 2|Viết lại 100%|Tải và Tiền xử lý Dữ liệu với TensorFlow
|13|14|5, tập 2|~50%|Thị giác Máy tính Sâu sử dụng Mạng Nơ-ron Tích chập
|Một phần chương 14|15|6, tập 2|~75%|Xử lý Chuỗi sử dụng RNN và CNN
|Một phần chương 14|16|7, tập 2|~90%|Xử lý Ngôn ngữ Tự nhiên với RNN và Cơ chế Tập trung
|15|17|8, tập 2|~75%|Bộ tự Mã hóa và GAN
|16|18|9, tập 2|~75%|Học tăng cường
|Một phần chương 12|19|10, tập 2|Mới ~75%|Sản xuất Mô hình TensorFlow

Một cách cụ thể, dưới đây sẽ là những thay đổi chính trong nội dung tái bản lần thứ nhất
(ngoài việc làm rõ, chỉnh sửa, và cập nhật mã lập trình).
Lưu ý, nội dung sẽ được sắp xếp theo cách mà bản tiếng Việt sẽ triển khai.

### Tập 1
* Chương 1 – Toàn cảnh Học Máy
  * Đã thêm nhiều ví dụ hơn về những ứng dụng Học Máy và các thuật toán tương ứng.
  * Bổ sung một phần nội dung về cách xử lý sự không khớp giữa tập huấn luyện và tập xác thực & kiểm tra.
* Chương 2 – Dự án Học Máy từ Đầu tới Cuối
  * Bổ sung cách để tính khoảng tin cậy.
  * Cải thiện hướng dẫn cài đặt (VD: dành cho Windows).
  * Giới thiệu `OneHotEncoder` được nâng cấp và hàm mới là `ColumnTransformer`.
  * Bổ sung chi tiết về triển khai, giám sát, và bảo trì.
* Chương 4 – Huấn luyện Mô Hình
  * Giải thích sự cần thiết của những mẫu huấn luyện cần độc lập và Phân phối Đồng nhất (IID).
* Chương 7 – Học Ensemble và Rừng Ngẫu nhiên
  * Bổ sung một phần ngắn nói về XGBoost.
* Chương 9 – Các kỹ thuật Học Không giám sát (chương mới)
  * Phân cụm với K-Means, cách chọn số lượng cụm, cách sử dụng nó để giảm chiều, học bán giám sát, phân đoạn hình ảnh, v.v.
  * Thuật toán phân cụm DBSCAN và tổng quan về những thuật toán phân cụm khác có sẵn trong Scikit-Learn.
  * Mô hình hỗn hợp Gauss, thuật toán Kỳ vọng–Cực đại hóa (EM), suy luận biến phân Bayes, 
  và cách các mô hình hỗn hợp có thể được sử dụng trong phân cụm, ước tính mật độ, phát hiện bất thường và tính mới.
  * Tổng quan về những thuật toán phát hiện bất thường và tính mới.
### Tập 2
Đang cập nhật...

## Chuyển đổi từ TensorFlow 1 sang TensorFlow 2
Việc chuyển đổi từ TensorFlow 1.x sang TensorFlow 2.0 cũng tương tự như việc chuyển đổi từ Python 2 sang Python 3 vậy.
Điều đầu tiên cần làm là... thở. Đừng vội vàng.
TensorFlow 1.x sẽ xuất hiện trong một thời gian, và bạn có thời gian.

* Bạn nên bắt đầu bằng cách nâng cấp lên phiên bản TensorFlow 1.x cuối cùng (có thể sẽ là 1.15 vào thời điểm bạn đọc bài này).
* Chuyển đổi càng nhiều mã nguồn của bạn sang sử dụng các API cấp cao, `tf.keras` hoặc Estimators API càng tốt. 
Estimators API vẫn sẽ hoạt động trong TensorFlow 2, nhưng chúng tôi gợi ý bạn nên sử dụng Keras từ bây giờ, 
nhóm phát triển TensorFlow đã thông báo rằng Keras sẽ được ưu tiên hơn và có nhiều khả năng họ sẽ nỗ lực nhiều hơn 
để cải thiện Keras API. Chúng tôi cũng gợi ý bạn sử dụng các tầng tiền xử lý của Keras (xem chương 4, tập 2) hơn là `tf.feature_columns`.
* Việc chuyển đổi cũng sẽ đơn giản hơn khi mã nguồn của bạn chỉ sử dụng các API cấp cao, 
vì nó sẽ hoạt động theo cùng một cách trong bản phát hành mới nhất của TensorFlow 1.x và trong cả TensorFlow 2.
* Bạn nên loại bỏ mọi cách sử dụng `tf.contrib` vì nó không còn khả dụng trong TensorFlow 2.
Một số phần của nó đã được chuyển sang nhóm API lõi, những phần khác được chuyển đến các dự án riêng biệt, 
một số phần không được duy trì nên chúng sẽ bị xóa đi. Nếu cần, bạn phải cài đặt những thư viện thích hợp hoặc sao chép
một số mã kế thừa `tf.contrib` vào dự án của riêng bạn (như một phương án cuối cùng).
* Viết càng nhiều thử nghiệm càng tốt, nó sẽ giúp việc chuyển đổi dễ dàng và an toàn hơn.
* Bạn có thể chạy mã lập trình của TensorFlow 1.x trong TensorFlow 2.0 bằng cách khởi động chương trình của mình
với `import tensorflow.compat.v1 as tf` và `tf.disable_v2_behavior()`.
* Khi bạn đã sẵn sàng thực hiện bước nhảy (như một bước chuyển đổi, nâng cấp), 
bạn có thể chạy [tập lệnh nâng cấp](https://www.tensorflow.org/beta/guide/upgrade) `tf_upgrade_v2`.

Để biết thêm thông tin chi tiết về bước chuyển này, 
hãy xem [Hướng dẫn chuyển đổi](https://www.tensorflow.org/beta/guide/migration_guide) từ TensorFlow.
