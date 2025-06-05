![Power BI](https://img.shields.io/badge/Tool-Power%20BI-yellow)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)

# 🍫 Chocolate Sales Performance Dashboard

An interactive **Power BI dashboard** for analyzing chocolate product shipments, sales volume, and category trends across a fictional retail network. Built using **Power BI, Excel, DAX**, and dynamic modeling techniques, this dashboard helps uncover key sales insights and business metrics like revenue, shipment size, and category performance.

---

## 🔍 Project Highlights

- Analyze total sales amount, shipment count, and boxes per shipment.
- Compare team member performance using DAX-based KPIs.
- Visualize sales by category and monthly shipment trends.
- Identify top-performing products and categories.
- Evaluate performance against a custom target.

---
---

## 🧠 Data Model Design (Power BI)

The data model follows a **star schema** centered on the `shipments` fact table. It links to four key dimension tables:

- `people`: Contains sales rep details.
- `calendar`: Supports date-based filtering and time intelligence.
- `products`: Provides product and category metadata.
- `locations`: Maps shipments to geographical regions.

This structure supports optimized DAX performance and clear relationship paths.

![Data Model](images/data_model.png)

---

## 📊 Sample Visuals

### Total Sales by Product Category
![Sales by Category](images/sales-by-category.png)

### Monthly Shipment Trend
![Monthly Sales Trend](images/monthly-sales-trend.png)

---

## 📁 Project Structure
Chocolate-Sales-Performance-Dashboard/
│
├── README.md
├── sample-chocolate-sales-data-all.xlsx
├── powerbi-dax-wip.pbix
├── powerbi-data-model-done.pbix
└── images/
    ├── sales-by-category.png
    └── monthly-sales-trend.png


---

## 🧠 Key DAX Measures Used
DAX
Total Amount = SUM(shipments[Amount])
Shipment Count = COUNTROWS(shipments)
Total Boxes = SUM(shipments[Boxes])
Boxes per Shipment = [Total Boxes] / [Shipment Count]
Amount per Shipment = DIVIDE([Total Amount],[Shipment Count])
Barr Amount = CALCULATE([Total Amount], people[Sales_person]="Barr Faughny")
Barr Amount Pct = DIVIDE([Barr Amount], [Total Amount])
Barr Bar Amount = CALCULATE([Total Amount], people[Sales_person]="Barr Faughny", products[Category]= "Bars")
Total Amount (my team v2) = CALCULATE([Total Amount], people[Sales_person] IN {"Barr Faughny", "Beverie Moffet", "Ches Bonnell", "Husien Augar"})
Sales Target = 2000000
Target Comparison v3 = IF([Total Amount]>[Sales Target], "👍", "👎")


---

## 📚 Dataset
- **File:** sample-chocolate-sales-data-all.xlsx
- **Sheets:**
  - **Shipments:** Main transactional data
  - **Dimension Data:** Salespeople and product metadata
  - **Calendar:** For time intelligence & filtering

---

## 🛠 Tools & Technologies
- Microsoft Power BI
- Microsoft Excel
- DAX
- Data Modeling & Relationships

---
