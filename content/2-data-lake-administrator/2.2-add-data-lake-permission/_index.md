---
title : "Add data lake permissions"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2. </b> "
---
In this lab, you will grant data lake permission for IAM Role (which you created from the beginning) to access Catalog Database, and have permission to create tables.

1. Access **AWS Lake Formation console** and click on the **Data lake permissions** on the left and then click on **Grant** button
![Workshop](/images/2-data-lake-administrator/grant-data-lake-permission.png)

2. On **Princial** section:
  * Select **IAM users and roles**
  * Select IAM Role created from beginning, named: `AWSGlueServiceRole-SDL-Jumpstart`

3. On **LF-Tags or catalog resources** section:
  * Select **Named Data Catalog resources**
  * Choose Database created name `nyctaxi_db`
![Workshop](/images/2-data-lake-administrator/grant-data-lake-permission-02.png)

4. On **Database permissions** section:
  * Tick for database permissions need: *Create table, Alter, Drop, Discribe, and Super*
  * Review then click **Grant**
![Workshop](/images/2-data-lake-administrator/grant-data-lake-permission-03.png)
