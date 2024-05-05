---
title : "Create S3 buckets and upload data"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 1.2 </b> "
---
### Create an S3 bucket to store raw data and upload dataset
{{% notice note %}}
An **S3 bucket** is a storage resource that act as a container for objects stored in Amazon S3. You can review the naming rules  before creating your buckets.
{{% /notice %}}

1. In the CloudShell terminal, run the following command to create a unique S3 bucket.
    {{% notice %}}
    aws s3api create-bucket --bucket [your-bucket-name]-raw --region ap-southeast-1
    {{% /notice %}}

### Upload the datasets to your Amazon S3 bucket
{{% notice note %}}
We will use the New York City Taxi and Limousine Commission (TLC) Trip Record Data. You can find more information about the dataset in the [Registry of Open Data on AWS](https://registry.opendata.aws/nyc-tlc-trip-records-pds/) and by visiting the New York City Taxi and Limousine Commission (TLC) [data record page](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page) 
{{% /notice %}}
1. Run the following command to upload the yellow taxi trip data dataset to the S3 bucket you just created.
  * **C1:**
    {{% notice %}}
    aws s3api create-bucket --bucket [your-bucket-name]-raw --region ap-southeast-1 --create-bucket-configuration LocationConstraint=ap-southeast-1
    {{% /notice %}}
{{% notice tip %}}
If you set region in *us-east-1*, then to create S3 bucket, you just need:\
*aws s3api create-bucket --bucket [your-bucket-name]-raw --region us-east-1*
{{% /notice %}}

  * **C2:**
    {{% notice %}}
    aws s3 mb s3://[your-bucket-name]-raw --region ap-southeast-1
    {{% /notice %}}

3. Run the following command to upload the taxi zone lookup table to the same S3 bucket.
    {{% notice %}}
    aws s3 cp "s3://nyc-tlc/misc/taxi _zone_lookup.csv" s3://[your-bucket-name]-raw/nyc-taxi/taxi_zone_lookup/taxi_zone_lookup.csv
    {{% /notice %}}

4. Run the following command to list the files you uploaded.
    {{% notice %}}
    aws s3 ls s3://[your-bucket-name]-raw --recursive
    {{% /notice %}}

### Create another Amazon S3 bucket to store transformed data
1. Run the following command to create another unique S3 bucket. We will use this bucket to store transformed data.
    {{% notice %}}
    aws s3api create-bucket --bucket [your-bucket-name]-transformed --region ap-southeast-1
    {{% /notice %}}