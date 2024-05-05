---
title : "Create a Glue Crawler"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---
{{% notice note %}}
**Glue Crawler** is a feature that automatically infer database and table schema from your source data then stores the associated metadata in the AWS Glue Data Catalog.
{{% /notice %}}

1. Go to the **AWS Glue Console**.
2. In the left navigation menu, click **Crawlers**.
3. On the Crawlers page, click **Create a crawler**. 
![Workshop](/images/3-cataloging-data/create-crawler.png)
4. Specify `fcj-sw2-nyc-taxi-yellow-trips-csv-crawler` as the crawler name, click **Next**.
![Workshop](/images/3-cataloging-data/create-crawler-02.png)
5. On the Choose data sources and classifiers screen, specify the following information, and then click **Next**.
    * Click **Add a data source**
    ![Workshop](/images/3-cataloging-data/create-crawler-03.png)
    * Choose a Data source – **S3**
    * Select Location of S3 data - **In this account**
    * Include S3 path – **s3://[your-bucket-name]-raw/nyc-taxi/yellow-tripdata**
    * For Subsequent crawler runs, select to **Crawl all sub-folders**
    * Then click **Add an S3 data source**.
  ![Workshop](/images/3-cataloging-data/create-crawler-04.png)
  ![Workshop](/images/3-cataloging-data/create-crawler-05.png)
6. On Configure security settings, choose **AWSGlueServiceRole-SDL-Jumpstart** from the **Existing IAM role**, click **Next**.
  ![Workshop](/images/3-cataloging-data/create-crawler-06.png)
7. On the **Set output and scheduling** section, click **Add database**.
8. Choose `nyctaxi_db` database created on the previous lab.
9. Specify `raw_` in the **Table name prefix - optional** field.
10. On the **Crawler schedule**, leave the frequency **On demand**, click **Next**.
  ![Workshop](/images/3-cataloging-data/create-crawler-07.png)
12. Review the crawler details, click **Create crawler**.
  ![Workshop](/images/3-cataloging-data/create-crawler-08.png)