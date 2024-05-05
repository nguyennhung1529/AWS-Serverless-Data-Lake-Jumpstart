---
title : "Visualize data"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 7.4. </b> "
---
### Visualize your data
1. QuickSight will attempt to load your data to SPICE, please wait for a few minutes.
![Workshop](/images/7-visualizing-data/quicksight-visualize-01.png)
2. To visualize the flow of yellow taxi trips from pickup borough to drop-off borough, click **+ Add** in the menu.
3. Select the **Sankey** visual type, specify the following on the Field wells.
    * Source – `pu_borough`
    * Destination – `do_borough`
    * You can click on the visual type title, change it to `Taxi Trips Flow`
![Workshop](/images/7-visualizing-data/quicksight-visualize-02.png)

### Filtering Data
1. Create a filter focus on taxi trips originating from Manhattan.
2. Type `pu_borough` and then select it.
![Workshop](/images/7-visualizing-data/quicksight-visualize-03.png)
3. Click on the menu besides the pu_borough filter, select **Edit**.
![Workshop](/images/7-visualizing-data/quicksight-visualize-05.png)
4. Select `Manhattan` from the Filter list, click **Apply**.
![Workshop](/images/7-visualizing-data/quicksight-visualize-04.png)
5. Get insights by examining the taxi trip flow based on pickup borough and drop-off borough.
6. Observe the traffic flow patterns.

