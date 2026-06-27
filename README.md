# Retail Sales Performance & Profitability Dashboard

An end-to-end Excel project analyzing retail sales data to uncover regional performance gaps, profitability drivers, and category-level trends — built entirely in Excel (no external BI tool).

<img width="921" height="456" alt="dashboard_screenshot" src="https://github.com/user-attachments/assets/e3daf6c7-3da2-48f3-99d9-6397391d3fad" />

## Problem Statement

A retail business needs visibility into:
- Which regions and categories drive the most sales and profit
- Where profit margins are weak or negative
- How sensitive profitability is to cost changes
- A single-screen view leadership can use for quick decision-making

## Key Insights

- **East region** delivers the highest profit margin among all regions, while **Central** underperforms — Furniture sales in Central actually run at a **negative margin**.
- **Technology** is the strongest category by profit contribution despite not having the highest sales volume, indicating better per-unit profitability.
- A 5-percentage-point increase in cost share (modeled via Goal Seek) drops profit margin from 30% to 25%, highlighting how cost-sensitive the business is.

## Tools & Techniques Used

| Category | Techniques |
|---|---|
| Data Cleaning | Remove Duplicates (correct column selection), TRIM/CLEAN, Text to Columns, data type fixes |
| Formulas | XLOOKUP, Nested IF, DATEDIF, SUMIFS, COUNTIFS |
| Pivot Tables | Multi-field pivots, Calculated Field (Profit Margin %), Show Values As % of Grand Total |
| Interactivity | Slicers (Region, Category), Timeline (Order Date) |
| What-If Analysis | Goal Seek (reverse-solving cost % for a target profit margin) |
| Visualization | Pivot Charts, Conditional Formatting (color scales on Profit), Data Validation dropdowns |
| Dashboard | Single-screen KPI cards, embedded chart, connected slicers |

## Dashboard Preview

The dashboard sheet consolidates:
- **4 KPI cards**: Total Sales, Total Profit, Total Orders, Avg Profit Margin
- **Pivot chart**: Region-wise Sales vs Profit
- **Slicers**: Region and Category filters
- **Timeline**: Order Date filter

## Dataset

Retail Superstore-style transactional dataset (~5,900 cleaned rows after duplicate removal) covering Order Date, Ship Date, Customer, Region, Category, Sub-Category, Sales, Quantity, and Profit.

Raw data: [`data/superstore_raw.csv`](data/superstore_raw.csv)

## File Structure

```
excel-retail-performance-dashboard/
├── data/
│   └── superstore_raw.csv
├── Retail_Dashboard.xlsx
├── README.md
└── images/
    └── dashboard_screenshot.png
```

## What I Learned

- Remove Duplicates must be scoped to the correct column(s) — deduplicating on a naturally repeating field like Order ID can silently delete valid transaction lines.
- Goal Seek only finds a solution within the mathematical bounds of the model — not every target value is achievable depending on which variable you're solving for.
- Calculated Fields in Pivot Tables are often a faster, more reliable way to get ratio-based metrics (like profit margin) than building them with raw formulas.
