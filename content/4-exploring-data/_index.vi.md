---
title : "Khám phá dữ liệu"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---
### Tổng quan
Trong lab này, bạn sẽ sử dụng Amazon Athena để khám phá dữ liệu của mình và xác định các vấn đề về chất lượng dữ liệu. Bạn cũng sẽ tìm hiểu cách cập nhật thuộc tính (properties) của bảng trong AWS Glue Catalog.
![Workshop](/images/4-exploring-data/exploring-data.png)

### Giới thiệu về Amazon Athena
**Amazon Athena** là _dịch vụ truy vấn tương tác_ giúp dễ dàng phân tích dữ liệu trong Amazon S3 bằng cách sử dụng các câu lệnh SQL. Athena là một dịch vụ serverless nên bạn sẽ không cần thiết lập hay quản lý cơ sở hạ tầng, mà có thể ngay lập tức bắt đầu phân tích dữ liệu với Athena. Bạn thậm chí không cần load dữ liệu của mình vào Athena, bởi nó hoạt động trực tiếp với dữ liệu được lưu trữ trong S3.

### Nội dung
 4.1. [Setup Amazon Athena lần đầu](4.1-using-athena-first-time/) \
 4.2. [Gán quyền truy xuất dữ liệu cho user](4.2-grant-permission/) \
 4.3. [Xem trước dữ liệu bảng](4.3-preview-data/) \
 4.4. [Làm việc với dữ liệu CSV](4.4-handling-csv-double-quote/) \
 4.5. [Chạy lệnh truy vấn SQL để khám phá dữ liệu](4.5-explore-data-run-queries/)