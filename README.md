# 🏪 Target Geospatial Retail Analytics

## 📊 Project Overview
This project analyzes **Target store locations across the United States** in relation to county-level **population** and **median household income** data.  
Using U.S. Census demographic data and geospatial insights, the analysis identifies **high-potential counties for new store expansion** and **regions of market oversaturation**.

---

## 🎯 Business Problem
Target’s retail expansion team needs data-driven insights to answer:
- Where should Target **expand** its store network in the U.S.?
- Which counties have **favorable demographics** (high population, strong income) but **no existing Target stores**?
- How can demographic trends support **strategic decision-making** for retail growth?

---

## 🧠 Data Sources
1. **Target Store Locations Dataset**  
   - Contains store addresses, city, county, state, and coordinates (latitude, longitude).
   - Used for spatial mapping and county-level aggregation.

2. **U.S. Census Bureau (ACS 5-Year Estimates)**  
   - [S1903] Median Income in the Past 12 Months (2023 Inflation-Adjusted Dollars)  
   - [DP05] Demographic and Housing Estimates (Population Totals)
   - Source: [data.census.gov](https://data.census.gov)

---

## 🧩 Data Processing Steps
1. **Data Cleaning**
   - Removed nulls, standardized case/format, and corrected county–state mismatches.
   - Converted population and income values to numeric format.

2. **Geospatial Merge**
   - Merged store locations with demographic datasets using a **county–state key**.
   - Achieved a 98.3% match rate between Target stores and U.S. county records.

3. **Opportunity Screening**
   - Identified counties with:
     - `Store_Count == 0`
     - `Population_Total ≥ 150,000`
     - `Median_Income ≥ $60,000`

4. **Exported Outputs**
   - `target_store_level.csv` → Clean store-level dataset  
   - `county_level_summary.csv` → County-level aggregated view  
   - `target_expansion_opportunities.csv` → Top opportunity counties for expansion  

---

## 📈 Key Insights
- 98% of Target stores successfully mapped to U.S. counties.
- Several **high-income, high-population** counties in **Georgia**, **Connecticut**, and **Alabama** lack Target stores.
- These represent the **top expansion opportunities** for Target’s next phase of retail growth.

---

## 📍 Visualization (Tableau)
An interactive **Tableau dashboard** is used to visualize:
- Store distribution by county and state  
- Median income vs. population density  
- Opportunity heatmap showing “white spaces” (counties with demand but no Target presence)

*(Dashboard link to be added after Tableau publish)*

---

## 🧰 Tech Stack
- **Python (pandas, geopandas, matplotlib)** – Data cleaning and analysis  
- **Jupyter / VS Code** – Notebook execution environment  
- **Tableau** – Visualization and storytelling  
- **Git & GitHub** – Version control and collaboration

---

## 📂 Repository Structure
├── Analysis_retail_1.ipynb # Jupyter Notebook (main analysis)
├── Target datasets.csv # Raw Target store data
├── county_population_2023.csv # U.S. Census population data
├── median_income_by_county_2023.csv # U.S. Census income data
├── target_store_level.csv # Cleaned store-level dataset
├── county_level_summary.csv # County-level summary
├── target_expansion_opportunities.csv # Identified high-potential counties
├── README.md # Project overview and documentation
└── .gitignore # Ignored files and logs
