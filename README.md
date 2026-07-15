# 📊 Sales Performance Dashboard | Tableau
## Overview

This project presents an interactive Tableau dashboard that analyzes sales performance and customer behavior using transactional sales data. The dashboard is designed to help sales managers, executives, and marketing teams monitor business performance, identify trends, and support data-driven decision-making.

The project consists of two interactive dashboards:

- Sales Dashboard
- Customer Dashboard

## Business Problem

Organizations need a quick and interactive way to monitor sales performance and customer behavior across different regions and product categories. Static reports make it difficult to identify trends, compare year-over-year performance, and understand customer purchasing patterns.

## Technical Highlights
- Developed Year-over-Year KPI comparisons
- Built dynamic dashboards with interactive filters
- Created calculated fields for Sales per Customer and Profit Margin
- Used dashboard actions for cross-filtering between visualizations
- Implemented dynamic year selection for historical analysis
- Designed KPI cards with monthly trend analysis

## 🛠️ Tools

### Data Source :

Dataset composition :
- `Customers.csv` - consist of customer ID and customer name
- `Location.csv` - consist of address (postal code, city, state, region, country
- `Orders.csv` - consist of order ID, order date, shipping date, customer ID, postal code, product ID, sales, quantity, profit
- `Products.csv` - consist of product ID, category, subcategory, product name

### Tools :
- **Tableau** : Data visualization and business intelligence dahsboard
- **CSV data files** : Standardized data format for analysis and integration

## Dashboard 1 — Sales Performance
<img width="1199" height="799" alt="Sales Dashboard" src="https://github.com/user-attachments/assets/3db2b55d-9804-4431-9530-eedbf057d01b" />
[Tableau Sales Dashboard](https://public.tableau.com/app/profile/nur.izyan.bolhan/viz/SalesCustomersDashboard_17809323886830/SalesDashboard)

### KPI Overview
- Displays current year and previous year performance for total sales, total profit, total quantity sold, sales trend
- Monthly comparison of sales, profit, quantity

Key Features:
- Current Year vs Previous Year
- Highest-performing month
- Lowest-performing month
- Product Subcategory Analysis
- Sales & Profit Weekly Trends Over Time

## Dashboard 2 — Customer Trend Analysis
<img width="1199" height="799" alt="Customers Dashboard" src="https://github.com/user-attachments/assets/24d04d28-da12-4a10-b018-9d6991639d6c" />
[Tableau Customer Dashboard](https://public.tableau.com/app/profile/nur.izyan.bolhan/viz/SalesCustomersDashboard_17809323886830/CustomersDashboard)

### KPI Overview
- Displays total customers, sales per customer, total orders
- Comparison between current year and previous year.

Key Features:
- Best Month
- Lowest Month
- Customer Distribution

The dashboard includes several interactive capabilities:
- Year Selector
- Dashboard Navigation
- Interactive Charts
- Cross Filtering
- Category Filter
- Subcategory Filter
- Region Filter
- State Filter
- City Filter

## Tableau Calculated Fields

| Calculated Field | Formula |
|-----------------|---------|
| % Diff Orders | (COUNTD([CY Orders]) - COUNTD([PY Orders])) / COUNTD([PY Orders]) |
| % Diff Sales per Customer | ([CY Sales per Customer] - [PY Sales per Customer]) / [PY Sales per Customer] |
| % Diff Customers | (COUNTD([CY Customers]) - COUNTD([PY Customers])) / COUNTD([PY Customers]) |
| % Diff Profit | (SUM ([CY Profit])- SUM ([PY Profit]))/(SUM ([PY Profit])) |
| % Diff Quantity | (SUM ([CY Quantity])- SUM ([PY Quantity]))/(SUM ([PY Quantity])) |
| % Diff Sales | (SUM ([CY Sales])- SUM ([PY Sales]))/(SUM ([PY Sales])) |
| CY Sales per Customer | SUM ([CY Sales])/COUNTD ([CY Customers]) |
| CY Total Customers | COUNTD ([CY Customers]) |
| CY Total Orders | COUNTD ([CY Orders]) |
| KPI CY less than PY | IF SUM ([CY Sales]) < SUM ([PY Sales]) THEN '⬤' ELSE '' END |
| KPI Profit Avg | IF  SUM ([CY Profit]) > WINDOW_AVG (SUM([CY Profit])) THEN 'above' ELSE 'below' END |
| KPI Sales Avg | IF  SUM ([CY Sales]) > WINDOW_AVG (SUM([CY Sales])) THEN 'above' ELSE 'below' END |
| Min/Max Customers | IF COUNTD ([CY Customers]) = WINDOW_MAX (COUNTD([CY Customers])) THEN COUNTD ([CY Customers]) ELSEIF COUNTD ([CY Customers]) = WINDOW_MIN (COUNTD([CY Customers])) THEN COUNTD ([CY Customers]) END |
| Min/Max Orders | IF COUNTD ([CY Orders]) = WINDOW_MAX (COUNTD([CY Orders])) THEN COUNTD ([CY Orders]) ELSEIF COUNTD ([CY Orders]) = WINDOW_MIN (COUNTD([CY Orders])) THEN COUNTD ([CY Orders]) END |
| Min/Max Profit | IF SUM ([CY Profit]) = WINDOW_MAX (SUM([CY Profit])) THEN SUM ([CY Profit]) ELSEIF SUM ([CY Profit]) = WINDOW_MIN (SUM([CY Profit])) THEN SUM ([CY Profit]) END |
| Min/Max Quantity | IF SUM ([CY Quantity]) = WINDOW_MAX (SUM([CY Quantity])) THEN SUM ([CY Quantity]) ELSEIF SUM ([CY Quantity]) = WINDOW_MIN (SUM([CY Quantity])) THEN SUM ([CY Quantity]) END |
| Min/Max Sales | IF SUM ([CY Sales]) = WINDOW_MAX (SUM([CY Sales])) THEN SUM ([CY Sales]) ELSEIF SUM ([CY Sales]) = WINDOW_MIN (SUM([CY Sales])) THEN SUM ([CY Sales]) END |
| Min/Max Sales per Customer | IF  ([CY Sales per Customer]) = WINDOW_MAX (([CY Sales per Customer])) THEN  ([CY Sales per Customer]) ELSEIF ([CY Sales per Customer]) = WINDOW_MIN (([CY Sales per Customer])) THEN  ([CY Sales per Customer]) END |
| PY Sales per Customer | SUM ([PY Sales])/COUNTD ([PY Customers]) |
| PY Total Customers | COUNTD ([PY Customers]) |
| PY Total Orders | COUNTD ([PY Orders]) |
| Total Customers | Count([Customer ID]) |




## Key Insights
1. Sales performance improved significantly in 2023, with total sales increasing by 20.4% compared to 2022, indicating strong year-over-year business growth.
2. November 2023 recorded the highest monthly sales revenue, making it the strongest-performing month of the year.
3. The Copiers category generated the highest profit, contributing approximately $63K, making it the most profitable product segment.
4. Raymond Buch was the most profitable customer, generating approximately $6.7K in total profit during the selected period.
5. Several weeks performed above the annual average for both sales and profit, while underperforming weeks may indicate seasonal slowdowns or operational opportunities.
6. A smaller group of repeat customers accounted for multiple purchases, highlighting the importance of customer loyalty initiatives.
7. The total number of customers increased year-over-year, reflecting successful customer acquisition efforts.

## Business Recommendations
1. Revenue Growth : Increase investment in high-performing products, particularly the Copiers subcategory, through targeted promotions and strategic inventory planning to maximize profit.
2. Customer Strategy : Develop customer retention initiatives focused on high-value customers while identifying characteristics shared by top-profit customers to support acquisition of similar customer segments.
3. Seasonal Planning : Align marketing campaigns and inventory planning with seasonal demand, especially ahead of November, to capitalize on historical sales peaks.
4. Product Portfolio Optimization : Evaluate underperforming product subcategories to determine whether pricing adjustments, promotional campaigns, or product rationalization could improve profitability.
5. Performance Monitoring :Track weekly sales and profit trends to detect performance fluctuations early and enable timely business interventions.
