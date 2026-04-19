# Sales Performance Analysis (EDA)

## Business Question
**What drives revenue across customers, products, and markets — and how has performance changed over time?**

---

## Project Overview
An end-to-end **Exploratory Data Analysis (EDA)** on the Northwind sales dataset covering orders from **July 2012 to May 2014**.

The analysis identifies revenue drivers across geographies, customers, and products, and tracks performance trends over time — answering questions that real business teams ask before making pricing, inventory, and market expansion decisions.

---

## Dataset
| Field | Details |
|---|---|
| Source | `Sales data.csv` |
| Rows (raw) | 2,161 |
| Orders (clean, deduplicated) | 830 |
| Date Range | Jul 2012 – May 2014 |
| Key Columns | `OrderDate`, `Country`, `City`, `CustomerID`, `ProductName`, `UnitPrice`, `TotalAmount`, `SupplierID` |


---

## Analysis Steps

### 1. Data Loading & Cleaning
- Standardized column names
- Converted `OrderDate` to datetime
- Fixed data types for all ID and numeric columns
- Handled missing values (dropped rows missing critical fields, filled `Fax` nulls)
- Built full customer name column
- **Fixed double-counting issue** in `TotalAmount`

### 2. Descriptive Statistics
- Summary stats for revenue per order and unit prices
- Distribution plots (Histogram + KDE) with mean/median lines
- Outlier detection using IQR method

### 3. Geographical Analysis
- Revenue and order volume by country and city
- Top 10 countries by revenue with percentage contribution
- Bar charts and pie charts

### 4. Time Series Analysis
- Monthly revenue trends and order volume
- **Month-over-Month (MoM) growth** visualization
- **Year-over-Year (YoY) comparison** across 2012, 2013, 2014
- Number of active countries per month

### 5. Customer Analysis
- Top 10 customers by **total revenue** (not just order count)
- Customer segmentation: order frequency vs average order value
- Scatter plot sized by total spend

### 6. Product Analysis
- Top 15 most frequently ordered products
- **Discontinued products still being ordered** — flagged as a business risk

### 7. Supplier Analysis
- Top 10 suppliers by order volume
- Products supplied per supplier and geographic distribution

---

## Key Insights

| Metric | Value |
|---|---|
| Total Revenue (corrected) | Calculated from deduplicated orders |
| Average Order Value | ~$1,986 |
| Top Market | USA |
| YoY Growth 2012→2013 | Positive |
| YoY Growth 2013→2014 | Partial year — growth trend visible |
| Discontinued products still ordered | Multiple — inventory risk identified |


---

## Business Risks Identified
1. **Discontinued products** still appearing in orders — potential fulfillment and customer satisfaction risk
2. **Revenue concentration** — top 3 countries account for a large share of total revenue
3. **High-value outlier orders** — a small number of orders drive disproportionate revenue

---

## Tools & Libraries

| Tool | Purpose |
|---|---|
| Python | Core language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Plotly | Interactive charts |
| Matplotlib + Seaborn | Static distribution plots |
