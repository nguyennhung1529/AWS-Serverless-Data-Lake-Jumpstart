---
title : "Add and join another dataset"
date :  "`r Sys.Date()`" 
weight : 7 
chapter : false
pre : " <b> 5.7. </b> "
---
In this lab, we will add and join **Dropoff Taxo Zone Lookup** source into our current workflow.
![Workshop](/images/5-transforming-data/create-job-add-and-join-third-source.png)

### Add lookup table for Taxi Drop-off Zone
1. Click on the **Source** icon, choose **Amazon S3**.
2. In the **Data source – S3 bucket** node, the specify the following information in **Data source properties** tab:
    * Name - `Dropoff Zone Lookup`
    * Database – `nyctaxi_db`
    * Table – `raw_taxi_zone_lookup`
    ![Workshop](/images/5-transforming-data/create-job-add-third-source.png)
3. Remember to **save** your work.

### Modify column names of Drop-off Taxi Zone Lookup table
1. Make sure the **Amazon S3 - Dropoff Zone Lookup** node is selected.
2. Click on the **Transform** icon, choose **Change Schema**.
3. Specify the following information:
    * Name - `ApplyMapping - Dropoff Zone Lookup`
    * In **Change Schema (Apply mapping)** section:
      - `locationid` => `do_location_id`
      - `borough` => `do_borough`
      - `zone` => `do_zone`
      - `service_zone` => `do_service_zone`
    ![Workshop](/images/5-transforming-data/create-job-change-schema-third-source.png)
4. Remember to **save** your work.

### Join Yellow Trips data and Dropoff Taxi Zone Lookup data
1. Click on the **Transform** icon, choose **Join**.
2. Specify the following information:
    * Name - `Yellow Trips Data + Pickup Zone Lookup + Dropoff Zone Lookup`
    * Node Parents:
      - **ApplyMapping - Dropoff Zone Lookup**
      - **Yellow Trips Data + Pickup Zone Lookup**
    * Transform properties tab, under the **Join** conditions, select the following keys:
      - **ApplyMapping - Dropoff Zone Lookup** - `do_location_id`
      - **Yellow Trips Data + Pickup Zone Lookup** - `dolocationid`
    ![Workshop](/images/5-transforming-data/create-job-join-with-third-source.png)
3. Remember to **save** your work.