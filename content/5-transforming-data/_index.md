---
title : "Transforming your Data"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---
### Overview
Data enrichment is the process of enhancing existing data with additional data from other sources to provide additional context or meaning, it makes data more useful and insightful during analysis.
![Workshop](/images/5-transforming-data/transforming-data.png)

### Introducing AWS Glue Studio
AWS Glue Studio is a graphical interface that makes it easy to create, run, and monitor extract, transform, and load (ETL) jobs in AWS Glue. You can visually compose data transformation workflows, AWS Glue studio will generate Apache Spark code on your behalf, and let it seamlessly run them on AWS Glue’s Apache Spark-based serverless ETL engine.

{{% notice note %}}
More: [Apache Spark and PySpark](https://docs.google.com/document/d/1rsWCHMeZWwzeVCyc3sQjZGQHK2J4EYsD/edit?usp=sharing&ouid=117097929676366412267&rtpof=true&sd=true)
{{% /notice %}}

### Content
 5.1. [Create a job using Glue Studio](5.1-create-glue-studio-job/) \
 5.2. [Add a data source](5.2-add-data-source/) \
 5.3. [Remove records with NULL values](5.3-remove-records-with-null/) \
 5.4. [Filter records](5.4-filter-records/) \
 5.5. [Add another data source](5.5-add-another-data-source/) \
 5.6. [Join data](5.6-join-data-sources/) \
 5.7. [Add and join another dataset](5.7-add-and-join-third-data-source/) \
 5.8. [Transform data and save to target](5.8-transform-and-save-to-target/) \
 5.9. [Run the job](5.9-run-and-monitor-job/)