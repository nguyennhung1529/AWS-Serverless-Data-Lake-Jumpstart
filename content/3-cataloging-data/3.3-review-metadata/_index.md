---
title : "Review the metadata in Glue Data Catalog"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3.3. </b> "
---
{{% notice note %}}
**Glue Data Catalog** contain references to data that is used as sources and targets of your extract, transform, and load (ETL) jobs in AWS Glue. It also maintain a unified view of the data and enables various AWS services such as Athena, EMR, and Redshift Spectrum to access it.
{{% /notice %}}

1. In the left navigation menu, click **Tables**.
2. On the **Tables** page, click on the name **raw_yellow_tripdata** to review the table metadata and schema information.
![Workshop](/images/3-cataloging-data/view-catalog.png)