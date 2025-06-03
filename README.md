# ASB_London_Analysis

> Antisocial Behaviour Analysis in London (01 Aug 2023 – 31 Aug 2024)  
> Using Python (pandas, SciPy, Matplotlib, Seaborn) and Tableau dashboards.  

---

## Table of Contents

1. [Project Overview]
2. [Data]
3. [Notebooks] 
4. [Statistical Tests]


---

## Project Overview

This project analyzes Antisocial Behaviour (ASB) incidents reported in London between 01/08/2023 and 31/08/2024. Key goals:

- Identify hourly and daily patterns of ASB incidents (peak hours: 14:00–23:00).  
- Compare weekday vs. weekend incident rates (Welch’s t-test: weekends are significantly higher).  
- Determine boroughs with highest vs. lowest ASB counts and test association between borough & incident type (Chi-Square test: significant association).  
- Compare monthly ASB counts (One-Way ANOVA: at least one month differs), with Tukey’s HSD post-hoc.

Python notebooks (`notebooks/`) walk through data cleaning, EDA, statistical tests, and plotting. Final dashboards in Tableau (`tableau/`) illustrate interactive summaries.

---

## Data

- **Raw Data:** `data/raw/MPS_Antisocial_Behaviour.csv` (27 columns, 254,226 rows).  
- **Processed Data:** any cleaned/filtered CSVs are in `data/processed/`.

---

## Notebooks

1. `01_data_preprocessing.ipynb` — load CSV, remove duplicates, convert `Date` to datetime index, drop nulls.  
2. `02_hourly_borough_analysis.ipynb` — hour-of-day bar chart, borough bar chart, top ASB types.  
3. `03_statistical_tests.ipynb` — Welch’s t-test (weekday vs. weekend), Chi-Square (borough vs. type), One-Way ANOVA & Tukey’s HSD (monthly differences).  
4. `04_feature_engineering.ipynb` — adding “weekend/weekday” and “month code” features, pivot tables, heatmap

---
## Monthly ASB incidents distribution
 <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/ASB_Month.png" alt="Monthly ASB incidents distribution" width="700" />
</p>

## Hourly ASB incidents

 <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/ASB_Hour.png" alt="Monthly ASB incidents distribution" width="700" />
 </p>

## ASB incidents by borough

 <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/ASB_Borough.png" alt="Monthly ASB incidents distribution" width="700" />
 </p>

 ## Frequent ASB incidents

  <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/Frequent_ASB_incidents.png" alt="Monthly ASB incidents distribution" width="700" />
 </p>

 ## Box Plot for Weekend and Weekdays incidents

   <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/Box_plot.png" alt="Monthly ASB incidents distribution" width="700" />
 </p>

 ## Descriptive Statistics between Weekend incidents and Weekdays incidents

    <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/Descriptive_statistics.png" alt="Monthly ASB incidents distribution" width="400" />
 </p>

 ## Heat-Map on ASB incidents across weeks
    <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/Heat_Map.png" alt="Monthly ASB incidents distribution" width="700" />
 </p>

 ## Pivot Table for ASB incidents across week and days
    <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/Pivot_Table.png" alt="Monthly ASB incidents distribution" width="700" />
 </p>

 ## Incidents per day

     <p align="center">
  <img src="https://raw.githubusercontent.com/imblessingdavid07/Analysis-of-London-ASB-incidents/main/Incidents_per_day.png" alt="Monthly ASB incidents distribution" width="700" />
 </p>

## Statistical Tests

- **Welch’s t-Test (RQ1):** Weekend mean ≈ 729.52 vs. Weekday mean ≈ 678.13. t ≈ 4.07, p ≈ 3.5×10⁻⁵ → reject H₀.  
- **Chi-Square (RQ2):** χ² ≈ 12,652.73, p ≈ 0 → reject H₀ (incident type distribution depends on borough).  
- **One-Way ANOVA (RQ3):** F ≈ 39.10, p ≈ 0 → reject H₀ (at least one month differs). Tukey’s HSD post-hoc identifies which pairs differ.

---


