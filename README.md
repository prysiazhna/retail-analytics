## Retail Sales Analytics & Forecasting Dashboard

This project was built using **Python**, **Pandas**, **Jupyter** and **Anaconda** for data preparation and analysis, and **Microsoft Power BI** for data modeling and dashboard visualization.

This project delivers a complete end to end analysis of weekly retail sales across multiple stores. 
It brings together Python based data preparation, exploratory analytics and a fully interactive Power BI dashboard to uncover seasonal patterns, evaluate external drivers such as holidays and temperature and project short term future performance.

The workflow covers the entire analytical lifecycle. It includes:
- cleaning and structuring raw datasets
- building a unified weekly time series foundation
- investigating trends and store level behavior
- generating a 12 week sales forecast

The final dashboard transforms the analytical pipeline into a clear narrative that helps identify performance drivers, compare store dynamics and anticipate upcoming demand.


https://github.com/user-attachments/assets/2eab8515-9392-4b36-8ffc-bfe16b64b95a

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

#### Highlights:
**Custom "Total Sales by Month" Visual**
<img width="946" height="377" alt="Screenshot 2025-12-09 192900" src="https://github.com/user-attachments/assets/7243c3b5-fc58-44fa-a6d4-3790c3962a1a" />

A combined visual that integrates:
- monthly sales (bar chart)
- month-over-month % change
- a yearly average reference line
This composite design allows users to see volume, direction of change, and seasonal volatility in one place, offering a richer view than a standard monthly chart.

**Other Highlights:**
- Store-level performance comparison
- Year-over-year monthly behavior
- Department-level contribution
- Seasonality patterns

**Insights:**
- Sales follow a consistent annual rhythm with clear mid-year and fall peaks
- A small group of stores drives a large share of total sales
- Department-level structure is stable, showing predictable product category behavior
- YOY trends confirm repeating seasonal cycles and business stability

---

## 🟣 2. Holiday Impact Analysis

**Highlights:**
- Clear three-layer structure: weekly overview, holiday comparison, and department-level sensitivity
- “Holiday Peak Ratio” highlights departments with the strongest seasonal uplift
- Layout helps identify where holidays actually matter for operations and planning

**Insights:**
- Overall uplift from holidays is modest
- Some departments show significantly stronger activity during holiday weeks
- Holiday patterns are distributed across the year rather than concentrated

---

## 🟣 3. Temperature Impact

**Highlights:**
The Temperature Impact section validates whether weather affects weekly sales using a structured layout that includes:
- a correlation metric
- a monthly temperature and sales trend comparison
- and a full scatterplot for pattern detection

**Insights:**
- Temperature has no meaningful influence on weekly sales
- Visual patterns remain stable regardless of weather variation
- Scatterplot confirms the absence of linear or nonlinear correlation

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
- Forecast aligns well with historical patterns
- Expected demand remains stable with recognizable seasonal structure
- Uncertainty increases gradually, as expected in mid-range forecasting

## ⭐ Summary

This project presents a complete analytical workflow that transforms raw retail data into structured and meaningful insights.  
Python was used to clean, organize and analyze the dataset, creating a stable weekly foundation for further exploration.  
Power BI then translated these results into a dashboard that reveals seasonal patterns, external influences and short term sales expectations.

The analysis uncovered several consistent trends. Sales follow a predictable seasonal rhythm with distinct monthly peaks. Holidays provide only a modest uplift and temperature shows no measurable effect on weekly revenue. Store performance varies significantly, with a small group of stores contributing a large share of total sales. The forecast aligns with historical behavior and offers a realistic outlook supported by confidence intervals.

In the end the project turns complex retail information into an understandable story that helps interpret current performance and anticipate what comes next.
