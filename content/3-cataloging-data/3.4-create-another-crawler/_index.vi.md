---
title : "Tạo Glue Crawler khác"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 3.4. </b> "
---
### Create another Glue Crawler
**Lặp lại các bước trên để "crawl" dữ liệu taxi zone lookup lưu trong S3**
1. Truy cập **AWS Glue Console**.
2. Ở bên trái thanh menu, click **Crawlers**.
3. Tại trang Crawlers, click **Create a crawler**. 
4. Đặt tên cho crawler `fcj-sw2-nyc-taxi-zone-lookup-csv-crawler`, click **Next**.
5. Tại mục **Choose data sources and classifiers**, cung cấp các thông tin sau và bấm **Next**.
    * Click **Add a data source**
    * Chọn Data source – **S3**
    * Chọn Location of S3 data - **In this account**
    * Tìm đến đường dẫn S3 nơi lưu dữ liệu của *taxi_zone_lookup* – **s3://[your-bucket-name]-raw/nyc-taxi/taxi_zone_lookup**
    * Tại phần **Subsequent crawler**, chọn **Crawl all sub-folders**
    * Click **Add an S3 data source**.
6. Tại mục **Configure security**, phần **Existing IAM role**, chọn IAM role mà bạn đã tạo trước đấy - **AWSGlueServiceRole-SDL-Jumpstart**, click **Next**.
7. Tại mục **Set output and scheduling**, click **Add database**.
8. Chọn database `nyctaxi_db` mà bạn đã tạo ở lab trước.
9. **Table name prefix - optional**, diền `raw_`.
10. **Crawler schedule** chọn **On demand**, click **Next**.
12. Kiểm tra lại toàn bộ thông tin của crawler, sau đó click **Create crawler**.
![Workshop](/images/3-cataloging-data/create-another-crawler.png)

### Chạy Glue Crawler
![Workshop](/images/3-cataloging-data/run-another-crawler.png)

### Xem thông tin metadata và schema của bảng **taxi_zone_lookup**
![Workshop](/images/3-cataloging-data/view-another-table.png)
![Workshop](/images/3-cataloging-data/view-another-table-02.png)
