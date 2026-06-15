# 🏪 Vendor Performance Analysis

> Uncovering $134M in gross profit opportunities across 10,692 vendor-product records — optimizing pricing, inventory turnover, and supplier strategy for a retail/wholesale business.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Dataset](#-dataset)
- [Tools & Technologies](#-tools--technologies)
- [Methods](#-methods)
- [Key Insights](#-key-insights)
- [Dashboard](#-dashboard)
- [How to Run](#-how-to-run-this-project)
- [Results & Conclusion](#-results--conclusion)
- [Author & Contact](#-author--contact)

---

## 🔍 Overview

This project delivers a **comprehensive vendor performance analysis** for a retail/wholesale beverage distribution business. By combining Python-based exploratory data analysis with an interactive Power BI dashboard suite, it identifies underperforming brands, evaluates vendor dependencies, quantifies the impact of bulk purchasing, and flags slow-moving inventory — empowering data-driven decisions to maximize profitability and reduce supply chain risk.

The dashboard suite features three interconnected views:
- 🏠 **Home** — A landing page with navigation to both views
- 📊 **Overview** — High-level KPIs, vendor rankings, and visual charts
- 🗂️ **Details Grid** — Granular product-level transactional data with filters

---

## ❗ Problem Statement

Effective inventory and sales management are critical for profitability in the retail and wholesale industry. Companies risk losses from:

- 📉 Inefficient pricing leading to poor gross margins
- 🏚️ Poor inventory turnover causing capital lock-up
- 🔗 Over-reliance on a small number of vendors (supply chain risk)
- 🏷️ Missed revenue from high-margin brands with low visibility

**This analysis answers 5 core business questions:**

1. Which brands need promotional or pricing adjustments?
2. Which vendors and brands demonstrate the highest sales performance?
3. Does bulk purchasing reduce unit cost — and by how much?
4. Which vendors have the lowest inventory turnover?
5. How much capital is locked in unsold inventory, and where?

---

## 📁 Dataset

| Attribute | Details |
|---|---|
| **Source** | SQLite database (`inventory.db`) — table: `vendor_sales_summary` |
| **Raw Records** | 10,692 rows × 18 columns |
| **Filtered Records** | 8,564 rows (after removing zero-sales & negative-margin entries) |
| **Scope** | Beverage retail/wholesale — wines, spirits, and liqueurs |

**Key columns include:**

| Column | Description |
|---|---|
| `VendorName` | Supplier/vendor name |
| `Description` | Product/brand name |
| `PurchasePrice` | Per-unit cost price |
| `ActualPrice` | Per-unit retail price |
| `TotalPurchaseDollars` | Total procurement spend |
| `TotalSalesDollars` | Total revenue generated |
| `GrossProfit` | Revenue minus procurement cost |
| `ProfitMargin` | Gross profit as a ratio of sales |
| `StockTurnover` | Ratio of sales to purchases |
| `FreightCost` | Logistics and shipping costs |

---

## 🛠️ Tools & Technologies

| Category | Tools |
|---|---|
| **Language** | Python 3 |
| **Data Storage** | SQLite (`sqlite3`) |
| **Data Manipulation** | Pandas, NumPy |
| **Visualization (Python)** | Matplotlib, Seaborn |
| **Statistical Analysis** | SciPy (`ttest_ind`, `stats`) |
| **BI Dashboard** | Power BI Desktop |
| **Environment** | Jupyter Notebook |

---

## ⚙️ Methods

```
1. Data Extraction      →  SQL query from SQLite database
2. EDA                  →  Summary statistics, distribution plots, boxplots
3. Data Cleaning        →  Removed records where GrossProfit ≤ 0,
                           ProfitMargin ≤ 0, or TotalSalesQuantity = 0
4. Correlation Analysis →  Heatmap across all numerical features
5. Brand Segmentation   →  Quadrant analysis (low sales vs. high margin)
6. Vendor Ranking       →  Top 10 by sales, purchases, and gross profit
7. Bulk Purchase Study  →  Quantile-based order size classification (S/M/L)
8. Inventory Analysis   →  Stock turnover ranking + unsold capital calculation
9. Dashboard Design     →  3-page Power BI report with slicers and navigation
```

---

## 💡 Key Insights

### 1. 🎯 Brands Needing Promotion
- **198 brands** have low sales but high profit margins (above the 85th percentile).
- These are hidden gems — targeted marketing or price adjustments could unlock volume without sacrificing profitability.

### 2. 🏆 Top Performing Vendors & Brands

| Rank | Vendor | Total Sales |
|---|---|---|
| 1 | Diageo North America Inc | $68M |
| 2 | Martignetti Companies | $39M |
| 3 | Pernod Ricard USA | $32M |
| 4 | Jim Beam Brands Company | $31M |
| 5 | Bacardi USA Inc | $25M |

| Rank | Brand | Total Sales |
|---|---|---|
| 1 | Jack Daniels No 7 Black | $8.0M |
| 2 | Tito's Handmade Vodka | $7.4M |
| 3 | Grey Goose Vodka | $7.2M |
| 4 | Capt Morgan Spiced Rum | $6.4M |
| 5 | Absolut 80 Proof | $6.2M |

### 3. 📦 Bulk Purchasing Reduces Unit Cost by ~72%

| Order Size | Avg. Unit Purchase Price |
|---|---|
| Small | $39.07 |
| Medium | $15.49 |
| **Large** | **$10.78** |

Large orders are ~72% cheaper per unit than small orders — a strong incentive to consolidate purchasing.

### 4. 🔄 Vendor Concentration Risk
- The **top 10 vendors account for 65.69%** of total purchases.
- The remaining vendors contribute only **34.31%**, indicating dangerous over-reliance on a few suppliers.

### 5. 🏦 Capital Locked in Unsold Inventory: **$2.71M**

| Vendor | Unsold Capital |
|---|---|
| Diageo North America Inc | $722K |
| Jim Beam Brands Company | $555K |
| Pernod Ricard USA | $471K |
| William Grant & Sons Inc | $402K |

### 6. 🐢 Lowest Inventory Turnover Vendors

| Vendor | Stock Turnover |
|---|---|
| Alisa Carr Beverages | 0.62 |
| Highland Wine Merchants LLC | 0.71 |
| Park Street Imports LLC | 0.75 |
| Circa Wines | 0.76 |
| Dunn Wine Brokers | 0.77 |

---

## 📊 Dashboard

### 🏠 Home Page
![Home Dashboard](https://github.com/krishnax704/vendor-performance-analysis-sql-python-powerbi/blob/main/dashboard/overview_dashboard.png)

> Navigation hub introducing the analysis scope and routing to Overview and Details Grid.

---

### 📈 Overview Dashboard
![Overview Dashboard]([https://raw.githubusercontent.com/your-username/your-repo/main/dashboard_images/overview_dashboard.png](https://github.com/krishnax704/vendor-performance-analysis-sql-python-powerbi/blob/main/dashboard/overview_dashboard.png))

> KPI cards showing $441M total sales, $134M gross profit, and 38.72% profit margin. Includes vendor contribution pie chart, top vendors bar chart, top brands ranking, low-performing vendor chart, and target brands scatter plot.

---

### 🗂️ Details Grid Dashboard
![Details Grid Dashboard](https://raw.githubusercontent.com/your-username/your-repo/main/dashboard_images/details_grid_dashboard.png)

> Filterable product-level table with vendor name, description, total sales, total purchases, gross profit, profit margin, and unsold capital. Supports slicing by description and vendor name.

---

## ▶️ How to Run This Project

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn scipy
```

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/your-username/vendor-performance-analysis.git
cd vendor-performance-analysis

# 2. Ensure the SQLite database is present
#    Place inventory.db in the project root directory

# 3. Launch the Jupyter Notebook
jupyter notebook vendor_performance_analysis.ipynb

# 4. Run all cells sequentially
#    (Kernel → Restart & Run All)

# 5. Open the Power BI Dashboard
#    Open Vendor_Performance_Analysis_Report.pbix in Power BI Desktop
```

### Folder Structure

```
vendor-performance-analysis/
│
├── 📓 vendor_performance_analysis.ipynb   # Main analysis notebook
├── 🗄️  inventory.db                        # SQLite database
├── 📊 Vendor_Performance_Analysis_Report.pbix  # Power BI dashboard
├── 📄 README.md
└── 📁 dashboard_images/
    ├── home_dashboard.png
    ├── overview_dashboard.png
    └── details_grid_dashboard.png
```

---

## ✅ Results & Conclusion

| Metric | Value |
|---|---|
| Total Sales | **$441.41M** |
| Total Purchases | **$307.34M** |
| Gross Profit | **$134.07M** |
| Overall Profit Margin | **38.72%** |
| Unsold Inventory Capital | **$2.71M** |
| Brands Needing Promotion | **198** |

**Key Recommendations:**

- 🎯 **Re-evaluate pricing** for 198 low-sales, high-margin brands to capture untapped revenue.
- 🤝 **Diversify vendor partnerships** — top 10 vendors holding 65.69% of purchases is a supply chain risk.
- 📦 **Encourage bulk purchasing** — the 72% unit cost reduction for large orders significantly boosts margins.
- 🏚️ **Liquidate slow-moving inventory** — $2.71M in unsold capital can be freed via clearance sales or revised purchase quantities.
- 📣 **Enhance marketing** for vendors like Alisa Carr Beverages (turnover: 0.62) to drive sales velocity.

By implementing these recommendations, the business can achieve **sustainable profitability**, mitigate supply chain risk, and unlock millions in trapped inventory capital.

---

## 👤 Author & Contact

**Krishna Gupta**

[![Email](https://img.shields.io/badge/Email-krishnagupta231296%40gmail.com-red?style=flat-square&logo=gmail)](mailto:krishnagupta231296@gmail.com)
[![Phone](https://img.shields.io/badge/Phone-%2B91%208368061760-green?style=flat-square&logo=whatsapp)

---

<p align="center">
  <i>⭐ If you found this project helpful, please consider giving it a star!</i>
</p>
