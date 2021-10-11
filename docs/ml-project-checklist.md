# Danh mục Công việc trong Dự án Học Máy 

Danh sách danh mục công việc cho dự án Học Máy các công việc này có thể là kim chỉ nam 
trong các dự án Học Máy của bạn. Nó bao gồm tám bước chính sau:

1. Định hình bài toán và xem xét bức tranh tổng thể.
2. Thu thập dữ liệu.
3. Khám phá dữ liệu để có được thông tin chi tiết.
4. Chuẩn bị dữ liệu để tạo ra những các dữ liệu đầu vào phù hợp cho các thuật toán Học Máy.
5. Khám phá các mô hình Học Máy khác nhau và chọn ra những mô hình tốt nhất.
6. Tinh chỉnh các mô hình và kết hợp chúng lại thành một giải pháp hoàn hảo hơn.
7. Trình bày giải pháp của bạn.
8. Khởi chạy, giám sát, và bảo trì hệ thống của bạn. 

Tất nhiên là bạn có thể tự do điều chỉnh danh sách trên cho phù hợp với nhu cầu cụ thể.

## Định hình Bài toán và Xem xét Bức tranh Tổng thể
1. Xác định mục tiêu theo phương diện kinh doanh.
2. Giải pháp của bạn sẽ được sử dụng như thế nào?
3. Các giải pháp hiện tại (nếu có) là gì?
4. Bạn sẽ định hình bài toán này như thế nào (có giám sát/không giám sát, trực tuyến/ngoại tuyến, v.v.)?
5. Chất lượng của giải pháp sẽ được đo lường như thế nào?
6. Thước đo chất lượng này có phù hợp với mục tiêu kinh doanh không?
7. Chất lượng mô hình tối thiểu cần thiết để đạt được mục tiêu kinh doanh là bao nhiêu?
8. Các bài toán tương tự là gì? Bạn có thể sử dụng lại kinh nghiệm hoặc công cụ có sẵn được không?
9. Yếu tố kiến thức chuyên môn có cần thiết không?
10. Bạn sẽ giải quyết bài toán theo cách thủ công như thế nào?
11. Liệt kê những giả định mà bạn (hoặc những người khác) đã đưa ra cho đến thời điểm hiện tại.
12. Kiểm chứng các giả định nếu có thể. 

## Thu thập Dữ liệu 
Lưu ý: hãy tự động hóa càng nhiều càng tốt để có thể thu thập được dữ liệu mới một cách dễ dàng. 

1. Liệt kê loại dữ liệu và số lượng mà bạn cần.
2. Tìm và ghi lại nơi bạn có thể thu thập được dữ liệu đó.
3. Kiểm tra xem dữ liệu sẽ chiếm bao nhiêu dung lượng.
4. Kiểm tra các nghĩa vụ pháp lý và xin quyền sử dụng nếu cần.
5. Xin quyền truy cập.
6. Tạo một môi trường làm việc (có đủ dung lượng lưu trữ).
7. Thu thập dữ liệu.
8. Chuyển đổi dữ liệu thành định dạng mà bạn có thể dễ dàng thao tác (mà không làm thay đổi thông tin dữ liệu).
9. Đảm bảo các thông tin nhạy cảm phải được bảo vệ hoặc xóa bỏ (ví dụ, dạng ẩn danh).
10. Kiểm tra kích thước và dạng dữ liệu (dạng chuỗi thời gian, mẫu, không gian địa lý, v.v.).
11. Lấy mẫu để tạo tập dữ liệu kiểm tra, để nó sang một bên và không được đụng vào (không được xem lén dữ liệu!).

## Khám phá Dữ liệu
Lưu ý: hãy cố gắng nhờ một chuyên gia trong ngành để hiểu rõ hơn về dữ liệu khi thực hiện các bước này.

1. Tạo một bản sao dữ liệu dành cho việc khám phá (lấy mẫu với kích thước nhỏ hơn để có thể xử lý dễ dàng nếu cần).
2. Tạo một Jupyter notebook để ghi lại quá trình khám phá dữ liệu.
3. Nghiên cứu từng thuộc tính và đặc điểm của nó:
    - Tên
    - Dạng dữ liệu (dạng hạng mục, dạng số nguyên/số thực, dạng bị chặn/không bị chặn, dạng văn bản, dạng có cấu trúc, v.v.)
    - Phần trăm của những giá trị bị thiếu
    - Độ nhiễu và dạng nhiễu (ngẫu nhiên, ngoại lai, lỗi làm tròn số, v.v.)
    - Tính hữu ích cho tác vụ
    - Dạng phân phối của dữ liệu (Gauss, đều, logarit, v.v.)
4. Đối với các tác vụ học có giám sát, hãy xác định (các) thuộc tính mục tiêu.
5. Trực quan hóa dữ liệu.
6. Nghiên cứu mối tương quan giữa các thuộc tính.
7. Nghiên cứu cách bạn sẽ giải quyết bài toán theo cách thủ công.
8. Xác định các phép biến đổi tiềm năng mà bạn có thể áp dụng.
9. Xác định dữ liệu bổ sung hữu ích (quay lại bước Thu thập Dữ liệu).
10. Ghi lại những gì bạn đã học được.

## Chuẩn bị Dữ liệu
Lưu ý:  
- Làm việc trên các bản sao của dữ liệu thay vì tập dữ liệu gốc (giữ nguyên tập dữ liệu gốc).
- Viết hàm cho tất cả các phép biến đổi dữ liệu, vì năm lý do sau:
    - Dễ dàng hơn trong việc chuẩn bị dữ liệu trong lần tiếp theo khi bạn có một tập dữ liệu mới
    - Có thể sử dụng các phép biến đổi này trong những dự án tương lai
    - Làm sạch và chuẩn bị tập kiểm tra
    - Làm sạch và chuẩn bị các mẫu dữ liệu mới khi giải pháp được triển khai
    - Dễ dàng để coi các lựa chọn trong việc chuẩn bị dữ liệu như các siêu tham số

1. Làm sạch dữ liệu:
    - Sửa hoặc loại bỏ các điểm ngoại lai (không bắt buộc).
    - Điền vào các giá trị còn thiếu (ví dụ với 0, trung bình, trung vị, v.v.) hoặc loại bỏ hàng (hoặc cột) chứa các giá trị đó.
2. Lựa chọn đặc trưng (không bắt buộc):
    - Loại bỏ các thuộc tính không hữu ích cho tác vụ.
3. Thiết kế đặc trưng, nếu thích hợp:
    - Biến các đặc trưng liên tục thành rời rạc.
    - Phân tách các đặc trưng (ví dụ như hạng mục, thời gian, v.v..)
    - Thêm các phép biến đổi đặc trưng tiềm năng (ví dụ như log(x), sqrt(x), x^2, etc.).
    - Tổng hợp các đặc trưng thành đặc trưng mới tiềm năng.
4. Co giãn đặc trưng: Chuẩn hóa hoặc chuẩn tắc hóa các đặc trưng.

## Rút gọn Danh sách các Mô hình Tiềm năng 
Lưu ý:
- Nếu tập dữ liệu lớn, bạn có thể lấy mẫu các tập huấn luyện nhỏ hơn để huấn luyện nhiều mô hình 
khác nhau trong một khoảng thời gian hợp lý (lưu ý rằng phương pháp này không hiệu quả với những 
mô hình phức tạp như các mạng nơ-ron lớn hoặc Rừng Ngẫu nhiên).
- Một lần nữa, hãy cố gắng tự động hoá các bước này nhiều nhất có thể.  

1. Huấn luyện nhiều loại mô hình đơn giản khác nhau (ví dụ như tuyến tính, naive Bayes, SVM, 
Rừng Ngẫu nhiên, Mạng nơ-ron, v.v..) sử dụng các tham số tiêu chuẩn.
2. Đo lường và so sánh chất lượng của chúng.
    - Với mỗi mô hình, sử dụng kiểm định N-fold, tính trung bình và độ lệch chuẩn 
    của chất lượng mô hình trên N-fold.
3. Phân tích những biến quan trọng nhất của từng thuật toán.
4. Phân tích những loại lỗi mà các mô hình gặp phải.
    - Con người sẽ sử dụng dữ liệu nào để tránh những lỗi này?
5. Thực hiện nhanh một lượt lựa chọn và thiết kế đặc trưng.
6. Thực hiện nhanh một hoặc hai lượt cả năm bước ở trên.
7. Tạo danh sách rút gọn từ ba tới năm mô hình có tiềm năng nhất, 
ưu tiên các mô hình có các loại lỗi khác nhau.

## Tinh chỉnh Hệ thống
Lưu ý: 
- Bạn nên sử dụng càng nhiều dữ liệu càng tốt tại bước này, đặc biệt là trong giai đoạn cuối của quá trình tinh chỉnh.
- Như thường lệ, cố gắng tự động hoá càng nhiều càng tốt.

1. Tinh chỉnh các siêu tham số sử dụng kiểm định chéo:
    - Xem các lựa chọn biến đổi dữ liệu như các siêu tham số, đặc biệt là khi bạn không chắc chắn về cách 
    lựa chọn chúng (ví dụ nếu bạn phân vân trong việc thay thế giá trị thiếu bằng 0 hay bằng giá trị trung vị, 
    hay chỉ đơn giản là bỏ luôn các hàng đó).
    - Trừ khi có rất ít các giá trị siêu tham số để thử nghiệm, hãy ưu tiên tìm kiếm ngẫu nhiên thay vì tìm kiếm 
    dạng lưới. Nếu quá trình huấn luyện tốn nhiều thời gian, bạn có thể sử dụng phương pháp tối ưu hóa Bayes 
    (ví dụ như dùng quá trình Gauss tiên nghiệm (Gaussian process prior),như được mô tả bởi Jasper Snoek, Hugo 
    Larochelle, và Ryan Adams ([https://goo.gl/PEFfGr](https://goo.gl/PEFfGr))).
2. Thử các phương pháp Ensemble. Kết hợp các mô hình tốt nhất thường sẽ cho kết quả tốt hơn so với từng mô hình riêng biệt.
3. Một khi bạn đã tự tin với mô hình cuối cùng, hãy đo lường chất lượng trên tập kiểm tra để ước lượng lỗi tổng quát hóa.

> Đừng tinh chỉnh mô hình sau khi đo lường lỗi tổng quát hóa, bạn sẽ bắt đầu quá khớp tập kiểm tra. 
  
## Trình bày Giải pháp 
1. Ghi chép lại những gì bạn đã làm.
2. Thực hiện một bài thuyết trình hay.
    - Hãy đảm bảo rằng bạn sẽ nhấn mạnh bức tranh tổng thể trước.
3. Giải thích tại sao giải pháp của bạn đạt được mục tiêu kinh doanh.
4. Đừng quên trình bày những điểm thú vị mà bạn tìm được trong quá trình phát triển hệ thống.
    - Mô tả những thứ hoạt động và không hoạt động.
    - Liệt kê các giả định cũng như các hạn chế của hệ thống.
5. Đảm bảo những phát hiện chính của bạn được truyền đạt bằng trực quan đẹp mắt hoặc mệnh đề dễ nhớ 
(ví dụ như "thu nhập trung bình là nhân tố quan trọng nhất để dự đoán giá nhà ở").

## Triển khai!
1. Chuẩn bị để triển khai giải pháp (đưa dữ liệu đầu vào vào hệ thống, viết unit test, v.v..).
2. Viết mã giám sát để kiểm tra định kỳ chất lượng của hệ thống trong quá trình hoạt động 
và kích hoạt cảnh bảo khi chất lượng đi xuống.
    - Cẩn thận với sự xuống cấp chậm của hệ thống: các mô hình có xu hướng "mục nát" khi dữ liệu thay đổi.
    - Việc đo lường chất lượng có thể yêu cầu nhân công con người (ví dụ như thông qua các dịch vụ crowdsourcing).
    - Đồng thời theo dõi chất lượng của đầu vào (ví dụ cảm biến bị trục trặc gửi đi các giá trị ngẫu nhiên, 
    hoặc đầu ra của một nhóm khác không được cập nhật theo thời gian thực).
    Điều này đặc biệt quan trọng với các hệ thống học trực tuyến.  
3. Huấn luyện lại các mô hình theo định kỳ với dữ liệu mới (tự động hóa nhiều nhất có thể).
