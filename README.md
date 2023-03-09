![](.github/assets/cover.jpg)

Dự án này mục tiêu là dạy cho bạn các kiến thức nền tảng về Học Máy trong Python. Kho chứa gồm ví dụ 
và lời giải cho các bài tập trong cuốn sách **Thực hành Học Máy với Scikit-Learn, Keras & TensorFlow**, dựa theo ấn bản lần thứ hai của 
tác giả Aurélien Géron (ấn bản gốc được xuất bản bởi [O'Reilly](https://oreilly.com/library/view/hands-on-machine-learning/9781492032632/)).

## Đặt sách
Bản chuyển ngữ dựa theo ấn bản lần thứ hai của tác giả Aurélien Géron do đội ngũ MLBVN thực hiện được phát hành dưới thể thức sách điện tử, tập tin PDF (DRM), cho phép tải về, không cấp phép in ấn, phân phối, chia sẻ, và chỉ được sử dụng cho mục đích cá nhân với các yêu cầu được quy định cụ thể.

Để đặt sách và tìm hiểu kỹ các quy định sử dụng nêu trên, quý độc giả vui lòng xem hướng dẫn tại **https://handson-ml.mlbvn.org**.

Những thông tin về cuốn sách được đội ngũ MLBVN cập nhật thường xuyên trên [Facebook Page của MLBVN](https://www.facebook.com/mlbvn.org).

## Bắt đầu

### Trực tuyến & Không cài đặt
Bạn có thể sử dụng bất kỳ dịch vụ nào sau đây (Chúng tôi đề xuất bạn sử dụng Google Colab 
hoặc Kaggle, bởi vì họ cung cấp GPU & TPU miễn phí).

**CẢNH BÁO**: *Xin lưu ý rằng các dịch vụ này cung cấp môi trường tạm thời. Mọi thứ bạn làm sẽ bị xoá đi 
sau một thời gian, vì vậy hãy đảm bảo rằng bạn đã tải xuống bất kỳ dữ liệu nào bạn quan tâm*.

* [![Open in Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mlbvn/handson-ml2-vn/blob/main/)

* [![Open in Kaggle](https://kaggle.com/static/images/open-in-kaggle.svg)](https://git.io/Jc6Ge)

* [![Open in Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/mlbvn/handson-ml2-vn/HEAD?filepath=%2Findex.ipynb)

* [![Open in Deepnote](https://deepnote.com/buttons/launch-in-deepnote-small.svg)](https://git.io/Jc6sF)

### Xem nhanh & Không thực hành
Bạn có thể sử dụng bất kỳ dịch vụ gợi ý nào dưới đây để xem nhanh các nội dung trong kho chứa này.

* [![Open in GitHub](https://img.shields.io/static/v1?logo=github&label=&message=Open%20in%20GitHub&color=0969da&labelColor=333&logoColor=fff)](https://github.com/mlbvn/handson-ml2-vn/blob/main/index.ipynb)

* [![Open in Visual Studio Code](https://img.shields.io/static/v1?logo=visualstudiocode&label=&message=Open%20in%20Visual%20Studio%20Code&color=086abf&labelColor=333&logoColor=086abf)](https://github.dev/mlbvn/handson-ml2-vn)

* [![Open in Jupyter NBViewer](https://img.shields.io/static/v1?logo=jupyter&label=&message=Open%20in%20Jupyter%20NBViewer&color=f37626&labelColor=333&logoColor=fff)](https://nbviewer.jupyter.org/github/mlbvn/handson-ml2-vn/blob/main/index.ipynb)

**Lưu ý**: Nếu bạn sử dụng Visual Studio Code, bạn có thể cần phải cài đặt một số tiện ích bổ sung để có thể chạy Notebook.

### Chạy trên Docker
Vui lòng đọc qua [hướng dẫn Docker](https://github.com/mlbvn/handson-ml2-vn/tree/main/docker) để biết thêm thông tin.

### Cài đặt Dự án trên Máy tính của bạn

Bắt đầu bằng việc cài đặt [Anaconda](https://www.anaconda.com/distribution/) (hoặc 
[Miniconda](https://docs.conda.io/en/latest/miniconda.html)), [git](https://git-scm.com/downloads), và nếu bạn có 
GPU tương tác với TensorFlow, hãy cài đặt [GPU driver](https://www.nvidia.com/Download/index.aspx), cũng như 
phiên bản CUDA và cuDNN thích hợp (xem tài liệu của TensorFlow để biết thêm chi tiết).

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

Nếu bạn cần thêm hướng dẫn, vui lòng đọc [hướng dẫn cài đặt chi tiết](./docs/install.md) để biết thêm thông tin.

### Bảng thuật ngữ
Các thuật ngữ trong cuốn sách được bổ sung và thảo luận [tại đây](./docs/glossary.md).

## Câu hỏi Thường gặp (FAQs)

**Tôi nên sử dụng phiên bản Python nào?**

Chúng tôi khuyên bạn nên sử dụng Python 3.7. Nếu bạn làm theo hướng dẫn cài đặt ở trên, đó là phiên bản bạn sẽ nhận được. 
Hầu hết mã nguồn sẽ hoạt động với các phiên bản khác của Python 3, nhưng một số thư viện chưa hỗ trợ Python 3.8 
và Python 3.9. Đó là lý tại sao chúng tôi khuyên dùng Python 3.7.

**Tôi gặp lỗi khi gọi `load_housing_data()`**

Hãy đảm bảo rằng bạn gọi `fetch_housing_data()` *trước khi* bạn gọi `load_housing_data()`. Nếu bạn gặp lỗi HTTP, 
hãy đảm bảo rằng bạn đang chạy mã nguồn chính xác như trong Jupyter Notebook (copy/paste nếu cần thiết). 
Nếu sự cố vẫn tiếp diễn, vui lòng kiểm tra cấu hình mạng của bạn.

**Tôi gặp lỗi SSL trên macOS**

Bạn có thể cần phải cài đặt chứng chỉ SSL (xem câu hỏi này trên 
[StackOverflow](https://stackoverflow.com/questions/27835619/urllib-and-ssl-certificate-verify-failed-error)). 
Nếu bạn đã tải xuống Python từ website chính thức, vui lòng chạy `/Applications/Python\ 3.7/Install\ Certificates.command` 
trên Terminal (thay đổi `3.7` thành bất kỳ phiên bản nào bạn đã cài đặt). Nếu bạn đã cài đặt Python bằng MacPorts, 
hãy chạy `sudo port install curl-ca-bundle` trên Terminal.

**Tôi đã cài đặt dự án trên máy tính, làm cách nào để cập nhật nó lên phiên bản mới nhất?**

Mời bạn xem qua [hướng dẫn cài đặt chi tiết](./docs/install.md) để biết thêm thông tin.

**Làm cách nào để cập nhật thư viện Python của tôi lên phiên bản mới nhất khi sử dụng Anaconda?**

Mời bạn xem qua [hướng dẫn cài đặt chi tiết](./docs/install.md) để biết thêm thông tin.

## Maintainer
Duy–Thanh Doan [@duythanhvn](https://github.com/duythanhvn)
