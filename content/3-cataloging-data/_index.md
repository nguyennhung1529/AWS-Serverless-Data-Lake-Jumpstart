---
title : "Cataloging your Data"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---
### Overview
With an array of data sources and formats in your data lake, it's important to have the ability to discover and catalog it order to better understand the data that you have and at the same time enable integration with other purpose-built AWS analytics. \
\
In this lab, we will create an AWS Glue Crawlers to auto discover the schema of the data stored in Amazon S3. The discovered information about the data stored in S3 will be registered in the AWS Glue Catalog. This allows AWS Glue to use the information stored in the catalog for ETL processing. It also allows other AWS services like Amazon Athena to run queries on the data stored in Amazon S3.
![Workshop](/images/3-cataloging-data/cataloging-data.png)

### Content
 3.1. [Create a Glue Crawler](3.1-create-crawler/) \
 3.2. [Run the Glue Crawler](3.2-run-crawler/) \
 3.3. [Review the metadata in Glue Data Catalog](3.3-review-metadata/) \
 3.4. [Create another Glue Crawler](3.4-create-another-crawler/)