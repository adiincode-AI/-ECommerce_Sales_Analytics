# E-Commerce Sales Analytics Dashboard

## Project Overview

This project presents an interactive **E-Commerce Sales Analytics Dashboard** developed in Tableau to analyze sales performance, customer behavior, geographic trends, seasonality, product performance, and shipping operations. The dashboard transforms raw transactional data into actionable business insights that support data-driven decision-making.

The project follows a complete analytics workflow including data validation, KPI development, exploratory analysis, dashboard design, and business insight generation.

---

## Business Problem

E-commerce businesses generate large volumes of transactional data, making it difficult for stakeholders to quickly understand performance trends and identify growth opportunities.

Key business questions addressed by this project:

* How much revenue is being generated?
* Which products and categories perform best?
* Which regions contribute the most sales?
* Who are the most valuable customers?
* Are there seasonal sales patterns?
* How efficient is the shipping process?

The objective was to create a centralized reporting solution that provides visibility into these areas through interactive dashboards.

---

## Dataset

### Data Source

Sample E-Commerce Sales Dataset

### Key Fields

| Category      | Fields                                           |
| ------------- | ------------------------------------------------ |
| Orders        | Order ID, Order Date                             |
| Shipping      | Ship Date, Ship Mode                             |
| Customers     | Customer ID, Customer Name, Segment              |
| Geography     | Country, City, State, Region                     |
| Products      | Product ID, Product Name, Category, Sub-Category |
| Sales Metrics | Sales                                            |

---

## Tools Used

* Tableau
* [Microsoft Excel](https://www.microsoft.com/microsoft-365/excel?utm_source=chatgpt.com)
* [GitHub](https://github.com?utm_source=chatgpt.com)

---

## Dashboard Structure

### 1. Overview / Executive Summary

Provides a high-level overview of business performance through key KPIs and summary visualizations.

#### KPIs

* Total Sales
* Total Orders
* Total Customers
* Average Order Value (AOV)

#### Visualizations

* Overall Sales Trend
* Sales by Category
* Sales by Region

#### Key Business Questions

* How is the business performing overall?
* Which categories generate the most revenue?
* Which regions contribute the highest sales?

---

### 2. Product Performance

Analyzes product and category-level performance.

#### Visualizations

* Sales by Category
* Sales by Sub-Category
* Top 10 Products by Sales
* Bottom 10 Products by Sales

#### Filters

* Date Range
* Region
* Category

#### Key Business Questions

* Which products drive revenue?
* Which categories perform best?
* Which products underperform?

---

### 3. Geographic Analysis

Provides insights into regional and location-based sales performance.

#### Visualizations

* Sales by Region
* Sales by State
* Sales by City
* Geographic Map

#### Key Business Questions

* Which regions are the strongest markets?
* Which states generate the highest revenue?
* Where are future growth opportunities?

---

### 4. Customer Insights

Examines customer purchasing behavior and segmentation.

#### Visualizations

* Customer Segment Breakdown
* Top Customers by Sales
* Customer Count Trend
* New vs Repeat Customer Analysis

#### Key Business Questions

* Which customer segment contributes the most revenue?
* Who are the highest-value customers?
* Is the customer base growing over time?

---

### 5. Time Trends & Seasonality

Identifies sales trends and seasonal patterns.

#### Visualizations

* Monthly Sales Trend
* Yearly Sales Trend
* Sales by Month
* Year-over-Year (YoY) Analysis

#### Key Business Questions

* Are sales increasing over time?
* Which months perform best?
* Are there seasonal demand patterns?

---

### 6. Operations & Shipping

Evaluates shipping performance and operational efficiency.

#### KPIs

* Average Shipping Time
* Total Orders Shipped

#### Visualizations

* Ship Mode Distribution
* Average Shipping Time by Ship Mode
* Average Shipping Time by Region
* Shipping Time Trend

#### Key Business Questions

* Which shipping methods are most frequently used?
* Which ship modes are fastest?
* Which regions experience shipping delays?

---

## KPIs Implemented

### Total Sales

```tableau
SUM([Sales])
```

### Total Orders

```tableau
COUNTD([Order ID])
```

### Total Customers

```tableau
COUNTD([Customer ID])
```

### Average Order Value (AOV)

```tableau
SUM([Sales]) / COUNTD([Order ID])
```

### Average Shipping Time

```tableau
AVG(DATEDIFF('day',[Order Date],[Ship Date]))
```

---

## Challenges Faced

### Challenge 1: Incorrect Order Count Calculation

Initially, order counts were calculated using:

```tableau
COUNT([Order ID])
```

This resulted in inflated values because a single order could contain multiple products across multiple rows.

#### Solution

Implemented:

```tableau
COUNTD([Order ID])
```

to count unique orders accurately.

---

### Challenge 2: Negative Shipping Time Values

While calculating shipping duration, several records returned values close to **-700 days**.

#### Root Cause

During data preparation, some Order Dates and Ship Dates were accidentally modified, causing Ship Dates to occur before Order Dates.

Example:

| Order Date | Ship Date |
| ---------- | --------- |
| 2025       | 2023      |

This produced unrealistic negative shipping durations.

#### Solution

* Investigated records with negative shipping times.
* Validated Order Date and Ship Date fields.
* Corrected invalid date values.
* Recalculated shipping metrics.

After cleaning the data, shipping KPIs produced accurate results.

---

### Challenge 3: Dashboard Organization

Initially, numerous visualizations were created without a clear analytical structure.

#### Solution

The project was reorganized into six focused dashboards:

1. Executive Summary
2. Product Performance
3. Geographic Analysis
4. Customer Insights
5. Time Trends & Seasonality
6. Operations & Shipping

This improved storytelling, usability, and stakeholder navigation.

---

## Key Insights

* Revenue is concentrated within specific product categories and customer segments.
* A small group of customers contributes a significant share of total sales.
* Sales performance varies considerably across regions and states.
* Seasonal patterns reveal peak sales periods during specific months.
* Standard Class is the most frequently used shipping method.
* Shipping efficiency differs across regions, highlighting operational improvement opportunities.

---

## Skills Demonstrated

### Data Analysis

* KPI Development
* Trend Analysis
* Customer Segmentation
* Geographic Analysis
* Operational Analysis

### Tableau

* Interactive Dashboards
* Calculated Fields
* Parameters & Filters
* Geographic Mapping
* Time-Series Analysis

### Business Intelligence

* Executive Reporting
* Performance Monitoring
* Data Validation
* Insight Generation
* Data Storytelling

---

## Future Enhancements

Future improvements could include:

* Profitability Analysis
* Discount Impact Analysis
* Customer Retention Metrics
* Cohort Analysis
* Sales Forecasting
* Predictive Analytics

---

## Project Outcomes

This project demonstrates the end-to-end process of transforming raw sales data into a business intelligence solution. Through data validation, KPI development, dashboard design, and insight generation, the dashboard provides stakeholders with a centralized view of business performance and supports data-driven decision-making.

---

## Dashboard Preview

*Add dashboard screenshots here.*

### Executive Summary

![Executive Summary](screenshots/executive-summary.png)

### Product Performance

![Product Performance](screenshots/product-performance.png)

### Geographic Analysis

![Geographic Analysis](screenshots/geographic-analysis.png)

### Customer Insights

![Customer Insights](screenshots/customer-insights.png)

### Time Trends & Seasonality

![Time Trends](screenshots/time-trends.png)

### Operations & Shipping

![Operations](screenshots/operations-shipping.png)
