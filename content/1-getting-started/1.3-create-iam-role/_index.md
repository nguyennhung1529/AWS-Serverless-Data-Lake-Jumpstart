---
title : "Create an IAM Service Role"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 1.3 </b> "
---
### Create an IAM service role for AWS Glue
{{% notice note %}}
**IAM Service Role** defines a set of permissions for making service requests that a trusted entity, an AWS service, can assume and perform.IAM Service Role defines a set of permissions for making service requests that a trusted entity, an AWS service, can assume and perform.
{{% /notice %}}

1. In the CloudShell terminal, run the following command to download and install **Nano Text Editor**. When prompted with "Is this ok", type `y`.
    {{% notice %}}
    sudo yum install nano
    {{% /notice %}}
2. Start nano to create a file.
    {{% notice %}}
    nano trust-policy.json
    {{% /notice %}}
3. In the editor, paste the following content. Type `Ctrl-X`, type `Y` and then **ENTER** to save and exit.
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
4. Create another file using nano editor
    {{% notice %}}
    nano s3access-policy.json
    {{% /notice %}}
5. In the editor, paste the following content and update the bucket name. Type `Ctrl-X`, type `Y` and then **ENTER** to save and exit.
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
6. In the CloudShell terminal, run the following commands to create an IAM role and attach permissions.
    {{% notice %}}
    aws iam create-role --role-name AWSGlueServiceRole-SDL-Jumpstart --assume-role-policy-document file://trust-policy.json
    {{% /notice %}}
    {{% notice %}}
    aws iam put-role-policy --role-name AWSGlueServiceRole-SDL-Jumpstart --policy-name Glue-SDLS3Access --policy-document file://s3access-policy.json
    {{% /notice %}}
    {{% notice %}}
    aws iam attach-role-policy --role-name AWSGlueServiceRole-SDL-Jumpstart --policy-arn arn:aws:iam::aws:policy/service-role/AWSGlueServiceRole
    {{% /notice %}}
7. To check if the IAM role was successfully created, run the following commands.
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
It is a best practice to follow the **principle of least privilege**. Grant only permissions required to perform a task. Determine what users and/or roles need to do and then craft policies that allow them to perform only those tasks.
{{% /notice %}}