
### Project Annapurna:PDS Supply Chain Analytics


### 1. Executive Summary and Key Deliverable

This project applies time-series machine learning and data engineering principles to address a critical public administration issue in Bihar: optimizing the allocation of rice within the Public Distribution System (PDS) to mitigate supply shortages and reduce waste. The primary outcome is a robust predictive model integrated into an **actionable Business Intelligence (BI) dashboard**.

| Key Metric | Result | Analytical Value |
| :--- | :--- | :--- |
| **Model Accuracy ($R^2$)** | **0.8715** (Random Forest) | Explains 87.1% of historical rice sales variation on unseen test data. |
| **Data Engineering** | Creation of a fully validated $1,596$-row master time-series dataset. | Demonstrated proficiency in ETL, data cleaning, and data alignment. |
| **Key Insight** | Strong Seasonality | Verified that major cultural events (e.g., Chhath Puja) are a significant, predictable factor in demand forecasting. |

**Core Deliverable:** An interactive **Power BI Risk Assessment Dashboard** providing a clear, color-coded warning system for predicted supply shortfalls.

**Live Dashboard Link:** [Insert Your Power BI Publish to Web (Public) URL Here]

---

### 2. Problem Statement and Solution Design

#### Problem Context
The existing PDS supply chain operates primarily on historic, static quotas. This reactive approach frequently results in **stockouts** in high-demand zones, depriving vulnerable populations, and unnecessary **surplus** in low-demand zones, increasing government waste.

#### Solution
The methodology transitions the allocation strategy from reactive logistics to **proactive, data-driven resource planning**. The predictive model forecasts the expected monthly district-level demand for the next six months. This forecast is then compared against estimated supply to quantify the **predicted shortage or surplus**, enabling targeted reallocation of resources.

---

### 3. Methodology and Technical Rigor

#### Data Pipeline and Engineering
* **Data Sourcing:** Historical monthly PDS Rice Sales (Demand) and Allotment (Supply) data for all 38 districts of Bihar were meticulously scraped, cleaned, and aligned from official state portals (Oct 2020 – Mar 2024).
* **Master Dataset Creation:** Two disparate data sources were merged into a single, standardized time-series dataset ($1,596$ rows), ready for machine learning consumption.

#### Feature Engineering and Model Selection
Model performance was maximized by engineering features directly driven by insights from **Exploratory Data Analysis (EDA)**:
* **Time-Series Features:** Created high-value **Lagged Sales** features ($1$-month, $3$-month, $12$-month) and a **Rolling Average** to capture sequential momentum.
* **Policy Granularity:** Maintained separate features for **AAY** and **PHH** allotments to distinguish between stable (household-based) and dynamic (per-person based) components of supply.
* **Event Flagging:** Engineered an **`Is_Festival_Month`** binary feature to account for recurring seasonal demand spikes.
* **Model Training:** The full dataset was split, with the last six months (Oct 2023 – Mar 2024) reserved for rigorous out-of-sample testing. The **Random Forest Regressor** proved superior in generalizing patterns across the different districts.

### 4. Project Structure and Tools

| Tool/Technology | Role in Project |
| :--- | :--- |
| **Python / Pandas** | Core ETL, data transformation, and feature engineering. |
| **Scikit-learn** | Model training and formal evaluation (RMSE, $R^2$). |
| **Random Forest / XGBoost** | Advanced ensemble modeling for forecasting. |
| **Power BI Desktop** | Visualization, creation of the interactive risk dashboard, and DAX calculations for risk categorization. |
| **SQLite (Optional Component)** | Demonstration of systematic data storage and retrieval via **SQL**. |
| **Git / GitHub** | Version control and professional portfolio presentation. |

---
