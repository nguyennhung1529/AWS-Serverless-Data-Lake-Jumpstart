---
title : "Quản trị data Lake với Lake Formation"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---
### Overview
In this lab, we will create a data lake for raw data and transformed data, then use Amazon Lake Formation for centrally govern, secure, and share data on data lake for analytics.
![Workshop](/images/2-data-lake-administrator/data-lake-administrator.png)

### Introducing Amazon Lake Formation
AWS Lake Formation makes it easier to centrally govern, secure, and globally share data for analytics and machine learning (ML). With Lake Formation, you can centralize data security and governance using the AWS Glue Data Catalog, letting you manage metadata and data permissions in one place with *familiar database-style features*. It also delivers fine-grained data access control, so you can help ensure users have access to the right data, down to the row, column, and cell level. You can then scale permissions across your users. And, because Lake Formation tracks data interactions by role and user, it provides comprehensive data access auditing to help ensure the right data was accessed by the right users at the right time.

### Data Lake
The data lake is your persistent data that is stored in Amazon S3 and managed by Lake Formation using a Data Catalog. A data lake typically stores the following:
  * Structured and unstructured data.
  * Raw data and transformed data For an Amazon S3 path to be within a data lake, it must be registered with Lake Formation.

### Data Catalog
  * **The Data Catalog** is your persistent **metadata store**. It is a managed service that lets you store, annotate, and   share metadata in the AWS Cloud in the same way you would in an Apache Hive metastore. It provides a uniform repository where disparate systems can store and find metadata to track data in data silos, and then use that metadata to query and transform the data. 
  * Lake Formation uses the **AWS Glue Data Catalog** to store metadata about data lakes, data sources, transforms, and targets.
  * **Metadata** about data sources and targets is in the form of databases and tables. 
  * **Tables** store schema information, location information, and more. 
  * **Databases** are collections of tables. 
  * Lake Formation provides a hierarchy of permissions to control access to databases and tables in the Data Catalog. 
  * Each AWS account has one Data Catalog per AWS Region.

{{% notice note %}}
**More:** [AWS Lake Formation Workshop](https://catalog.us-east-1.prod.workshops.aws/workshops/78572df7-d2ee-4f78-b698-7cafdb55135d/en-US)
{{% /notice %}}

### Content
 2.1. [Create data lake](2.1-create-catalog-database/) \
 2.2. [Add data lake permissions](2.2-add-data-lake-permission/) 