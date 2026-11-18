# Retail Sales Case Study (Python)

## 📄 Project Description

[Read the project description (PDF)](Sales_Case_Study_Project_Description.pdf)

## Project Overview

This project analyses daily retail sales from 30 December 2013 to 16 November 2016. It looks at unit pricing, gross profit, promotional periods and Price Elasticity of Demand (PED), and turns the results into pricing recommendations.

The main analysis is in Python (pandas, matplotlib). An earlier SQL version of the same case study, run in Databricks, is kept in `Sales Case Study Analysis.ipynb`.

---

## Business Questions

1. How much does a unit sell for, and how much gross profit does each unit earn?
2. Which days were promotional, and how did they change sales volume?
3. How sensitive is customer demand to price changes?
4. What should the business do about pricing and cost?

---

## Dataset

File: `Retail_Sales_Dataset.csv(Sales Master).csv` (1,053 daily records, no missing values or duplicate dates)

| Column | Description |
|---|---|
| Date | Trading date (MM/DD/YYYY) |
| Sales | Total sales for the day |
| Cost Of Sales | Total cost of the goods sold that day |
| Quantity Sold | Units sold that day |

---

## Method

- **Unit price** = Sales / Quantity Sold, calculated per day. Average unit price is reported as a weighted average (total sales / total units) and as a simple average of daily prices.
- **Gross profit** = Sales − Cost Of Sales. **GP%** = Gross profit / Sales.
- **Promotional day:** unit price at least 5% below the previous 30-day average, and quantity sold at least 20% above the previous 30-day average. Consecutive promotional days form one **window**.
- **PED** for each window = % change in quantity / % change in price, measured against the 30-day baseline.

---

## Key Results

- Weighted average unit price: about 35.40. Simple average of daily prices: about 37.07.
- Total gross profit is negative, at about −3.8% of sales. Cost of sales exceeds sales on about 58% of trading days.
- 145 promotional days across 49 windows.
- Mean PED is about −14.2 and median PED is about −13.6. All 49 windows are elastic (below −1).
- Promotional days average about 8,600 units, against about 4,400 on non-promotional days.

---

## Recommendations

1. Review cost of sales before the next promotion, since cost exceeds sales on most days.
2. Test smaller discounts, such as 5%, to see whether they keep most of the volume lift while protecting margin.
3. Re-run the PED analysis each quarter using new data.
4. Prioritise promotions in windows with the most negative PED.

---

## Charts

| Chart | File |
|---|---|
| Monthly sales and gross profit | `images/monthly_sales_gp.png` |
| Unit price vs quantity sold | `images/price_vs_quantity.png` |
| PED by promotional window | `images/ped_by_window.png` |

---

## Repository Contents

```
Sales_Case_Study/
├── Sales_Case_Study_Python.ipynb        # Python analysis (main)
├── Sales Case Study Analysis.ipynb      # Earlier Databricks SQL version
├── Retail_Sales_Dataset.csv(Sales Master).csv
├── images/
│   ├── monthly_sales_gp.png
│   ├── price_vs_quantity.png
│   └── ped_by_window.png
└── README.md
```

---

## How to Run

```bash
pip install pandas matplotlib jupyter
jupyter notebook Sales_Case_Study_Python.ipynb
```

Run the notebook from the repository folder so the CSV and image paths resolve.

---

## Tools Used

- Python (pandas, NumPy, matplotlib)
- Jupyter Notebook
- SQL and Databricks (earlier version)
- GitHub

---

## Author

**William Mathekuana**

GitHub: https://github.com/williammoscow743-prog
