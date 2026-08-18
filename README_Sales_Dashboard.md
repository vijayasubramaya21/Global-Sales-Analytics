<div align="center">

# 📊 Global Sales Analytics Dashboard

**An interactive business intelligence dashboard analyzing $17.29M in retail revenue across 60,000+ transactions, 4 global regions, and 2 fiscal years.**

[![Made with Python](https://img.shields.io/badge/Data-Python%20%7C%20Pandas-3776AB?logo=python&logoColor=white)](#)
[![Dashboard](https://img.shields.io/badge/Dashboard-HTML%20%7C%20JavaScript%20%7C%20SVG-E34F26?logo=html5&logoColor=white)](#)
[![BI Tools](https://img.shields.io/badge/BI-Power%20BI%20%7C%20Tableau-F2C811?logo=powerbi&logoColor=white)](#)
[![License](https://img.shields.io/badge/License-MIT-green)](#license)

</div>

---

## Table of Contents
- [Overview](#overview)
- [Business Problem](#business-problem)
- [Key Findings](#key-findings)
- [Dashboard Preview](#dashboard-preview)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Methodology](#methodology)
- [Tech Stack](#tech-stack)
- [Data Notes](#data-notes)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## Overview

This project simulates a real-world retail analytics engagement: a global sales team needs a single, self-service view of revenue performance to identify growth opportunities, underperforming segments, and channel investment priorities — without waiting on an analyst to pull a new report every time.

The result is a fully interactive dashboard covering **revenue trends, regional performance, category mix, customer segmentation, and channel effectiveness**, built once as a lightweight standalone web app and again as a Power BI / Tableau specification for enterprise deployment.

## Business Problem

> *"Where is our revenue growing, which customers are actually driving it, and which channels deserve more investment next quarter?"*

Leadership needed answers broken down by **region**, **product category**, **customer segment**, and **time period** — filterable on demand, not locked in a static slide deck.

## Key Findings

| Metric | Value | Insight |
|---|---|---|
| **Total Revenue** | $17.29M | Across FY2024–FY2025 |
| **YoY Growth** | +19.2% | Accelerating in H2 both years (seasonal holiday lift) |
| **Total Orders** | 60,000 | ~2,500 orders/month average |
| **Avg Order Value** | $288.18 | Driven up by Electronics category mix |
| **Unique Customers** | 28,784 | 1.5 orders per customer on average |

**Strategic insights surfaced by the analysis:**

1. **Revenue is regionally concentrated.** North America drives 42% of total revenue, followed by Europe (28%), APAC (21%), and LATAM (8%) — LATAM is a clear expansion candidate.
2. **Electronics dominates category mix**, contributing 61% of revenue — a concentration risk worth monitoring alongside category-level margin data.
3. **Retention beats acquisition.** Returning customers generate **49% of revenue** while representing only 50% of the customer base and a fraction of acquisition spend — this supports reallocating budget toward retention over pure top-of-funnel growth.
4. **Online is the primary channel** (55% of orders), but Retail Store maintains a meaningfully higher AOV — suggesting a blended channel strategy rather than an online-only push.

## Dashboard Preview

The live dashboard includes:
- **KPI summary cards** — Revenue, Orders, AOV, Unique Customers, all with trend context
- **Revenue trend chart** — interactive, filterable by year and region, hover for exact monthly values
- **Category breakdown** — donut chart with percentage share
- **Regional performance** — horizontal bar comparison
- **Customer segment table** — New / Returning / VIP with customers, orders, revenue, AOV
- **Channel mix** — Online / Retail Store / Marketplace with share of revenue

> Open `Sales_Dashboard_Offline.html` in any browser to explore it live — no installation required.

## Project Structure

```
global-sales-analytics-dashboard/
│
├── Sales_Dashboard_Offline.html   # Interactive dashboard (self-contained, offline-ready)
├── sales_transactions.csv         # Raw transaction-level dataset (60,000 rows)
├── PowerBI_Tableau_Build_Guide.md # Step-by-step guide to rebuild in Power BI / Tableau
└── README.md                      # This file
```

## Getting Started

### Option 1 — View the interactive dashboard (fastest)
1. Download `Sales_Dashboard_Offline.html`
2. Double-click to open in any browser (Chrome, Edge, Firefox, Safari)
3. Filter by year (chips) or region (dropdown) at the top of the dashboard
4. Hover over the revenue trend line for exact monthly figures

No installation, server, or internet connection required — all charts are rendered client-side with hand-built SVG and vanilla JavaScript.

### Option 2 — Rebuild in Power BI or Tableau
1. Open `PowerBI_Tableau_Build_Guide.md`
2. Import `sales_transactions.csv`
3. Follow the step-by-step DAX measures (Power BI) or calculated fields (Tableau) to reproduce every visual in this dashboard

### Option 3 — Explore the raw data
```python
import pandas as pd
df = pd.read_csv("sales_transactions.csv", parse_dates=["order_date"])
df.groupby("region")["revenue"].sum().sort_values(ascending=False)
```

## Methodology

1. **Data generation** — Transaction-level records generated at production scale (60,000 rows) with realistic seasonality (holiday Q4 lift), regional weighting, and category pricing bands, using Python (pandas, numpy).
2. **Aggregation** — Revenue, orders, and customer counts rolled up by month, region, category, channel, and customer segment.
3. **KPI design** — Total Revenue, YoY Growth, Average Order Value, and Unique Customers selected as headline metrics because they map directly to how retail leadership tracks performance.
4. **Visualization** — Dashboard built with hand-coded SVG (line/area chart, donut chart) and CSS (bar charts, progress indicators) for a fully dependency-free, offline-capable deliverable — with an equivalent Power BI/Tableau build path documented for enterprise contexts.
5. **Insight extraction** — Each visual is paired with a specific business question (e.g., "are we too reliant on one region?") rather than shown as a generic chart, to demonstrate analysis, not just visualization.

## Tech Stack

| Layer | Tools |
|---|---|
| Data processing | Python, pandas, NumPy |
| Dashboard (standalone) | HTML5, CSS3, vanilla JavaScript, SVG |
| BI (enterprise equivalent) | Power BI (DAX, star-schema date table), Tableau (calculated fields, filter actions) |
| Version control | Git, GitHub |

## Data Notes

The dataset is synthetically generated to realistically mirror multi-region e-commerce transaction data at production scale — 2 years, 4 regions, 5 categories, 3 channels, and 3 customer segments — built for portfolio demonstration purposes since live proprietary transaction data was not available. The analytical methodology (KPI design, time-series trend analysis, segmentation, channel mix) mirrors exactly what would be applied to real transaction data in a production analytics role.

## Future Improvements

- [ ] Add cohort-based retention analysis (Day 30/60/90) by acquisition month
- [ ] Layer in profit margin by category to complement revenue-only view
- [ ] Add forecasting (e.g., Prophet or ARIMA) for next-quarter revenue projection
- [ ] Deploy live version to Power BI Service / Tableau Public with scheduled refresh
- [ ] Add customer lifetime value (CLV) segmentation

## Author

**Vijayasubramanya H M**
Data Analyst | MCA Graduate
📧 vijayasubramanyahm@gmail.com · 🔗 [LinkedIn](https://linkedin.com/in/vijayasubramanyahm-dataanalyst) · 💻 [GitHub](https://github.com/vijayasubranya21)

---

<div align="center">
<sub>Built as part of a data analytics portfolio. Feedback and suggestions welcome via GitHub Issues.</sub>
</div>
