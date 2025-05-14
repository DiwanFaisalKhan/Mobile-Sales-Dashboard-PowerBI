# Mobile-Sales-Dashboard-PowerBI

Project Overview

This project is a complete Mobile Sales Dashboard designed in Power BI, providing detailed insights into mobile sales data using advanced DAX measures, interactive visuals, and dynamic page navigation.

Key Features

	Advanced DAX Measures including:

	MTD (Month-to-Date) Sales

	QTD (Quarter-to-Date) Sales

	YTD (Year-to-Date) Sales

	Same Period Last Year Sales

	Total Sales, Total Transactions, Average Price, and Total Quantity

	Customer Rating Status Calculation


	Dynamic Data Filtering with slicers for:

	Mobile Model

	Payment Method

	Brand


	Comprehensive Data Visualizations:

	Map visualization for sales by city.

	Line chart for total sales trend over months.

	Bar charts for rating analysis and mobile model sales.

	Pie chart for payment method distribution.

•	Page Navigation for seamless user experience.


 DAX Measures Used
 
	Total Sales:
Total_Sales = SUMX(Mobile_Sales_Data, Mobile_Sales_Data[Units Sold] * Mobile_Sales_Data[Price Per Unit])

	Total Transactions:
Transactions = COUNT(Mobile_Sales_Data[Transaction ID])

	Average Price:
Average_Price = AVERAGE(Mobile_Sales_Data[Price Per Unit])

	Total Quantity:
Total_Quantity = SUM(Mobile_Sales_Data[Units Sold])

	MTD Sales:
MTD_REPORT = TOTALMTD([Total_Sales], Custom_Calender[Date].[Date])

	QTD Sales:
QTD_REPORT = TOTALQTD([Total_Sales], Custom_Calender[Date].[Date])

	YTD Sales:
YTD_REPORT = TOTALYTD([Total_Sales], Custom_Calender[Date].[Date])

	Same Period Last Year Sales:
Same_Period_Last_Year = CALCULATE([Total_Sales], SAMEPERIODLASTYEAR(Custom_Calender[Date].[Date]))


	Customer Rating Status (Calculated Column):

•Rating_Status = IF(Mobile_Sales_Data[Customer Ratings]>=4,"Good",
IF(Mobile_Sales_Data[Customer Ratings]>2,"Average","Poor"))

How to Use

	Use the slicers to filter data based on Mobile Model, Payment Method, and Brand.

	Switch between pages using the page navigator.

	View sales trends, ratings, and other KPIs directly from the dashboard.

