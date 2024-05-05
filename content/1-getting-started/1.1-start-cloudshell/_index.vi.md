---
title : "Bắt đầu với AWS CloudShell"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
{{% notice tip %}}
Trong workshop này sẽ thực hiện tạo khởi tạo các tài nguyên cơ bản ngay từ đầu bằng giao diện dòng lệnh (CLI) thay vì sử dụng CloudFormation Template.
{{% /notice %}}

### Start an AWS CloudShell Environment
{{% notice note %}}
**AWS CloudShell** là một shell dựa trên trình duyệt được xác thực trước mà bạn có thể khởi chạy trực tiếp từ AWS Management Console. Bạn có thể chạy các lệnh AWS CLI trên các dịch vụ AWS bằng cách sử dụng shell tùy nhu cầu (Bash, PowerShell hoặc Z shell) mà không cần tải/cài đặt các công cụ dòng lệnh.
{{% /notice %}}

1. Đăng nhập vào [AWS Management Console](https://ap-southeast-1.console.aws.amazon.com/console/home).
2. Ở phần menu phía trên bên phải, chọn region **Singapore (ap-southeast-1)**.
3. Bắt đầu với phiên AWS CloudShell bằng cách nhấp vào **biểu tượng CloudShell** trên thanh menu dưới cùng.
![CloudShell](/images/1-getting-started/cloudshell-open.png)
4. Một hộp thoại chào mừng sẽ bật lên, tích chọn **do not show this again**, sau đó click **Close**.
![CloudShell](/images/1-getting-started/cloudshell-open-02.png)
5. CloudShell sẽ bắt đầu chuẩn bị môi trường Linux sẽ sẵn sàng sau giây lát.
![CloudShell](/images/1-getting-started/cloudshell-open-03.png)
