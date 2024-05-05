---
title : "Validate transformed data"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 6.2. </b> "
---
1. Go to **Athena console**.
2. Select **Preview table** to examine the data in **yellow_tripdata** table.
3. On the **Query editor** page, run the following queries to examine the data
    {{% notice %}}
    -- total records
    -- 5646361
    SELECT COUNT(*) "Count"
    FROM   yellow_tripdata;
    {{% /notice %}}
    ![Workshop](/images/6-enriching-data/review-data-01.png)
    
    {{% notice %}}
    -- 2024-01-01  2824455
    -- 2024-02-01  2821904
    -- 2024-03-01  2
    SELECT DATE_TRUNC('month', pickup_datetime) "Period", 
        COUNT(*) "Total Records"
    FROM   yellow_tripdata
    GROUP BY DATE_TRUNC('month', pickup_datetime)
    ORDER BY 1;
    {{% /notice %}}
    ![Workshop](/images/6-enriching-data/review-data-02.png)