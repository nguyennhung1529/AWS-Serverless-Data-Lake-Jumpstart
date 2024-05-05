---
title : "Loại bỏ các bản ghi có giá trị NULL"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 5.3. </b> "
---
1. Chọn **Transform**, chọn **Custom transform**.
![Workshop](/images/5-transforming-data/create-job-04.png)
2. Tại node **Transform – Custom code**, khai báo các thông tin sau:
    * Name - `Remove Records with NULL`
    * Node parents - chọn node **Yellow Trip Data**
    * Thêm đoạn code sau vào mục **Code block**:
        {{% notice %}}
        def MyTransform (glueContext, dfc) -> DynamicFrameCollection:
            df = dfc.select(list(dfc.keys())[0]).toDF().na.drop()
            results = DynamicFrame.fromDF(df, glueContext, "results")
            return DynamicFrameCollection({"results": results}, glueContext)
        {{% /notice %}}
    * Review dữ liệu tại tab **Data preview**
    ![Workshop](/images/5-transforming-data/create-job-05.png)
3. Chọn **Transform**, chọn **Select From Collection**.
![Workshop](/images/5-transforming-data/create-job-06.png)
4. Khai báo các thông tin sau:
    * Name – `Select From Collection`
    * Node parents - chọn node **Remove Records with NULL**
    * Transform tab, **Frame index** – **0**
    * Review dữ liệu tại tab **Data preview**
    ![Workshop](/images/5-transforming-data/create-job-04.png)
5. Nhớ **Save** job của bạn.
