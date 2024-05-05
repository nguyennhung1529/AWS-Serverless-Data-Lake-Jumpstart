---
title : "Thêm nguồn dữ liệu khấc"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5.5. </b> "
---
### Thêm nguồn S3 cho dữ liệu Taxi Pickup Zone
Thực hiện các bước tương tự như [lab 5.2](../5.2-add-data-source/):
1. Click chọn **Source**, chọn **Amazon S3**.
2. Tại node **Data source – S3 bucket**, khai báo các thông tin sau trong tab **Data source properties**:
   * **Name** - `Pickup Zone Lookup`
   * **S3 source type** - **Data Catalog table**
   * **Database** – `nyctaxi_db`
   * **Table** – `raw_taxi_zone_lookup`
3. Vào tab **Data preview** để xem dữ liệu mẫu hiển thị.
![Workshop](/images/5-transforming-data/create-job-add-second-source.png)
4. Nhớ **save** lại job của bạn.

### Modify column names of Pickup Taxi Zone Lookup table
1. Đảm bảo bạn đang trỏ tới node **Amazon S3 - Pickup Zone Lookup**.
2. Click chọn **Transform**, chọn **Change Schema**.
![Workshop](/images/5-transforming-data/create-job-change-schema-second-source.png)
3. Khai báo các thông tin sau:
    * Name - `ApplyMapping - Pickup Zone Lookup`
    * Tại phần **Change Schema (Apply mapping)**:
      - `locationid` => `pu_location_id`
      - `borough` => `pu_borough`
      - `zone` => `pu_zone`
      - `service_zone` => `pu_service_zone`
    ![Workshop](/images/5-transforming-data/create-job-change-schema-second-source-02.png)
4. Nhớ **save** lại job của bạn.