# 🚲 Urban Micro-Mobility & Ride Dynamics: Ford GoBike System Analytics

## Project Overview

Micro-mobility systems in dense urban centers generate millions of operational telemetry records. Optimizing fleet rebalancing, pricing models, and station infrastructure requires understanding the dual nature of bike-share demand: daily commuter utility versus recreational leisure usage.

This project delivers a full-cycle **Exploratory and Explanatory Data Analysis** on **1.8+ million ride records** across 2018 from the **Ford GoBike (now Bay Wheels)** bike-sharing network in the Greater San Francisco Bay Area (San Francisco, East Bay, and San Jose).

The project concludes with an interactive, presentation-ready slide deck communicating actionable insights for business stakeholders and municipal transport planners.

---

## Research Questions & Executive Insights

### 1. Trip Duration Dynamics
- **Question**: What is the distribution of trip duration across the network, and what constitutes a standard trip?
- **Finding**: Raw trip duration exhibits extreme positive skewness (with outliers extending beyond several hours). Applying a logarithmic transformation reveals a unimodal, log-normal distribution with a steep mode at **10 minutes (600 seconds)**, showing that the vast majority of rides serve short-distance point-to-point transit.

### 2. Seasonality & Weather Sensitivity
- **Question**: How do weather variations, months, and seasons impact ride duration and overall demand?
- **Finding**: Weather exhibits a measurable but relatively bounded effect on ride duration. Spring and summer months exhibit peak riding durations, whereas fall and winter show reduced frequency. Seasonal variance is primarily reflected in total trip volume rather than significant changes in duration for individual rides.

### 3. User Segmentation: Subscribers vs. Casual Customers
- **Question**: How do usage patterns, peak hours, and trip durations diverge between annual Subscribers (members) and casual Customers (single-ride / day-pass users)?
- **Finding**:
  - **Subscribers**: Dominate total ride volume (>80% of trips). Their usage is sharply concentrated around daily commute rush hours (**08:00–09:00** and **17:00–18:00**, Monday through Friday), with shorter, highly focused trip durations (~8–12 minutes).
  - **Casual Customers**: Exhibit much longer, highly dispersed trip durations (often exceeding 25–45 minutes), with activity peaking on weekends and sunny afternoons. Their usage correlates strongly with leisure, tourism, and recreational routes along the waterfront.

### 4. Strategic Business & Revenue Implications
- Because bike-share pricing typically charges fees beyond an initial 30-minute threshold, casual customers generate significantly higher per-ride overage revenue.
- **Recommendations**:
  1. *Conversion Campaigns*: Target frequent casual customers during peak weekend months with introductory annual memberships to smooth recurring revenue.
  2. *Fleet Rebalancing*: Prioritize morning reverse-commute rebalancing from financial and downtown employment districts back to residential transit hubs.

---

## Data Pipeline & Wrangling

The raw dataset comprises 12 monthly compressed archives:

1. **Automated Batch Ingestion**: Programmatically loaded and concatenated twelve compressed CSV archives (`201801-fordgobike-tripdata.csv.zip` through `201812-fordgobike-tripdata.csv.zip`) into a unified Pandas DataFrame exceeding 1.86 million records.
2. **Feature Engineering**:
   - Extracted start hour, day of the week, month, and season from raw ISO timestamp strings.
   - Calculated member ages from `member_birth_year` and filtered unrealistic outliers (>100 years).
   - Converted `user_type` and `member_gender` into memory-efficient `category` datatypes.
3. **Outlier Filtering**: Applied 99th percentile capping on trip durations to remove anomalous dock errors and forgotten rental returns.

---

## Technical Visualizations & Deliverables

- **`Data-Exploration-with-Bike-Data.ipynb`**: Complete exploratory workflow with univariate histograms, bivariate boxplots/scatter matrices, and multivariate facet grids.
- **`Data-Exploration-with-Bike-Data.html`**: Standalone HTML export of the exploratory process.
- **`Data-Finding-Slide-Deck-with-Bike-Data.ipynb`**: Polished explanatory notebook configured with slide type metadata.
- **`Data-Finding-Slide-Deck-with-Bike-Data.slides.html`**: Interactive, browser-based Reveal.js presentation designed for non-technical stakeholders.

---

## Tech Stack & Libraries

- **Language**: Python 3
- **Data Manipulation**: Pandas, NumPy
- **Data Visualization**: Matplotlib, Seaborn
- **Presentation Framework**: Jupyter Slides / Reveal.js via `nbconvert`

---

## Repository Structure

```
├── Data-Exploration-with-Bike-Data.ipynb               # Full exploratory analysis notebook
├── Data-Exploration-with-Bike-Data.html                # HTML export of exploratory notebook
├── Data-Finding-Slide-Deck-with-Bike-Data.ipynb        # Explanatory presentation notebook
├── Data-Finding-Slide-Deck-with-Bike-Data.slides.html # Interactive presentation slide deck
├── Ford_Go_Bike_Dataset/                              # 12 monthly compressed ride archives (2018)
│   ├── 201801-fordgobike-tripdata.csv.zip
│   └── ... (201802 through 201812)
└── README.md                                          # Project documentation
```

---

## How to Run & View

1. **Interactive Slide Presentation**:
   - Double-click or open `Data-Finding-Slide-Deck-with-Bike-Data.slides.html` in any web browser to view the interactive presentation slide deck directly without running code.
2. **Jupyter Notebook Execution**:
   - Install dependencies: `pip install pandas numpy matplotlib seaborn`.
   - Launch Jupyter and run `Data-Exploration-with-Bike-Data.ipynb` to step through the data transformations and visualizations.
