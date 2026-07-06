# Power-BI-Projects

Welcome to my personal Power BI portfolio repository! Here you will find a collection of Power BI projects and dashboards that demonstrate my skills in data visualization, business intelligence, analytics, data modeling, DAX, and interactive reporting using Power BI.

---

# Project #1

## EAG WIT PO Tracker Report

### Project Overview

Developed the **EAG WIT PO Tracker Report** in Power BI to provide end-to-end visibility of Purchase Order (PO) status across the East Asia GeoUnit, covering Malaysia, Thailand, Philippines, Vietnam, and Myanmar.

The dashboard automated manual tracking, monitored overdue and pending POs, and enabled stakeholders to identify bottlenecks, improving procurement monitoring and reporting efficiency.

### Overview

This project was developed during my internship at **SLB** as part of the Planning and Supply Chain function. It focused on improving procurement visibility by replacing manual tracking with a centralized dashboard.

<p align="center">
  <a href="https://github.com/user-attachments/assets/3b1e30f3-27c8-4560-b825-4f4f864e6108">
    <img src="https://github.com/user-attachments/assets/3b1e30f3-27c8-4560-b825-4f4f864e6108" width="700" alt="Dashboard Overview">
  </a>
</p>

<p align="center">
  <a href="https://github.com/user-attachments/assets/ef7fb1a4-8c61-4a87-b74e-955fa110b7a1">
    <img src="https://github.com/user-attachments/assets/ef7fb1a4-8c61-4a87-b74e-955fa110b7a1" width="550" alt="Dashboard Documentation">
  </a>
</p>

<p align="center">
  <a href="https://github.com/user-attachments/assets/6d76bcd8-5985-4613-80ca-55681cc87f54">
    <img src="https://github.com/user-attachments/assets/6d76bcd8-5985-4613-80ca-55681cc87f54" width="700" alt="PO Tracker">
  </a>
</p>

<p align="center">
  <a href="https://github.com/user-attachments/assets/ecd4049b-94f8-4f5a-b9c9-eaddaabe75c4">
    <img src="https://github.com/user-attachments/assets/ecd4049b-94f8-4f5a-b9c9-eaddaabe75c4" width="700" alt="Dashboard Analysis">
  </a>
</p>










<img width="1234" height="708" alt="image" src="https://github.com/user-attachments/assets/3b1e30f3-27c8-4560-b825-4f4f864e6108" />
<img width="972" height="1304" alt="image" src="https://github.com/user-attachments/assets/ef7fb1a4-8c61-4a87-b74e-955fa110b7a1" />
<img width="952" height="540" alt="image" src="https://github.com/user-attachments/assets/6d76bcd8-5985-4613-80ca-55681cc87f54" />
<img width="1434" height="812" alt="image" src="https://github.com/user-attachments/assets/ecd4049b-94f8-4f5a-b9c9-eaddaabe75c4" />

## Methodology

**Process Mapping:** Analyzed the existing Purchase Order (PO) tracking workflow to identify bottlenecks, key stakeholders, and critical data fields such as PO status, ETA, ETD, plant location, and impact month.

**Data Collection & Preparation:** Consolidated and standardized PO data from Microsoft Excel and SharePoint by validating entries, creating calculated columns, and ensuring consistent formatting for seamless integration into Power BI.

**Data Modeling:** Developed relationships between datasets and implemented DAX measures to calculate key procurement KPIs, financial metrics, and real-time operational insights.

**Dashboard Development:** Built interactive Power BI dashboards with automated data refresh, dynamic filtering, role-based access, and real-time visualization to replace manual email-based tracking.

**Testing & Optimization:** Validated dashboard accuracy against existing manual records, gathered stakeholder feedback, and refined visuals and calculations to improve usability and decision-making.

## Analysis & Visualization

**Purchase Order Status:** Monitored Approved, In-Transit, In-Use, and other PO statuses to provide a real-time operational overview.

**Open Purchase Order Value:** Calculated the financial value of active purchase orders to monitor procurement commitments.

**Monthly Impact Analysis:** Compared planned versus actual PO impact values to support budgeting and resource planning.

**Regional Procurement Visibility:** Enabled stakeholders across Malaysia, Thailand, Philippines, Vietnam, and Myanmar to track procurement activities through a centralized dashboard.

**Operational Performance:** Identified procurement bottlenecks, monitored dashboard refresh status, and improved visibility into supply chain operations through interactive reports.

## Tools

- Microsoft Power BI  
- Power Query  
- DAX  
- Microsoft Excel  
- Microsoft SharePoint  
- Microsoft Teams  
- SAP Integrated Business Planning (SAP IBP)

  ## Key DAX Measures

### Open PO Value
Calculates the total value of all active Purchase Orders with statuses:
- Approved
- In-Transit
- In-Use

```DAX
Open PO Value =
CALCULATE(
    SUM(potracker1[PO Value]),
    FILTER(
        potracker1,
        potracker1[STATUS] IN {
            "APPROVED",
            "IN-TRANSIT",
            "IN-USE"
        }
    )
)
```

**Purpose**
- Tracks total financial commitments across active procurement.
- Supports budgeting and procurement monitoring.

---

### Open PO Value (In-Transit)

```DAX
Open PO Value IN-TRANSIT =
CALCULATE(
    SUM(potracker1[PO Value]),
    FILTER(
        potracker1,
        potracker1[STATUS] = "IN-TRANSIT"
    )
)
```

**Purpose**
- Measures the financial value of goods currently in transit.
- Helps monitor logistics performance.

---

### Current Month Actual Impact

```DAX
Current Month Actual Impact =
CALCULATE(
    SUM(potracker1[PO Value]),
    FILTER(
        potracker1,
        MONTH(potracker1[ACTUAL IMPACT MONTH]) = MONTH(TODAY()) &&
        YEAR(potracker1[ACTUAL IMPACT MONTH]) = YEAR(TODAY())
    )
)
```

**Purpose**
- Calculates the total PO value impacting the current month.
- Used for monitoring actual monthly procurement costs.

---

### Current Month Planned Impact

```DAX
Current Month Planned Impact =
CALCULATE(
    SUM(potracker1[PO Value]),
    FILTER(
        potracker1,
        MONTH(potracker1[Planned Impact Month]) = MONTH(TODAY()) &&
        YEAR(potracker1[Planned Impact Month]) = YEAR(TODAY())
    )
)
```

**Purpose**
- Calculates planned procurement impact for the current month.
- Supports planning and budget forecasting.

---

### Last Refreshed

```DAX
Last Refreshed = NOW()
```

**Purpose**
- Displays the dashboard refresh timestamp.
- Provides confidence that users are viewing the latest available data.

Project #2
---
# Executive Sales Dashboard

## Project Overview

This project was developed as part of my preparation for the **Microsoft Power BI Data Analyst Associate (PL-300)** certification. Using a retail sales dataset provided during the training, I designed an interactive Power BI dashboard to analyze sales performance, profitability, customer purchasing patterns, and regional trends.

The project demonstrates an end-to-end Business Intelligence workflow, from data cleaning and transformation to data modeling, DAX calculations, and dashboard development.

---

## Dashboard Preview

### Executive Overview
<img width="1886" height="1072" alt="image" src="https://github.com/user-attachments/assets/b318ef3a-aec3-4ffe-96ff-087d1989e5d4" />

### Sales Performance
<img width="1988" height="1132" alt="image" src="https://github.com/user-attachments/assets/57e5114b-e730-4c6c-b801-35ecf52f29e7" />

### Profitability Insights
<img width="2020" height="1140" alt="image" src="https://github.com/user-attachments/assets/75e44daa-cd32-487c-ba63-1af6076478d5" />

---

## Methodology

### Data Collection
- Imported retail sales data from Microsoft Excel.

### Data Cleaning & Transformation
- Cleaned and transformed raw Excel data using Power Query.
- Removed duplicate records.
- Standardized column names and data formats.
- Corrected inconsistent data types.
- Handled missing values.
- Structured the dataset for efficient reporting.

### Data Modeling
Designed a **Star Schema** consisting of:

**Fact Table**
- FactSales

**Dimension Tables**
- DimDate
- DimProduct
- DimCustomer
- DimRegion

The model was optimized using one-to-many relationships to improve report performance and filtering.
<img width="1158" height="786" alt="image" src="https://github.com/user-attachments/assets/32f9b595-a35a-4f0f-96d9-2c2fe3c03b84" />

### DAX Development
Created custom DAX measures to calculate business KPIs, including:

- Total Sales
- Total Profit
- Profit Margin %
- Total Orders
- Quantity Sold
- Sales by Region
- Product Profitability### Dashboard Development

Built an interactive dashboard consisting of:

- Executive Overview
- Sales Performance Analysis
- Profitability Analysis

The dashboard includes dynamic slicers for:

- Year
- Quarter
- Region
- Product

---

## Analysis & Visualization

### Executive Overview
- Total Sales
- Total Profit
- Profit Margin
- Total Orders
- Quantity Sold
- Monthly Sales Trend
- Top Products by Quantity Sold
- Monthly Order Volume

### Sales Performance
- Product Sales Performance
- Regional Sales Comparison
- Regional Order Analysis
- Product Performance Matrix

### Profitability Analysis
- Cost vs Profit Trend
- Regional Profit Margin
- Product Profitability Breakdown
- Profit Margin Analysis

---

## Tools

- Microsoft Power BI
- Power Query
- DAX
- Microsoft Excel

---

## Skills Demonstrated

- Data Cleaning
- Data Transformation
- Data Modeling
- Star Schema Design
- DAX
- Power Query
- Business Intelligence
- Dashboard Design
- KPI Development
- Data Visualization
- Interactive Reporting

---

## Project Highlights

- Built a complete Business Intelligence solution from raw Excel data.
- Designed a Star Schema data model for optimized performance.
- Created interactive dashboards with drill-down capabilities.
- Developed reusable DAX measures for business KPIs.
- Applied best practices in Power BI data modeling and visualization.

## Data Preparation

The dataset was provided as an Excel workbook during the Microsoft PL-300 training. Although the data was relatively well-structured, Power Query was used to prepare it for analysis by:

- Verifying data types
- Checking for duplicate records
- Validating missing values
- Standardizing date formats
- Creating dimension tables for Products, Customers, Regions, and Dates
- Preparing the dataset for a star schema model
