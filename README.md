# North America Greenhouse Gas EDA and Power BI Visualization

## Overview

This project analyzes greenhouse gas emissions and economic indicators in North America from 2000 to 2023. Using Power BI, I performed data cleaning, exploratory data analysis (EDA), and created interactive visualizations to uncover trends, sectoral contributions, and relationships with GDP and energy use.

---
## Analysis Questions

1. How have total and per capita CO₂ emissions changed over time from 2000 to 2023?
2. How do greenhouse gas emissions correlate with economic indicators such as GDP and primary energy consumption?
3. Which sectors (coal, oil, gas, cement, land use change) contribute most to CO₂ emissions in different countries?
4. How does primary energy consumption per capita relate to GHG emissions per capita, and which countries have high energy use but low emissions intensity?
5. What is the contribution of methane and nitrous oxide to total GHG emissions across countries?

---
## Data Sourcing and Justification

- **Source:** [Our World in Data: CO₂ and Greenhouse Gas Emissions](https://ourworldindata.org/co2-and-greenhouse-gas-emissions)
- **Coverage:** Annual, country-level data from 1750 to 2023, including emissions by gas, sector, GDP, population, energy use.
- **Why this dataset:** Comprehensive, reliable, integrates multiple authoritative sources. Enables cross-country and sectoral analysis.
- **Access:** Download instructions in `/data/README_Data.md`.

**Key columns include:**  
`country`, `year`, `population`, `gdp`, `co2`, `co2_per_capita`, `primary_energy_consumption`, `methane`, `nitrous_oxide`, etc.

---
## Data Cleaning

- **Null values:** Filled missing GDP with country median (Power BI Group By & Merge); replaced missing sector emissions/energy with 0.
- **Outlier handling:** Retained outliers as they reflect real differences (e.g., US vs. small countries).
- **Skewed data:** Used log transformations for highly skewed columns (Power BI custom columns).
- **Column consistency:** Created new columns for calculations.
  
---
## How to View the Dashboard

- Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
- Open the file in `/powerbi/north-america-ghg.pbix`.

---
## Tools Used

- Power BI (for data cleaning, EDA, visualization)
- GitHub (for version control and sharing)
- Excel/CSV (for initial data handling)

---
## Limitations & Next Steps

- Only major greenhouse gases included.
- Future work: Add more countries, predictive modeling.

---
## References

- [Our World in Data: CO₂ and Greenhouse Gas Emissions](https://ourworldindata.org/co2-and-greenhouse-gas-emissions)
- International Energy Agency (IEA): [North America Emissions](https://www.iea.org/regions/north-america/emissions)
- IPCC Reports

---


