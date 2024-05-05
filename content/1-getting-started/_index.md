---
title : "Getting started"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
### Overview
In preparation for the workshop, we will create Amazon S3 buckets, copy sample data files to Amazon S3, and create an IAM service role.
![Workshop](/images/1-getting-started/prepare.png)

### What is a data lake?
A data lake is a centralized repository that allows you to store all your structured and unstructured data at any scale. You can store your data as-is, without having to first structure the data, and run different types of analytics—from dashboards and visualizations to big data processing, real-time analytics, and machine learning to guide better decisions.

### Introducing Amazon S3
Amazon Simple Storage Service (S3) is the largest and most performant object storage service for structured and unstructured data and the storage service of choice to build a data lake. With Amazon S3, you can cost-effectively build and scale a data lake of any size in a secure environment where data is protected by 99.999999999% (11 9s) of durability.

With data lakes built on Amazon S3, you can use native AWS services to run big data analytics, artificial intelligence (AI) and Machine Learning (ML) to gain insights from your unstructured data sets. Data can be collected from multiple sources and moved into the data lake in its original format. It can be accessed or processed with your choice of purpose-built AWS analytics tools and frameworks. Making it easy and quick to run analytics without the need to move your data to a separate analytics system.

{{% notice note %}}
**More**: [Started with Amazon S3](https://000057.awsstudygroup.com/vi/)
{{% /notice %}}

### Content
 1.1. [Start an AWS CloudShell environment](1.1-start-cloudshell/) \
 1.2. [Create S3 buckets and upload data](1.2-create-bucket-upload-data/) \
 1.3. [Create an IAM Service Role](1.3-create-iam-role/) 