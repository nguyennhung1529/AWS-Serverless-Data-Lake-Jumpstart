---
title : "Lọc bản ghi"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 5.4. </b> "
---
### Chuyển kiểu dữ liệu timestamp về string
{{% notice note %}}
Bạn cần đổi kiểu dữ liệu dạng timestamp thành string phục vụ cho việc filter ở bước sau.
{{% /notice %}}

1. Chọn **Transform**, chọn **Format Timestamp**.
![Workshop](/images/5-transforming-data/create-job-format-timestamp-01.png)
2. Khai báo các thông tin sau:
    * Name - `Format pickup_datetime`
    * Node parents - chọn node **Select From Collection**
    * Column with the timestamp - **tpep_pickup_datetime**
    * Timestamp format - `%Y-%m-%d %H:%M:%S`
    * Review dữ liệu tại tab **Data preview**
    ![Workshop](/images/5-transforming-data/create-job-format-timestamp-02.png)

### Lọc bản ghi
1. Chọn **Transform**, chọn **Filter**.
![Workshop](/images/5-transforming-data/create-job-filter-records-01.png)
2. Khai báo các thông tin sau:
    * Name - `Filter - Yellow Trip Data`
    * Filter condition – `tpep_pickup_datetime` `matches` `^2020-1`
    * Review dữ liệu tại tab **Data preview**
    ![Workshop](/images/5-transforming-data/create-job-filter-records-02.png)
3. Nhớ **save** lại job của bạn.

### Review script được sinh tự động
1. Truy cập tab **Script**.
2. Bạn có thể thấy đoạn scripts được sinh tự động dựa trên flow kéo thả nhờ Glue Studio.
![Workshop](/images/5-transforming-data/create-job-view-script.png)