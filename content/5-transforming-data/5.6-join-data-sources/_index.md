---
title : "Join data"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 5.6. </b> "
---
### Join the Yellow Trips data with Pickup Taxi Zone Lookup data
1. Click on the **Transform** icon, choose **Join**.
![Workshop](/images/5-transforming-data/create-job-join-with-second-source.png)
2. Specify the following information:
    * Name - `Yellow Trips Data + Pickup Zone Lookup`
    * Node Parents:
      - **ApplyMapping - Pickup Zone Lookup**
      - **Filter - Yellow Trip Data**
    * Transform properties tab, under the **Join** conditions, select the following keys:
      - **ApplyMapping - Pickup Zone Lookup** - `pu_location_id`
      - **Filter - Yellow Trip Data** - `pulocationid`
    ![Workshop](/images/5-transforming-data/create-job-join-with-second-source-02.png)
3. Remember to **save** your work.


