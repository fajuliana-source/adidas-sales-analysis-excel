# adidas-sales-analysis-excel
An interactive Excel sales dashboard analyzing 2020–2021 Adidas US sales across regions, retailers, product categories, and channels with profit margin tracking.
# Adidas Sales Performance Analysis: Excel Dashboard

[![Tools](https://img.shields.io/badge/Tools-Microsoft_Excel-blue?style=flat-square)](https://github.com)
[![Domain](https://img.shields.io/badge/Domain-Retail_%26_Sales_Analytics-darkblue?style=flat-square)](https://github.com)
[![Dataset](https://img.shields.io/badge/Data_Size-9%2C648_Records-orange?style=flat-square)](https://www.kaggle.com)


![Adidas_overall_view](/adidas_dashboard_overall.png)

## 1. Project Overview

This project analyses Adidas sales performance across the United States using Microsoft Excel.

I prepared the dataset in Power Query, checked for data quality issues, created the necessary calculated fields, and built an interactive dashboard to track sales, profit, units sold, profit margin, regional performance, retailer contribution, product mix, and year-on-year growth.

The dashboard covers two full years of sales (2020 and 2021) and allows filtering by sales method (In-store, Online, and Outlet). The goal was to turn the raw sales records into clear insights that can support decisions around regions, retail partners, product focus, and channel strategy.

## 2. Business Problem

Adidas sells its products through multiple retail partners and sales channels (In-store, Online, and Outlet) across different regions of the United States. With transactions spread across many states, product categories, and retailers, management needs a clear and consolidated view of performance to understand what is truly driving the business.

Without this visibility, strong top-line growth can hide important details. A business can be growing overall while depending too heavily on one region, one product category, or a handful of retail partners. In the same way, sales volume can be increasing in a channel while profit margin is quietly declining. These are the kinds of issues that only become visible when performance is broken down properly.

This project uses two years of Adidas sales data (2020 and 2021) to bring all of this together in one interactive dashboard, making it easier to see where the business is strong, where it is exposed, and where attention or investment may be needed.

## 3. Dataset Description
**Excel Workbook:** [`Adidas_sales_analysis.xlsx`](./Adidas_US_Sales_Datasets.xlsx)
The dataset was sourced from Kaggle and contains Adidas sales transactions across US regions, states, cities, retailers, products, and sales methods for 2020 and 2021.

### Dataset Summary
- Total Records: 9,648
- Timeframe: January 2020 – December 2021
- Geographic Scope: United States (Midwest, Northeast, South, Southeast, West)
- Sales Methods: In-store, Online, Outlet
- Key retailers include Foot Locker, West Gear, Sports Direct, Kohl’s, Walmart, and Amazon

| Field | Description |
|---|---|
| Retailer | Name of the retail partner |
| Retailer ID | Unique retailer identifier |
| Invoice Date | Date of the sales transaction |
| Region | US region (Midwest, Northeast, South, Southeast, West) |
| State | US state |
| City | City of sale |
| Product | Product category (e.g. Men’s Street Footwear, Men’s Athletic Footwear, Women’s Apparel) |
| Price per Unit | Selling price per unit |
| Units Sold | Number of units sold |
| Total Sales | Revenue from the transaction |
| Operating Profit | Profit from the transaction |
| Operating Margin | Profit margin percentage on the transaction |
| Sales Method | In-store, Online, or Outlet |


## 4. Business Questions

To understand overall business performance and support decision-making, this analysis focuses on answering the following questions:

Executive KPIs
- What is the total gross sales revenue, total operating profit, total units sold, and overall profit margin?
- How did sales, profit, units, and profit margin change year-on-year between 2020 and 2021?

Regional Performance
- Which region generates the highest sales?
- How large is the performance gap between the top-performing region and the others?

Retailer Performance
- Which retail partners sell the highest volume of units?
- Are some retailers performing more efficiently than others relative to their location footprint?

Product Performance
- Which product categories contribute the largest share to total sales?
- How dependent is total revenue on the top-performing product category?

Channel Performance & Profitability
- How do In-store, Online, and Outlet channels compare in total sales, profit, units sold, and profit margin?
- Is fast volume growth in any channel coming at the expense of profit margin percentage?

## 5. Tools and Commands

Microsoft Excel:
Used for data cleaning, transformation, feature engineering, analysis, and interactive dashboard development.

- Power Query:
  - Data ingestion and automated data transformation.
  - Removed blank rows, verified uniqueness, handled errors, and set proper data types.

- Data Preparation & Formulas:
  - Checked raw data integrity and created calculated fields on the analysis sheet.
  - Created a check column (`Profit Margin Check = Operating Profit / Total Sales`) to audit the raw data margin field.
  - Calculated aggregate profit margin percentage using `SUM(Operating Profit) / SUM(Total Sales)` to avoid unweighted averages.

- PivotTables & Aggregations:
  - Built  PivotTables for regional sales, retailer unit volumes, top product sales shares, monthly YoY (Year-on-Year) trends, and channel KPIs.

- Interactive Dashboard Development:
  - Designed a 4-card KPI header (Total Sales, Total Profit, Units Sold, Operating Margin) with YoY growth comparisons.
  - Integrated Slicers for sales channels (In-store, Online, Outlet) connected across all PivotTables.
  - Formatted map visuals, bar charts, donut charts, and year-on-year charts using an Adidas-branded blue visual theme.

## 6. Data Cleaning and Preparation

Data cleaning and preparation were completed in Power Query and Microsoft Excel before building the dashboard.

Step 1: Data Ingestion and Power Query Preparation
- Imported the raw Kaggle dataset into Power Query.
- Filtered out and removed blank rows across the dataset.
- Evaluated key fields for duplicates, uniqueness, and data entry errors.
- Verified that all 9,648 rows contained complete, clean transaction records.

Step 2: Data Type Standardization
Every column was formatted to its strict native data type:
- `Invoice Date`: Set to Short Date (`YYYY-MM-DD`) for time-series and month-over-month analysis.
- `Total Sales`, `Operating Profit`, `Price per Unit`: Formatted as Currency (`$`).
- `Units Sold`: Formatted as Whole Number (`Integer`).
- `Operating Margin`: Formatted as Percentage (`%`).
- `Region`, `State`, `City`, `Retailer`, `Product`, `Sales Method`: Formatted as Text.

Step 3: Data Integrity Audit
- Created an explicit audit column on the data sheet: `Margin_Check = Operating Profit / Total Sales`.
- Reconciled the original `Profit Margin` column against the new `Margin_Check` column to confirm 100% mathematical accuracy across all records.


## 7. Exploratory Data Analysis and Methodology

The analytical methodology followed a 3-stage visual and quantitative workflow:

| Phase | Focus & Activities |
|---|---|
| **Phase 1: Analytical Modeling & Metric Setup** | • created  `ANALYSIS` worksheet to separate raw data from calculations.<br>• calculated weighted Profit Margin formulas (`SUM(Operating Profit) / SUM(Total Sales)`) to avoid mathematical averaging bias.<br>• Created Year-over-Year (YoY) comparison logic for Sales, Profit, Units, and Margins between 2020 and 2021. |
| ↓ | **Followed by Phase 2: Analysis** |
| **Phase 2:  Analysis** | • Aggregated sales distribution across US regions to evaluate regional revenue contribution.<br>• Analyzed transaction order frequency across retail partners to assess partner activity.<br>• Evaluated product category  to measure revenue concentration risks.<br>• Tracked monthly sales trends across 2020 and 2021 to identify seasonal patterns and baseline operational gaps. |
| ↓ | **Followed by Phase 3: Results visualization** |
| **Phase 3: Interactive Dashboard Build** | • Designed a 4-card executive KPI header with YoY growth indicators.<br>• Integrated channel Slicers (In-store, Online, Outlet) connected dynamically across all PivotTables.<br>• Formatted US map visuals, bar charts, donut charts, and trend lines using an Adidas navy blue visual 

## 8. Dashboard, Key Findings and Business Interpretation

The interactive dashboard uses an Adidas-branded navy blue visual theme with high-contrast card containers, clear chart labels, and channel slicers.

### A. Overall Business Performance (All Channels Combined)

Over the 2-year period (2020–2021), the business generated $899.9M in total sales across 9,648 transaction records.

![Adidas_overall_view](/adidas_dashboard_overall.png)

| Performance Metric | 2020 (PY) | 2021 (CY) | Total / Overall | YoY Growth (%) |
|---|---:|---:|---:|---:|
| **Total Sales Revenue** | $83.7M | $211.9M | **$899.9M** | **+294%** |
| **Total Operating Profit** | $29.7M | $78.3M | **$332.1M** | **+324%** |
| **Total Units Sold** | 218,689 | 631,089 | **2,478,861** | **+336%** |
| **Overall Profit Margin** | 35.5% | 37.0% | **36.9%** | **+2.6pp** |
| **Top Region by Sales** | - | - | **West ($269.9M)** | - |
| **Top Product Share** | - | - | **Men's Street Footwear (39%)** | - |
| **Top Retailer by Transactions** | - | - | **Foot Locker (2,637)** | - |

Both revenue and profitability expanded significantly in 2021 compared to 2020, with profit margin improving by 2.6 percentage points overall.

### B. Regional Performance: The West Region Gap

Sales distribution across US regions reveals a strong geographic concentration:

| Region | Total Sales ($) |
|---|---:|
| **West** | **$269.9M** |
| **Northeast** | **$186.3M** |
| **Southeast** | **$163.2M** |
| **South** | **$144.7M** |
| **Midwest** | **$135.8M** |

The West region generated $269.9M in sales—nearly double the Midwest region ($135.8M). This gap shows that overall corporate growth is being carried heavily by the West, meaning strategies working in the West need to be analyzed before assuming they can be applied identically to other regions.

### C. Retailer Activity & Efficiency

Retailer performance was measured by transaction order volume across 2020–2021:

| Retailer Partner | Transaction Count (Invoices) |
|---|---:|
| **Foot Locker** | **2,637** |
| **West Gear** | **2,374** |
| **Sports Direct** | **2,032** |
| **Kohl's** | **1,030** |
| **Amazon** | **949** |
| **Walmart** | **626** |

Foot Locker generated the highest transaction frequency (2,637 orders). West Gear followed closely behind at 2,374 transactions while operating across fewer store footprints, indicating high sales efficiency and strong per-location productivity.

### D. Product Mix & Risk Exposure

Sales share among the top 3 product categories shows significant revenue dependence:

| Product Category | Sales Share (%) |
|---|---:|
| **Men's Street Footwear** | **39%** |
| **Women's Apparel** | **33%** |
| **Men's Athletic Footwear** | **28%** |

Men's Street Footwear alone accounts for 39% of total revenue. While this category is the primary growth engine, relying heavily on a single product line exposes overall business revenue to market shifts in consumer fashion.

### E. Channel Performance & The Online Margin Compression

Filtering the dashboard across sales channel slicers reveals a key trade-off between volume growth and margin retention:
- In-Store Channel View  
- Online Channel View  
- Outlet Channel View 

![`In-Store View`](/adidas_dashboard_instore.png) 

![`Online View`](/adidas_dashboard_online.png) 

![`Outlet View`](/adidas_dashboard_outlet.png) 

| Performance Metric | In-Store View | Outlet View | Online View |
|---|---:|---:|---:|
| **Total Sales Revenue** | **$356.6M** | **$295.6M** | **$247.7M** |
| **Total Operating Profit** | **$127.6M** | **$108.0M** | **$96.6M** |
| **Total Units Sold** | **689,990** | **849,778** | **939,093** |
| **Profit Margin %** | **35.8%** | **36.5%** | **39.0%** *(Highest Overall)* |
| **YoY Margin Change** | **▲ +2.9pp** | **▲ +1.5pp** | **▼ -8.0pp** *(Margin Compressed)* |
| **YoY Sales Growth** | **+180%** | **+153%** | **+5,280%** *(Explosive)* |

- **Volume vs. Value:** The **Online channel** moved the highest volume of physical units (939,093 units) and achieved the highest overall Profit Margin percentage (39.0%).
- **Margin Compression:** However, while Online sales experienced massive growth (+5,280% YoY), its **profit margin dropped by 8.0 percentage points YoY**. This indicates that digital expansion came with higher customer acquisition, promotional discounting, and fulfillment costs.

### F. Year-on-Year Operational Trends (June 2020 Baseline Note)

Monthly sales distribution shows consistent year-over-year expansion throughout 2021. 

A notable data observation occurs in **June 2020**, where Outlet channel sales recorded $0 due to physical retail store closures during that period of COVID-19. Understanding this baseline gap is essential when evaluating 2021 Outlet growth rates to avoid misinterpreting operational recovery as organic expansion.


## 9. Business Recommendations

Based on the dashboard findings, executive leadership should consider the following actions:

### 1. Analyze and replicate success drivers in the West Region
The West region is the primary revenue engine, generating $269.9M (nearly double the Midwest). Before increasing promotional spend in lower-performing regions, conduct a regional review of the West's retail partner mix, channel distribution, and product preferences to understand what drives its higher volume.

### 2. Strengthen support for high-efficiency retail partners
Foot Locker leads in transaction frequency (2,637 orders), while West Gear follows closely behind (2,374 orders) across a smaller location footprint. Account management and co-marketing investment should prioritize highly productive partners like West Gear rather than applying uniform treatment across all retail accounts.

### 3. Diversify product mix to reduce category reliance
Men's Street Footwear generates 39% of overall business revenue. To protect total sales against trend shifts in consumer footwear preference, marketing campaigns should intentionally promote secondary categories like Women's Apparel (33%) and Men's Athletic Footwear (28%).

### 4. Optimize digital channel profitability
The Online channel achieved massive volume expansion (+5,280% YoY sales growth) and the highest overall profit margin (39.0%), but experienced an **8.0 percentage point margin drop YoY**. Digital strategy should focus on optimizing fulfillment costs, refining digital ad spend, and controlling promotional discounting to protect profit margins during volume scaling.

### 5. Account for operational baselines in future planning
The absence of Outlet sales in June 2020 reflects physical store closures rather than organic demand drops. Future forecasting and target setting should account for these baseline operational disruptions to ensure YoY growth expectations are realistic.

## Author and Contact
Fatolu Adedoyin Juliana

Data Analyst | Statistics Graduate | Research Analyst

- **LinkedIn:** [Fatolu Adedoyin Juliana](https://www.linkedin.com)
- **GitHub Profile:** [fajuliana-source](https://github.com/fajuliana-source)
- **Email:** fatoluadedoyin46@gmail.com
