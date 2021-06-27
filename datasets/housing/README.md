# California Housing

## Nguồn dữ liệu
Bộ dữ liệu này là phiên bản sửa đổi từ Bộ dữ liệu California Housing có sẵn trên website của [Luís Torgo's](http://www.dcc.fc.up.pt/~ltorgo/Regression/cal_housing.html) (Đại học Porto). Luís Torgo đã thu được bộ dữ liệu này từ kho chứa StatLib (bây giờ không còn nữa). Bộ dữ liệu này chỉ có thể tải xuống từ bản sao lưu StatLib.

Bộ dữ liệu này xuất hiện trong một bài báo có tên là *Sparse Spatial Autoregressions* của Pace, R. Kelley và Ronald Barry; được xuất bản trên Tạp chí *Statistics and Probability Letters* năm 1997. Họ đã xây dựng nó bằng cách sử dụng bộ dữ liệu điều tra dân số California năm 1990. Nó chứa một hàng cho mỗi nhóm khối diều tra dân số. Nhóm khối là đơn vị địa lý nhỏ nhất mà Cục điều tra dân số Hoa công bố  trên dữ liệu mẫu (một nhóm khối thường có dân số từ 600 đến 3,000 người).

## Tinh chỉnh
Bộ dữ liệu trong thư mục này gần giống với bản gốc, với hai điểm khác biệt sau:

* 207 giá trị được xoá ngẫu nhiên khỏi cột `total_bedrooms`, điều này là để chúng ta có thể thảo luận về những việc cần làm với những dữ liệu bị thiếu.
* Một thuộc tính phân loại bổ sung gọi là `ocean_proximity` đã được thêm vào, biểu thị (một cách chung chung) về nhóm khối ở gần đại dương (ocean), gần khu vực Vịnh (Bay), trong nội địa (Inland) hoặc trên một hòn đảo (Island). Điều này cho phép ta thảo luận về những việc cần làm với các dữ liệu phân loại.

Lưu ý rằng các nhóm khối được gọi là "districts" (quận) ở trong Jupyter Notebooks, vì trong một số bối cảnh tên này có thể gây nhầm lẫn.

## Mô tả Dữ liệu

    >>> housing.info()
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 20640 entries, 0 to 20639
    Data columns (total 10 columns):
    longitude             20640 non-null float64
    latitude              20640 non-null float64
    housing_median_age    20640 non-null float64
    total_rooms           20640 non-null float64
    total_bedrooms        20433 non-null float64
    population            20640 non-null float64
    households            20640 non-null float64
    median_income         20640 non-null float64
    median_house_value    20640 non-null float64
    ocean_proximity       20640 non-null object
    dtypes: float64(9), object(1)
    memory usage: 1.6+ MB
    
    >>> housing["ocean_proximity"].value_counts()
    <1H OCEAN     9136
    INLAND        6551
    NEAR OCEAN    2658
    NEAR BAY      2290
    ISLAND           5
    Name: ocean_proximity, dtype: int64
    
    >>> housing.describe()
              longitude      latitude  housing_median_age   total_rooms  \
    count  16513.000000  16513.000000        16513.000000  16513.000000   
    mean    -119.575972     35.639693           28.652335   2622.347605   
    std        2.002048      2.138279           12.576306   2138.559393   
    min     -124.350000     32.540000            1.000000      6.000000   
    25%     -121.800000     33.940000           18.000000   1442.000000   
    50%     -118.510000     34.260000           29.000000   2119.000000   
    75%     -118.010000     37.720000           37.000000   3141.000000   
    max     -114.310000     41.950000           52.000000  39320.000000   

           total_bedrooms    population    households  median_income  
    count    16355.000000  16513.000000  16513.000000   16513.000000  
    mean       534.885112   1419.525465    496.975050       3.875651  
    std        412.716467   1115.715084    375.737945       1.905088  
    min          2.000000      3.000000      2.000000       0.499900  
    25%        295.000000    784.000000    278.000000       2.566800  
    50%        433.000000   1164.000000    408.000000       3.541400  
    75%        644.000000   1718.000000    602.000000       4.745000  
    max       6210.000000  35682.000000   5358.000000      15.000100
 
