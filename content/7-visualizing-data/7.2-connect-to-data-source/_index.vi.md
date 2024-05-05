---
title : "Kết nối tới nguồn dữ liệu"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 7.2. </b> "
---
1. Tại giao diện QuickSight, chọn **Datasets**.
2. Click chọn **New Dataset**
![Workshop](/images/7-visualizing-data/quicksight-04.png)
3. Chọn **Athena**
![Workshop](/images/7-visualizing-data/quicksight-05.png)
4. Tại cửa sổ **New Athena data source**, thực hiện khai báo như sau:
    * Data source name – `Athena - SDL Jumpstart`
    * Athena workgroup – **primary**
    * Click **Create Data Source**
    ![Workshop](/images/7-visualizing-data/quicksight-06.png)
5. Tại phần **Choose your table**, thực hiện khai báo như sau:
    * Catalog – **AwsDataCatalog**
    * Database – `nyctaxi_db`
    * Tables – `v_yellow_tripdata`
    * Click **Select**.
    ![Workshop](/images/7-visualizing-data/quicksight-07.png)
6. Tại cửa sổ **Finish dataset creation**, thực hiện khai báo như sau:
    * Import to SPICE for quicker analytics
    * Click **Edit/Preview data**.
    ![Workshop](/images/7-visualizing-data/quicksight-08.png)

{{% notice note %}}
**SPICE** là viết tắt của *Super-fast, Parallel, In-memory Calculation Engine*. Nó được thiết kế để nhanh chóng thực hiện các phép tính nâng cao và cung cấp dữ liệu. Dung lượng SPICE được chia sẻ bởi tất cả những người sử dụng QuickSight trong một AWS Region duy nhất.
{{% /notice %}}