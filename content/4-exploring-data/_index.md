---
title : "Exploring your Data"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---
### Overview
In this lab, we will use Amazon Athena to explore our data and identify data quality issues. We will also learn how to update table properties in AWS Glue Catalog.
![Workshop](/images/4-exploring-data/exploring-data.png)

### Introducing Amazon Athena
Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. Athena is serverless, so there is no infrastructure to setup or manage, and you can start analyzing data immediately. You don’t even need to load your data into Athena, it works directly with data stored in S3.

### Content
 4.1. [Using Amazon Athena for the first time](4.1-using-athena-first-time/) \
 4.2. [Grant permission to access data for user](4.2-grant-permission/) \
 4.3. [Preview table data](4.3-preview-data/) \
 4.4. [Working with CSV data enclosed in quotes](4.4-handling-csv-double-quote/) \
 4.5. [Run SQL queries to explore the data](4.5-explore-data-run-queries/)