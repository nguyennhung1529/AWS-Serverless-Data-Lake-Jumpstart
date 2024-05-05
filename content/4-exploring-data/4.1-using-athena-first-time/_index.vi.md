---
title : "Setup Amazon Athena lần đầu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1. </b> "
---
{{% notice note %}}
**Amazon Athena** tự động lưu kết quả truy vấn và metadata của mỗi truy vấn được khởi chạy ở vị trí mà bạn có thể chỉ định trong Amazon S3. Nếu cần, bạn có thể truy cập các file này và cũng có thể trực tiếp tải xuống file kết quả truy vấn từ Athena console.
{{% /notice %}}

1. Tại **CloudShell terminal**, chạy lệnh sau để tạo S3 bucket - nơi lưu trữ kết quả truy vấn Athena.
    {{% notice %}}
    aws s3 mb aws-athena-query-results-[Account-ID]-ap-southeast-1--region ap-southeast-1
    {{% /notice %}}
2. Truy cập **Athena console**. Chọn **Get Started**.
3. Chọn **Workgroup: primary**.
4. Chọn **Settings**, click chọn **Browse S3** và tại mục **Location of query result - optional** chọn bucket bạn vừa tạo - **aws-athena-query-results-[Account-ID]-ap-southeast-1**.
5. Chọn **Save**.
![Workshop](/images/4-exploring-data/athena-01.png)
6. Trên thanh menu đầu, click tab **Editor** để quay trở lại giao diện **Query editor**.
