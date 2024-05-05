---
title : "Thêm và join nguồn dữ liệu khác"
date :  "`r Sys.Date()`" 
weight : 7 
chapter : false
pre : " <b> 5.7. </b> "
---
Trong lab này, bạn sẽ add thêm bảng nguồn **Dropoff Taxo Zone Lookup** và join với dữ liệu kết hợp trong luồng hiện có.
![Workshop](/images/5-transforming-data/create-job-add-and-join-third-source.png)

### Thêm nguồn cho bảng Taxi Drop-off Zone Lookup
1. Click chọn **Source**, chọn **Amazon S3**.
2. Tại node **Data source – S3 bucket**, khai báo các thông tin sau trong tab **Data source properties**:
   * **Name** - `Dropoff Zone Lookup`
   * **S3 source type** - **Data Catalog table**
   * **Database** – `nyctaxi_db`
   * **Table** – `raw_taxi_zone_lookup`
3. Vào tab **Data preview** để xem dữ liệu mẫu hiển thị.
    ![Workshop](/images/5-transforming-data/create-job-add-third-source.png)
4. Nhớ **save** lại job của bạn.

### Modify column names of Drop-off Taxi Zone Lookup table
1. Đảm bảo bạn đang trỏ tới node **Amazon S3 - Dropoff Zone Lookup**.
2. Click chọn **Transform**, chọn **Change Schema**.
3. Khai báo các thông tin sau:
    * Name - `ApplyMapping - Dropoff Zone Lookup`
    * Tại phần **Change Schema (Apply mapping)**:
      - `locationid` => `do_location_id`
      - `borough` => `do_borough`
      - `zone` => `do_zone`
      - `service_zone` => `do_service_zone`
    ![Workshop](/images/5-transforming-data/create-job-change-schema-third-source.png)
4. Nhớ **save** lại job của bạn.

### Join Yellow Trips data and Dropoff Taxi Zone Lookup data
1. Chọn **Transform**, chọn **Join**.
2. Khai báo các thông tin sau:
    * Name - `Yellow Trips Data + Pickup Zone Lookup + Dropoff Zone Lookup`
    * Node Parents:
      - **ApplyMapping - Dropoff Zone Lookup**
      - **Yellow Trips Data + Pickup Zone Lookup**
    * **Join conditions**:
      - **ApplyMapping - Dropoff Zone Lookup** - `do_location_id`
      - **Yellow Trips Data + Pickup Zone Lookup** - `dolocationid`
    ![Workshop](/images/5-transforming-data/create-job-join-with-third-source.png)
3. Nhớ **save** lại job của bạn.