---
title : "Tạo IAM Role"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 1.3 </b> "
---
### Tạo IAM role cho AWS Glue
{{% notice note %}}
**IAM Service Role** (Vai trò dịch vụ IAM) định nghĩa một tập hợp các quyền hạn (permissions) cần thiết cho việc gửi yêu cầu dịch vụ. Các quyền hạn này có thể được cấp và thực thi bởi một thực thể đáng tin cậy (được ủy quyền) - thường là một dịch vụ của AWS.
{{% /notice %}}

1. Tại CloudShell terminal, chạy lệnh sau để tải xuống và cài đặt **Nano Text Editor**. Khi terminal xuất hiện câu hỏi "Is this ok", gõ `y`.
    {{% notice %}}
    sudo yum install nano
    {{% /notice %}}
2. Bắt đầu với nano để tạo tập tin.
    {{% notice %}}
    nano trust-policy.json
    {{% /notice %}}
3. Trong trình chỉnh sửa, paste nội dung sau. Gõ `Ctrl-X`, gõ `Y` sau đó bấm **ENTER** để lưu và thoát.
    {{% notice %}}
    {
        "Version":"2012-10-17",
        "Statement":[
            {
                "Effect":"Allow",
                "Principal":{
                    "Service":"glue.amazonaws.com"
                },
                "Action":"sts:AssumeRole"
            }
        ]
    }
    {{% /notice %}}
4. Tạo file khác sử dụng nano editor
    {{% notice %}}
    nano s3access-policy.json
    {{% /notice %}}
5. Tại trình chỉnh sửa, paste nội dung sau (lưu ý thay đổi lại tên bucket). Gõ `Ctrl-X`, gõ `Y` sau đó bấm **ENTER** để lưu và thoát.
    {{% notice %}}
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "s3:PutObject",
                    "s3:GetObject",
                    "s3:ListBucket"
                ],
                "Resource": [
                    "arn:aws:s3:::[your-bucket]-raw/*",
                    "arn:aws:s3:::[your-bucket]-raw",
                    "arn:aws:s3:::[your-bucket]-transformed/*",
                    "arn:aws:s3:::[your-bucket]-transformed"
                ]
            }
        ]
    }
    {{% /notice %}}
6. Tại CloudShell terminal, chạy các lệnh sau để tạo IAM role và gán các quyền cho role.
    {{% notice %}}
    aws iam create-role --role-name AWSGlueServiceRole-SDL-Jumpstart --assume-role-policy-document file://trust-policy.json
    {{% /notice %}}
    {{% notice %}}
    aws iam put-role-policy --role-name AWSGlueServiceRole-SDL-Jumpstart --policy-name Glue-SDLS3Access --policy-document file://s3access-policy.json
    {{% /notice %}}
    {{% notice %}}
    aws iam attach-role-policy --role-name AWSGlueServiceRole-SDL-Jumpstart --policy-arn arn:aws:iam::aws:policy/service-role/AWSGlueServiceRole
    {{% /notice %}}
7. Để kiểm tra xem IAM role đã được tạo thành công hay chưa, chạy các lệnh sau.
    {{% notice %}}
    aws iam get-role --role-name AWSGlueServiceRole-SDL-Jumpstart
    {{% /notice %}}
    {{% notice %}}
    aws iam  list-role-policies --role-name AWSGlueServiceRole-SDL-Jumpstart
    {{% /notice %}}
    {{% notice %}}
    aws iam  list-attached-role-policies --role-name AWSGlueServiceRole-SDL-Jumpstart
    {{% /notice %}}

{{% notice note %}}
Best practice là bạn sẽ tuân theo nguyên tắc đặc quyền tối thiểu (**principle of least privilege**). Chỉ cấp các quyền cần thiết để thực thi nhiệm vụ. Xác định những gì user/role cần thực hiện, sau đó xây dựng các chính sách cho phép chúng chỉ thực hiện những nhiệm vụ đó.
{{% /notice %}}