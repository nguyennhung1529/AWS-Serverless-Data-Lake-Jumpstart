---
title : "Remove records with NULL values"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 5.3. </b> "
---
1. Click on the **Transform** icon, choose **Custom transform**.
![Workshop](/images/5-transforming-data/create-job-04.png)
2. In the **Transform – Custom code** node, specify the following information:
    * Name - `Remove Records with NULL`
    * Node parents - choose node **Yellow Trip Data**
    * Add the following in the **Code block**:
        {{% notice %}}
        def MyTransform (glueContext, dfc) -> DynamicFrameCollection:
            df = dfc.select(list(dfc.keys())[0]).toDF().na.drop()
            results = DynamicFrame.fromDF(df, glueContext, "results")
            return DynamicFrameCollection({"results": results}, glueContext)
        {{% /notice %}}
    * Review data on **Data preview** tab
    ![Workshop](/images/5-transforming-data/create-job-05.png)
3. Click on the **Transform** icon, choose **Select From Collection**.
![Workshop](/images/5-transforming-data/create-job-06.png)
4. Specify the following information:
    * Name – `Select From Collection`
    * Node parents - choose node **Remove Records with NULL**
    * Transform tab, **Frame index** – **0**
    ![Workshop](/images/5-transforming-data/create-job-04.png)
5. Remember to **Save** your work.
