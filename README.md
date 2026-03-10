# Inventory Management Dashboard (Power BI)

## Project Overview

This project presents an **Inventory Management Dashboard** built using **Power BI** as part of the **Data Analytics Skill Up program by GeeksforGeeks**.

The dashboard helps analyze **inventory movement, sales performance, revenue, and profitability** using interactive visualizations and business intelligence techniques.

In addition to completing the assigned project, I enhanced the dashboard with **improved design, additional metrics, and better visual storytelling**.

---

## Dashboard Preview

```
![Dashboard Preview](dashboard.png)
```

---

## Key Insights

The dashboard provides insights into:

* Revenue and COGS analysis
* Gross Margin and profitability tracking
* Sales quantity trends
* Inventory movement and stock levels
* Revenue distribution by product
* Yearly comparison of Revenue and Gross Margin
* Average daily demand for inventory planning

---

## Dashboard Features

### KPI Metrics

* Revenue
* COGS
* Gross Margin
* Gross Margin %
* Sales Quantity


### Visualizations

* Line Chart → Sales Quantity trend by month
* Gauge Chart → Average Daily Demand
* Donut Chart → Revenue by Product ID
* Column Chart → Sales Quantity by Product
* Column + Line Chart → Revenue vs Gross Margin by Year
* Interactive Slicers → Product, Supplier, Category, Date

---

## Tools & Technologies

| Tool          | Purpose                                   |
| ------------- | ----------------------------------------- |
| Power BI      | Data visualization and dashboard creation |
| DAX           | Creating business metrics                 |
| Power Query   | Data transformation                       |
| Data Modeling | Table relationships                       |

---

## Key DAX Measures

### Revenue

```DAX
Revenue :=
- SUMX(
    FILTER(Transactions, Transactions[TxnType] = "Sale"),
    Transactions[Quantity] * Transactions[UnitPrice]
)
```

### Gross Margin

```DAX
Gross Margin :=
[Revenue] - [COGS]
```

### Inventory On Hand

```DAX
Inventory On Hand :=
VAR SelectedDate = MAX('Calendar'[Date])
RETURN
CALCULATE(
    SUM(Transactions[Quantity]),
    FILTER(
        ALL('Calendar'[Date]),
        'Calendar'[Date] <= SelectedDate
    )
)
```

---

## Project Structure

```
Inventory-Management-PowerBI
│
├── dataset
│   └── inventory_dataset.xlsx
│
├── dashboard
│   └── inventory_dashboard.pbix
│
├── images
│   └── dashboard_preview.png
│
└── README.md
```

---

## Learning Outcomes

Through this project, I learned:

* Designing interactive Power BI dashboards
* Creating DAX measures for business metrics
* Building data models and relationships
* Using visualizations to communicate insights
* Improving dashboard UI and layout design

---

## Future Improvements

Possible improvements for the dashboard:

* Low stock alerts
* Inventory turnover analysis
* Supplier performance analysis
* Forecasting future demand

---

Adithya Vinod
Data Analyst Aspirant
