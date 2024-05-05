---
title : "Làm việc với dữ liệu CSV"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4.4. </b> "
---
{{% notice note %}}
**Làm việc với các tệp CSV** \
Các tệp CSV đôi khi có các dấu **"** bao xung quanh các giá trị dữ liệu kiểu chuỗi, và khi tiến hành phân tích dữ liệu, chúng ta cần loại bỏ các dấu **"** này. Để thực hiện điều đó, bạn có thể cập nhật thuộc tính bảng trong AWS Glue bằng cách sử dụng **OpenCSVSerDe**.
{{% /notice %}}

1. Truy cập **Glue console**.
2. Tại thanh công cụ điều hướng bên trái, click chọn **Tables** trong mục **Data Catalog**.
3. Chọn bảng **raw_taxi_zone_lookup**.
4. Click chọn **Actions**, sau đó chọn **Edit table**.
![Workshop](/images/4-exploring-data/edit-quota-csv-table.png)
5. Cập nhật **Serde serialization lib**: `org.apache.hadoop.hive.serde2.OpenCSVSerde`.
![Workshop](/images/4-exploring-data/edit-quota-csv-table-02.png)
6. Xóa bỏ **Serde parameters** mặc định, sau đó thêm các parameter sau:
   * Key: `escapeChar`, Value: `\`
   * Key: `quoteChar`, Value: `"`
   * Key: `separatorChar`, Value: `,`
   ![Workshop](/images/4-exploring-data/edit-quota-csv-table-03.png)
7. Click chọn **Save**.
8. Quay trở lại giao diện **Athena console**.
9. Tại trang **Query editor**, click vào icon **⋮** bên cạnh bảng **raw_taxi_zone_lookup**, và click **Preview table** để xem dữ liệu.
![Workshop](/images/4-exploring-data/edit-quota-csv-table-review.png)