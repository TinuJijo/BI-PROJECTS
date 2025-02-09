# PlantCo Performance Analysis: A Dynamic Reporting Solution

## Project Overview
This Power BI project showcases the development of a dynamic and interactive performance report for a fictional company, PlantCo. The report empowers users to analyze key business metrics, including sales, gross profit, and quantity, on both a year-to-date and prior-year-to-date basis. Leveraging switch measures and conditional formatting, the report provides a clear and concise overview of performance trends, highlighting areas of growth and potential concern

https://github.com/user-attachments/assets/94fab8f3-1a0a-4cfb-a30b-34f381a48567

### Key Features
- **Interactive slicers** for metric selection and date filtering.
- **Waterfall chart** to visualize the drivers of YTD vs. PYTD performance, with drill-down capabilities.
- **Stacked column and line chart** for trend analysis across product types and time periods.
- **Scatter chart** for account profitability segmentation, with average lines for gross profit percentage and sales.
- **Conditional formatting** to highlight performance against targets.
- **Dynamic report and chart titles** that update based on user selections.
- **Modern and clean design** with consistent formatting and attention to detail.

---

## Process Breakdown

### 1. Data Acquisition and Transformation (Power Query)
- Imported data from an Excel workbook containing three tables: `fact_sales`, `dim_account`, and `dim_product`.
- Renamed and cleaned tables for clarity.
- Removed duplicate values from `dim_product` and `dim_account`.
- Ensured proper data types, e.g., converting `invoice_date` to Date type.
- Loaded transformed data into the Power BI model.

### 2. Data Modeling (Relationships and Calculated Tables)
- Created a `dim_date` table using `CALENDARAUTO()`.
- Added an `in_past` column to `dim_date` to flag prior dates for PYTD calculations.
- Created a `slicer_values` table for metric selection (`Sales`, `Gross Profit`, `Quantity`).
- Established relationships:
  - `fact_sales` ↔ `dim_product` (one-to-many)
  - `fact_sales` ↔ `dim_account` (one-to-many)
  - `fact_sales` ↔ `dim_date` (one-to-many)

### 3. DAX Measure Creation
- Created a **measures table** to organize all DAX measures.
- Developed base measures for `Sales`, `Quantity`, and `Cost of Goods`.
- Created **YTD and PYTD measures** using `TOTALYTD()` and `SAMEPERIODLASTYEAR()`.
- Implemented **switch measures** (`switch_PYTD` and `switch_YTD`) using `SELECTEDVALUE()`.
- Calculated `year_to_date_vs_prior_year_to_date` and `GP_percent`.
- Created **dynamic title measures** for visuals using string concatenation.

### 4. Report Design and Visualization
- Imported a **custom background** from PowerPoint.
- Created slicers for **metric selection** and **year filtering**.
- Developed visuals:
  - **Card visuals** for YTD, PYTD, and variance values.
  - **Treemap** for bottom 10 countries by YTD vs. PYTD.
  - **Waterfall chart** for YTD vs. PYTD variance breakdown.
  - **Stacked column and line chart** for monthly and quarterly trends.
  - **Scatter chart** for account segmentation.
- Applied **dynamic titles, conditional formatting, and consistent styling**.

### 5. Report Testing and Refinement
- Validated slicers, filters, and drill-down functionality.
- Refined tooltips and adjusted layout for readability.
- Optimized performance by reviewing DAX measures and model size.
- Checked **mobile view** for usability.
- Ensured **accessibility** with proper color contrast and text size.

---

## Summary
The project demonstrates proficiency in data modeling, DAX measure creation (including advanced techniques like switch measures and time intelligence functions), and report design best practices. The report's intuitive interface and dynamic features enable users to quickly access and interpret critical business information, supporting data-driven decision-making.  The project also emphasizes best practices in visual communication, accessibility, and performance optimization.
