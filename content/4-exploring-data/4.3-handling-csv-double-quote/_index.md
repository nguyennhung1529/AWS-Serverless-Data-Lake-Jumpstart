---
title : "Working with CSV data enclosed in quotes"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4.4. </b> "
---
{{% notice note %}}
**Working with CSV files enclosed in Quotes** \
CSV files occasionally have quotes around the data values intended for each column which aren't part of the data to be analyzed. To read the CSV file properly, we can update the table properties in AWS Glue to use the OpenCSVSerDe.
{{% /notice %}}

1. Go to **Glue console**.
2. In the left navigation menu, click **Tables** under the **Data Catalog** section.
3. On the **Table** screen, click on the **raw_taxi_zone_lookup** table.
4. Click **Actions**, then click on **Edit table**.
![Workshop](/images/4-exploring-data/edit-quota-csv-table.png)
5. Update the **Serde serialization lib** with `org.apache.hadoop.hive.serde2.OpenCSVSerde`.
![Workshop](/images/4-exploring-data/edit-quota-csv-table-02.png)
6. Remove existing **Serde parameters** and then add the following:
   * `escapeChar`, enter a backslash `\`
   * `quoteChar`, enter a double quote `"`
   * `separatorChar`, enter a comma `,`
   ![Workshop](/images/4-exploring-data/edit-quota-csv-table-03.png)
7. Click **Save**.
8. Go to back to the **Athena console**.
9. On the **Query editor** page, click on the actions menu icon **⋮** besides **raw_taxi_zone_lookup**, and then click **Preview table**.
![Workshop](/images/4-exploring-data/edit-quota-csv-table-review.png)