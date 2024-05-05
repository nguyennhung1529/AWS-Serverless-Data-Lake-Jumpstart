---
title : "Transform data and save to target"
date :  "`r Sys.Date()`" 
weight : 8 
chapter : false
pre : " <b> 5.8. </b> "
---
### Modify column names and data types of the joined dataset
1. Click on the **Transform** icon, choose **ApplyMapping**.
2. Specify the following information:
	* Name - `ApplyMapping - Joined Data`
	* **Change Schema (Apply mapping)** section, modify the **Target key** and **Data type** of the following:
	  - `vendorid` => `vendor_id`
	  - `tpep_pickup_datetime` => `pickup_datetime`, `string` => `timestamp`
	  - `tpep_dropoff_datetime` => `dropoff_datetime`, `string` => `timestamp`
	* **Change Schema (Apply mapping)** section, **drop** the following Source keys:
	  - `pulocationid`
	  - `dolocationid`
    ![Workshop](/images/5-transforming-data/create-job-apply-joined-data.png)
3. Remember to **save** your work.

### Save transformed data to Amazon S3
1. Click on the **Target** icon, choose **Amazon S3**.
![Workshop](/images/5-transforming-data/create-job-add-target-source.png)
2. Specify the following information:
	* Name – `Transformed Yellow Trip Data`
	* Specify the following:
	  - Format – **Parquet**
	  - Compression Type - **Snappy**
	* S3 Target Location – **s3://[your-bucket-name]–transformed/nyc-taxi/yellow-tripdata/**
    ![Workshop](/images/5-transforming-data/create-job-add-target-source-02.png)
3. Remember to **save** your work.

And after all, you will have an ETL workflow like the image:
![Workshop](/images/5-transforming-data/create-job-workflow.png)
