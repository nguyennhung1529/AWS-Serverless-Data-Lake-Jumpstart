---
title : "Cấp quyền đối với data lake"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2. </b> "
---
Trong lab này, bạn sẽ cấp quyền đối với data lake cho IAM Role (đã được tạo ở bước chuẩn bị ban đầu) để truy cập vào Catalog Database, và có quyền để tạo bảng.

1. Truy cập **AWS Lake Formation console**, chọn **Data lake permissions**, sau đó click **Grant**
![Workshop](/images/2-data-lake-administrator/grant-data-lake-permission.png)

2. Tại mục **Princial**:
  * Chọn **IAM users and roles**
  * Chọn IAM Role mà bạn đã tạo từ ban đầu, tên là: `AWSGlueServiceRole-SDL-Jumpstart`

3. Tại mục **LF-Tags or catalog resources**:
  * Chọn **Named Data Catalog resources**
  * Tìm và chọn `nyctaxi_db` database
![Workshop](/images/2-data-lake-administrator/grant-data-lake-permission-02.png)

4. Tại mục **Database permissions**:
  * Tick chọn các quyền cần thiết: *Create table, Alter, Drop, Discribe, and Super*
  * Click chọn **Grant**
![Workshop](/images/2-data-lake-administrator/grant-data-lake-permission-03.png)
