---
title : "Run the Glue Crawler"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
### Run the Glue Crawler
1. On the **Crawlers** page, select `fcj-w2-nyc-taxi-yellow-trips-csv-crawler`, and then click **Run crawler**.
![Workshop](/images/3-cataloging-data/run-crawler.png)

### Check Table on Data Catalog
1. On the **Database** page, select `nyctaxi_db` database.
![Workshop](/images/3-cataloging-data/check-table-catalog.png)
2. You can see there are a table **raw_yellow_tripdata** created by crawler.
![Workshop](/images/3-cataloging-data/check-table-catalog-01.png)