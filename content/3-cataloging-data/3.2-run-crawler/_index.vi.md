---
title : "Khởi chạy Glue Crawler"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
1. Tại trang **Crawlers**, chọn crawler  `fcj-w2-nyc-taxi-yellow-trips-csv-crawler`, sau đó bấm **Run crawler**.
![Workshop](/images/3-cataloging-data/run-crawler.png)

### Kiểm tra bảng trong Data Catalog
1. Tại trang **Database**, chọn database `nyctaxi_db`.
![Workshop](/images/3-cataloging-data/check-table-catalog.png)
2. Bạn có thể thấy có 1 bảng **raw_yellow_tripdata** đã được tạo bởi crawler.
![Workshop](/images/3-cataloging-data/check-table-catalog-01.png)