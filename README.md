![](.github/assets/cover.jpg)

Dự án này mục tiêu là dạy cho bạn các kiến thức nền tảng về Học Máy trong Python. Kho chứa gồm ví dụ và lời giải cho các bài tập trong cuốn sách **Thực hành Học Máy với Scikit-Learn, Keras & TensorFlow** của tác giả Aurélien Géron (ấn bản gốc được xuất bản bởi [O'Reilly](https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/)).

## Bắt đầu

### Trực tuyến & Không cài đặt
Bạn có thể sử dụng bất kỳ dịch vụ nào sau đây (Chúng tôi đề xuất bạn sử dụng Google Colab hoặc Kaggle, bởi vì họ cung cấp GPU & TPU miễn phí).

**CẢNH BÁO**: *Xin lưu ý rằng các dịch vụ này cung cấp môi trường tạm thời. Mọi thứ bạn làm sẽ bị xoá đi sau một thời gian, vì vậy hãy đảm bảo rằng bạn đã tải xuống bất kỳ dữ liệu nào bạn quan tâm*.

| Google Colab | Kaggle | Binder | Deepnote |
|---|---|---|---|
| <a href="https://colab.research.google.com/github/mlbvn/handson-ml2-vn/blob/main/" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a> | <a href="https://git.io/JnA16"><img src="https://kaggle.com/static/images/open-in-kaggle.svg" alt="Open in Kaggle" /></a> | <a href="https://mybinder.org/v2/gh/mlbvn/handson-ml2-vn/HEAD?filepath=%2Findex.ipynb"><img src="https://mybinder.org/badge_logo.svg" alt="Launch binder" /></a> | <a href="https://git.io/JnA1S"><img src="https://deepnote.com/buttons/launch-in-deepnote-small.svg" alt="Launch in Deepnote" /></a> |

### Xem nhanh & Không thực hành

* [Jupyter NBViewer](https://nbviewer.jupyter.org/github/mlbvn/handson-ml2-vn/blob/main/index.ipynb) là một lựa chọn tốt để làm việc này.
* [Github](https://github.com/mlbvn/handson-ml2-vn/blob/main/index.ipynb) là một lựa chọn nhưng không quá lý tưởng: nó chậm hơn, những phương trình toán học không phải lúc nào cũng được hiển thị chính xác và các Jupyter Notebooks lớn có thể sẽ không hoạt động.

### Chạy trên Docker

Vui lòng đọc qua [hướng dẫn Docker](https://github.com/mlbvn/handson-ml2-vn/tree/main/docker) để biết thêm thông tin.

### Cài đặt Dự án trên Máy tính của bạn

Bắt đầu bằng việc cài đặt [Anaconda](https://www.anaconda.com/distribution/) (hoặc [Miniconda](https://docs.conda.io/en/latest/miniconda.html)), [git](https://git-scm.com/downloads), và nếu bạn có GPU tương tác với TensorFlow, hãy cài đặt [GPU driver](https://www.nvidia.com/Download/index.aspx), cũng như phiên bản CUDA và cuDNN thích hợp (xem tài liệu của TensorFlow để biết thêm chi tiết).

Tiếp theo, sao chép kho lưu trữ này bằng cách mở một trình Terminal và nhập các lệnh sau 
(không nhập ký tự `$` đầu tiên trên mỗi dòng, đó chỉ là quy ước để cho thấy rằng đây là dấu nhắc của Terminal):

    $ git clone https://github.com/mlbvn/handson-ml2-vn.git
    $ cd handson-ml2-vn

Chạy những lệnh sau đây:

    $ conda env create -f environment.yml
    $ conda activate tf2
    $ python -m ipykernel install --user --name=python3

Cuối cùng, khởi động Jupyter:

    $ jupyter notebook

Nếu bạn cần thêm hướng dẫn, vui lòng đọc [hướng dẫn cài đặt chi tiết](install.md) để biết thêm thông tin.

# Câu hỏi Thường gặp (FAQ)

**Tôi nên sử dụng phiên bản Python nào?**

Chúng tôi khuyên bạn nên sử dụng Python 3.7. Nếu bạn làm theo hướng dẫn cài đặt ở trên, đó là phiên bản bạn sẽ nhận được. Hầu hết mã nguồn sẽ hoạt động với các phiên bản khác của Python 3, nhưng một số thư viện chưa hỗ trợ Python 3.8 và Python 3.9. Đó là lý tại sao chúng tôi khuyên dùng Python 3.7.

**Tôi gặp lỗi khi gọi `load_housing_data()`**

Hãy đảm bảo rằng bạn gọi `fetch_housing_data()` *trước khi* bạn gọi `load_housing_data()`. Nếu bạn gặp lỗi HTTP, hãy đảm bảo rằng bạn đang chạy mã nguồn chính xác như trong Jupyter Notebook (copy/paste nếu cần thiết). Nếu sự cố vẫn tiếp diễn, vui lòng kiểm tra cấu hình mạng của bạn.

**Tôi gặp lỗi SSL trên macOS**

Bạn có thể cần phải cài đặt chứng chỉ SSL (xem câu hỏi này trên [StackOverflow](https://stackoverflow.com/questions/27835619/urllib-and-ssl-certificate-verify-failed-error)). Nếu bạn đã tải xuống Python từ website chính thức, vui lòng chạy `/Applications/Python\ 3.7/Install\ Certificates.command` trên Terminal (thay đổi `3.7` thành bất kỳ phiên bản nào bạn đã cài đặt). Nếu bạn đã cài đặt Python bằng MacPorts, hãy chạy `sudo port install curl-ca-bundle` trên Terminal.

**Tôi đã cài đặt dự án trên máy tính, làm cách nào để cập nhật nó lên phiên bản mới nhất?**

Mời bạn xem qua [hướng dẫn cài đặt chi tiết](install.md) để biết thêm thông tin.

**Làm cách nào để cập nhật thư viện Python của tôi lên phiên bản mới nhất khi sử dụng Anaconda?**

Mời bạn xem qua [hướng dẫn cài đặt chi tiết](install.md) để biết thêm thông tin.

## Lời cảm ơn
Để hoàn thành dự án này, chúng tôi xin gửi lời cảm ơn đến [**O'Reilly**](https://www.oreilly.com/) & tác giả [**Aurélien Géron**](https://github.com/ageron) đã đồng ý cho chúng tôi được thực hiện chuyển ngữ và giúp đỡ chúng tôi trong suốt quá trình hoàn thiện cuốn sách.

Chúng tôi cũng gửi lời cảm ơn đến các [thành viên trực tiếp tham gia]() vào dự án này, nếu không có sự nỗ lực và trách nhiệm của từng cá nhân thì dự án khó có thể đảm bảo được thời gian và chất lượng cho cuốn sách.

Và chúng tôi cũng không quên gửi lời cảm ơn chân thành đến [**Đại học FUNiX**](https://funix.edu.vn/) đã hỗ trợ chúng rất nhiều trong các vấn đề xuất bản và còn hơn thế nữa.

Những lời cảm ơn khác xin dành cho những Cộng tác viên đã giúp đỡ cho tác giả để dự án gốc có thể trở nên tốt hơn, có thể xem **[tại đây](https://github.com/ageron/handson-ml2/graphs/contributors)**.

Cuối cùng, chúng tôi cảm ơn những độc giả đã và đang tin tưởng, tín nhiệm và ủng hộ những cuốn sách mà nhóm đã thực hiện. Thiếu những ủng hộ này, những cuốn sách này khó có thể được lan truyền và giúp đỡ được nhiều người hơn.

## Maintainers

Đoàn Võ Duy Thanh [@duythanhvn](https://github.com/duythanhvn)


