---
title : "Kiểm tra metadata trong Glue Data Catalog"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3.3. </b> "
---
{{% notice note %}}
**Glue Data Catalog** chứa các tham chiếu đến dữ liệu nguồn và đích phục vụ cung cấp dữ liệu cho các hoạt động/tác vụ trích xuất, chuyển đổi và tải (ETL) trong AWS Glue. Nó cũng cung cấp một nơi quan sát chung về dữ liệu và cho phép nhiều dịch vụ AWS khác nhau như Athena, EMR và Redshift Spectrum truy cập dữ liệu đó.
{{% /notice %}}

1. Trong menu điều hướng bên trái, click **Tables**.
2. Tại trang **Tables**, click chọn bảng **raw_yellow_tripdata** để xem lại metadata và schema của bảng.
![Workshop](/images/3-cataloging-data/view-catalog.png)