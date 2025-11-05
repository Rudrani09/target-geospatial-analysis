# 🏪 Target Geospatial Retail Analytics

## 📊 Project Overview
This project analyzes **Target store locations** across the United States in relation to **county-level population** and **median household income** data.  
Using U.S. Census Bureau demographics and geospatial insights, the analysis identifies **high-potential counties for new store expansion** and regions of **market oversaturation**.

---

## 🎯 Business Problem
Target’s retail expansion team aims to make **data-driven location decisions** by answering:

- 🗺️ Where should Target expand its store network across the U.S.?  
- 💰 Which counties have favorable demographics (high population, strong income) but **no Target stores**?  
- 📈 How can demographic trends guide **strategic retail growth** and **resource allocation**?

---

## 🧠 Data Sources

**1. Target Store Locations Dataset**  
- Contains store address, city, county, state, and coordinates (latitude, longitude).  
- Used to map Target’s current presence and compute county-level store counts.  

**2. U.S. Census Bureau (ACS 5-Year Estimates, 2023)**  
- [S1903] Median Household Income in the Past 12 Months (2023 Inflation-Adjusted Dollars)  
- [DP05] Demographic and Housing Estimates (Population Totals)  
_Source: [data.census.gov](https://data.census.gov)_

---

## 🧩 Data Processing Steps

### 🧹 1. Data Cleaning
- Standardized county and state names.
- Converted population and income columns to numeric format.
- Removed nulls and corrected county–state mismatches.

### 🌎 2. Geospatial Merge
- Merged store location data with U.S. Census demographics using a **County–State Key**.
- Achieved **98.3% match rate** between Target stores and U.S. county records.

### 🚦 3. Opportunity Screening
Identified high-potential counties with:
- `Store_Count == 0`
- `Population_2023 ≥ 150,000`
- `Median_HH_Income_2023 ≥ $60,000`

### 📤 4. Exported Outputs
| File | Description |
|------|--------------|
| `stores_clean.csv` | Clean Target store data with geocoordinates |
| `county_level_summary.csv` | County-level population, income, and store count |
| `target_expansion_opportunities.csv` | High-potential counties (no stores, strong demographics) |
| `target_opportunity_summary_by_state.csv` | Summary of opportunities aggregated by state |

---

## 📈 Key Insights
- ✅ **98%** of Target stores successfully mapped to counties.  
- 💡 Several **high-income, high-population counties** in **Georgia, Connecticut, and Alabama** currently lack Target stores.  
- 🧭 These regions represent **prime opportunities** for Target’s next retail expansion phase.  
- ⚙️ Nationwide coverage: ~1,844 stores across ~626 counties, out of 3,200+ total counties.

---

## 📍 Visualization (Power BI)
The **interactive Power BI dashboard** visualizes:
- 🏬 Store distribution by county and state  
- 💵 Median income vs. population density  
- 🔥 “White space” heatmap of counties with demand but no Target presence  
- 🧮 State-level KPIs (store coverage %, average income, opportunity count)

---

## 🧰 Tech Stack
| Tool | Purpose |
|------|----------|
| **Python (pandas, geopandas, matplotlib)** | Data cleaning, analysis, and aggregation |
| **Jupyter / VS Code** | Notebook development |
| **Power BI** | Visualization and storytelling |
| **Git & GitHub** | Version control and collaboration |

---

## 📂 Repository Structure
├── Analysis_retail_1.ipynb # Jupyter Notebook (core analysis)
├── Target datasets.csv # Raw Target store dataset
├── county_population_2023.csv # U.S. Census population data
├── median_income_by_county_2023.csv # U.S. Census income data
├── county_level_summary.csv # Clean, aggregated county-level data
├── target_expansion_opportunities.csv # Identified opportunity counties
├── target_opportunity_summary_by_state.csv # State-level opportunity summary
├── stores_clean.csv # Cleaned Target store list
├── README.md # Project overview and documentation
└── .gitignore # Ignored files and logs
