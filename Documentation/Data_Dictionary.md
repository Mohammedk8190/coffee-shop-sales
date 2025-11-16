# Data Dictionary

## Table: Sales
| Column Name     | Data Type | Description |
|-----------------|-----------|-------------|
| Transaction ID  | Text      | Unique transaction identifier |
| Transaction Date| DateTime  | Date and time of sale |
| Store ID        | Text      | Unique store identifier |
| Product ID      | Text      | Product identifier |
| Product Name    | Text      | Product name |
| Category        | Text      | Product category (Coffee/Tea/Bakery) |
| Quantity        | Integer   | Units sold |
| Unit Price      | Decimal   | Price per unit |
| Revenue         | Decimal   | Quantity * Unit Price |

## Table: Store
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| Store ID    | Text      | Unique store identifier |
| Store Name  | Text      | Name of store/location |
| City        | Text      | City |
| Region      | Text      | Region or state |

## Notes
- `Revenue` is calculated inside Power BI as `Quantity * Unit Price`.
- Date column stored as DateTime; use Time/Hour extraction for hourly analysis.

