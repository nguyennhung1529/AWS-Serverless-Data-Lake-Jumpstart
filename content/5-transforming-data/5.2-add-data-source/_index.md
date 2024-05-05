---
title : "Add a data source"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 5.2. </b> "
---
### Adding Yellow Trips data from Amazon S3
1. Click on the **Source** icon, choose **Amazon S3**.
![Workshop](/images/5-transforming-data/create-job-02.png)
2. In the **Data source – S3 bucket** node, the specify the following information in **Data source properties** tab:
   * **Name** - `Yellow Trip Data`
   * **S3 source type** - **Data Catalog table**
   * **Database** – `nyctaxi_db`
   * **Table** – `raw_yellow_tripdata`
3. Go to **Data preview** tab to check sample data set while editing your job.
4. Click **Save**. Remember to save your work as you progress on building the transformation steps.
![Workshop](/images/5-transforming-data/create-job-03.png)
