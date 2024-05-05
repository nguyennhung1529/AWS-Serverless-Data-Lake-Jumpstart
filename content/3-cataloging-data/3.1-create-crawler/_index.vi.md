---
title : "Tạo Glue Crawler"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---
{{% notice note %}}
**Glue Crawler** là tính năng tự động khám phá schema table và database từ dữ liệu nguồn, sau đó lưu trữ siêu dữ liệu (metadata) trong AWS Glue Data Catalog.
{{% /notice %}}

1. Truy cập **AWS Glue Console**.
2. Ở bên trái thanh menu, click **Crawlers**.
3. Tại trang Crawlers, click **Create a crawler**. 
![Workshop](/images/3-cataloging-data/create-crawler.png)
4. Đặt tên cho crawler `fcj-sw2-nyc-taxi-yellow-trips-csv-crawler`, click **Next**.
![Workshop](/images/3-cataloging-data/create-crawler-02.png)
5. Tại mục **Choose data sources and classifiers**, cung cấp các thông tin sau và bấm **Next**.
    * Click **Add a data source**
    ![Workshop](/images/3-cataloging-data/create-crawler-03.png)
    * Chọn Data source – **S3**
    * Chọn Location of S3 data - **In this account**
    * Tìm đến đường dẫn S3 nơi lưu dữ liệu của *yellow-tripdata* – **s3://[your-bucket-name]-raw/nyc-taxi/yellow-tripdata**
    * Tại phần **Subsequent crawler**, chọn **Crawl all sub-folders**
    * Click **Add an S3 data source**.
  ![Workshop](/images/3-cataloging-data/create-crawler-04.png)
  ![Workshop](/images/3-cataloging-data/create-crawler-05.png)
6. Tại mục **Configure security**, phần **Existing IAM role**, chọn IAM role mà bạn đã tạo trước đấy - **AWSGlueServiceRole-SDL-Jumpstart**, click **Next**.
  ![Workshop](/images/3-cataloging-data/create-crawler-06.png)
7. Tại mục **Set output and scheduling**, click **Add database**.
8. Chọn database `nyctaxi_db` mà bạn đã tạo ở lab trước.
9. **Table name prefix - optional**, diền `raw_`.
10. **Crawler schedule** chọn **On demand**, click **Next**.
  ![Workshop](/images/3-cataloging-data/create-crawler-07.png)
12. Kiểm tra lại toàn bộ thông tin của crawler, sau đó click **Create crawler**.
  ![Workshop](/images/3-cataloging-data/create-crawler-08.png)