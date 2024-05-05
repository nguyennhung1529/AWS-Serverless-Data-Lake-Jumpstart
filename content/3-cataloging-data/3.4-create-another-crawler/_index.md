---
title : "Create another Glue Crawler"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 3.4. </b> "
---
### Create another Glue Crawler
**Repeat the same steps to "crawl" the taxi zone lookup data stored in S3**
1. Go to the **AWS Glue Console**.
2. In the left navigation menu, click **Crawlers**.
3. On the Crawlers page, click **Create a crawler**. 
4. Specify `fcj-sw2-nyc-taxi-zone-lookup-csv-crawler` as the crawler name, click **Next**.
5. On the Choose data sources and classifiers screen, specify the following information, and then click **Next**.
    * Click **Add a data source**
    * Choose a Data source – **S3**
    * Select Location of S3 data - **In this account**
    * Include S3 path – **s3://[your-bucket-name]-raw/nyc-taxi/taxi_zone_lookup**
    * For Subsequent crawler runs, select to **Crawl all sub-folders**
    * Then click **Add an S3 data source**.
6. On Configure security settings, choose **AWSGlueServiceRole-SDL-Jumpstart** from the **Existing IAM role**, click **Next**.
7. On the **Set output and scheduling** section, click **Add database**.
8. Choose `nyctaxi_db` database created on the previous lab.
9. Specify `raw_` in the **Table name prefix - optional** field.
10. On the **Crawler schedule**, leave the frequency **On demand**, click **Next**.
12. Review the crawler details, click **Create crawler**.
![Workshop](/images/3-cataloging-data/create-another-crawler.png)

### Run Glue Crawler
![Workshop](/images/3-cataloging-data/run-another-crawler.png)

### Review metadata and schema information of the table
![Workshop](/images/3-cataloging-data/view-another-table.png)
![Workshop](/images/3-cataloging-data/view-another-table-02.png)
