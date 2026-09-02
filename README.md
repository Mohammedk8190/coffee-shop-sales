
**Coffee Shop Sales – Power BI Dashboard**

**Project Overview**

This Power BI project provides a complete analysis of Coffee Shop Sales across multiple outlets.
The dashboard helps business stakeholders understand trends in revenue, customer behavior, and product performance to support data-driven decision making.

**Project Objective**

The primary goal of this dashboard is to analyze sales and uncover insights such as:

How much total revenue the coffee shop generated

Which products or categories perform best

What days and hours have the highest sales

Which store locations contribute the most revenue

Monthly and daily sales patterns

Customer purchase behaviours

**Tools & Technologies Used**
Tool	Purpose
Power BI Desktop	Data modeling, transformation, dashboards
Power Query Editor	Cleaning & transforming datasets
DAX (Data Analysis Expressions)	Calculated columns and measures
Excel / CSV	Source data for transactions
**Repository Structure**
Coffee-Shop-Sales
│
├── COFFEE SHOP SALES.pbix              # Power BI Dashboard file
├── README.md                           # Project documentation
├── /Images                             # Dashboard screenshots
│     ├── dashboard-overview.png
│     ├── kpi-section.png
│     └── sales-trend.png
└── /Documentation                      # Technical documentation
      ├── Data_Dictionary.md
      ├── Insights.md
      └── DAX_Measures.md

**Dashboard Features**

**1. KPI Cards**

Total Sales

Total Orders

Total Quantity Sold

Avg Bill per Customer

Provides clear business performance at a glance.

**2. Sales Trend Analysis**

Includes:

Daily sales trend

Monthly sales comparison

Peaks & dips in sales

Helps understand performance over time.

**3. Product Performance**

Shows:

Sales by product

Contribution by product category

Best-selling items

Useful for inventory planning and product strategy.

**4. Store Location Analysis**

Compares all store branches to identify:

Top performing locations

Slow-moving branches

Location-based revenue differences

**5. Sales by Hour & Weekday/Weekend**

Displays:

Hourly heatmap

Time-of-day sales

Weekday vs weekend comparison

Great for staffing and scheduling optimization.

**Data Cleaning & Transformation**

Performed in Power Query:

Removed empty rows & duplicates

Fixed incorrect data types

Added new calculated fields:

Revenue = unit_price × quantity

Month Name

Day Type (Weekday/Weekend)

Hour of Transaction

**Data Model (Star Schema)**
     Product Dimension
            │
     Store Dimension
            │
 Date Dimension ───► FACT TABLE (Transactions)


This improves performance and enables time-intelligence calculations.

**Key DAX Measures**

Some important DAX measures used:

Total Sales = SUM(Transactions[unit_price] * Transactions[transaction_qty])

Total Orders = DISTINCTCOUNT(Transactions[transaction_id])

Total Quantity Sold = SUM(Transactions[transaction_qty])

Avg Bill Per Customer = DIVIDE([Total Sales], [Total Orders])


All DAX formulas are included inside:
📄 /Documentation/DAX_Measures.md

**Key Insights**

Morning hours (7 AM – 11 AM) show the highest activity

Weekends generate more sales than weekdays

Brewed coffee and espresso are top-selling categories

Location performance varies significantly

Certain days show strong seasonal patterns

**Business Recommendations**

Increase staffing during peak morning hours

Promote high-margin bakery items with combos

Improve inventory for best-selling items

Focus marketing campaigns on low-performing stores

Use seasonal trends to plan marketing and stock

**How to Use This Project**

Download the .pbix file

Open in Power BI Desktop

Refresh data if using updated dataset

Explore insights interactively

**Connect With Me**

If you want collaboration or dashboards like this:

LinkedIn: www.linkedin.com/in/mohammed-k-40a78a2a4
GitHub: https://github.com/Mohammedk8190/
