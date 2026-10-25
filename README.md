# 📊 Data Analytics & Applied Data Science Portfolio

Welcome to my **Data Analytics Portfolio**. This repository houses 8 end-to-end data analytics and statistical modeling projects spanning diverse industries—including **e-commerce A/B testing**, **clinical trial quality assurance**, **social media viral dynamics**, **automotive emissions & fuel economy**, **micro-mobility fleet analytics**, **market valuation & Simpson's Paradox**, **entertainment industry economics**, and **longitudinal climate trends**.

Each project is self-contained with documented workflows, exploratory analyses, reproducible code, and publication-ready visualizations or interactive presentation decks.

---

## 🚀 Projects Overview

| # | Project | Domain | Core Analytical Techniques | Primary Tech Stack |
|---|---|---|---|---|
| **01** | [**A/B Test Results Analysis**](./AB%20Testing%20Result%20Analyze/) | E-Commerce / Product | Hypothesis testing, Bootstrapping (10k iterations), P-values, Logistic Regression | Python, Pandas, Statsmodels |
| **02** | [**Clinical Trial Data Wrangling**](./Data%20Wrangle%20and%20Analyze%20with%20Phase2%20Clinic%20Trial%20Data/) | Healthcare / Pharma | Define-Code-Test framework, 3NF Relational design, Data quality & tidiness audits | Python, Pandas, Regex |
| **03** | [**Viral Social Media Analytics**](./Data%20Wrangle%20and%20Analyze%20with%20Twitter%20WeRateDogs%20Data%20Set/) | Social Media / NLP | Multi-source ingestion (API JSON, Requests, CSV), Deep Neural Net predictions, Virality metrics | Python, Requests, Tweepy, Seaborn |
| **04** | [**EPA Automotive Fuel Economy (10-Yr Study)**](./Data%20Analytics%20with%20Fuel%20Economy%20Data/) | Automotive / Energy | 10-year longitudinal tracking, Dual-fuel string parsing, Cross-fleet efficiency metrics | Python, Pandas, Matplotlib |
| **05** | [**Urban Micro-Mobility & Bike Sharing**](./Communicate%20Data%20Findings%20with%20Ford%20Bike%20Sharing%20Data/) | Smart Cities / Logistics | 1.8M ride telemetry analysis, User segmentation (Subscribers vs. Casual), Interactive slides | Python, Pandas, Reveal.js, Slides |
| **06** | [**Diamond Valuation & Simpson's Paradox**](./Data%20Visulization%20with%20Diamond%20Data%20Set/) | Retail / Pricing Strategy | Resolving Simpson's Paradox, Cube-root/log power transformations, Multivariate FacetGrids | Python, Seaborn, Matplotlib, SciPy |
| **07** | [**TMDb Film Industry Economics**](./Data%20Analytics%20with%20Movie%20Data/) | Entertainment / Media | 10,000+ film records, 30-year longitudinal trends, Budget-to-profit elasticity | Python, Pandas, Seaborn |
| **08** | [**Global vs. Local Weather Trends**](./Intro%20to%20Data%20Analysis%20with%20Weather%20Forecast%20Data/) | Climate / Public Policy | SQL database querying, Moving averages, Long-term trendline smoothing | SQL, Time-Series Analysis |

---

## 📂 Project Deep Dives

### 1. [A/B Test Results Analysis](./AB%20Testing%20Result%20Analyze/)
- **Business Question**: Should an e-commerce platform roll out a new landing page design, keep the legacy page, or extend the test duration?
- **Methods**: Probability modeling, non-parametric bootstrapping simulation under $H_0$, two-tailed z-tests, and logistic regression with demographic/geographic covariates.
- **Key Finding**: The new layout failed to produce a statistically significant conversion lift ($p > 0.05$). The recommendation was to avoid unnecessary deployment costs and retain the current page.

### 2. [Clinical Trial Data Wrangling & Quality Assurance](./Data%20Wrangle%20and%20Analyze%20with%20Phase2%20Clinic%20Trial%20Data/)
- **Business Question**: How can fragmented and flawed Phase II diabetes trial tables (Auralin oral insulin vs. Novodra injectable insulin) be audited and cleansed into an audit-compliant schema?
- **Methods**: Programmatic auditing across completeness, validity, accuracy, and consistency dimensions; regex string normalization; melting wide-format dose tables into tidy relational data.
- **Key Finding**: Reconstructed 70 missing records, re-calculated faulty transcription errors in HbA1c metrics, and unified adverse-event monitoring for biostatistical readiness.

### 3. [WeRateDogs: Multi-Source Data Wrangling & Viral Analytics](./Data%20Wrangle%20and%20Analyze%20with%20Twitter%20WeRateDogs%20Data%20Set/)
- **Business Question**: What factors govern engagement and viral reach on social media?
- **Methods**: Triple-stream pipeline merging flat archives, programmatic HTTP downloads of neural network image classifications, and JSON API streaming; resolved 9 quality and 4 tidiness defects.
- **Key Finding**: Mature dog stages (`doggo`, `puppo`) generate peak retweets; posting during off-work hours (late night and late afternoon) drives the highest engagement multipliers.

### 4. [EPA Automotive Fuel Economy: A 10-Year Longitudinal Study](./Data%20Analytics%20with%20Fuel%20Economy%20Data/)
- **Business Question**: How did automotive fleet efficiency, powertrain displacement, and alternative fuel adoption shift across the decade from 2008 to 2018?
- **Methods**: Cross-year schema harmonization, complex slash-separated dual-fuel record parsing, and longitudinal vehicle tracking.
- **Key Finding**: Alternative fuel adoption grew by 6.75% across unique models; every tracked vehicle class gained in average combined MPG, with the Volvo XC90 showing the largest efficiency gain.

### 5. [Urban Micro-Mobility & Ride Dynamics (Ford GoBike)](./Communicate%20Data%20Findings%20with%20Ford%20Bike%20Sharing%20Data/)
- **Business Question**: How do commute routines compare to leisure rides across 1.8M ride transactions in the San Francisco Bay Area, and how can pricing be optimized?
- **Methods**: Concatenation and processing of 12 compressed monthly ride datasets; feature engineering on timestamps and stations; creation of an interactive Reveal.js presentation.
- **Key Finding**: Annual subscribers take short, routine commute trips (~10 min) during rush hours; casual riders use bikes for extended weekend leisure (>30 min), driving significant overage fee revenue.

### 6. [Diamond Valuation & Market Analytics: Resolving Simpson's Paradox](./Data%20Visulization%20with%20Diamond%20Data%20Set/)
- **Business Question**: Why do raw diamond sales show lower-clarity stones selling for higher prices than flawless ones, and how do the Four Cs truly interact?
- **Methods**: Logarithmic and cube-root mathematical transformations, bivariate conditioning, faceting, and publication-ready visual design.
- **Key Finding**: Uncovered and resolved **Simpson's Paradox**—carat weight is a massive confounding factor. Once carat is controlled for, clarity and color display their expected exponential price premiums.

### 7. [Investigating TMDb Movie Dataset Economics](./Data%20Analytics%20with%20Movie%20Data/)
- **Business Question**: What attributes predict movie popularity and financial return, and how has the film landscape evolved over three decades (1984–2014)?
- **Methods**: Missing value imputation, string parsing of pipe-separated multi-genre and cast variables, and financial return correlation analysis.
- **Key Finding**: Popularity strongly correlates with profitability; the industry has experienced sustained growth in both budgets and genre diversification over time.

### 8. [Exploring Weather Trends: Global vs. Local Temperature Analysis](./Intro%20to%20Data%20Analysis%20with%20Weather%20Forecast%20Data/)
- **Business Question**: Does local climate change in Albuquerque, New Mexico mirror global temperature trends over multi-century timelines?
- **Methods**: SQL relational database extraction, rolling window moving average smoothing, and comparative time-series visualization.
- **Key Finding**: Moving averages filter out high-frequency annual noise to reveal a shared upward warming trajectory, with Albuquerque maintaining a consistent positive temperature delta above global baselines.

---

## 🛠️ Technical Skills & Tooling

```
Programming & Querying : Python (3.x), SQL (PostgreSQL / MySQL)
Data Manipulation      : Pandas, NumPy
Data Visualization     : Matplotlib, Seaborn, Reveal.js
Statistical Modeling   : Statsmodels, SciPy (Hypothesis Testing, Logistic Regression, Bootstrapping)
Data Engineering       : Requests, JSON Parsing, Regular Expressions (re), File I/O
Environments & Tools   : Jupyter Notebook, Git, GitHub
```

---

## 💻 How to Clone & Run

```bash
# Clone this repository
git clone https://github.com/<your-username>/Data-Analytics-Projects.git

# Navigate into the project directory
cd Data-Analytics-Projects

# Set up a virtual environment (optional but recommended)
python -m venv venv
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install foundational data science packages
pip install pandas numpy matplotlib seaborn scipy statsmodels requests
```

Open any project subfolder and launch Jupyter Notebook to inspect the code and interactive analyses:
```bash
jupyter notebook
```
