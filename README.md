# Data-Analysis-Expressions-DAX-introduction
This is an introduction to get in touch with basic DAX  uses


### What is DAX ? 
DAX stands for Data Analysis Expressions, and it is a formula language used in Microsoft Power BI, Power Pivot for Excel, and SQL Server Analysis Services (SSAS) Tabular mode. It is designed to work with relational and tabular data from various sources, including databases, spreadsheets, and text files.
DAX is used to create custom calculations, also known as measures, which can be used in reports and visualizations. 

Formulas in DAX are based on functions and operators, and they are similar in syntax to Excel formulas. However,functions are designed to work with column values, not just individual cells, and they are optimized for performance in large datasets.
It allows users to create complex calculations, such as aggregations, percentages, and time intelligence, which are not possible with standard aggregation functions in SQL or Excel. It also provides a rich set of functions for data manipulation and analysis, including filtering, ranking, and conditional logic.

Overall, DAX is a powerful tool for data analysis and reporting, especially for users working with large datasets or complex calculations.


### General  uses categories : 

#### 1)Calculated Columns:
DAX can be used to create calculated columns in a table based on the values of other columns in the same table. Calculated columns can be used for various purposes, such as creating hierarchies, concatenating columns, or performing calculations on data that is not available in the source data.
 * Creating a column to concatenate the values of two columns: `FullName = [FirstName] & " " & [LastName]`
 * Creating a column to calculate the profit margin of each product: `ProfitMargin = ([Revenue] - [Cost]) / [Revenue]`


#### 2))Measures: 
DAX is often used to create measures, which are used to aggregate data in a table. Measures can be used to calculate sums, averages, minimum and maximum values, and other types of aggregations. DAX measures can also be used to calculate percentages, ratios, and other types of complex calculations.

 * Creating a measure to calculate the total sales amount: `TotalSales = SUM([SalesAmount])`
 * Creating a measure to calculate the average price per unit: `AvgPricePerUnit = [TotalSales] / SUM([UnitsSold])`

#### 3)Time Intelligence: 
DAX includes a set of functions that enable time-based analysis, such as calculating year-to-date, quarter-to-date, and month-to-date totals, comparing values across different time periods, and calculating moving averages.

* Creating a measure to calculate year-to-date sales: `YTD Sales = TOTALYTD([SalesAmount], 'Date'[Date])`
* Creating a measure to calculate the percentage change in sales compared to the same period last year: `YoY Sales Growth = ([TotalSales] - CALCULATE([TotalSales], SAMEPERIODLASTYEAR('Date'[Date]))) / CALCULATE([TotalSales], SAMEPERIODLASTYEAR('Date'[Date]))`

#### 4)Filter and Summarize Data:
DAX can be used to filter data and summarize it in various ways. For example, DAX can be used to calculate the top or bottom values, create conditional statements, or apply filters to data.

* Creating a measure to calculate the maximum sales amount for a specific product category: `MaxSalesAmount = MAXX(FILTER('Sales', [ProductCategory] = "Clothing"), [SalesAmount])`
* Creating a measure to calculate the total sales amount for a specific region: `RegionSales = CALCULATE([TotalSales], 'Sales'[Region] = "North")`

#### 5)Data Modeling:
DAX is also used for data modeling in Power BI, Excel, and SQL Server Analysis Services. Data modeling involves creating relationships between tables, defining calculated columns and measures, and creating hierarchies and other structures that enable data analysis and reporting.

* Creating a calculated table to filter the products with sales greater than a specified value:
`ProductsWithSalesGreaterThan = FILTER('Product', CALCULATE(SUM('Sales'[SalesAmount])) > 100000)`

* Creating a hierarchy to group products by category and subcategory: `[Product Hierarchy] = PATH('Product'[Category], 'Product'[Subcategory])`
