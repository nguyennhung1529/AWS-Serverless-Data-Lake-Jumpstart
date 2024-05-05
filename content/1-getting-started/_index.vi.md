---
title : "Chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
### Tổng quan
Trong workshop này, chúng ta sẽ tạo các S3 bucket (lưu trữ dữ liệu thô đầu vào, dữ liệu sạch đã biến đổi), copy file dữ liệu mẫu vào Amazon S3, và tạo IAM role.
![Workshop](/images/1-getting-started/prepare.png)

### Data lake là gì?
**Data lake** là một kho lưu trữ tập trung cho phép bạn lưu trữ tất cả dữ liệu có cấu trúc và phi cấu trúc ở mọi quy mô. Bạn có thể lưu trữ dữ liệu thô (dữ liệu mà không cần phải cấu trúc/mô hình hóa trước dữ liệu) và thực hiện các loại phân tích khác nhau — từ dashboards và trực quan hóa đến xử lý big data, phân tích thời gian thực và học máy giúp chúng ta tối ưu hóa việc đưa ra các quyết định.

### Giới thiệu về Amazon S3
**Amazon Simple Storage Service (S3)** là dịch vụ lưu trữ đối tượng (object storage) lớn nhất và hiệu quả nhất dành cho dữ liệu có cấu trúc và phi cấu trúc, đồng thời là dịch vụ lưu trữ được sử dụng để xây dựng data lake. Với Amazon S3, bạn có thể xây dựng và mở rộng quy mô data lake ở mọi quy mô một cách tiết kiệm chi phí trong một môi trường an toàn nơi dữ liệu được bảo vệ với độ bền 99,999999999% (11 9s).

Với các data lake được xây dựng trên Amazon S3, bạn có thể sử dụng các dịch vụ của AWS để thực hiện phân tích big data, trí tuệ nhân tạo (AI) và Machine Learning (ML) giúp thu thập thông tin chi tiết từ các tập dữ liệu phi cấu trúc của bạn. Dữ liệu có thể được thu thập từ nhiều nguồn và chuyển vào data lake ở định dạng gốc. Nó có thể được truy cập hoặc xử lý dựa trên các công cụ và framework phân tích chuyên dụng của AWS. Giúp việc chạy phân tích trở nên dễ dàng và nhanh chóng mà không cần phải di chuyển dữ liệu của bạn sang hệ thống phân tích riêng.

{{% notice note %}}
**Tham khảo thêm**: [Started with Amazon S3](https://000057.awsstudygroup.com/vi/)
{{% /notice %}}

### Nội dung
 1.1. [Bắt đầu với AWS CloudShell](1.1-start-cloudshell/) \
 1.2. [Tạo S3 bucket và upload dữ liệu](1.2-create-bucket-upload-data/) \
 1.3. [Tạo IAM Role](1.3-create-iam-role/) 