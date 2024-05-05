---
title : "Gán quyền truy xuất dữ liệu cho user"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2. </b> "
---
{{% notice note %}}
Như ở các lab trước, bạn đã dùng Amazon Lake Formation để quản lý quyền truy cập và bảo vệ dữ liệu. Để có thể khám phá dữ liệu trong database `nyctaxi_db` với Athena, bạn cần cấp quyền cho phép thực hiện truy xuất dữ liệu trong Lake Formation đối với user thực hiện truy vấn dữ liệu 
{{% /notice %}}

1. Truy cập **AWS Lake Formation console**, chọn **Data lake permissions**, click nút **Grant**
![Workshop](/images/4-exploring-data/grant-data-lake-permission.png)

2. Tại mục **Princial**:
  * Chọn **IAM users and roles**
  * Chọn **IAM user** sẽ gán quyền - trong trường hợp này sẽ là user mà bạn đang đăng nhập vào AWS.
  ![Workshop](/images/4-exploring-data/grant-data-lake-permission-02.png)

3. Tại mục **LF-Tags or catalog resources**:
  * Chọn **Named Data Catalog resources**
  * **Database**: chọn database cần truy cập **nyctaxi_db**
  * **Tables - optional**: chọn **All Tables**
  ![Workshop](/images/4-exploring-data/grant-data-lake-permission-03.png)

4. Tại mục **Table permissions**:
  * Tích chọn các quyền truy cập vào bảng cần thiết: *Create table, Alter, Drop, Discribe, and Super*
  * Rà soát lại sau đó chọn **Grant**
  ![Workshop](/images/4-exploring-data/grant-data-lake-permission-04.png)

Như vậy, với các quyền như trên, giờ bạn đã có thể tạo, xem, sửa, xóa các bảng trong database *nyctaxi_db*