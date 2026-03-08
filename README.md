# 📊 Power BI – Executive Summary Sales Report

<div align="center">

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

**An interactive sales analytics dashboard built with Microsoft Power BI.**  
Explore order quantities, sales amounts, product categories, and reseller channels across geographies and time — all in one place.

[📥 View Report](#-getting-started) • [📸 Screenshots](#-dashboard-screenshots) • [📂 Dataset](#-dataset) • [✨ Features](#-features)

</div>

---

## 📌 Table of Contents

- [About the Project](#-about-the-project)
- [Dashboard Screenshots](#-dashboard-screenshots)
- [Features](#-features)
- [Dataset](#-dataset)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation & Setup](#installation--setup)
  - [Opening the Report](#opening-the-report)
- [How to Use the Dashboard](#-how-to-use-the-dashboard)
- [Interactivity Guide](#-interactivity-guide)
- [Key Insights](#-key-insights)
- [Data Model](#-data-model)
- [File Structure](#-file-structure)
- [Tech Stack](#-tech-stack)
- [FAQ](#-faq)
- [License](#-license)

---

## 🧠 About the Project

This repository contains a **Microsoft Power BI report** (`Report.pbix`) that delivers an executive-level view of AdventureWorks sales data across multiple fiscal years. It transforms raw Excel data into an interactive, filterable dashboard that helps stakeholders understand sales performance, product demand, and regional distribution at a glance.

The report covers:

- 📅 **Time Periods** — 2017 through 2021 (Year → Month hierarchy)
- 🌍 **Regions** — North America, Europe, and Pacific (via ArcGIS bubble map)
- 🛒 **Product Categories** — Bikes, Components, Clothing, Accessories
- 🏢 **Sales Channels** — Warehouse, Value Added Reseller, Specialty Bike Shop

---

## 📸 Dashboard Screenshots

All screenshots are stored in the [`Dashboard ScreenShot/`](./Dashboard%20ScreenShot/) folder.

---

### 🔹 Full Overview — All Years, No Filters Applied
> A complete view of global order quantities on the map, monthly sales trends on the line chart, and the full category/channel breakdown in the matrix table.

![Full Overview](https://raw.githubusercontent.com/Karnita-Saumya/powerbi-executive-summary-sales-report/main/Dashboard%20ScreenShot/SS1.png)

---

### 🔹 2018 — Year Filter Active
> Filtering to 2018 reveals the full monthly trend for that year. Total sales drop to ₹65,91,525.97, with Bikes still leading at ₹51,03,681.29.

![2018 Year Filter](https://raw.githubusercontent.com/Karnita-Saumya/powerbi-executive-summary-sales-report/main/Dashboard%20ScreenShot/SS2.png)

---

### 🔹 Drill-Down: May Sales Tooltip
> Hovering over May on the line chart reveals Sum of Sales Amount of **₹9,86,866.90** and Sales Amount by Due Date of **₹9,00,011.67**, with an option to drill up the time hierarchy.

![May Tooltip Drill-Down](https://raw.githubusercontent.com/Karnita-Saumya/powerbi-executive-summary-sales-report/main/Dashboard%20ScreenShot/SS3.png)

---

### 🔹 Cross-Filter: Components Category Selected
> Selecting the Components row in the matrix table cross-filters the line chart, showing a peak of ₹1.88M in September and strong performance through Q3.

![Components Cross-Filter](https://raw.githubusercontent.com/Karnita-Saumya/powerbi-executive-summary-sales-report/main/Dashboard%20ScreenShot/SS4.png)

---

### 🔹 Map Visual — Two Visual Types Compared
> A side-by-side view of the legacy Bing Map and the ArcGIS map visual, showing order quantity bubbles concentrated in North America and Europe.

![Map Visual Comparison](https://raw.githubusercontent.com/Karnita-Saumya/powerbi-executive-summary-sales-report/main/Dashboard%20ScreenShot/SS5.png)

---

### 🔹 Data Model — Star Schema
> The underlying Power BI data model showing the Sales fact table connected to Date, Product, Customer, Reseller, SalesTerritory, and SalesOrder dimension tables.

![Data Model](https://raw.githubusercontent.com/Karnita-Saumya/powerbi-executive-summary-sales-report/main/Dashboard%20ScreenShot/SS6.png)

---

## ✨ Features

| Feature | Description |
|---|---|
| 📅 **Date Slicer** | Collapsible Year → Month hierarchy to filter all visuals simultaneously |
| 📈 **Dual-Series Line Chart** | Monthly comparison of Sum of Sales Amount vs. Sales Amount by Due Date with area shading |
| 🗺️ **ArcGIS Bubble Map** | Country-level order quantity visualization with proportional bubble sizing |
| 📋 **Matrix Table** | Hierarchical breakdown of sales by Category → Sales Channel with expandable rows |
| 🔍 **Drill Down / Drill Up** | Navigate the time hierarchy directly from the line chart tooltip |
| 🔗 **Cross-Filtering** | Every visual is linked — selecting one automatically filters all others |
| 🧭 **Hover Tooltips** | Exact numeric values on every data point across all visuals |
| 🎨 **Consistent Color Coding** | Orange for Sum of Sales Amount, Blue for Sales Amount by Due Date across all visuals |

---

## 📂 Dataset

The source data `AdventureWorks_Sales.xlsx` is stored in the root of this repository.

### 📋 Key Tables in the Data Model

| Table | Type | Description |
|---|---|---|
| `Sales` | Fact | Core transaction table — Sales Amount, Order Quantity, Extended Amount, Product Standard Cost |
| `Date` | Dimension | Full date hierarchy — Date, DateKey, Month, MonthKey, Fiscal Quarter, Fiscal Year |
| `Product` | Dimension | Product details — Category, Subcategory, Model, Color, List Price, Standard Cost, SKU |
| `Customer` | Dimension | Customer info — City, Country-Region, Postal Code, State-Province |
| `Reseller` | Dimension | Reseller info — Business Type, City, Country-Region, Reseller ID |
| `SalesTerritory` | Dimension | Territory groupings — Country, Region, Group |
| `SalesOrder` | Dimension | Order line details — Channel, Sales Order, Sales Order Line |

### 📊 Quick Stats

| Metric | Value |
|---|---|
| Total Sales (All Years) | ₹8,04,50,596.98 |
| Time Range | 2017 – 2021 |
| Product Categories | 4 (Bikes, Components, Clothing, Accessories) |
| Sales Channels | 3 (Warehouse, Value Added Reseller, Specialty Bike Shop) |
| Regions Covered | North America, Europe, Pacific |

---

## 🚀 Getting Started

### Prerequisites

| Requirement | Details |
|---|---|
| **Power BI Desktop** | Free — [Download here](https://powerbi.microsoft.com/en-us/desktop/) |
| **OS** | Windows 10 or Windows 11 (Power BI Desktop is Windows-only) |
| **Microsoft Excel** *(optional)* | Only needed to view or edit `AdventureWorks_Sales.xlsx` |

> 🍎 **Mac Users:** Power BI Desktop does not run on macOS natively.  
> Options: Use **[Power BI on the Web](https://app.powerbi.com)** (free Microsoft account required), or run Windows via **Parallels / Boot Camp / a VM**.

---

### Installation & Setup

**1. Clone this repository**

```bash
git clone https://github.com/Karnita-Saumya/powerbi-executive-summary-sales-report.git
cd powerbi-executive-summary-sales-report
```

Or click **Code → Download ZIP** on GitHub and extract the folder.

**2. Install Power BI Desktop** *(skip if already installed)*

1. Visit [https://powerbi.microsoft.com/desktop](https://powerbi.microsoft.com/desktop)
2. Click **"Download free"**
3. Run the installer and complete the setup
4. Launch **Power BI Desktop**

---

### Opening the Report

**3. Open `Report.pbix`**

1. In Power BI Desktop, go to **File → Open report → Browse**
2. Navigate to your cloned/extracted folder
3. Select **`Report.pbix`** and click **Open**
4. The full dashboard loads immediately — no refresh or login required ✅

> 💡 If prompted about data source credentials, click **"Cancel"** — all data is embedded inside the `.pbix` file.

---

## 🧭 How to Use the Dashboard

### 1️⃣ Date Slicer (Left Panel)

The left panel is a **Year → Month hierarchy slicer**.

- ☑️ Check a **year** (e.g., `2018`) to select the entire year
- ▶️ Click the **arrow** next to a year to expand and pick individual months
- `Ctrl + Click` to select **multiple months** across different years
- Click the **eraser icon** at the top of the slicer to clear all selections

---

### 2️⃣ Line Chart — Sales Amount vs. Sales Amount by Due Date

- **Orange line** = Sum of Sales Amount (order date basis)
- **Blue line** = Sales Amount by Due Date
- Data labels (e.g., `1.4M`) are shown directly on each data point
- The **shaded area** beneath each line provides a quick sense of volume
- **Right-click** any data point to access Drill Down / Drill Up options

---

### 3️⃣ Map — Sum of Order Quantity by Country-Region

- **Bubble size** represents the relative order quantity for that country
- **Hover** over a bubble to see the country name and exact value
- **Click** a bubble to cross-filter all other visuals to that region
- Use `+` / `−` buttons or scroll to zoom the map in or out

---

### 4️⃣ Matrix Table — Sales by Category & Channel

- Rows are **grouped by Category** (Bikes, Components, Clothing, Accessories)
- Click the **expand arrow** next to any category to reveal sub-channel rows
- **Click** any row to cross-filter the line chart and map to that category/channel
- Values are shown as **Sum of Sales Amount** in the right column

---

## 🔗 Interactivity Guide

| Action | What Happens |
|---|---|
| Select a year or month in the slicer | All three visuals filter to that time period only |
| Click a data point on the line chart | Highlights related categories/channels in the matrix |
| Click a country bubble on the map | Filters the line chart and matrix to that region |
| Click a row in the matrix table | Cross-filters the line chart and map to that category |
| Right-click a line chart point | Opens **Drill Up** / **Drill Down** time hierarchy options |
| Hover over any visual element | Displays a tooltip with exact numeric values |
| Click empty space inside a visual | Clears that visual's active cross-filter |

---

## 📈 Key Insights

Notable findings you can discover in the dashboard:

- 🚲 **Bikes** is the dominant category, accounting for **82%** of total revenue (₹6,63,02,381.56)
- 🏭 **Warehouse** is the top-performing sales channel across all product categories
- 📅 **September** consistently peaks in monthly sales across multiple years (₹1.22M in 2018)
- 📉 **January** is the lowest-performing month, consistently across all years
- 🌍 **North America** dominates order volume, followed by Europe on the map
- 🔧 **Components** rank second in revenue at ₹1,17,99,076.66, far ahead of Clothing and Accessories
- 📆 **2018** shows the lowest annual total (₹65,91,525.97), suggesting this may be a partial-year or early-ramp dataset

---

## 🗃️ Data Model

The report is built on a **Star Schema** — a central Sales fact table connected to six dimension tables:

```
Sales (Fact Table)
├── Date           → DueDateKey, OrderDateKey  (role-playing dimension)
├── Product        → ProductKey  (Category, Subcategory, Model, Color, Price)
├── Customer       → CustomerKey (City, Country-Region, Postal Code)
├── Reseller       → ResellerKey (Business Type, City, Country-Region)
├── SalesTerritory → SalesTerritoryKey (Country, Region, Group)
└── SalesOrder     → SalesOrderLineKey (Channel, Order Number, Line)
```

> 🔁 **Note:** The `Date` table connects to `Sales` via two relationships — `OrderDateKey` (active) and `DueDateKey` (inactive, used via DAX `USERELATIONSHIP()`). This enables the dual-series line chart comparing sales on both date dimensions.

---

## 📁 File Structure

```
📦 powerbi-executive-summary-sales-report/
│
├── 📁 Dashboard ScreenShot/
│   ├── 🖼️ SS1.png     ← Full dashboard, no filters
│   ├── 🖼️ SS2.png     ← 2018 year filter active
│   ├── 🖼️ SS3.png     ← May drill-down tooltip
│   ├── 🖼️ SS4.png     ← Components category cross-filter
│   ├── 🖼️ SS5.png     ← Map visual type comparison
│   └── 🖼️ SS6.png     ← Data model — star schema
│
├── 📗 AdventureWorks_Sales.xlsx   ← Source data
├── 📊 Report.pbix                 ← Power BI report ← Open this!
└── 📄 README.md                   ← This file
```

---

## 🛠️ Tech Stack

| Tool | Role |
|---|---|
| **Microsoft Power BI Desktop** | Report design, DAX measures, interactive visuals, data modeling |
| **Microsoft Excel (.xlsx)** | Source data file (AdventureWorks dataset) |
| **Power Query (M Language)** | Data loading and transformation inside Power BI |
| **DAX** | Calculated measures — Sales Amount by Due Date via `USERELATIONSHIP()` |
| **ArcGIS / Esri Maps** | Geographic bubble map visual for order quantity by country |

---

## ❓ FAQ

**Q: Can I use this on a Mac?**  
A: Power BI Desktop is Windows-only. Mac users can upload `Report.pbix` to [app.powerbi.com](https://app.powerbi.com) using a free Microsoft account to view it in the browser.

**Q: Do I need a paid Power BI license?**  
A: No. Opening `.pbix` files in **Power BI Desktop** is completely free. A Pro license is only needed to publish and share reports via the Power BI Service online.

**Q: The map shows a "This visual type is being retired" warning — is that a problem?**  
A: The report still works fully. Power BI is deprecating the older Map visual in favour of Azure Maps. You can upgrade it by switching to the **Azure Maps** visual in edit mode in Power BI Desktop.

**Q: Can I connect this to live AdventureWorks data?**  
A: Yes! In Power BI Desktop, go to **Home → Transform Data → Data Source Settings** and update the connection to point to your own AdventureWorks database or updated Excel file.

**Q: How do I reset all filters at once?**  
A: Clear the slicer using its **eraser icon**, and click any blank space inside other visuals to deselect cross-filters. You can also go to **View → Reset to default** if a reset bookmark has been configured.

**Q: Why are there two lines on the line chart?**  
A: The orange line shows **Sum of Sales Amount** (based on Order Date), while the blue line shows **Sales Amount by Due Date**. This dual view helps identify fulfillment delays — gaps between the two lines indicate orders placed but not yet fulfilled by their due date.

---

## 📄 License

This project is licensed under the **MIT License**.  
The `AdventureWorks_Sales.xlsx` dataset is a sample file originally provided by **Microsoft** for educational and demonstration purposes.

---

<div align="center">

Made with ❤️ by [Karnita-Saumya](https://github.com/Karnita-Saumya)

⭐ **If you found this project useful, please give it a star!** ⭐

</div>
