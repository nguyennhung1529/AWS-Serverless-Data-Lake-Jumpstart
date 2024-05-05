---
title : "Grant permission to access data for user"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2. </b> "
---
{{% notice note %}}
With the lab above, you used Amazon Lake Formation to manage permissions access, centrally govern and secure data. To be able to explore data in database `nyctaxi_db` (managed by Lake Formation) with Athena, you need to grant permission to perform data retrieval in Lake Formation to the user performing data queries.
{{% /notice %}}

1. Access **AWS Lake Formation console** and click on the **Data lake permissions** on the left and then click on **Grant** button
![Workshop](/images/4-exploring-data/grant-data-lake-permission.png)

2. On **Princial** section:
  * Select **IAM users and roles**
  * Select **IAM user** - in this case is the user that you login into AWS account.
  ![Workshop](/images/4-exploring-data/grant-data-lake-permission-02.png)

3. On **LF-Tags or catalog resources** section:
  * Select **Named Data Catalog resources**
  * On **Database**, choose database need grant access **nyctaxi_db**
  * On **Tables - optional**, choose **All Tables**
  ![Workshop](/images/4-exploring-data/grant-data-lake-permission-03.png)

4. On **Table permissions** section:
  * Tick for table permissions need: *Create table, Alter, Drop, Discribe, and Super*
  * Review then click **Grant**
  ![Workshop](/images/4-exploring-data/grant-data-lake-permission-04.png)

Now, with above permission, you can *create, view, update, drop* tables in the database *nyctaxi_db*