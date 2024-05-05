---
title : "Catalog transformed data"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 6.1. </b> "
---
### Create a Glue Crawler
Do the same like lab [3.1. Create crawler](../../3-cataloging-data/3.1-create-crawler)
1. Go to the **AWS Glue Console**.
2. In the left navigation menu, click **Crawlers**.
3. On the Crawlers page, click **Create a crawler**. 
4. Specify `fcj-sw2-nyc-yellow-tripdata-parquet-crawler` as the crawler name, click **Next**.
5. On the Choose data sources and classifiers screen, specify the following information, and then click **Next**.
    * Click **Add a data source**
    * Choose a Data source – **S3**
    * Select Location of S3 data - **In this account**
    * Include S3 path – **s3://[your-bucket-name]-transformed/nyc-taxi/yellow-tripdata**
    * For Subsequent crawler runs, select to **Crawl all sub-folders**
    * Then click **Add an S3 data source**.
6. On Configure security settings, choose **AWSGlueServiceRole-SDL-Jumpstart** from the **Existing IAM role**, click **Next**.
7. On the **Set output and scheduling** section, click **Add database**.
8. Choose `nyctaxi_db` database created on the previous lab.
9. On the **Crawler schedule**, leave the frequency **On demand**, click **Next**.
10. Review the crawler details, click **Create crawler**.
11. On the **Crawlers** page, select `fcj-sw2-nyc-yellow-tripdata-parquet-crawler`, and then click **Run crawler**.
![Workshop](/images/6-enriching-data/create-crawler-for-tranformed-data.png)
