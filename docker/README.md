# Thực hành Học Máy với Docker (Đang thực hiện)

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

### Chuẩn bị Ảnh

Tùy chọn đầu tiên là kéo Ảnh (image) từ Docker Hub (có thể tải xuống khoảng 1.9 GB dữ liệu nén):

```bash
$ docker pull mlbvn/handson-ml2-vn-vn
```

**Lưu ý**: Ảnh này chỉ dành cho CPU. Để chạy được với GPU, vui lòng đọc hướng dẫn ở phía dưới.

Ngoài ra, bạn có thể tự xây dựng một Ảnh riêng cho mình. Điều này có thể chậm hơn, nhưng nó sẽ
đảm bảo Ảnh được cập nhật với các thư viện mới nhất. Đối với điều này, giả sử bạn đã tải xuống
dự án này vào thư mục `/path/to/project/handson-ml2-vn`:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ docker-compose build
```

Việc này có thể mất khá nhiều thời gian, nhưng chỉ yêu cầu một lần.

Sau khi quá trình này hoàn tất, bạn sẽ có một Ảnh `mlbvn/handson-ml2-vn-vn:latest`, đó sẽ là
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
trước khi tạo Ảnh) và bạn đã sẵn sàng để thực hành với mã nguồn của cuốn sách.

Máy chủ chạy trong thư mục chứa Notebook và những thay đổi bạn thực hiện từ trình duyệt sẽ
vẫn tồn tại ở đó.

Bạn có thể đóng máy chủ bằng cách nhấn tổ hợp phím `Ctrl–C` (đối với Windows) hoặc `Command–C` (đối với macOS)
trong cửa sổ dòng lệnh (Terminal).

### Sử dụng `make` (Tùy chọn)

Nếu bạn đã cài đặt `make` trên máy tính của mình, bạn có thể sử dụng nó như một tầng mỏng để chạy
lệnh `docker-compose`. Ví dụ, việc thực thi lệnh `make rebuild` sẽ chạy `docker-compose build --no-cache`,
sẽ xây dựng lại Ảnh mà khkông cần sử dụng bộ nhớ cache. Điều này đảm bảo rằng Ảnh của bạn dựa trên
phiên bản mới nhất của Ảnh `continuumio/miniconda3`, và Ảnh `mlbvn/handson-ml2-vn-vn` này được dựa trên nó.

Nếu bạn không có `make` (và bạn không muốn cài đặt nó), bạn chỉ cần kiểm tra nội dung của tệp tin `Makefile`
để xem bạn có thể chạy lệnh `docker-compose` để thay thế không.

### Chạy các lệnh bổ sung trên Container

Run `make exec` (or `docker-compose exec handson-ml2-vn bash`) while the server is running to run an additional `bash` shell inside the `handson-ml2-vn` container. Now you're inside the environment prepared within the image.

One of the useful things that can be done there would be starting TensorBoard (for example with simple `tb` command, see bashrc file).

Another one may be comparing versions of the notebooks using the `nbdiff` command if you haven't got `nbdime` installed locally (it is **way** better than plain `diff` for notebooks). See [Tools for diffing and merging of Jupyter notebooks](https://github.com/jupyter/nbdime) for more details.

You can see changes you made relative to the version in git using `git diff` which is integrated with `nbdiff`.

You may also try `nbd NOTEBOOK_NAME.ipynb` command (custom, see bashrc file) to compare one of your notebooks with its `checkpointed` version.<br/>
To be precise, the output will tell you *what modifications should be re-played on the **manually saved** version of the notebook (located in `.ipynb_checkpoints` subdirectory) to update it to the **current** i.e. **auto-saved** version (given as command's argument - located in working directory)*.

## Hỗ trợ GPU trên Linux (Thử nghiệm)

### Kiến thức Cần có

If you're running on Linux, and you have a TensorFlow-compatible GPU card (NVidia card with Compute Capability ≥ 3.5) that you would like TensorFlow to use inside the Docker container, then you should download and install the latest driver for your card from [nvidia.com](https://www.nvidia.com/Download/index.aspx?lang=en-us). You will also need to install [NVidia Docker support](https://github.com/NVIDIA/nvidia-docker): if you are using Docker 19.03 or above, you must install the `nvidia-container-toolkit` package, and for earlier versions, you must install `nvidia-docker2`.

Next, edit the `docker-compose.yml` file:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ edit docker-compose.yml  # use your favorite editor
```

* Replace `dockerfile: ./docker/Dockerfile` with `dockerfile: ./docker/Dockerfile.gpu`
* Replace `image: mlbvn/handson-ml2-vn-vn:latest` with `image: mlbvn/handson-ml2-vn-vn:latest-gpu`
* If you want to use `docker-compose`, you will need version 1.28 or above for GPU support, and you must uncomment the whole `deploy` section in `docker-compose.yml`. 

### Chuẩn bị Ảnh

If you want to pull the prebuilt image from Docker Hub (this will download over 3.5 GB of compressed data):

```bash
$ docker pull mlbvn/handson-ml2-vn-vn:latest-gpu
```

If you prefer to build the image yourself:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ docker-compose build
```

### Run the notebooks with `docker-compose` (version 1.28 or above)

If you have `docker-compose` version 1.28 or above, that's great! You can simply run:

```bash
$ cd /path/to/project/handson-ml2-vn/docker
$ docker-compose up
[...]
     or http://127.0.0.1:8888/?token=[...]
```

Then point your browser to the URL and Jupyter should appear. If you then open or create a notebook and execute the following code, a list containing your GPU device(s) should be displayed (success!):

```python
import tensorflow as tf

tf.config.list_physical_devices("GPU")
```

To stop the server, just press Ctrl-C.

### Run the notebooks without `docker-compose`

If you have a version of `docker-compose` earlier than 1.28, you will have to use `docker run` directly.

If you are using Docker 19.03 or above, you can run:

```bash
$ cd /path/to/project/handson-ml2-vn
$ docker run --name handson-ml2-vn --gpus all -p 8888:8888 -p 6006:6006 --log-opt mode=non-blocking --log-opt max-buffer-size=50m -v `pwd`:/home/devel/handson-ml2-vn mlbvn/handson-ml2-vn-vn:latest-gpu /opt/conda/envs/tf2/bin/jupyter notebook --ip='0.0.0.0' --port=8888 --no-browser
```

If you are using an older version of Docker, then replace `--gpus all` with `--runtime=nvidia`.

Now point your browser to the displayed URL: Jupyter should appear, and you can open a notebook and run `import tensorflow as tf` and `tf.config.list_physical_devices("GPU)` as above to confirm that TensorFlow does indeed see your GPU device(s).

Lastly, to interrupt the server, press Ctrl-C, then run:

```bash
$ docker rm handson-ml2-vn
```

This will remove the container so you can start a new one later (but it will not remove the image or the notebooks, don't worry!).

Have fun!
