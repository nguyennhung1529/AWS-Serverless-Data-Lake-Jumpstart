---
title : "Tạo Glue job với Glue Studio"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---
### Lập kế hoạch cho các bước chuyển đổi dữ liệu
Dựa trên các thông tin thu thập được trong giai đoạn thăm dò dữ liệu, chúng ta có các bước chuyển đổi sau đây:
1. Đọc dữ liệu các yellow trip từ S3 trong bảng `raw_yellow_tripdata`.
2. Làm sạch dữ liệu yellow trip data.
	* Loại bỏ các bảng ghi NULL (xét trên các trường *vendorid, payment_type, passenger count, ratecodeid*).
	* Lọc các bảng ghi trong khoảng thời gian phân tích (loại bỏ các bản ghi với datatime không hợp lệ, thu gọn lượng dữ liệu cần xử lý).
3. Kết hợp dữ liệu các chuyến đi - yellow trip data với dữ liệu khu vực - taxi zone lookup để lấy được thông tin địa điểm đón khách.
	* Đọc dữ liệu từ nguồn S3 cho bảng `raw_taxi_zone_lookup`.
	* Thay đổi tên cột của bảng để phân biệt địa điểm đón và địa điểm trả khách.
	* Thực hiện việc kết hợp bảng.
4. Kết hợp dữ liệu chuyển đi - yellow trip data với dữ liệu khu vực - taxi zone lookup để lấy được thông tin địa điểm trả khách.
	* Đọc dữ liệu từ nguồn S3 cho bảng `raw_taxi_zone_lookup`.
	* Thay đổi tên cột của bảng để phân biệt địa điểm đón và địa điểm trả khách.
	* Thực hiện việc kết hợp bảng.
5. Thực hiện chuyển đổi dữ liệu trên tập dữ liệu đã kết hợp.
	* Thay đổi tên cột.
	* Khai báo kiểm dữ liệu phù hợp.
	* Loại bỏ các cột dư thừa.
6. Lưu tập dữ liệu đã xử lý vào S3 ở định dạng tối ưu hóa truy vấn (ví dụ định dạng parquet).

### Tạo job với Glue Studio
1. Truy cập **Glue console**.
![Workshop](/images/5-transforming-data/aws-glue.png)
2. Bên phải thanh công cụ điều hướng, dưới mục **Data Intergration and ETL**, chọn **ETL jobs** để được điều hướng tới trang **AWS Glue Studio**.
![Workshop](/images/5-transforming-data/aws-glue-studio.png)
3. Tại trang **AWS Glue Studio**, chọn **Visual ETL**
![Workshop](/images/5-transforming-data/create-job-01.png)
4. Tại diao diện job editor, chọn tab **Job details**, thiết lập job như sau:
	* Name – `transform-nyc-taxi-trip-data`
	* IAM Role – `AWSGlueServiceRole-SDL-Jumpstart`
    ![Workshop](/images/5-transforming-data/create-job-config-job-01.png)
	* Job bookmark – **Disable**
	* Number of retries – **0**
    ![Workshop](/images/5-transforming-data/create-job-config-job-02.png)
{{% notice note %}}
**AWS Glue job bookmark** lưu trữ thông tin trạng thái dữ liệu, tránh việc chạy lại dữ liệu cũ. Nó cho phép job chỉ xử lý trên tập dữ liệu mới khi chạy lại theo khoảng thời gian đã lên lịch.
{{% /notice %}}
5. Click chọn **Save**. Quay trở lại tab **Visual**.
