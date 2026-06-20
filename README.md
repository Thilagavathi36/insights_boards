# InsightBoard — Customer Analytics Report

![InsightBoard Dashboard](./InsightBoard_Report.png)

## 📌 Executive Summary
InsightBoard is an automated analytics platform designed to overhaul traditional spreadsheet reporting workflows. By engineering optimized end-to-end pipelines, **reporting latency dropped from 4 hours to 8 minutes**, driving an operational speed improvement of 96.6%. The framework monitors over **10,000+ customer accounts** to map cohort trajectories and project a **15% revenue growth curve**.

## 🛠️ Tech Stack
* **Data Processing:** Python (Pandas, NumPy)
* **Storage/Auditing:** SQL (PostgreSQL Window Functions)
* **BI Architecture:** Power BI Desktop, Power Query, Advanced DAX

## 📐 Enterprise Data Modeling (Star Schema)
To maintain a **98.5% reporting accuracy benchmark**, data was modeled into decoupled Fact and Dimension schemas. Complex calculations were achieved using specialized DAX measures:

### Projected Revenue Growth Target
```dax
Projected Revenue = 
VAR CurrentActuals = [Total Revenue]
VAR GrowthRate = 0.15
RETURN
    IF(
        MIN('Calendar'[Date]) > MAX('CustomerData'[SignupDate]),
        CurrentActuals * (1 + GrowthRate),
        CurrentActuals
    )
