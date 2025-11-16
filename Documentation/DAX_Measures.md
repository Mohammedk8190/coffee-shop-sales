## 📌 1. Revenue & Sales Measures
🔹 Total Sales
Total Sales = SUM(Transactions[unit_price] * Transactions[transaction_qty])

🔹 Total Quantity Sold
Total Quantity Sold = SUM(Transactions[transaction_qty])

🔹 Total Orders
Total Orders = DISTINCTCOUNT(Transactions[transaction_id])

🔹 Average Selling Price (ASP)
Average Selling Price = DIVIDE([Total Sales], [Total Quantity Sold])

🔹 Avg Bill Per Customer
Avg Bill Per Customer = DIVIDE([Total Sales], [Total Orders])

## 📌 2. Date & Time Measures
🔹 Sales by Hour
Hour = HOUR(Transactions[transaction_time])

🔹 Sales by Weekday / Weekend
Day Type =
IF(
    WEEKDAY(Transactions[transaction_date],2) > 5,
    "Weekend",
    "Weekday"
)

🔹 Month Name
Month Name = FORMAT(Transactions[transaction_date], "MMM")

🔹 Month Number
Month Number = MONTH(Transactions[transaction_date])

🔹 Year
Year = YEAR(Transactions[transaction_date])

## 📌 3. Trend Line Measures (Used in Sales Trend Visual)
🔹 Daily Sales
Daily Sales = 
VAR TotalRevenue =
    SUMX(
        Transactions,
        Transactions[unit_price] * Transactions[transaction_qty]
    )
RETURN
    TotalRevenue

🔹 Average Daily Sales
Average Daily Sales = 
AVERAGEX(
    VALUES(Transactions[transaction_date]),
    [Daily Sales]
)

## 📌 4. Product Category Measures
🔹 Sales by Product Category
Category Sales =
SUMX(
    Transactions,
    Transactions[unit_price] * Transactions[transaction_qty]
)

🔹 Top Product by Revenue
Top Product by Revenue =
CALCULATE(
    [Category Sales],
    TOPN(1, Products, [Category Sales], DESC)
)

## 📌 5. Store Location Measures
🔹 Sales by Store Location
Sales by Store =
SUMX(
    Transactions,
    Transactions[unit_price] * Transactions[transaction_qty]
)

🔹 Store Rank by Sales
Store Rank =
RANKX(
    ALL(Stores[store_location]),
    [Sales by Store],
    ,
    DESC
)

## 📌 6. YoY, MoM Performance (Optional Advanced Measures)

If you want to enhance your dashboard later with YoY and MoM:

🔹 Previous Month Sales
Previous Month Sales =
CALCULATE(
    [Total Sales],
    DATEADD(Transactions[transaction_date], -1, MONTH)
)

🔹 Month-over-Month % Change
MoM % Change =
DIVIDE(
    [Total Sales] - [Previous Month Sales],
    [Previous Month Sales]
)

🔹 Previous Year Sales
Previous Year Sales =
CALCULATE(
    [Total Sales],
    DATEADD(Transactions[transaction_date], -1, YEAR)
)

🔹 Year-over-Year % Change
YoY % Change =
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales]
)

## 📌 7. Tooltip Measures (If you use ToolTips Pages)
🔹 Max Sales Day
Max Sales Day =
MAXX(
    VALUES(Transactions[transaction_date]),
    [Daily Sales]
)

🔹 Min Sales Day
Min Sales Day =
MINX(
    VALUES(Transactions[transaction_date]),
    [Daily Sales]
)

