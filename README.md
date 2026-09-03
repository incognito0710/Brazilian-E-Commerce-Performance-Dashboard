# Brazilian E-Commerce Performance Dashboard

An end-to-end analytics pipeline built on the Olist Brazilian e-commerce dataset — 9 raw CSVs, about 1.5 million rows, taken from flat files all the way to a live dashboard.

## What's in here

This isn't a single clean CSV turned into a chart. It's 9 separate relational tables — customers, orders, order items, payments, products, sellers, reviews, and so on — the way data actually sits in a real database. The pipeline:

1. **Extract & Load** — Python (pandas + SQLAlchemy) reads all 9 CSVs and loads them into MySQL as linked tables.
2. **Analyze** — SQL joins across tables to answer the actual business questions: revenue by state, delivery delays, top-selling categories.
3. **Segment customers** — RFM analysis in Python, scoring every customer on recency, frequency, and spend, then grouping them into Champions, Loyal Customers, At Risk, and so on.
4. **Visualize** — Power BI, connected live to the MySQL database rather than a static import, with a couple of DAX measures built in for delivery performance.

## What the data says

- São Paulo alone brings in roughly a third of total revenue.
- About 8% of orders show up later than the estimated delivery date.
- Health & Beauty and Watches/Gifts top the category rankings by revenue, even though they're not the highest-volume categories.
- The RFM segmentation surfaced something worth flagging: "At Risk" is the single largest customer group, over 22,000 people — more than Champions and Loyal Customers put together.

## Stack

Python (pandas, SQLAlchemy) · MySQL · SQL · Power BI · DAX

## Dashboard

KPI cards for total revenue, orders, customers, average order value, and on-time delivery rate, plus visuals for delivery status, revenue by state, sales by category, and the RFM segments.

## Dataset

[Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce), Kaggle.

## Files

- `load_to_mysql.ipynb` — loads the 9 CSVs into MySQL
- `rfm_segmentation.ipynb` — RFM scoring and segmentation
- `queries.sql` — the SQL used for the analysis
- `dashboard.pbix` — the Power BI file
