---
title : "Biến đổi dữ liệu"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---
### Overview
Làm giàu dữ liệu là quá trình nâng cao chất lượng dữ liệu hiện có bằng việc bổ sung dữ liệu từ các nguồn khác để cung cấp thêm ngữ cảnh hoặc ý nghĩa, làm cho dữ liệu trở nên có ý nghĩa và sâu sắc phục vụ cho việc phân tích dữ liệu.
![Workshop](/images/5-transforming-data/transforming-data.png)

### Giới thiệu về AWS Glue Studio
**AWS Glue Studio** là giao diện đồ họa giúp dễ dàng tạo, chạy và giám sát các công việc trích xuất, chuyển đổi và tải (ETL) trong AWS Glue. Bạn có thể xây dựng các quy trình ETL dữ liệu một cách trực quan, AWS Glue studio sẽ thay mặt bạn tạo mã Apache Spark và cho phép mã này chạy trên công cụ ETL serverless dựa trên Apache Spark của AWS Glue.

{{% notice note %}}
Tham khảo thêm: [Tổng hợp về Apache Spark và PySpark](https://docs.google.com/document/d/1rsWCHMeZWwzeVCyc3sQjZGQHK2J4EYsD/edit?usp=sharing&ouid=117097929676366412267&rtpof=true&sd=true)
{{% /notice %}}

### Nội dung
 5.1. [Tạo Glue job với Glue Studio](5.1-create-glue-studio-job/) \
 5.2. [Thêm nguồn dữ liệu](5.2-add-data-source/) \
 5.3. [Loại bỏ các bản ghi có giá trị NULL](5.3-remove-records-with-null/) \
 5.4. [Lọc bản ghi](5.4-filter-records/) \
 5.5. [Thêm nguồn dữ liệu khấc](5.5-add-another-data-source/) \
 5.6. [Join data](5.6-join-data-sources/) \
 5.7. [Thêm và join nguồn dữ liệu khác](5.7-add-and-join-third-data-source/) \
 5.8. [Biến đổi dữ liệu và lưu vào bảng đích](5.8-transform-and-save-to-target/) \
 5.9. [Chạy job](5.9-run-and-monitor-job/)