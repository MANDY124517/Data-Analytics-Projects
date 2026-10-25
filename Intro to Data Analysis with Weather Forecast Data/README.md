# 🌡️ Exploring Weather Trends — Global vs. Local Temperature Analysis

## Project Overview

This project analyzes **long-term temperature trends** by comparing global average temperatures against local temperatures in **Albuquerque, New Mexico**. The goal is to uncover whether local climate patterns mirror global warming trends, identify deviations, and present findings through clear, data-driven visualizations.

---

## Objectives

- Extract global and city-level temperature data using **SQL queries**
- Calculate **moving averages** to smooth out short-term fluctuations and reveal long-term trends
- Visualize the comparison between **global** and **Albuquerque** temperature trends over time
- Draw conclusions about how local climate change aligns with global patterns

---

## Key Findings

- Albuquerque consistently records **higher average temperatures** than the global average, which is expected given its desert climate
- Both global and local temperature trends show a clear **upward trajectory** over the observed period, consistent with global warming data
- The **moving average** smoothing technique effectively highlights the long-term warming trend while filtering out year-to-year noise

---

## Methodology

1. **Data Extraction** — Used SQL to query global and Albuquerque temperature data from the database and exported results as CSV files
2. **Moving Average Calculation** — Applied a rolling window to compute moving averages, reducing volatility in annual temperature readings
3. **Visualization** — Created line plots comparing both temperature series with proper titles, axis labels, and legends

---

## Dataset

| File | Description |
|---|---|
| `Global_data - weather_forecast.pdf` | Global average temperature data over time |
| `Albuquerque_data.pdf` | Local temperature data for Albuquerque, NM |
| `Weather_Trends_Analysis_Report.pdf` | Final analysis report with visualizations and conclusions |

---

## Tools & Technologies

- **SQL** — Data extraction from relational database
- **Spreadsheet Software** — Data analysis, moving average calculations, and chart creation

---

## How to Explore This Project

Open the `Weather_Trends_Analysis_Report.pdf` to see the complete analysis, including:
- The line chart comparing global vs. local temperature trends
- Moving average calculations
- Written observations and conclusions

The raw data exports (`Global_data - weather_forecast.pdf` and `Albuquerque_data.pdf`) are also included for reference.
