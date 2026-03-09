# Phân Tích Doanh Thu Quán Cà Phê (Dự Án Excel)

## 1. Tổng Quan Dự Án

Dự án này phân tích dữ liệu bán hàng của một quán cà phê nhằm hiểu rõ
hiệu suất kinh doanh và tìm ra các insight giúp cải thiện doanh thu và
hoạt động kinh doanh.

Phân tích được thực hiện bằng **Microsoft Excel**, bao gồm các bước làm
sạch dữ liệu, phân tích bằng Pivot Table và trực quan hóa bằng
Dashboard.

Quy mô dữ liệu: **10.000 giao dịch**.

------------------------------------------------------------------------

## 2. Mục Tiêu

Mục tiêu của dự án bao gồm:

-   Làm sạch và tiền xử lý dữ liệu bán hàng bị lỗi
-   Phân tích hiệu suất bán hàng của quán cà phê
-   Xác định các sản phẩm bán chạy nhất
-   Hiểu hành vi mua hàng của khách hàng
-   Xây dựng dashboard tương tác trong Excel
-   Rút ra các insight kinh doanh từ dữ liệu

------------------------------------------------------------------------

## 3. Mô Tả Dataset

Các cột chính trong dataset:

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

Nguồn dữ liệu: dữ liệu bán hàng quán cà phê mô phỏng có chủ ý chứa các
vấn đề về chất lượng dữ liệu.

------------------------------------------------------------------------

## 4. Làm Sạch Dữ Liệu

Quá trình làm sạch dữ liệu được thực hiện trong Excel để chuẩn bị cho
việc phân tích.

Các bước chính:

-   Xóa các dòng trống
-   Sửa các kiểu dữ liệu không đúng
-   Xử lý các giá trị **UNKNOWN**
-   Kiểm tra lại phép tính của cột **Total Spent**
-   Chuẩn hóa các giá trị dạng phân loại (payment method, location)
-   Kiểm tra giá trị thiếu và các điểm không nhất quán

Sau khi làm sạch, dataset trở nên phù hợp cho việc phân tích.

------------------------------------------------------------------------

## 5. Các Câu Hỏi Phân Tích

Các câu hỏi được sử dụng trong quá trình phân tích:

1.  **Tổng doanh thu** của quán cà phê là bao nhiêu?
2.  **Sản phẩm nào tạo ra nhiều doanh thu nhất?**
3.  **Sản phẩm nào bán được nhiều nhất (theo số lượng)?**
4.  **Doanh thu thay đổi như thế nào theo thời gian?**
5.  **Trung bình mỗi ngày bán được bao nhiêu sản phẩm?**
6.  **Phương thức thanh toán nào được sử dụng nhiều nhất?**
7.  **Sự khác biệt giữa doanh thu tại quán và mang đi là gì?**

------------------------------------------------------------------------

## 6. Phân Tích Pivot Table

Một số Pivot Table đã được tạo để tổng hợp dữ liệu:

-   Doanh thu theo sản phẩm
-   Số lượng bán theo sản phẩm
-   Doanh thu theo phương thức thanh toán
-   Doanh thu theo địa điểm (tại quán / mang đi)
-   Doanh thu theo ngày

Pivot Table giúp nhanh chóng phát hiện xu hướng và mẫu dữ liệu trong
dataset.

------------------------------------------------------------------------

## 7. Dashboard

Một dashboard tương tác được xây dựng trong Excel để trực quan hóa kết
quả phân tích.

Các thành phần của dashboard bao gồm:

-   KPI tổng doanh thu
-   Tổng số sản phẩm đã bán
-   Biểu đồ doanh thu theo sản phẩm
-   Biểu đồ doanh thu theo phương thức thanh toán
-   Biểu đồ doanh thu theo địa điểm
-   Xu hướng doanh thu theo thời gian

Dashboard giúp người dùng nhanh chóng hiểu được hiệu suất kinh doanh của
quán cà phê.

------------------------------------------------------------------------

## 8. Insight Chính

Một số insight có thể rút ra từ phân tích:

-   Một số sản phẩm tạo ra doanh thu cao hơn đáng kể so với các sản phẩm
    khác.
-   Một số phương thức thanh toán được khách hàng sử dụng thường xuyên
    hơn.
-   Mô hình bán hàng có sự khác biệt giữa **mua tại quán và mang đi**.
-   Doanh thu biến động theo thời gian, cho thấy có thể tồn tại các
    **thời điểm nhu cầu cao**.

Những insight này có thể giúp quán cà phê cải thiện chiến lược sản phẩm
và hoạt động kinh doanh.

------------------------------------------------------------------------

## 9. Công Cụ Sử Dụng

-   **Microsoft Excel**
    -   Data Cleaning
    -   Pivot Tables
    -   Charts
    -   Dashboard Design

------------------------------------------------------------------------

## 10. Cấu Trúc Dự Án

    coffee-shop-sales-analysis
    │
    ├── dirty_cafe_sales.csv
    ├── Coffee_Shop_Analyst.xlsx
    └── README.md

------------------------------------------------------------------------

## 11. Tác Giả

Dự án Data Analyst -- Bài tập xây dựng Portfolio
