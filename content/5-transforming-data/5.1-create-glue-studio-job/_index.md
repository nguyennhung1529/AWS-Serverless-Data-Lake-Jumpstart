---
title : "Create a job using Glue Studio"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---
### Planning the Data Transformation Steps
It’s a good practice to plan the steps to transform your data. Based on the information we captured during data exploration stage, we can come up with the following transformation step:
1. Read yellow trip data from S3, `raw_yellow_tripdata` table.
2. Clean yellow trip data data.
	* Remove records with NULL values (vendorid, payment_type, passenger count, ratecodeid).
	* Filter records within a time period (remove records with invalid pickup datetime, narrow down data to be processed).
3. Join yellow trip data with taxi zone lookup to obtain pickup location information.
	* Read lookup data from S3, `raw_taxi_zone_lookup` table.
	* Rename column names of lookup data to differentiate pickup locations from drop-off locations.
	* Perform the join.
4. Join yellow trip data with taxi zone lookup to obtain drop-off location information.
	* Read lookup data from S3, `raw_taxi_zone_lookup` table.
	* Rename column names of lookup data to differentiate drop-off locations from pickup locations.
	* Perform the join.
5. Perform data transformation on joined dataset.
	* Rename column names.
	* Set appropriate data types.
	* Remove redundant columns as a result of table joins.
6. Save processed dataset to S3 in a query optimized format.

### Create a job using Glue Studio
1. Go to **Glue console**.
![Workshop](/images/5-transforming-data/aws-glue.png)
2. In the left navigation menu, under the **Data Intergration and ETL** section, click **ETL jobs** to go to **AWS Glue Studio** page.
![Workshop](/images/5-transforming-data/aws-glue-studio.png)
3. On the **AWS Glue Studio** page, choose **Visual ETL**
![Workshop](/images/5-transforming-data/create-job-01.png)
4. In the **Glue Studio editor** page, go to the **Job details** tab, set the following configuration:
	* Name – `transform-nyc-taxi-trip-data`
	* IAM Role – `AWSGlueServiceRole-SDL-Jumpstart`
    ![Workshop](/images/5-transforming-data/create-job-config-job-01.png)
	* Job bookmark – **Disable**
	* Number of retries – **0**
    ![Workshop](/images/5-transforming-data/create-job-config-job-02.png)
{{% notice note %}}
**AWS Glue job bookmark** feature helps maintain state information and prevent the reprocessing of old data. It enables the job to process only new data when rerunning on a scheduled interval.
{{% /notice %}}
5. Click **Save**. Go back to the **Visual** tab.

