---
title : "Add another data source"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5.5. </b> "
---
### Add lookup table for Taxi Pickup Zone
Do the same like lab [5.2](../5.2-add-data-source/):
1. Click on the **Source** icon, choose **Amazon S3**.
2. In the **Data source – S3 bucket** node, the specify the following information in **Data source properties** tab:
   * **Name** - `Pickup Zone Lookup`
   * **S3 source type** - **Data Catalog table**
   * **Database** – `nyctaxi_db`
   * **Table** – `raw_taxi_zone_lookup`
3. Go to **Data preview** tab to check sample data set while editing your job.
![Workshop](/images/5-transforming-data/create-job-add-second-source.png)
4. Remember to **save** your work.

### Modify column names of Pickup Taxi Zone Lookup table
1. Make sure the **Amazon S3 - Pickup Zone Lookup** node is selected.
2. Click on the **Transform** icon, choose **Change Schema**.
![Workshop](/images/5-transforming-data/create-job-change-schema-second-source.png)
3. Specify the following information:
    * Name - `ApplyMapping - Pickup Zone Lookup`
    * In **Change Schema (Apply mapping)** section:
      - `locationid` => `pu_location_id`
      - `borough` => `pu_borough`
      - `zone` => `pu_zone`
      - `service_zone` => `pu_service_zone`
    ![Workshop](/images/5-transforming-data/create-job-change-schema-second-source-02.png)
4. Remember to **save** your work.