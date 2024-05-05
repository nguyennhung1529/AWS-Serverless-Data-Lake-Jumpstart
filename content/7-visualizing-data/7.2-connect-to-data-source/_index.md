---
title : "Connect to a data source"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 7.2. </b> "
---
1. On the QuickSight page, click **Datasets** in the left navigation menu pane.
2. On the upper right section of the screen, click **New Dataset**
![Workshop](/images/7-visualizing-data/quicksight-04.png)
3. Select **Athena**
![Workshop](/images/7-visualizing-data/quicksight-05.png)
4. In the **New Athena data source** window, specify the following:
    * Data source name – `Athena - SDL Jumpstart`
    * Athena workgroup – **primary**
    * Click **Create Data Source**
    ![Workshop](/images/7-visualizing-data/quicksight-06.png)
5. In the **Choose your table** window, specify the following:
    * Catalog – **AwsDataCatalog**
    * Database – `nyctaxi_db`
    * Tables – `v_yellow_tripdata`
    * Click **Select**.
    ![Workshop](/images/7-visualizing-data/quicksight-07.png)
6. In the **Finish dataset creation** window, specify the following:
    * Import to SPICE for quicker analytics
    * Click **Edit/Preview data**.
    ![Workshop](/images/7-visualizing-data/quicksight-08.png)

{{% notice note %}}
**SPICE** stands for Super-fast, Parallel, In-memory Calculation Engine. It's engineered to rapidly perform advanced calculations and serve data. SPICE capacity is shared by all the people using QuickSight in a single AWS Region.
{{% /notice %}}