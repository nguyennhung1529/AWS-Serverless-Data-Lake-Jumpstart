---
title : "Trực quan hóa dữ liệu"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 7.4. </b> "
---
### Trực quan hóa dữ liệu
1. Đợi một vài phút chờ QuickSight tải dữ liệu của bạn lên SPICE.
![Workshop](/images/7-visualizing-data/quicksight-visualize-01.png)
2. Để visualize luồng chuyến xe taxi màu vàng từ điểm đón đến điểm trả khách, hãy nhấp vào **+ Add** trong menu.
4. Chọn loại visual **Sankey**, và chỉ định các trường thông tin sau:
    * Source – `pu_borough`
    * Destination – `do_borough`
    * Bạn có thể nhấp vào tiêu đề loại hình ảnh, đổi loại thành `Taxi Trips Flow`
![Workshop](/images/7-visualizing-data/quicksight-visualize-02.png)

### Lọc dữ liệu
1. Tạo bộ lọc lọc các chuyến đi taxi xuất phát từ Manhattan.
2. Nhập `pu_borough` và chọn.
![Workshop](/images/7-visualizing-data/quicksight-visualize-03.png)
3. Nhấp vào menu bên cạnh bộ lọc pu_borough, chọn **Edit**.
![Workshop](/images/7-visualizing-data/quicksight-visualize-05.png)
4. Chọn `Manhattan` từ Filter list, chọn **Apply**.
![Workshop](/images/7-visualizing-data/quicksight-visualize-04.png)
5. Nhận thông tin chi tiết luồng chuyến đi taxi dựa trên điểm đón và trả khách
6. Quan sát luồng di chuyển.