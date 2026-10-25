# 📊 A/B Test Results Analysis

## Project Overview

A comprehensive statistical analysis to help an **e-commerce company** decide whether to implement a **new version of their web page** or keep the old one. This project applies probability theory, hypothesis testing, and logistic regression to draw data-driven conclusions from real A/B test data.

---

## Objectives

- Determine whether a new landing page design leads to **higher conversion rates** than the existing page
- Apply multiple statistical approaches to ensure robust, reliable conclusions
- Provide actionable recommendations backed by statistical evidence

---

## Approach

The analysis follows a three-part statistical framework:

### Part I — Probability
- Computed baseline conversion rates for both control and treatment groups
- Assessed data quality: handled duplicates and mismatched group assignments
- Calculated conditional probabilities to understand initial patterns

### Part II — Hypothesis Testing (A/B Test)
- Defined null and alternative hypotheses for the conversion rate comparison
- Simulated the sampling distribution under the null hypothesis using **bootstrapping** (10,000 iterations)
- Computed the **p-value** to determine statistical significance
- Used a **z-test** as a secondary validation method

### Part III — Logistic Regression
- Built a logistic regression model to predict conversion based on page type
- Incorporated additional factors (country of origin) to check for interaction effects
- Assessed whether geographic location impacts the relationship between page type and conversion

---

## Key Findings

- The new page did **not** show a statistically significant improvement in conversion rates over the old page
- The p-value was **above the significance threshold** (α = 0.05), meaning we fail to reject the null hypothesis
- Logistic regression confirmed the same conclusion — page type is **not a significant predictor** of conversion
- Country of origin also did **not** significantly interact with page type to affect conversions
- **Recommendation**: The company should **keep the old page** — there is insufficient evidence that the new page improves performance

---

## Dataset

| File | Description |
|---|---|
| `ab_data.csv` | A/B test data with ~295K user sessions (user ID, timestamp, group, landing page, conversion) |
| `countries.csv` | User country data for geographic analysis |

---

## Tools & Technologies

- **Python 3** — Core language
- **Pandas & NumPy** — Data manipulation and numerical computing
- **Matplotlib** — Visualization
- **Statsmodels** — Logistic regression and statistical testing

---

## Project Structure

```
├── Analyze_ab_test_results_notebook.ipynb   # Full analysis notebook
├── Analyze_ab_test_results_notebook.html    # HTML export for easy viewing
├── ab_data.csv                              # A/B test results data
├── countries.csv                            # Country data for users
├── A_B Testing_Notes_Practice.pdf           # Statistical reference notes
└── README.md                                # This file
```

---

## How to Run

1. Ensure Python 3 with `pandas`, `numpy`, `matplotlib`, and `statsmodels` is installed
2. Open `Analyze_ab_test_results_notebook.ipynb` in Jupyter Notebook
3. Run all cells sequentially to reproduce the complete analysis

---

## Statistical Methods Used

| Method | Purpose |
|---|---|
| Bootstrapping | Simulating sampling distribution under H₀ |
| Z-test | Parametric test for proportion comparison |
| Logistic Regression | Modeling conversion as a function of page type and country |
| P-value Analysis | Determining statistical significance |
