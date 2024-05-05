---
title : "Tạo S3 bucket và upload dữ liệu"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 1.2 </b> "
---
### Tạo S3 bucket để lưu trữ dữ liệu thô và load tập dữ liệu
{{% notice note %}}
**S3 bucket** đóng vai trò là container/nơi chứa các đối tượng lưu trữ trong Amazon S3. Bạn có thể xem lại [quy tắc đặt tên](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html) trước khi tạo bucket
{{% /notice %}}

1. Tại CloudShell terminal, hãy chạy lệnh sau để tạo S3 bucket,
    {{% notice %}}
    aws s3api create-bucket --bucket [your-bucket-name]-raw --region ap-southeast-1
    {{% /notice %}}

### Tải tập dữ liệu vào S3 bucket
{{% notice note %}}
Workshop này sẽ sử dụng Dữ liệu Hồ sơ Chuyến đi Taxi và Xe Limousine (TLC) của Thành phố New York. Bạn có thể tìm thêm thông tin về tập dữ liệu trong [Registry of Open Data on AWS](https://registry.opendata.aws/nyc-tlc-trip-records-pds/) và bằng cách truy cập [data record page](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
{{% /notice %}}

1. Chạy lệnh sau để tải tập dữ liệu dữ liệu chuyến đi taxi vàng (yellow taxi trip) vào S3 bucket mà bạn vừa tạo
  * **C1:**
    {{% notice %}}
    aws s3api create-bucket --bucket [your-bucket-name]-raw --region ap-southeast-1 --create-bucket-configuration LocationConstraint=ap-southeast-1
    {{% /notice %}}
{{% notice tip %}}
Nếu bạn chọn region ở *us-east-1*, thì khi tạo S3 bucket, câu lệnh bạn sử dụng như sau:\
*aws s3api create-bucket --bucket [your-bucket-name]-raw --region us-east-1*
{{% /notice %}}

  * **C2:**
    {{% notice %}}
    aws s3 mb s3://[your-bucket-name]-raw --region ap-southeast-1
    {{% /notice %}}

3. Chạy lệnh sau để upload bảng tra cứu vùng taxi (taxi zone lookup) lên cùng S3 bucket.
    {{% notice %}}
    aws s3 cp "s3://nyc-tlc/misc/taxi _zone_lookup.csv" s3://[your-bucket-name]-raw/nyc-taxi/taxi_zone_lookup/taxi_zone_lookup.csv
    {{% /notice %}}

5. Chạy lệnh sau để liệt kê các tệp bạn đã tải lêns.
    {{% notice %}}
    aws s3 ls s3://[your-bucket-name]-raw --recursive
    {{% /notice %}}

### Tạo S3 bucket khác để lưu trữ dữ liệu đã xử lý
1. Chạy lệnh sau để tạo S3 bucket. Các bài lab sau, bạn sẽ dùng bucket này để lưu trữ các dữ liệu đã chuyển đổi.
    {{% notice %}}
    aws s3 mb s3://[your-bucket-name]-transformed --region ap-southeast-1
    {{% /notice %}}