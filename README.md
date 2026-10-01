# Customer Sales & Revenue Analytics

## Project Overview

This project analyzes online retail sales data using **Excel, SQL Server, and Power BI** to identify revenue trends, customer behavior, product performance, geographic sales patterns, and return/cancellation activity.

The project demonstrates an end-to-end data analytics workflow:

**Excel → SQL Server → SQL Analysis → Power BI Dashboard**

---

## Business Objective

The objective of this project is to analyze retail transaction data and answer key business questions such as:

* How is revenue changing over time?
* Which countries generate the most sales revenue?
* Which products generate the highest revenue?
* Which customers contribute the most revenue?
* How many transactions are returns or cancellations?
* How does average order value change over time?
* Which periods have the highest transaction activity?

---

## Dataset

**Source:** UCI Online Retail Dataset

The dataset contains transaction-level records from an online retail business.

### Key columns

* InvoiceNo
* StockCode
* Description
* Quantity
* InvoiceDate
* UnitPrice
* CustomerID
* Country

### Additional analytical columns created

* **Revenue** = Quantity × UnitPrice
* **Sales_Status** = Sale / Return/Cancelled
* **Year_Month** = Year-month extracted from InvoiceDate

Dataset size:

* **541,909 transaction records**
* **4,373 unique customers identified in Excel analysis**
* Transaction period: **December 2010 – December 2011**

---

## Tools & Technologies

* **Microsoft Excel** — Data preparation, calculated columns, filtering and PivotTable analysis
* **SQL Server / SSMS** — Data storage, transformation and analytical queries
* **Power BI** — Interactive dashboard and data visualization
* **GitHub** — Project documentation and portfolio

---

## Data Preparation

The raw transaction data was prepared in Excel before loading into SQL Server.

Key preparation steps included:

1. Created a `Revenue` column using:

```text
Revenue = Quantity × UnitPrice
```

2. Identified negative quantities as return/cancellation activity.

3. Identified invoices beginning with `C` as cancellations.

4. Created a `Sales_Status` classification:

```text
If Quantity < 0 OR InvoiceNo begins with C
→ Return/Cancelled

Otherwise
→ Sale
```

5. Created a `Year_Month` field from the transaction date.

6. Preserved return/cancellation records rather than deleting them so that their impact could be analyzed separately.

---

## SQL Analysis

The cleaned dataset was imported into a SQL Server database named:

```text
SalesAnalytics
```

Main table:

```text
dbo.OnlineRetail
```

SQL analysis included:

* Sales vs Return/Cancelled transactions
* Monthly revenue trends
* Monthly transaction volume
* Average order value
* Revenue by country
* Top customers by revenue
* Top products by revenue

---

## Key Findings

### Sales and Returns

Sales transactions generated approximately:

**£10.64 million**

Return/Cancelled transactions represented approximately:

**£896.81K negative revenue**

Net revenue after returns/cancellations:

**£9.75 million**

There were **10,624 Return/Cancelled records** out of 541,909 total records.

---

### Monthly Revenue

The highest monthly sales revenue occurred in:

**November 2011 — £1,509,496.33**

November also had the highest sales transaction volume:

**83,498 transactions**

December 2011 had the highest average revenue per transaction:

**£25.41**

---

### Revenue by Country

The United Kingdom generated the largest sales revenue:

**£9,003,097.96**

Other major markets included:

* Netherlands — £285,446.34
* EIRE — £283,453.96
* Germany — £228,867.14
* France — £209,715.11

---

### Top Customers

The highest-revenue customers included:

| Customer ID | Sales Revenue |
| ----------- | ------------: |
| 14646       |   £280,206.02 |
| 18102       |   £259,657.30 |
| 17450       |   £194,550.79 |
| 16446       |   £168,472.50 |
| 14911       |   £143,825.06 |

---

### Top Products

After excluding postage/service descriptions such as `POSTAGE` and `DOTCOM POSTAGE`, the highest-revenue product descriptions included:

| Product                            | Sales Revenue |
| ---------------------------------- | ------------: |
| REGENCY CAKESTAND 3 TIER           |   £174,484.74 |
| PAPER CRAFT , LITTLE BIRDIE        |   £168,469.60 |
| WHITE HANGING HEART T-LIGHT HOLDER |   £106,292.77 |
| PARTY BUNTING                      |    £99,504.33 |
| JUMBO BAG RED RETROSPOT            |    £94,340.05 |

`Manual` also appeared among the top revenue descriptions and was retained as a data-quality observation rather than treated as a conventional product.

---

## Power BI Dashboard

The Power BI dashboard provides an interactive view of:

* Total sales revenue
* Sales transaction volume
* Average order value
* Return/cancellation activity
* Monthly revenue trends
* Revenue by country
* Top customers
* Top products
* Sales performance over time

Interactive filtering allows the analysis to be explored by relevant dimensions such as country, month and sales status.

---

## Example Business Insights

The analysis demonstrates several useful retail insights:

* Revenue was strongly concentrated in the United Kingdom within this dataset.
* November 2011 recorded the highest sales revenue and transaction volume.
* Higher transaction volume did not always correspond to the highest average order value.
* A small group of customers contributed substantial sales revenue.
* Return/cancellation activity had a measurable impact on overall revenue.
* Product-level analysis required separating postage/service descriptions from physical product descriptions.

---

## Project Structure

```text
Customer-Sales-Revenue-Analytics/
│
├── README.md
├── Online_Retail_Analysis.xlsx
├── SQL/
│   └── Sales_Analysis.sql
└── PowerBI/
    └── Customer_Sales_Revenue_Analytics.pbix
```

---

## Skills Demonstrated

**Data Analysis**

* Revenue analysis
* Customer analysis
* Product analysis
* Sales trend analysis
* Return/cancellation analysis
* KPI analysis

**SQL**

* SELECT
* WHERE
* GROUP BY
* ORDER BY
* Aggregate functions
* Filtering
* Business-oriented analytical queries

**Excel**

* Data cleaning
* Calculated columns
* Filtering
* PivotTables
* Revenue calculations

**Power BI**

* KPI development
* Interactive dashboards
* Trend analysis
* Business data visualization
* Slicers and filters

---

## Project Outcome

This project demonstrates the ability to take raw transaction-level data, prepare and classify the data, analyze it using SQL, and present business insights through an interactive Power BI dashboard.

**Tools:** Excel | SQL Server | Power BI
