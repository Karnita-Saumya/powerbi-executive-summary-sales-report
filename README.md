# 📊 AdventureWorks Executive Sales Report — Power BI
[![GitHub repo](https://img.shields.io/badge/GitHub-powerbi--executive--summary--sales--report-181717?style=for-the-badge&logo=github)](https://github.com/Karnita-Saumya/powerbi-executive-summary-sales-report)

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

> An interactive **Executive Sales Dashboard** built with Power BI, using the AdventureWorks dataset. This report delivers multi-dimensional sales insights across geographies, product categories, channels, and time — designed for executive-level decision-making.

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `Report.pbix` | Power BI Desktop report file |
| `AdventureWorks_Sales.xlsx` | Source data (Excel) used in the report |
| `SS1.png` – `SS6.png` | Dashboard screenshots |

---

## 🖼️ Dashboard Preview

### Overview — All Years
![Executive Summary Overview](SS1.png)

### Filtered View — 2018
![2018 Filtered View](SS2.png)

### Tooltip Drill-Down — May Sales
![Tooltip Drill-Down](SS3.png)

### Category Highlight — Components
![Category Highlight](SS4.png)

### Map Visual Comparison
![Map Visual](SS5.png)

### Data Model
![Data Model](SS6.png)

---

## 📌 Report Highlights

### 🔑 Key Metrics
- **Total Sales Amount:** ₹8,04,50,596.98 (all years)
- **Top Category:** Bikes — ₹6,63,02,381.56
- **Top Sub-channel:** Value Added Reseller & Warehouse
- **Date Range:** 2017 – 2021

### 📈 Visuals Included

| Visual | Description |
|--------|-------------|
| 🗺️ **Map (ArcGIS/Esri)** | Order Quantity by Country-Region — bubble size indicates volume |
| 📉 **Line & Area Chart** | Sum of Sales Amount vs. Sales Amount by Due Date — monthly trends |
| 📋 **Matrix Table** | Sales breakdown by Category → Sub-category → Channel |
| 🗓️ **Slicer** | Year and Month hierarchy filter for cross-report interactivity |

### 🏷️ Product Categories Covered
- **Bikes** (Warehouse, Value Added Reseller, Specialty Bike Shop)
- **Components** (Warehouse, Value Added Reseller, Specialty Bike Shop)
- **Clothing** (Warehouse, Value Added Reseller, Specialty Bike Shop)
- **Accessories**

---

## 🗃️ Data Model

The report is built on a **Star Schema** with the following tables:

```
Sales (Fact Table)
├── Date        → DueDateKey, OrderDateKey
├── Product     → ProductKey (Category, Subcategory, Model, Price)
├── Customer    → CustomerKey (City, Country-Region)
├── Reseller    → ResellerKey (Business Type, City, Country-Region)
├── SalesTerritory → SalesTerritoryKey (Country, Region, Group)
└── SalesOrder  → SalesOrderLineKey
```

**Key Fields in Sales Fact Table:**
`CustomerKey`, `DueDateKey`, `ExtendedAmount`, `OrderQuantity`, `OrderDateKey`, `ProductStandardCost`, `ProductKey`, `ResellerKey`, `SalesAmount`

---

## 🚀 How to Open This Report on Your System

### ✅ Prerequisites

1. **Install Power BI Desktop** (Free)
   - Download from: [https://powerbi.microsoft.com/desktop](https://powerbi.microsoft.com/desktop)
   - Supported on: **Windows 10/11** (64-bit recommended)
   - macOS users: Use a Windows VM or [Power BI Web](https://app.powerbi.com)

2. **Microsoft Account** (free) — required to open `.pbix` files

---

### 📥 Steps to Open the Report

```bash
# 1. Clone this repository
git clone https://github.com/Karnita-Saumya/powerbi-executive-summary-sales-report.git

# 2. Navigate into the folder
cd powerbi-executive-summary-sales-report
```

3. Open **Power BI Desktop**
4. Click **File → Open report → Browse**
5. Select `Report.pbix` from the cloned folder
6. The report will load with all visuals and data pre-embedded ✅

> 💡 **No need to reconnect the data source** — the `.pbix` file contains the data model and all transformations internally.

---

### 🌐 View on Power BI Service (Web)

To share this report online:

1. Open the `.pbix` in Power BI Desktop
2. Click **Home → Publish**
3. Sign in with your Microsoft/Power BI account
4. Choose a workspace → Click **Publish**
5. Visit [app.powerbi.com](https://app.powerbi.com) → open your workspace → view the report in browser

> You can also share the published report link with others so they can view it **without installing Power BI Desktop**.

---

### ⚠️ Troubleshooting

| Issue | Fix |
|-------|-----|
| Map visuals show blank | Enable ArcGIS Maps in **File → Options → Security → Map visuals** |
| "This visual type is being retired" warning | Replace the Bing Map visual with the **Azure Maps** visual |
| Data not loading | Refresh via **Home → Refresh** after re-linking `AdventureWorks_Sales.xlsx` |
| `.pbix` won't open | Ensure Power BI Desktop is up to date (Check: Help → About) |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Report building, DAX, data modeling |
| **Microsoft Excel** | Source data (`AdventureWorks_Sales.xlsx`) |
| **ArcGIS / Esri Maps** | Geographic visualization |
| **DAX** | Calculated measures and KPIs |
| **Power Query (M)** | Data transformation and loading |

---

## 📊 Sample Insights

- 📅 **Peak Sales Month:** September (₹1.22M in 2018 filter view)
- 🌍 **Highest Order Volume Region:** North America & Europe
- 🚲 **Best Performing Category:** Bikes (82% of total revenue)
- 📦 **Top Channel:** Warehouse leads across all categories
- 📉 **Lowest Sales Month:** January (consistent across years)

---

## ⬆️ How to Push This Project to GitHub (First Time)

Since the repository is currently empty, follow these steps to upload all files:

```bash
# 1. Clone the empty repo
git clone https://github.com/Karnita-Saumya/powerbi-executive-summary-sales-report.git
cd powerbi-executive-summary-sales-report

# 2. Copy your project files into this folder:
#    - Report.pbix
#    - AdventureWorks_Sales.xlsx
#    - README.md
#    - SS1.png through SS6.png

# 3. Stage all files
git add .

# 4. Commit
git commit -m "Initial commit: Add Power BI Sales Report, data, and screenshots"

# 5. Push to GitHub
git push origin main
```

> ⚠️ **Note:** `.pbix` files can be large. If your file exceeds 100MB, use [Git LFS](https://git-lfs.github.com/) to track it:
> ```bash
> git lfs install
> git lfs track "*.pbix"
> git add .gitattributes
> ```

---

**Karnita Saumya**
- GitHub: [@Karnita-Saumya](https://github.com/Karnita-Saumya)
- Repository: [powerbi-executive-summary-sales-report](https://github.com/Karnita-Saumya/powerbi-executive-summary-sales-report)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

> ⭐ If you found this useful, please consider giving this repo a star!
