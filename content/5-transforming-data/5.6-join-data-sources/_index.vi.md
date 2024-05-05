---
title : "Join data"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 5.6. </b> "
---
### Kết hợp dữ liệu Yellow Trips data (chuyến đi) với Pickup Taxi Zone Lookup data (địa điểm đón khách)
1. Chọn **Transform**, chọn **Join**.
![Workshop](/images/5-transforming-data/create-job-join-with-second-source.png)
2. Khai báo các thông tin sau:
    * Name - `Yellow Trips Data + Pickup Zone Lookup`
    * Node Parents:
      - **ApplyMapping - Pickup Zone Lookup**
      - **Filter - Yellow Trip Data**
    * Join Type: **Inner join**
    * **Join conditions**:
      - **ApplyMapping - Pickup Zone Lookup** - `pu_location_id`
      - **Filter - Yellow Trip Data** - `pulocationid`
    ![Workshop](/images/5-transforming-data/create-job-join-with-second-source-02.png)
3. Nhớ **save** lại job của bạn.