# Retail Business Performance Analysis

An end-to-end **Power BI portfolio project** exploring sales performance, profitability, customer behaviour, product performance, and city-level operations using a synthetic retail dataset.

> **Data notice:** This project uses a synthetic dataset created for learning and portfolio demonstration. It does not represent an actual company's transactions or performance.

## Project Overview

The goal of this project is to turn raw retail data into an interactive business intelligence report that helps stakeholders understand:

- How revenue and gross profit are performing.
- Which sales channels and product categories contribute most to revenue and profit.
- Which customer segments and acquisition channels contribute to sales.
- How cities compare on target achievement, order processing time, cancellations, and returns.

The report contains four pages:

1. [Executive Summary](https://ibb.co/ycVXKWxg) – headline KPIs, monthly revenue trend, revenue versus sales target, revenue by region, and top products by revenue.
2. [Sales & Profitability](https://ibb.co/qMkNywqd) – revenue by sales channel, monthly gross profit, profit margin by category, and revenue by discount band.
3. [Product & Customer Analysis](https://ibb.co/LXM9KdGC) – revenue by product category, top products by profit, revenue by customer segment, and customers by acquisition channel.
4. [City & Operational Analysis](https://ibb.co/hJxpwKKY) – target achievement by city, average order-to-ship time by city, cancellation rate by city, and return rate by city.

## Tools & Techniques

- **Microsoft Power BI Desktop** – report development and interactive visualisation.
- **Power Query** – data cleaning, transformation, and preparation.
- **DAX** – calculated measures, KPI calculations, time-intelligence comparisons, and business metrics.
- **Data modelling** – relationships between sales, products, customers, regions, calendar, and monthly targets.

## Dataset

The practice dataset covers **January 2024 to December 2025** and contains these tables:

| Table | Approximate records | Purpose |
|---|---:|---|
| Sales | 3,198 | Transaction-level sales information |
| Products | 20 | Product attributes and unit costs |
| Customers | 500 | Customer and segment information |
| Regions | 6 | City and regional mapping |
| MonthlyTargets | 144 | Monthly sales targets by region |
| Calendar | Generated in Power BI | Date dimension for time-based analysis |

The dataset includes sales dates, order status, product and customer identifiers, quantities, unit prices, discount rates, sales channels, shipping dates, city/region information, and monthly targets.

## Data Preparation

The Power Query preparation process included:

- Removing exact duplicate sales records.
- Handling missing discount-rate values.
- Reviewing records with missing shipping dates.
- Excluding invalid quantity and unit-price records.
- Reviewing and excluding an unknown region identifier.
- Standardising categorical values such as sales channel, order status, and payment method.
- Applying appropriate data types to date, numeric, and text columns.

The final row counts and transformation steps should be checked against the latest PBIX file before publication.

## Data Model

The model uses a star-schema-style structure with the sales table connected to supporting dimensions:

- `Products` → `Sales` through `ProductID`
- `Customers` → `Sales` through `CustomerID`
- `Regions` → `Sales` through `RegionID`
- `Calendar` → `Sales` through `OrderDate`
- `Regions` → `MonthlyTargets` through `RegionID`
- `Calendar` → `MonthlyTargets` through `MonthStart`

A dedicated Calendar table supports month, year, quarter, and year-over-year analysis.

## Key Metrics

The report includes measures such as:

- Total Revenue
- Gross Profit
- Gross Profit Margin
- Total Orders
- Target Achievement
- Average Order Value
- Average Selling Price
- Units Sold
- Revenue per Customer
- Average Discount Rate
- Average Order-to-Ship Time
- Order Cancellation Rate
- Order Return Rate

Revenue excludes cancelled and returned orders in the core sales measures. Order cancellation and return rates are reported separately to monitor order quality.

**Metric interpretation:** Average Order-to-Ship Time measures the elapsed time between order placement and shipment. It is not a delivery-time measure because the dataset does not contain a delivery date.

## Selected Dashboard Findings

The following are observations from the report's displayed values and should be interpreted within the selected report filters:

- Executive Summary displays approximately **₦1.09M total revenue**, **₦459K gross profit**, and a **42.31% gross profit margin**.
- Marketplace is the highest-revenue sales channel at approximately **₦399K**.
- Electronics records the highest displayed category profit margin at **47.19%**, while Fashion records the lowest at **36.84%**.
- Home & Living is the highest-revenue product category at approximately **₦321K**.
- Website acquisition contributes **132 customers (26.4%)** in the displayed customer analysis.
- Abuja records the highest displayed cancellation rate at **6.12%** and the longest average order-to-ship time at **4.2 days**.
- Kano records the highest displayed return rate at **3.54%**, while Ibadan has the lowest displayed cancellation and return rates at **2.70%** and **1.93%**, respectively.

## Recommendations

- Review the causes of cancellations and longer order-to-ship times in Abuja.
- Investigate product, fulfilment, or customer-service factors that may contribute to returns in Kano.
- Examine the practices associated with Ibadan's lower cancellation and return rates for possible application in other cities.
- Continue monitoring category profitability, sales-channel contribution, and discount performance to support pricing and promotion decisions.

## Repository Structure

```text
Retail_Business_Performance_Analysis/
├── README.md
├── powerbi/
│   └── Retail_Business_Performance_Analysis.pbix
```

## How to Explore the Project

1. Download or clone this repository.
2. Open the `.pbix` file from the `powerbi/` folder using Power BI Desktop.
3. Use the report slicers to explore year, month, region, category, and sales channel.
4. Navigate across the four report pages to explore executive, sales, product/customer, and operational performance.

## Author Oladotun Olawale

**Data Analytics Portfolio Project**

Built with Microsoft Power BI, Power Query, and DAX.

