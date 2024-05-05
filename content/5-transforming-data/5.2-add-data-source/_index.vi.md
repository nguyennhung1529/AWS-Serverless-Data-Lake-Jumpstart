---
title : "Thêm nguồn dữ liệu"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 5.2. </b> "
---
### Thêm dữ liệu Yellow Trips từ Amazon S3
1. Click chọn **Source**, chọn **Amazon S3**.
![Workshop](/images/5-transforming-data/create-job-02.png)
2. Tại node **Data source – S3 bucket**, khai báo các thông tin sau trong tab **Data source properties**:
   * **Name** - `Yellow Trip Data`
   * **S3 source type** - **Data Catalog table**
   * **Database** – `nyctaxi_db`
   * **Table** – `raw_yellow_tripdata`
3. Vào tab **Data preview** để xem dữ liệu mẫu hiển thị.
4. Chọn **Save**. Hãy nhớ lưu công việc của bạn khi bạn tiến hành xây dựng các bước chuyển đổi.
![Workshop](/images/5-transforming-data/create-job-03.png)
