# 🎬 Investigating the TMDb Movie Dataset

## Project Overview

An exploratory data analysis of **10,000+ movies** from The Movie Database (TMDb) to uncover the factors that drive a movie's commercial success and popularity. This project investigates relationships between budget, revenue, popularity, genres, and how movie industry trends have evolved over three decades (1984–2014).

---

## Research Questions

1. **Does a higher budget lead to higher popularity?** — Exploring the correlation between production budget and audience popularity scores
2. **What are the most popular genres over the years?** — Identifying which genres dominate and how audience preferences shift over time
3. **Does higher popularity translate to higher profits?** — Testing whether audience buzz actually drives financial returns
4. **What characteristics are associated with the highest-revenue movies?** — Profiling the traits of top-grossing films
5. **How has the movie industry changed over time?** — Analyzing trends in budgets, revenues, and genre diversity from 1984 to 2014

---

## Key Findings

- Higher budgets show a **positive correlation with popularity**, but the relationship is not perfectly linear — some low-budget films achieve exceptional popularity
- **Popularity is a strong predictor of profit** — movies with higher popularity scores tend to generate significantly higher average profits
- The movie industry has experienced **substantial growth** in both budgets and revenues over the 30-year period
- Genre diversity has **expanded over time**, with audiences having access to a wider range of movie categories in recent years
- Despite growing budgets, **returns are not guaranteed** — the gap between budget and revenue varies significantly

---

## Methodology

| Phase | Description |
|---|---|
| **Data Wrangling** | Removed duplicates, dropped irrelevant columns (e.g., `imdb_id`, `homepage`), handled missing values — filled object-type nulls with "missing" and replaced zero budgets with NaN |
| **Exploratory Analysis** | Used scatter plots, bar charts, histograms, and trend lines to investigate each research question |
| **Statistical Analysis** | Examined correlations between key variables (budget, revenue, popularity) and computed summary statistics |

---

## Dataset

- **Source**: [The Movie Database (TMDb)](https://www.themoviedb.org/) via Kaggle
- **File**: `tmdb-movies.csv` — 10,866 movies with 21 attributes
- **Key Attributes**: budget, revenue, popularity, vote average, vote count, genres, cast, director, release year, runtime

---

## Tools & Technologies

- **Python 3** — Core programming language
- **Pandas** — Data manipulation and cleaning
- **NumPy** — Numerical computations
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical visualizations

---

## Project Structure

```
├── Investigate_TMDb_Movie_Dataset.ipynb   # Main analysis notebook
├── Investigate_TMDb_Movie_Dataset.html    # HTML export of the notebook
├── tmdb-movies.csv                        # Raw dataset
└── README.md                              # This file
```

---

## How to Run

1. Ensure you have Python 3 with `pandas`, `numpy`, `matplotlib`, and `seaborn` installed
2. Open `Investigate_TMDb_Movie_Dataset.ipynb` in Jupyter Notebook
3. Run all cells sequentially to reproduce the analysis

---

## Limitations

- Budget and revenue data contain many zero/missing values, which may skew financial analyses
- Popularity scores are relative and may change over time as TMDb updates its algorithm
- The dataset does not account for inflation, making direct budget/revenue comparisons across decades less precise
