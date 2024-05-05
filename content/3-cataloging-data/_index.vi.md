---
title : "Lập danh mục (catalog) dữ liệu"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---
### Tổng quan
Như vậy bạn đã có một datalake với dữ liệu đa định dạng lấy từ nhiều nguồn khác nhau, điều quan trọng bây giờ, là bạn cần có khả năng khám phá và danh mục hóa dữ liệu để có thể hiểu rõ hơn về dữ liệu bạn đang có, đồng thời cho phép tích hợp với các dịch vụ phân tích dữ liệu AWS phục vụ cho các mục đích sử dụng khác nhau. \
\
Trong lab này, bạn sẽ tạo **AWS Glue Crawlers** để tự động khám phá schema của các file dữ liệu được lưu trữ trong Amazon S3. Thông tin lược đồ (schema) dữ liệu được phát hiện sẽ được đăng ký/khai báo trong **AWS Glue Catalog**. Điều này cho phép AWS Glue sử dụng thông tin được lưu trữ trong catalog để thực hiện ETL dữ liệu. Ngoài ra, AWS Glue cũng cho phép các dịch vụ AWS khác như Amazon Athena chạy các câu lệnh truy vấn trên dữ liệu lưu trữ trong Amazon S3.
![Workshop](/images/3-cataloging-data/cataloging-data.png)

### Nội dung
 3.1. [Tạo Glue Crawler](3.1-create-crawler/) \
 3.2. [Khởi chạy Glue Crawler](3.2-run-crawler/) \
 3.3. [Kiểm tra metadata trong Glue Data Catalog](3.3-review-metadata/) \
 3.4. [Tạo Glue Crawler khác](3.4-create-another-crawler/)