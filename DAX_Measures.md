
DAX Measures Used

•Total Sales:
Total_Sales = SUMX(Mobile_Sales_Data, Mobile_Sales_Data[Units Sold] * Mobile_Sales_Data[Price Per Unit])

•Total Transactions:
Transactions = COUNT(Mobile_Sales_Data[Transaction ID])

•Average Price:
Average_Price = AVERAGE(Mobile_Sales_Data[Price Per Unit])

•Total Quantity:
Total_Quantity = SUM(Mobile_Sales_Data[Units Sold])

•MTD Sales:
MTD_REPORT = TOTALMTD([Total_Sales], Custom_Calender[Date].[Date])

•QTD Sales:
QTD_REPORT = TOTALQTD([Total_Sales], Custom_Calender[Date].[Date])

•YTD Sales:
YTD_REPORT = TOTALYTD([Total_Sales], Custom_Calender[Date].[Date])

•Same Period Last Year Sales:
Same_Period_Last_Year = CALCULATE([Total_Sales], SAMEPERIODLASTYEAR(Custom_Calender[Date].[Date]))


Customer Rating Status (Calculated Column):
•Rating_Status = IF(Mobile_Sales_Data[Customer Ratings]>=4,"Good",
IF(Mobile_Sales_Data[Customer Ratings]>2,"Average","Poor"))
