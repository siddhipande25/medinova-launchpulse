# MediNova LaunchPulse – Pharma New Product Launch Dashboard

An interactive multi-page Power BI analytics solution built to track new product launch performance across zones, channels, therapy areas, field force, and SKUs for **MediNova Critical Care Pharma Ltd**.

## Dashboard Preview

### Executive Overview
![Page 1 Overview](screenshots/page1-overview.png)

### Product 360 (Drill-Through View)
![Page 2 Product 360](screenshots/page2-product360.png)

## Dataset & Business Scope
- **Granularity & Scale:** 6,000 order-level records (`Fact_Launch_Sales`) spanning **FY 2025-26** and **FY 2026-27** (April 2025 – September 2026).
- **Geographic & Commercial Coverage:** 12 SKUs across 9 brands, 8 therapy sub-areas, 4 zones (19 states, 24 cities), 240 prescribing doctors, 72 hospital/retail accounts, and 24 sales representatives.
- **Overall Dataset Metrics (FY 2025-26 & FY 2026-27):**
  - **Total Net Sales:** ₹19.45 Cr (`₹194.49M`) vs. **Target Sales:** ₹21.79 Cr (`₹217.87M`)
  - **Total Gross Profit:** ₹11.20 Cr (`₹112.02M`)
  - **Total Units Sold:** 6,55,987 | **Total Prescriptions (Rx):** 89,593

## Key Dashboard Features
- **Executive KPI Cards & Variance Tracking:** Monitors Net Sales, Target Sales, Units Sold, Prescriptions, Prescribing Doctors, and Gross Profit with interactive slicers for Fiscal Year, Zone, Therapy Area, and Launch Phase.
- **Multi-Dimensional Performance Breakdown:** Visualizes monthly Net Sales vs. Target trends, Prescriptions by Therapy Area, Net Sales by Zone, Therapy Area, Field Force, Distribution Channel, and Top 10 Prescribing Doctors alongside an SKU summary table.
- **Product 360 Drill-Through Page:** Enables right-click drill-through from any SKU on the Executive Overview to a dedicated SKU deep-dive featuring a dynamic DAX header (`Dynamic_SKU_Header`), monthly target pacing, zonal breakdown, top 10 accounts, and an account-level breakdown table.

## Data Model & Technical Implementation
- **Star Schema Architecture:** Built a 20-table star schema centered on `Fact_Launch_Sales` (34 columns) connected to 19 dimension tables (`Dim_Date`, `Dim_Product`, `Dim_Therapy_Area`, `Dim_Dosage_Form`, `Dim_Plant`, `Dim_Territory`, `Dim_Sales_Rep`, `Dim_Doctor`, `Dim_Speciality`, `Dim_Hospital_Account`, `Dim_Customer_Type`, `Dim_Distributor`, `Dim_Channel`, `Dim_Campaign`, `Dim_Trade_Scheme`, `Dim_Launch_Phase`, `Dim_Payment_Terms`, `Dim_Order_Status`, and `Dim_Shipment_Mode`).
- **DAX & Data Modeling:** Created custom KPI measures, configured active star-schema relationships for accurate zonal and therapy-level cross-filtering, standardized `Launch Date` formatting, and built dynamic text measures for drill-through headers.

## Repository Structure
- `MediNova_LaunchPulse.pbix` – Power BI report file containing the star schema model, DAX measures, and interactive visuals
- `data/MediNova_Launch_Data.xlsx` – Source multi-sheet Excel dataset (1 fact table + 19 dimension tables)
- `screenshots/` – Full-screen views of the Executive Overview and Product 360 pages
