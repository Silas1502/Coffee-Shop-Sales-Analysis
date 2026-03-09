# ☕ Phân Tích Doanh Thu Quán Cà Phê (Dự Án Excel)

## 📊 1. Tổng Quan Dự Án

Dự án này phân tích dữ liệu bán hàng của một quán cà phê nhằm hiểu rõ
hiệu suất kinh doanh và tìm ra các insight giúp cải thiện doanh thu và
hoạt động kinh doanh.

Phân tích được thực hiện bằng **Microsoft Excel**, bao gồm các bước làm
sạch dữ liệu, phân tích bằng Pivot Table và trực quan hóa bằng
Dashboard.

📦 Quy mô dữ liệu: **10.000 giao dịch**.


## 🎯 2. Mục Tiêu

Mục tiêu của dự án bao gồm:

-   Làm sạch và tiền xử lý dữ liệu bán hàng bị lỗi
-   Phân tích hiệu suất bán hàng của quán cà phê
-   Xác định các sản phẩm bán chạy nhất
-   Hiểu hành vi mua hàng của khách hàng
-   Xây dựng dashboard tương tác trong Excel
-   Rút ra các insight kinh doanh từ dữ liệu



## 🗂️ 3. Mô Tả Dataset

Các cột chính trong dataset:
```
  -----------------------------------------------------------------------
  Cột                          Mô tả
  ---------------------------- ------------------------------------------
  Transaction ID               Mã định danh duy nhất cho mỗi giao dịch

  Item                         Sản phẩm được bán

  Quantity                     Số lượng sản phẩm được mua

  Price Per Unit               Giá của mỗi sản phẩm

  Total Spent                  Tổng số tiền chi tiêu trong giao dịch

  Payment Method               Phương thức thanh toán (Tiền mặt, Thẻ tín
                               dụng, Ví điện tử)

  Location                     Hình thức đặt hàng (Tại quán / Mang đi)

  Transaction Date             Ngày giao dịch
  -----------------------------------------------------------------------
```
📁 Nguồn dữ liệu: dữ liệu bán hàng quán cà phê mô phỏng có chủ ý chứa các
vấn đề về chất lượng dữ liệu.

## ⚙️ 4. Quy trình thực hiện
1. Thu thập dữ liệu từ Kaggle.
2. Làm sạch dữ liệu bằng Power Query.
3. Chuyển đổi và chuẩn hóa dữ liệu.
4. Phân tích khám phá dữ liệu.
5. Phân tích dữ liệu bằng Pivot Table.
6. Xây dựng Dashboard để trực quan hóa dữ liệu.
7. Rút ra các insight kinh doanh từ dữ liệu.

## 🧹 5. Làm Sạch Dữ Liệu

Quá trình làm sạch dữ liệu được thực hiện trong Power Query của Excel để chuẩn bị cho
việc phân tích.

Các bước chính:

-   Đưa dòng đầu lên làm header.
-   Xóa các dòng trống.
-   Thay các giá trị ERROR, UNKNOWN, blank thành null để dễ dàng xử lý.
-   - Xử lý các cột số (Numerical variables) trước, sau đó xử lý các cột phân loại (Categorical variables).
    + Thay đổi kiểu dữ liệu của các cột cho phù hợp.
    + Xử lý cột Price Per Unit bằng cách thay giá trị null bằng median của cột.
    + Xử lý cột Quantity bằng cách dùng cột Total Spent / Price Per Unit new đối với các ô dữ liệu null.
    + Tính toán cột Total Spent new bằng cách Price Per Unit new * Quantity new.
    + Đối với cột Transaction Date thì các dòng chứa giá trị null sẽ bị loại bỏ vì không thể suy ra giá trị Transaction Date từ biến nào khác và cũng để đảm bảo cho mục đích phân tích doanh thu theo thời gian được chính xác.
    + Đối với cột Item thì dùng bảng phụ chứa giá trị 2 cột Item và Price Per Unit new để có thể suy ra giá trị Item từ Price Per Unit new.
    + Đối với cột Location, các giá trị null sẽ được thay thành Unknown.
    + Đối với Payment Method, các giá trị null sẽ được thay thành Other.
-   Lọc ra những dòng sạch và load vào Excel.

Sau khi làm sạch, dataset còn lại 9,521 dòng đã trở nên phù hợp cho việc phân tích. Tuy nhiên, do hai cột Payment Method và Location với mức độ nhiễu cao nên các phân tích liên quan đến hai biến này được hạn chế nhằm đảm bảo tính chính xác của kết quả.



## ❓ 6. Các Câu Hỏi Phân Tích

Các câu hỏi được sử dụng trong quá trình phân tích:

1.  Tổng doanh thu của quán cà phê là bao nhiêu?
  - Doanh thu theo tháng?
  - Doanh thu theo các ngày trong tuần?
3.  Tổng số đơn hàng được giao?
  - Tổng số đơn theo tháng?
  - Tổng số đơn theo các ngày trong tuần?
4.  Tổng số lượng sản phẩm đã được bán?
  - Tổng số lượng sản phẩm được bán trong tháng?
  - Tổng số lượng sản phẩm được bán trong các ngày trong tuần?
  - Sản phẩm nào bán chạy nhất và chậm nhất?
5.  Doanh thu theo từng sản phẩm?
  - Sản phẩm nào tạo ra nhiều và ít doanh thu nhất?
6.  Trung bình mỗi ngày bán được bao nhiêu đơn hàng?
7.  Doanh thu trung bình mà một đơn hàng mang lại?
  - Trung bình một đơn hàng sẽ bao gồm bao nhiêu sản phẩm?


## 📊 7. Phân Tích Pivot Table

Một số Pivot Table đã được tạo để tổng hợp dữ liệu:

-   Tổng doanh thu, doanh thu theo tháng, theo ngày trong tuần, theo từng sản phẩm.
-   Tổng số lượng sản phẩm đã bán, theo tháng, theo thứ trong tuần.
-   Tổng số lượng đơn hàng đã bán, theo tháng, theo thứ trong tuần.
-   Doanh thu trung bình của mỗi đơn hàng.
-   Số lượng trung bình sản phẩm trong một đơn hàng.

Pivot Table giúp nhanh chóng phát hiện xu hướng và mẫu dữ liệu trong
dataset.


## 📈 8. Dashboard

Một dashboard tương tác được xây dựng trong Excel để trực quan hóa kết
quả phân tích.

Các thành phần của dashboard bao gồm đầy đủ các biểu đồ liên quan đến các câu hỏi phân tích để từ đó có thể phân tích và làm rõ vấn đề.

Dashboard giúp người dùng nhanh chóng hiểu được hiệu suất kinh doanh của
quán cà phê.

# 📷 Dashboard:
<img width="1330" height="557" alt="image" src="https://github.com/user-attachments/assets/6d6359e8-60f9-4aac-b65b-cea1c0b751a7" />

## 💡 9. Insight Chính

Một số insight có thể rút ra từ phân tích:

-   Một số sản phẩm tạo ra doanh thu cao hơn đáng kể so với các sản phẩm
    khác.
-   Một số sản phẩm được bán với số lượng lớn nhưng tỉ lệ đóng góp vào tổng doanh thu chưa cao.
-   Doanh thu biến động nhẹ theo thời gian, cho thấy chưa thể tồn tại các
    **thời điểm nhu cầu cao**.
-   Các chiến lược kinh doanh để tăng khả năng mua hàng và doanh thu trung bình ở mỗi đơn hàng.

Những insight này có thể giúp quán cà phê cải thiện chiến lược sản phẩm
và hoạt động kinh doanh.


## 🛠️ 10. Công Cụ Sử Dụng

-   **Microsoft Excel**
    -   Data Cleaning
    -   Pivot Tables
    -   Charts
    -   Dashboard Design


## 📁 11. Cấu Trúc Dự Án

    coffee-shop-sales-analysis
    │
    ├── dirty_cafe_sales.csv
    ├── Coffee_Shop_Analyst.xlsx
    └── README.md

# ⭐ Thanks for reading!
