---
title : "Catalog của dữ liệu đã chuyển đổi"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 6.1. </b> "
---
### Create a Glue Crawler
Thực hiện tương tự lab [3.1. Create crawler](../../3-cataloging-data/3.1-create-crawler)
1. Truy cập **AWS Glue Console**.
2. Ở bên trái thanh menu, click **Crawlers**.
3. Tại trang Crawlers, click **Create a crawler**. 
4. Đặt tên cho crawler `fcj-sw2-nyc-yellow-tripdata-parquet-crawler`, click **Next**.
5. Tại mục **Choose data sources and classifiers**, cung cấp các thông tin sau và bấm **Next**.
    * Click **Add a data source**
    * Chọn Data source – **S3**
    * Chọn Location of S3 data - **In this account**
    * Tìm đến đường dẫn S3 nơi lưu dữ liệu của *yellow-tripdata* – **s3://[your-bucket-name]-transformed/nyc-taxi/yellow-tripdata**
    * Tại phần **Subsequent crawler**, chọn **Crawl all sub-folders**
    * Click **Add an S3 data source**.
6. Tại mục **Configure security**, phần **Existing IAM role**, chọn IAM role mà bạn đã tạo trước đấy - **AWSGlueServiceRole-SDL-Jumpstart**, click **Next**.
7. Tại mục **Set output and scheduling**, click **Add database**.
8. Chọn database `nyctaxi_db` mà bạn đã tạo ở lab trước.
9. **Crawler schedule** chọn **On demand**, click **Next**.
10. Kiểm tra lại toàn bộ thông tin của crawler, sau đó click **Create crawler**.
11. Tại trang **Crawlers**, chọn crawler `fcj-sw2-nyc-yellow-tripdata-parquet-crawler`, chọn **Run crawler**.
![Workshop](/images/6-enriching-data/create-crawler-for-tranformed-data.png)