# 📊 Power BI Dashboard – Performance & Trend Analysis

![PowerBI](https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Tool-Power%20Query-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/Language-DAX-F2C811?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

> An interactive Power BI dashboard designed to track business KPIs, analyze performance trends, and support data-driven decision-making through dynamic visuals and drill-down filters.

---

## 📌 Project Overview

This project showcases an end-to-end Power BI reporting solution — from raw data import and transformation in Power Query, to DAX measure creation, to building an interactive multi-page dashboard with filters and drill-through capabilities.

---

## 🎯 Objectives

- Import and transform raw datasets using Power Query
- Create calculated measures using DAX (Total, Average, Growth %)
- Build an interactive dashboard with slicers and drill-through filters
- Design a clear, business-ready layout for management reporting

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Dashboard development |
| Power Query (M Language) | Data ingestion and transformation |
| DAX | Calculated measures and KPIs |
| Data Modeling | Table relationships and star schema |

---

## 📂 Project Structure

```
powerbi-performance-dashboard/
│
├── data/
│   ├── sales_data.xlsx          # Sales transactions
│   ├── targets.xlsx             # Monthly targets
│   └── region_mapping.xlsx      # Region master table
│
├── dashboard/
│   └── performance_dashboard.pbix   # Power BI Desktop file
│
├── screenshots/
│   ├── overview_page.png            # Executive overview page
│   ├── regional_analysis.png        # Regional breakdown page
│   └── trend_analysis.png           # Monthly trend page
│
├── dax_measures.md              # All DAX measures documented
└── README.md
```

---

## 🔍 Key Features

### 1. Data Transformation (Power Query)
- Merged sales, targets, and region tables
- Removed blank rows and null values
- Split date columns into Year, Month, Quarter
- Standardized category and region names
- Added calculated columns (e.g., Revenue After Discount)

### 2. DAX Measures
```DAX
-- Total Revenue
Total Revenue = SUM(Sales[Revenue])

-- Average Order Value
Avg Order Value = AVERAGE(Sales[Revenue])

-- Month-over-Month Growth %
MoM Growth % = 
VAR CurrentMonth = [Total Revenue]
VAR PrevMonth = CALCULATE([Total Revenue], DATEADD(Dates[Date], -1, MONTH))
RETURN DIVIDE(CurrentMonth - PrevMonth, PrevMonth, 0) * 100

-- Target vs Actual %
Target Achievement % = 
DIVIDE([Total Revenue], SUM(Targets[Target_Revenue]), 0) * 100

-- YTD Revenue
YTD Revenue = TOTALYTD([Total Revenue], Dates[Date])
```

### 3. Dashboard Pages

#### Page 1 — Executive Overview
- KPI cards: Total Revenue, Total Orders, Avg Order Value, MoM Growth %
- Revenue vs Target gauge chart
- Monthly revenue trend (line chart)
- Top 5 categories (bar chart)

#### Page 2 — Regional Analysis
- Map visual showing revenue by region
- Region-wise revenue table with conditional formatting
- Slicer: Region, Category, Time Period

#### Page 3 — Trend Analysis
- Monthly and quarterly revenue trend lines
- YoY comparison chart
- Growth % indicator cards
- Drill-through to individual category performance

### 4. Interactivity
- Cross-filtering enabled across all visuals
- Date slicer (Year, Quarter, Month)
- Region and Category multi-select slicers
- Drill-through from summary to detail pages
- Bookmarks for saved filter views

---

## 📈 Key Insights Surfaced

- **Revenue Growth:** 18% growth in Q4 vs Q3 driven by Electronics category
- **Underperforming Region:** East region missed monthly targets by 12% for 3 consecutive months
- **Best Month:** October showed highest order volume (peak season effect)
- **Category Leader:** Electronics accounted for 35% of total revenue

---

## 💡 Skills Demonstrated

- Power Query for multi-source data transformation
- DAX for time intelligence and calculated KPIs
- Star schema data modeling (Fact + Dimension tables)
- Interactive report design for business stakeholders
- Clear visual hierarchy for executive-level reporting

---

## 🚀 How to Use

### Prerequisites
- [Download Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Free)

### Steps
1. Clone or download this repository
2. Open `dashboard/performance_dashboard.pbix` in Power BI Desktop
3. If prompted, update data source paths to point to the `data/` folder
4. Refresh the data (Home → Refresh)
5. Explore using the slicers and drill-through options

---

## 📸 Dashboard Preview

> *(Add your Power BI screenshots here)*
> Take screenshots of each page → save in `/screenshots/` → update below:

**Overview Page**
![Overview](screenshots/overview_page.png)

**Regional Analysis**
![Regional](screenshots/regional_analysis.png)

**Trend Analysis**
![Trends](screenshots/trend_analysis.png)

---

## 📋 DAX Measures Reference

See [`dax_measures.md`](dax_measures.md) for the full list of all measures used in this project with explanations.

---

## 👤 Author

**Vishal Khare**
📧 vishalkhare54@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/vishalkhare9bb31436b)
🐙 [GitHub](https://github.com/VishalKhare1402)
