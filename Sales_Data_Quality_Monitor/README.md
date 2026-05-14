## Project: Sales & Data Quality Monitor – Dirty Sales Data 4
This project demonstrates how to clean, transform, validate, and analyze poorly structured sales data using Power Query, Power BI, and data quality rules.
The goal is to build a complete, professional Data Quality Monitor that identifies errors, visualizes data issues, and provides insights into sales performance.

# 1. Project Overview
The dataset (“Dirty Sales Data 4”) contains sales information in a badly structured, matrix‑style format, where:

shipping modes and customer segments are spread across multiple columns,

dates and values require cleaning,

some records contain intentionally added errors (missing values, negative amounts, missing dates).

The project transforms this dataset into a clean, analytical model and builds a dashboard that monitors both sales metrics and data quality issues.

# 2. Technologies Used
Power BI Desktop

Power Query (M language)

DAX (Data Analysis Expressions)

Excel (source file)

# 3. Data Cleaning & Transformation (Power Query)
Key transformation steps:

Converted matrix‑style data into a long format using Unpivot Other Columns

Split combined column names into:

Ship Mode

Segment

Standardized data types (Date, Text, Decimal)

Added a calculated column ErrorType to classify data issues:

Missing Amount

Negative Amount

Missing Date

Missing Ship Mode

No Error

These rules simulate real‑world data validation logic used in ETL processes.

# 4. Dashboard Features (Power BI)
The report includes:

KPI Cards
Total Rows

Error Rows

Error Rate %

Total Sales

Data Quality Visuals
Rows by Error Type (bar chart)

Error Records Table filtered to show only invalid rows

Sales Analysis
Sales by Segment & Ship Mode (stacked bar chart)

Sales by Segment (bar chart)

Filters (Slicers)
Ship Mode

Segment

Order Date (Year → Month hierarchy)

# 5. DAX Measures
Key measures used in the report:

DAX
Total Rows = COUNTROWS('Dirty 4')

Error Rows =
CALCULATE(
    COUNTROWS('Dirty 4'),
    'Dirty 4'[ErrorType] <> "No Error"
)

Valid Rows = [Total Rows] - [Error Rows]

Error Rate % = DIVIDE([Error Rows], [Total Rows])

Total Sales = SUM('Dirty 4'[Amount])
# 6. What This Project Demonstrates
This project showcases:

Data cleaning and restructuring skills

Building validation logic for data quality

Designing a clear, professional BI dashboard

Using DAX to create KPIs and metrics

Applying slicers, hierarchies, and interactive visuals

Presenting both data quality and business insights in one report

It is an excellent example of combining ETL thinking, data validation, and Power BI reporting.

# 7. Repository Contents
Dirty Sales Data 4.xlsx – source dataset

Power BI report (.pbix)

Screenshots of the dashboard

README (this file)

# 8. Future Improvements
Possible extensions:

Automated refresh using Power Automate

Email alerts when new errors appear

Additional validation rules

Integration with a clean “gold” dataset
