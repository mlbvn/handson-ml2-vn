# Cài đặt

## Tải kho chứa về

Để cài đặt kho lưu trữ và chạy các Jupyter Notebook trên máy tính của bạn, trước tiên bạn sẽ cần `git`, 
có thể bạn đã có sẵn. Mở một trình Terminal và nhập `git` để kiểm tra. 
Nếu bạn không có `git`, bạn có thể tải xuống từ [git-scm.com](https://git-scm.com/).

Tiếp theo, sao chép kho lưu trữ này bằng cách mở một trình Terminal và nhập các lệnh sau 
(không nhập ký tự `$` đầu tiên trên mỗi dòng, đó chỉ là quy ước để cho thấy rằng đây là dấu nhắc của 
Terminal, không phải thử gì khác như mã lập trình Python):

    $ cd $HOME  # or any other development directory you prefer
    $ git clone https://github.com/mlbvn/handson-ml2-vn.git
    $ cd handson-ml2-vn

Nếu bạn không muốn cài đặt `git`, bạn có thể tài xuống tập tin [main.zip](https://github.com/mlbvn/handson-ml2-vn/archive/main.zip) này, 
giải nén nó, đổi tên thư mục đã giải nén thành `handson-ml2-vn` và chuyển nó vào thư mục lập trình riêng của bạn.

## Cài đặt Anaconda

Tiếp theo, bạn sẽ cần Python 3 và một loại các thư viện Python. 
Cách đơn giản nhất để cài đặt chúng là [tải xuống và cài đặt Anaconda](https://www.anaconda.com/distribution/), 
đây là một bản phân phối Python đa nền tảng tuyệt vời cho tính toán khoa học. 
Anaconda đi kèm với nhiều thư viện khác như: NumPy, Pandas, MatplotLib, Scikit-Learn và nhiều hơn thế; 
vì vậy nó là một bản cài đặt khá lớn. 
Nếu bạn thích bản phân phối Anaconda có dung lượng nhẹ hơn, bạn có thể 
[cài đặt Miniconda](https://docs.conda.io/en/latest/miniconda.html) ở mức tối thiểu để chạy công cụ đóng gói `conda`. 
Bạn nên cài đặt phiên bản mới nhất của Anaconda (hoặc Miniconda) có sẵn.

Trong quá trình cài đặt trên macOS và Linux, bạn sẽ được hỏi có nên khởi tạo Anaconda bằng cách chạy `conda init` hay không?
Bạn nên chấp nhận, vì nó sẽ cập nhật tập lệnh shell của bạn để đảm bảo rằng `conda` có sẵn bất cứ khi nào bạn mở một Terminal.
Sau khi cài đặt, bạn phải đóng Terminal và mở lại để các thay đổi có hiệu lực.

Trong quá trình cài đặt trên Windows, bạn sẽ được hỏi có muốn trình cài đặt cập nhật biến môi trường `PATH` hay không?
Điều này không được khuyến khích vì nó có thể ảnh hưởng đến phần mềm khác. Thay vào đó, sau khi cài đặt, bạn nên mở Start Menu 
và khởi chạy Anaconda Shell bất cứ khi nào bạn muốn sử dụng Anaconda.

Sau khi cài đặt Anaconda (hoặc Miniconda), hãy chạy lệnh sau để cập nhật công cụ đóng gói `conda` ở phiên bản mới nhất:

    $ conda update -n base -c defaults conda

> **Lưu ý**: Nếu bạn không thích Anaconda vì một lý do nào đó, bạn có thể cài đặt Python 3 và sử dụng `pip` để cài đặt 
> các thư viện cần thiết theo cách thủ công (điều này không được khuyến khích, trừ khi bạn thật sự biết mình đang làm gì). 
> Tôi khuyên bạn nên sử dụng Python 3.7, vì một số thư viện chưa hỗ trợ Python 3.8 hoặc Python 3.9.

## Cài đặt GPU Driver và Các thư viện

Nếu bạn có GPU card tương thích với Tensorflow (NVIDIA card với khả năng tính toán ≥ 3.5), và bạn muốn TensorFlow sử dụng nó, 
bạn nên tải xuống bản Driver mới nhất cho card của mình từ [nvidia.com](https://www.nvidia.com/Download/index.aspx?lang=en-us) và cài đặt nó.
Bạn cũng sẽ cần các thư viện gồm CUDA và cuDNN của NVIDIA, tin tốt là chúng sẽ được cài đặt tự động khi bạn cài đặt gói tensorflow-gpu từ Anaconda.
Tuy nhiên, nếu bạn không sử dụng Anaconda, bạn sẽ phải cài đặt chúng theo cách thủ công.
Nếu bạn gặp phải bất kỳ rào cản nào, hãy xem qua [hướng dẫn cài đặt GPU](https://tensorflow.org/install/gpu) của TensorFlow để biết thêm chi tiết.

## Tạo lập môi trường `tf2`

Tiếp theo, hãy đảm bảo rằng bạn đang ở trong thư mục `handson-ml2-vn` và chạy lệnh sau.
Nó sẽ tạo một môi trường `conda` mới nơi chưa mọi thư viện mà bạn sẽ cần để chạy tất cả các Jupyter Notebooks 
(mặc định, môi trường sẽ được đặt tên là `tf2`, nhưng bạn có thể chọn một tên khác bằng cách sử dụng tuỳ chọn `-n`):

    $ conda env create -f environment.yml

Sau đó, kích hoạt môi trường mới:

    $ conda activate tf2


## Khởi động Jupyter

Bạn chỉ cần đăng ký môi trường conda `tf2` cho Jupyter. Các Jupyter Notebooks trong dự án này mặc định sẽ là môi trường có tên là `python3`,
vì vậy tốt nhất bạn nên đăng ký môi trường này bằng tên `python3` 
(nếu bạn muốn sử dụng tên khác, bạn sẽ phải chọn nó ở bảng chọn trong Jupyter "Kernel > Change kernel..." mỗi khi bạn mở Jupyter Notebooks):

    $ python3 -m ipykernel install --user --name=python3

Bây giờ, bạn có thể khởi động Jupyter như sau:

    $ jupyter notebook

Thao tác này sẽ mở trình duyệt của bạn và bạn sẽ thấy chế độ xem dạng cây của Jupyter (tree view), với nội dung của thư mục hiện tại.
Nếu trình duyệt của bạn không tự động mở, hãy truy cập [localhost:8888](http://localhost:8888/tree).
Nhấp chọn `index.ipynb` để bắt đầu.

Xin chúc mừng! Bạn đã sẵn sàng để học về Máy Học, hãy cùng thực hành!

Khi bạn hoàn tất việc sử dụng Jupyter, bạn có thể đóng nó bằng cách nhấn tổ hợp phím `Ctrl-C` (đối với Windows) 
hoặc `Command-C` (đối với macOS) trong cửa sổ Terminal nơi bạn bắt đầu sử dụng.
Mỗi khi bạn muốn làm việc với dự này, bạn cần phải mở một Terminal ra và chạy những lệnh sau:

    $ cd $HOME # or whatever development directory you chose earlier
    $ cd handson-ml2-vn
    $ conda activate tf2
    $ jupyter notebook

## Cập nhật Dự án & Các thư viện của nó

Nhóm Dịch thuật Machine Learning cơ bản sẽ thường xuyên cập nhật những Jupyter Notebooks này theo tác giả nhằm khắc phục 
sự cố và thêm các hỗ trợ cần thiết cho những thư viện mới.
Vì vậy, hãy chắc chắn rằng bạn cập nhật dự án này thường xuyên.

Để làm việc này, bạn có thể mở Terminal và chạy:

    $ cd $HOME # or whatever development directory you chose earlier
    $ cd handson-ml2-vn # go to this project's directory
    $ git pull

Nếu bạn gặp lỗi, có thể là do bạn đã sửa đổi Jupyter Notebook. Trong trường hợp này, trước khi chạy `git pull`, bạn cần phải commit các thay đổi của mình.
Tôi khuyên bạn nên làm điều này trong branch của riêng bạn, nếu không bạn có thể nhận được các xung đột:

    $ git checkout -b my_branch # you can use another branch name if you want
    $ git add -u
    $ git commit -m "describe your changes here"
    $ git checkout master
    $ git pull

Tiếp theo, hãy cập nhật các thư viện. Đầu tiên là cập nhật chính `conda`:

    $ conda update -c defaults -n base conda

Sau đó, ta sẽ tiến hành xoá môi trường `tf2` của dự án này:

    $ conda activate base
    $ conda env remove -n tf2

Và tạo lại một môi trường mới:

    $ conda env create -f environment.yml

Cuối cùng, ta kích hoạt lại môi trường và khởi động Jupyter:

    $ conda activate tf2
    $ jupyter notebook
