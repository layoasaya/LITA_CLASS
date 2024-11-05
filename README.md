# LITA_CLASS_DOCUMENTATIONS
## PROJECT

### Project Overview
This data analysis project represents the culmination of a 3-month intensive course aimed at building fundamental and advanced skills in data analysis. The project showcases skills in data wrangling, database management, visualization, and insights generation through tools like Microsoft Excel, SQL Server (SQL Server Management Studio) and Power BI. This project is structured to provide insights into the journey, learning outcomes, and the applied knowledge gathered throughout the course.


## Table of Contents

1. Course Overview and Goals
2. Course Duration
3. Tools Used
4. Learning Outcomes and Skills
5. Tests and Assignments
6. Detailed Analysis
- Data Collection and Preprocessing
- Data Cleaning and Transformation
- Data Visualization and Insights
7. Practical and code used
8. Conclusion and Future Work



----
### 1. Course Overview and Goals

The primary goal of this course was to develop a deep understanding of data analysis and the tools used by data analysts to extract, process, and visualize data. Over the three-month period, I was introduced to various data analysis techniques, which equipped me with essential skills to:

Conduct exploratory data analysis (EDA).

Manage and query data effectively using SQL.

Design dashboards and visualizations that communicate insights clearly and effectively.

Solve real-world data analysis problems that are valuable for business decision-making.


### 2. Course Duration

Duration: 3 Months
Class Frequency: 3 times per week
Class Hours: 2 hours per session


### 3. Tools Used

The tools learned and applied in this course are essential for data analysts in industry:

1. Microsoft Excel [DOWNLOAD HERE](https://www.microsoft.com).
  - For data cleaning, exploratory data analysis, and basic visualizations.


2. SQL Server SSMS [DOWNLOAD HERE](https://www.microsoft.com/en-us/sql-server/sql-server-downloads?msockid=0bc67129e9ea6da0170a6561e8b66c4d).
 - For data management, querying, and database operations.


3. Power BI [DOWNLOAD HERE](https://apps.microsoft.com/detail/9ntxr16hnw1t?launch=true&mode=full&hl=en-us&gl=ng&ocid=bingwebsearch).
 - For creating professional dashboards and data visualizations to support decision-making.
 


### 4. Learning Outcomes and Skills

The project emphasizes the following skills:

1. Data Cleaning and Transformation: Proficiency in data wrangling and transforming raw data for analysis.
2. Data Querying: Skilled in writing SQL queries to retrieve, filter, and manipulate data for various purposes.
3. Data Visualization: Ability to create informative, interactive visualizations and dashboards in Power BI.
4. Analytical Thinking: Applying logical approaches to solve data-related challenges and interpret trends.


### 5. Tests and Assignments

Each course segment concluded with practical assessments hosted on our LMS (Canvas) to test comprehension and application skills. Here’s a summary:

A. Excel Module:
 Test: Focused on data wrangling, pivot tables, conditional formatting, and creating basic charts.
 Assignments: Involved cleaning datasets, using formulas, and performing basic statistical analysis.


B. SQL Module:
 Test: Examined querying skills, including joins, aggregations, and subqueries.
 Assignments: Involved working with a relational database to extract meaningful information from structured datasets.


C. Power BI Module:
 Test: Assessed the ability to create dashboards and interpret data visualizations.
 Assignments: Required building a dashboard with multiple charts and providing insights based on visualization.



---

### 6. Detailed Analysis
This section includes a step-by-step breakdown of the data analysis workflow followed during the course, complete with examples and visuals.
- Data Collection and Preprocessing
Data Sources: Outline the types of data used (e.g., sample business datasets, customer data, etc.).

Data Import and Storage: Show how data was imported using Excel and SQL Server SSMS. Discuss methods for handling different data types and formats.


- Data Cleaning and Transformation
Steps Taken: Document the data cleaning process—e.g., removing duplicates, handling missing values, and formatting inconsistencies.

Tools: Use screenshots or code snippets to demonstrate the cleaning and transformation steps in Excel and SQL.


- Data Visualization and Insights
Power BI Dashboards: Include screenshots and descriptions of each visualization (e.g., bar charts, line graphs, heat maps).

Insights Generated: Present findings with explanations, such as key trends, patterns, or anomalies. Example: "Sales increased by 15% quarter-over-quarter, with a marked spike in Q2 due to promotional campaigns."



---

### 7. Practicals and Codes Used
  Here are some code snippet used during our training;
```Excel Code Snippets
Data Cleaning with Excel Formulas

This snippet demonstrates how to clean a dataset by removing duplicates and filling in missing values.
excel
Copy code
' Remove duplicates from a range
Sub RemoveDuplicates()
    Dim rng As Range
    Set rng = ThisWorkbook.Sheets("Sheet1").Range("A1:C100")
    rng.RemoveDuplicates Columns:=1, Header:=xlYes
End Sub

' Fill down missing values in Column A
Sub FillDownMissingValues()
    Dim lastRow As Long
    lastRow = ThisWorkbook.Sheets("Sheet1").Cells(Rows.Count, 1).End(xlUp).Row
    ThisWorkbook.Sheets("Sheet1").Range("A2:A" & lastRow).SpecialCells(xlCellTypeBlanks).FormulaR1C1 = "=R[-1]C"
End Sub
Creating Pivot Table

This snippet creates a pivot table from a dataset.
excel
Copy code
Sub CreatePivotTable()
    Dim ws As Worksheet
    Dim ptCache As PivotCache
    Dim pt As PivotTable
    Dim dataRange As Range
    Set ws = ThisWorkbook.Sheets("Data")
    Set dataRange = ws.Range("A1:D100") ' Adjust the range as necessary
    
    Set ptCache = ThisWorkbook.PivotCaches.Create(SourceType:=xlDatabase, SourceData:=dataRange)
    Set pt = ptCache.CreatePivotTable(TableDestination:=ThisWorkbook.Sheets("PivotTable").Range("A1"))
    
    With pt
        .PivotFields("Category").Orientation = xlRowField
        .PivotFields("Sales").Orientation = xlDataField
        .PivotFields("Date").Orientation = xlColumnField
    End With
End Sub
SQL Code Snippets
Selecting and Filtering Data

This SQL query retrieves specific columns from a table and filters the results.
sql
Copy code
SELECT ProductID, ProductName, Price
FROM Products
WHERE Price > 20 AND StockQuantity > 0
ORDER BY Price DESC;
Creating a New Table and Inserting Data

This snippet demonstrates how to create a new table and insert records into it.
sql
Copy code
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    OrderDate DATE,
    TotalAmount DECIMAL(10, 2)
);

INSERT INTO Orders (OrderID, CustomerID, OrderDate, TotalAmount)
VALUES (1, 101, '2024-11-01', 150.75),
       (2, 102, '2024-11-02', 245.50),
       (3, 103, '2024-11-03', 99.99);
Using JOIN to Combine Data

This snippet demonstrates how to join two tables to get related data.
sql
Copy code
SELECT o.OrderID, c.CustomerName, o.TotalAmount
FROM Orders o
INNER JOIN Customers c ON o.CustomerID = c.CustomerID
WHERE o.OrderDate >= '2024-11-01';
Power BI Code Snippets (DAX)
Creating a Calculated Column

This DAX formula creates a new column in a table to calculate the total sales.
dax
Copy code
TotalSales = Sales[Quantity] * Sales[Price]
Creating a Measure for Total Revenue

This DAX measure calculates total revenue, which can be used in visualizations.
dax
Copy code
TotalRevenue = SUM(Sales[TotalSales])
Filtering Data in a Measure

This measure calculates total revenue for a specific product category.
dax
Copy code
RevenueForCategory = 
CALCULATE(
    SUM(Sales[TotalSales]),
    Products[Category] = "Electronics"
)
---

### 8. Conclusion and Future Work

This project provided a comprehensive analysis of key data using various analytical tools such as Microsoft Excel, SQL, and Power BI. Throughout the process, I demonstrated proficiency in data cleaning, data visualization, and creating meaningful insights from complex datasets. Key tasks included designing pivot tables in Excel to summarize data trends, writing SQL queries for efficient data extraction and manipulation, and utilizing DAX formulas in Power BI to create measures and calculated columns that facilitated deeper analysis. The project culminated in the presentation of actionable insights, showing my ability to transform raw data into clear, decision-driving visualizations and reports.



---

Repository Structure
To make the repository navigable:
README.md: This file provides an overview, background, and instructions for readers.
Data Files: Folder containing cleaned sample data files.
SQL Scripts: Folder containing SQL queries used in analysis.
Power BI Dashboards: Folder with Power BI files or screenshots.


Final Notes

This comprehensive setup, with well-organized sections, rich explanations, and visuals, will enhance readability and showcase your data analysis skills effectively.

