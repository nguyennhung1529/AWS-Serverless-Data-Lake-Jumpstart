---
title : "Tạo Data Catalog Database"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1. </b> "
---
AWS Glue Data Catalog giúp quản lý metadata tập trung với tính năng kiểu cơ sở dữ liệu quen thuộc. Trong lab này, bạn sẽ tạo Data Catalog Database để về sau làm data lake lưu trữ dữ liệu thô và dữ liệu đã xử lý trong S3.

1. Truy cập **AWS Lake Formation console**, click vào **Databases** trên thanh điều hướng phía bên trái, sau đó click vào  **Create database**
![Workshop](/images/2-data-lake-administrator/catalog-database-create.png)

2. Đặt tên cho Database: `nyctaxi_db`
3. Các lựa chọn còn lại để mặc định, và click **Create database**
![Workshop](/images/2-data-lake-administrator/catalog-database-create-02.png)
