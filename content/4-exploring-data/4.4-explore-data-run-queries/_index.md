---
title : "Run SQL queries to explore the data"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 4.5. </b> "
---
1. Check number of yellow taxi trip records.
    {{% notice %}}
    -- total records = 5972150
    SELECT COUNT(*) "Count" FROM raw_yellow_tripdata;
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-01.png)

2. Explore data categories.
    {{% notice %}}
    -- observe vendorid categories
    SELECT vendorid, COUNT(*) "Count"
    FROM  raw_yellow_tripdata
    GROUP BY vendorid
    ORDER BY 1;
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-02.png)

    {{% notice %}}
    -- observe pulocationid categories
    SELECT pulocationid, COUNT(*) "Count"
    FROM   raw_yellow_tripdata
    GROUP BY pulocationid
    ORDER BY 1;
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-02-2.png)

    {{% notice %}}
    -- observe payment_type categories
    SELECT payment_type, COUNT(*) "Count"
    FROM   raw_yellow_tripdata
    GROUP BY payment_type
    ORDER BY 1;
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-02-3.png)

3. Explore records with NULL Vendor ID.
    {{% notice %}}
    -- observe other columns with NULL values
    -- passenger_count, ratecodeid, store_and_fwd_flag, payment_type
    SELECT * 
    FROM   raw_yellow_tripdata
    WHERE  vendorid IS NULL
    LIMIT 100;
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-03.png)
    
4. Explore records by time period.
    {{% notice %}}
    -- tpep_pickup_datetime is defined as STRING
    -- observe record counts that falls outside of the time period 
    SELECT format_datetime(tpep_pickup_datetime, 'dd/MM/yyyy') "Period", COUNT(*) "Total Records"
    FROM   raw_yellow_tripdata
    GROUP BY format_datetime(tpep_pickup_datetime, 'dd/MM/yyyy')
    ORDER BY 1;
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-04.png)
    
5. Count records that falls outside of year 2024.
    {{% notice %}}
    -- records with incorrect pickup datetime values
    -- 17
    SELECT COUNT(*) "Count"
    FROM   raw_yellow_tripdata 
    WHERE  format_datetime(tpep_pickup_datetime, 'yyyy') <> '2024';
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-05.png)
    
6. Count records with NULL values (based on Vendor ID) that falls within 2024.
    {{% notice %}}
    -- Records with NULL categories like Vendor ID
    -- 0
    SELECT COUNT(*) "Count"
    FROM   raw_yellow_tripdata
    WHERE  vendorid IS NULL
    AND    format_datetime(tpep_pickup_datetime, 'yyyy') = '2024';
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-06.png)
    
7. Count records that falls in the last quarter of 2020, exclude records with missing Vendor ID.
    {{% notice %}}
    -- Total records in BER months, excluding columns with missing Vendor ID
    -- 995220
    SELECT COUNT(*) "Count"
    FROM   raw_yellow_tripdata
    WHERE  vendorid IS NOT NULL
    AND    format_datetime(tpep_pickup_datetime, 'yyyy-mm') LIKE '2024-1%';
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-07.png)
    
8. Join taxi trips data with taxi zone look up table.
    {{% notice %}}
    -- explore data with lookup information
    -- observe column names from lookup tables
    SELECT td.*, pu.*, do.*
    FROM   raw_yellow_tripdata td
    JOIN   raw_taxi_zone_lookup pu ON td.pulocationid = pu.locationid
    JOIN   raw_taxi_zone_lookup do ON td.pulocationid = do.locationid
    WHERE  vendorid IS NOT NULL AND
        format_datetime(tpep_pickup_datetime, 'yyyy-mm') LIKE '2024-1%'
    LIMIT 100;
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-08.png)
    
    {{% notice %}}
    -- Count total joined records for the last quarter of 2024.
    -- 995220
    SELECT COUNT(*) "Count"
    FROM   raw_yellow_tripdata td
    JOIN   raw_taxi_zone_lookup pu ON td.pulocationid = pu.locationid
    JOIN   raw_taxi_zone_lookup do ON td.pulocationid = do.locationid
    WHERE  vendorid IS NOT NULL AND
        format_datetime(tpep_pickup_datetime, 'yyyy-mm') LIKE '2024-1%';
    {{% /notice %}}
    ![Workshop](/images/4-exploring-data/explore-data-08-2.png)
