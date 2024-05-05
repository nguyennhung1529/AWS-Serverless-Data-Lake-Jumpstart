---
title : "Biến đổi dữ liệu và lưu vào bảng đích"
date :  "`r Sys.Date()`" 
weight : 8 
chapter : false
pre : " <b> 5.8. </b> "
---
### Thay đổi tên cột và loại dữ liệu cho tập dataset tổng hợp
1. Click chọn **Transform**, chọn **ApplyMapping**.
2. Khai báo các thông tin sau:
	* Name - `ApplyMapping - Joined Data`
	* Tại phần **Change Schema (Apply mapping)**, thay đổi **Target key** và **Data type** cho các cột sau:
	  - `vendorid` => `vendor_id`
	  - `tpep_pickup_datetime` => `pickup_datetime`, `string` => `timestamp`
	  - `tpep_dropoff_datetime` => `dropoff_datetime`, `string` => `timestamp`
	* Tại phần **Change Schema (Apply mapping)**, drop các cột dư thừa sau
	  - `pulocationid`
	  - `dolocationid`
    ![Workshop](/images/5-transforming-data/create-job-apply-joined-data.png)
3. Nhớ **save** lại job của bạn.

### Save transformed data to Amazon S3
1. Chọn **Target**, chọn **Amazon S3**.
![Workshop](/images/5-transforming-data/create-job-add-target-source.png)
2. Khai báo các thông tin sau:
	* Name – `Transformed Yellow Trip Data`
	* Format – **Parquet**
	* Compression Type - **Snappy**
	* S3 Target Location – **s3://[your-bucket-name]–transformed/nyc-taxi/yellow-tripdata/**
    ![Workshop](/images/5-transforming-data/create-job-add-target-source-02.png)
3. Nhớ **save** lại job của bạn.

Đến bước này, bạn đã xây dựng thành công luồng ETL job như hình dưới đây:
![Workshop](/images/5-transforming-data/create-job-workflow.png)
