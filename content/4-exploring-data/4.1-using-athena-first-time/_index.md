---
title : "Using Amazon Athena for the first time"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1. </b> "
---
{{% notice note %}}
**Amazon Athena** automatically stores query results and metadata information for each query that runs in a query result location that you can specify in Amazon S3. If necessary, you can access the files in this location to work with them. You can also download query result files directly from the Athena console.
{{% /notice %}}

1. Launch a **CloudShell terminal**, and then run the following command to create an S3 bucket to store Athena’s query results.
    {{% notice %}}
    aws s3 mb aws-athena-query-results-[Account-ID]-ap-southeast-1--region ap-southeast-1
    {{% /notice %}}
2. Go to **Athena console**. Click **Get Started**.
3. On the top menu, click **Workgroup: primary**.
4. Choose Settings, click on **Browse S3** and select **aws-athena-query-results-[Account-ID]-ap-southeast-1** as the value for the **Location of query result - optional** field.
![Workshop](/images/4-exploring-data/athena-01.png)
5. Go to the bottom of the page, click **Save**.
6. Go to the top menu, click on **Editor** to return back to the **Query editor** page.
