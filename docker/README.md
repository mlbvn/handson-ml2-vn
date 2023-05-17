# Thực hành Học Máy với Docker

Đây là cấu hình Docker cho phép bạn chạy và chỉnh sửa các Notebook của cuốn sách này mà
không cần phải cài đặt bất kỳ các gói dữ liệu phụ thuộc (dependencies) nào vào thiết bị của bạn.

Ngoại trừ `docker`, `docker-compose`, có thể thêm `make`, và một số thành phần khác nếu bạn
muốn hỗ trợ GPU (chi tiết xem ở bên dưới).

## Kiến thức Cần có

Hãy làm theo hướng dẫn để [Cài đặt Docker](https://docs.docker.com/engine/installation/) 
và [Docker Compose](https://docs.docker.com/compose/install/) cho môi trường trên thiết bị của 
bạn nếu bạn đang không có sẵn `docker` và `docker-compose`.

Nếu bạn có thể trang bị một số kiến thức chung về hệ thống `docker` có thể sẽ hữu ích 
(riêng nó đã là một chủ đề thú vị) nhưng không hoàn toàn **bắt buộc** chỉ để chạy những Notebook.

## Sử dụng

### Chuẩn bị Image

Tùy chọn đầu tiên là kéo Image từ Docker Hub (có thể tải xuống khoảng 1.9 GB dữ liệu nén):

```bash
$ docker pull mlbvn/handson-ml2-vn-vn
```

**Lưu ý**: Image này chỉ dành cho CPU. Để chạy được với GPU, vui lòng đọc hướng dẫn ở phía dưới.

Ngoài ra, bạn có thể tự xây dựng một Image riêng cho mình. Điều này có thể chậm hơn, nhưng nó sẽ
đảm bảo Image được cập nhật với các thư viện mới nhất. Đối với điều này, giả sử bạn đã tải xuống
dự án này vào thư mục `/path/to/project/handson-ml2-vn`:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ docker-compose build
```

Việc này có thể mất khá nhiều thời gian, nhưng chỉ yêu cầu một lần.

Sau khi quá trình này hoàn tất, bạn sẽ có một Image `mlbvn/handson-ml2-vn-vn:latest`, đó sẽ là
cơ sở cho các thử nghiệm của bạn. Bạn có thể xác nhận điều này bằng cách chạy lệnh sau:

```bash
$ docker images
REPOSITORY                    TAG          IMAGE ID              CREATED         SIZE
mlbvn/handson-ml2-vn-vn    latest      3ebafebc604a        2 minutes ago       4.87GB
```

### Chạy các Notebook

Vẫn giả sử bạn đã tải kho chứa này theo thư mục `/path/to/project/handson-ml2-vn`, hãy chạy các
lệnh sau để khởi động lại máy chủ Jupyter bên trong Container, có tên là `handson-ml2-vn`:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ docker-compose up
```

Tiếp theo, cần trỏ trình duyệt của bạn đến URL được hiển thị trên màn hình (hoặc truy cập 
<http://localhost:8888> nếu bạn đã bật xác thực mật khẩu bên trong tệp tin `jupyter_notebook_config.py`,
trước khi tạo Image) và bạn đã sẵn sàng để thực hành với mã nguồn của cuốn sách.

Máy chủ chạy trong thư mục chứa Notebook và những thay đổi bạn thực hiện từ trình duyệt sẽ
vẫn tồn tại ở đó.

Bạn có thể đóng máy chủ bằng cách nhấn tổ hợp phím `Ctrl–C` (đối với Windows) hoặc `Command–C` (đối với macOS)
trong cửa sổ dòng lệnh (Terminal).

### Sử dụng `make` (Tùy chọn)

Nếu bạn đã cài đặt `make` trên máy tính của mình, bạn có thể sử dụng nó như một tầng mỏng để chạy
lệnh `docker-compose`. Ví dụ, việc thực thi lệnh `make rebuild` sẽ chạy `docker-compose build --no-cache`,
sẽ xây dựng lại Image mà khkông cần sử dụng bộ nhớ cache. Điều này đảm bảo rằng Image của bạn dựa trên
phiên bản mới nhất của Image `continuumio/miniconda3`, và Image `mlbvn/handson-ml2-vn-vn` này được dựa trên nó.

Nếu bạn không có `make` (và bạn không muốn cài đặt nó), bạn chỉ cần kiểm tra nội dung của tệp tin `Makefile`
để xem bạn có thể chạy lệnh `docker-compose` để thay thế không.

### Chạy các lệnh bổ sung trên Container

Chạy lệnh `make exec` (hoặc `docker-compose exec handson-ml2-vn bash`) trong khi máy chủ đang chạy để chạy thêm một 
`bash` shell bên trong Container `handson-ml2-vn`. Bây giờ bạn đã ở trong môi trường được chuẩn bị trong Image.

Một trong những điều hữu ích có thể là bắt đầu với TensorBoard (ví dụ với lệnh `tb` đơn giản, xem tập tin bashrc).

Một cách khác có thể so sánh các phiên bản của các Notebook bằng cách sử dụng lệnh `nbdiff` nếu bạn chưa cài đặt 
`nbdime` cục bộ (nó **tốt hơn** so với `diff` thông thường cho các Notebook). Xem 
[Công cụ Diff & Merg cho Jupyter Notebook](https://github.com/jupyter/nbdime) để biết thêm chi tiết.

Bạn có thể thấy các thay đổi bạn đã thực hiện so với phiên bản trong git bằng cách sử dụng `git diff` được tích hợp với `nbdiff`.

Bạn cũng có thể thử lệnh `nbd NOTEBOOK_NAME.ipynb` (tùy chỉnh, xem tập tin bashrc) để so sánh một trong các Notebook của bạn 
với phiên bản `checkpointed` của nó.<br/>

Một cách chính xác thì đầu ra sẽ cho bạn biết *những thay đổi nào cần được phát lại trên phiên bản **được lưu thủ công** của 
Notebook (nằm trong thư mục con `.ipynb_checkpoints`) để cập nhật nó thành phiên bản **hiện tại** tức là phiên bản **được lưu 
tự động** (được đưa ra như đối số của lệnh - nằm trong thư mục làm việc)*.

## Hỗ trợ GPU trên Linux (Thử nghiệm)

### Kiến thức Cần có

Nếu bạn đang chạy trên Linux, và bạn có một card GPU tương thích với TensorFlow (card NVidia với khả năng tính toán ≥ 3.5) 
mà bạn muốn TensorFlow sử dụng bên trong Container Docker, thì bạn nên tải xuống và cài đặt phiên bản mới nhất cho card của 
bạn từ [nvidia.com](https://www.nvidia.com/Download/index.aspx?lang=en-us). Bạn cũng sẽ cần cài đặt 
[Hỗ trợ Docker từ NVidia](https://github.com/NVIDIA/nvidia-docker): nếu bạn đang sử dụng Docker 19.03 hoặc cao hơn, bạn phải 
cài đặt gói `nvidia-container-toolkit`, và đối với các phiên bản trước đó, bạn phải cài đặt `nvidia-docker2`.

Tiếp theo, chỉnh sửa tập tin `docker-compose.yml`:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ edit docker-compose.yml  # use your favorite editor
```

* Thay thế `dockerfile: ./docker/Dockerfile` bằng `dockerfile: ./docker/Dockerfile.gpu`
* Thay thế `image: mlbvn/handson-ml2-vn-vn:latest` bằng `image: mlbvn/handson-ml2-vn-vn:latest-gpu`
* Nếu bạn muốn sử dụng `docker-compose`, bạn sẽ cần phiên bản 1.28 trở lên để hỗ trợ GPU, và bạn phải bỏ dấu chú thích cho toàn bộ phần `deploy` trong `docker-compose.yml`.

### Chuẩn bị Image

Nếu bạn muốn kéo Image đã được tạo dựng trước đó từ Docker Hub (nó sẽ tải xuống hơn 3,5 GB dữ liệu nén):

```bash
$ docker pull mlbvn/handson-ml2-vn-vn:latest-gpu
```

Nếu bạn muốn tự mình làm một bản dựng Image khác thì:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ docker-compose build
```

### Chạy các notebooks với `docker-compose` (phiên bản 1.28 hoặc cao hơn)

Nếu bạn có phiên bản `docker-compose` 1.28 hoặc cao hơn, thì tuyệt vời! Bạn có thể đơn giản chạy:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ docker-compose up
[...]
     or http://127.0.0.1:8888/?token=[...]
```

Sau đó, hãy trỏ trình duyệt của bạn đến URL và Jupyter sẽ xuất hiện. Nếu sau đó bạn mở hoặc tạo một 
notebook và thực thi mã sau, một danh sách chứa thiết bị GPU của bạn sẽ được hiển thị (thành công!):

```python
import tensorflow as tf

tf.config.list_physical_devices("GPU")
```

Để dừng server, chỉ cần nhấn Ctrl-C.

### Chạy các notebooks mà không cần `docker-compose`

Nếu bạn có phiên bản `docker-compose` trước 1.28, bạn sẽ phải sử dụng `docker run` trực tiếp.

Nếu bạn đang sử dụng Docker 19.03 hoặc cao hơn, bạn có thể chạy:

```bash
$ cd /path/to/project/handson-ml2-vn
$ docker run --name handson-ml2-vn --gpus all -p 8888:8888 -p 6006:6006 --log-opt mode=non-blocking --log-opt max-buffer-size=50m -v `pwd`:/home/devel/handson-ml2-vn mlbvn/handson-ml2-vn-vn:latest-gpu /opt/conda/envs/tf2/bin/jupyter notebook --ip='0.0.0.0' --port=8888 --no-browser
```

Nếu bạn đang sử dụng phiên bản cũ hơn của Docker, thì hãy thay thế `--gpus all` bằng `--runtime=nvidia`.

Bây giờ hãy trỏ trình duyệt của bạn đến URL và Jupyter sẽ xuất hiện, và bạn có thể mở một notebook và chạy 
`import tensorflow as tf` và `tf.config.list_physical_devices("GPU)` như trên để xác nhận rằng TensorFlow 
thật sự nhìn thấy thiết bị GPU của bạn.

Cuối cùng, để ngắt máy chủ, nhấn Ctrl-C, sau đó chạy:

```bash
$ docker rm handson-ml2-vn
```

Thao tác này sẽ xóa Container để bạn có thể bắt đầu một Container mới sau này 
(nhưng nó sẽ không xóa Image hoặc các Notebook, đừng lo lắng!).
