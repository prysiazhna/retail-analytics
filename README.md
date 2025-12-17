## Retail Sales Analytics & Forecasting Dashboard
https://github.com/user-attachments/assets/2eab8515-9392-4b36-8ffc-bfe16b64b95a

## Project Context
This project analyzes weekly retail sales to understand seasonality, store-level performance drivers and short-term demand forecasting for planning and operations.

## Business Goals

- Understand seasonal demand patterns across stores
- Evaluate external factors (holidays, temperature)
- Identify concentration and store-level performance differences
  
## Tools & Stack
- Python (Pandas) — data cleaning, transformation, EDA, forecasting
- Jupyter Notebook — analytical workflow and reproducibility
- Power BI — data modeling, DAX, dashboard storytelling

  
## Project Structure

```
project/
  data/
    raw/
      sales_data.csv
      features_data.csv
      stores_data.csv
    clean/
      cleaned_data.csv
      forecast_results.csv
  notebooks/
    01_cleaning.ipynb
    02_exploration.ipynb
    03_forecast.ipynb
  Retail_Analytics_Dashboard.pbix
  README.md
```

## 📚 Data Preparation & Python Workflow

Below is a structured overview of each dataset and how it was used in the analytical workflow

- **sales_data.csv** — raw weekly sales by store and department
- **features_data.csv** — raw temperature values and holiday indicators
- **stores_data.csv** — basic store metadata
- **cleaned_data.csv** — fully prepared and merged dataset after preprocessing
- **forecast_results.csv** — 12-week forecast output generated in Python

These datasets were consolidated into a consistent weekly analytical structure for further analysis and visualization.

---

### **Jupyter Notebooks**

All data processing and analysis were performed in Python using three Jupyter notebooks

#### **01_cleaning.ipynb — Data Cleaning & Integration**
This notebook establishes the analytical foundation for all further steps.
Key operations:
- date parsing and normalization
- merging raw datasets
- handling missing values
- type standardization
- validating one-record-per-store-per-week structure
- exporting `cleaned_data.csv`

---

#### **02_exploration.ipynb — Exploratory Data Analysis**
EDA helped identify which visuals and KPIs should be included in the Power BI dashboard.
In this notebook, I explored:
- monthly and weekly seasonality
- store-level performance distribution
- department-level behavior
- holiday and temperature trends

---

#### **03_forecast.ipynb — Time-Series Forecasting**
The forecast output integrates directly into the Forecast
This notebook:
- prepared a clean, continuous weekly time-series
- generated a 12-week forecast
- calculated prediction intervals
- exported all results to `forecast_results.csv`


## 🧩 Power BI Data Model

Power BI uses three main tables:

<img width="1225" height="280" alt="Screenshot 2025-12-09 160641" src="https://github.com/user-attachments/assets/e9966fb2-d0c3-4205-b14c-5b663d093443" />

- **cleaned_data** — historical sales
- **forecast_results** — forecasted weekly values
- **DateTable** — a custom calendar table created to align and filter both datasets

The DateTable provides a continuous timeline for joining historical and forecast data, enabling correct sorting, filtering, and time intelligence which is a standard practice for time-series reporting.


# 📊 Dashboard Highlights

## 🟣 1. Sales Overview 

**Custom "Total Sales by Month" Visual**
<img width="946" height="377" alt="Screenshot 2025-12-09 192900" src="https://github.com/user-attachments/assets/7243c3b5-fc58-44fa-a6d4-3790c3962a1a" />

A combined visual that integrates:
- monthly sales (bar chart)
- month-over-month % change
- a yearly average reference line
This composite design allows users to see volume, direction of change, and seasonal volatility in one place, offering a richer view than a standard monthly chart.

**Highlights:**
- Store-level performance comparison
- Year-over-year monthly behavior
- Department-level contribution
- Seasonality patterns

**Insights:**
- Sales follow a stable annual seasonal pattern with recurring mid-year and fall peaks, likely driven by predictable consumer demand cycles and planned promotional periods typical for large retail chains
- A small group of stores generates a disproportionate share of total sales, suggesting differences in store size, location, or catchment area rather than random performance variation
- Department-level contribution remains structurally consistent over time, indicating a mature product mix with limited category-level volatility
- Year-over-year trends closely mirror each other, confirming demand stability and the absence of structural shocks in the observed period

---

## 🟣 2. Holiday Impact Analysis

**Highlights:**
- Clear three-layer structure: weekly overview, holiday comparison, and department-level sensitivity
- “Holiday Peak Ratio” highlights departments with the strongest seasonal uplift
- Layout helps identify where holidays actually matter for operations and planning

**Insights:**
- Overall sales uplift during holiday weeks is modest, implying that baseline demand remains dominant and holidays act as incremental rather than transformative drivers
- Certain departments experience significantly stronger holiday-related spikes, likely reflecting category-specific purchasing behavior tied to gifting or seasonal consumption
- Holiday effects are spread across the calendar instead of being concentrated, suggesting multiple smaller demand triggers rather than a single dominant peak season

---

## 🟣 3. Temperature Impact

**Highlights:**
The Temperature Impact section validates whether weather affects weekly sales using a structured layout that includes:
- a correlation metric
- a monthly temperature and sales trend comparison
- and a full scatterplot for pattern detection

**Insights:**
- Temperature shows no meaningful correlation with weekly sales, indicating that weather variation does not materially influence customer purchasing behavior at the aggregated level
- Sales trends remain stable across temperature ranges, likely because product assortment and store formats are not weather-sensitive
- The absence of visible patterns in the scatterplot confirms that temperature is not a reliable explanatory variable for sales fluctuations in this dataset
  
---

## 🟣 4. 12-Week Sales Forecast

**Highlights:**

The Forecast page integrates Python generated predictions into Power BI.
It provides a clear view of historical values compared to the 12 week forecast.

The visual layout combines:

- actual vs predicted weekly sales
- a forecast curve with lower and upper confidence bands
- uncertainty progression over time
- high-level forecast KPIs

This structure gives a realistic view of expected demand and communicates not only the forecasted values but also the level of confidence behind them, which is an important part of time series forecasting. Because the forecasted dataset operates at a slightly different granularity than the historical data, minor alignment differences may appear, but they do not affect the overall trend or interpretation.

**Insights:**
- The forecast closely follows historical seasonality, suggesting that past demand patterns provide a reliable basis for short-term projections
- Expected sales remain stable over the forecast horizon, indicating no signals of upcoming demand disruption
- Forecast uncertainty increases gradually over time, which is consistent with standard time-series behavior and supports the reliability of near-term estimates

## 💡Potential Business Actions

1. Align inventory and staffing plans with recurring seasonal peaks to reduce stockouts and overcapacity during low-demand periods.
2. Prioritize performance analysis and best-practice replication from top-performing stores, as they drive a disproportionate share of total revenue.
3. Apply targeted holiday promotions only to departments with proven holiday sensitivity, rather than using broad store-wide discounting.
4. Base short-term planning and replenishment decisions on the 12-week forecast, while accounting for increasing uncertainty further into the horizon.

## ⭐ Summary

This project applies a structured analytics pipeline to evaluate weekly retail performance, seasonal demand patterns and short-term sales expectations.
It combines Python-based data preparation and forecasting with Power BI modeling to translate raw operational data into business-ready insights.

The analysis shows stable seasonal behavior, limited impact from external factors such as weather, strong revenue concentration across a small set of stores and a forecast that closely follows historical patterns, supporting reliable short-term planning.
