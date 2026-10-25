# 💎 Diamond Valuation & Market Analytics: Exploratory & Explanatory Data Visualization

## Project Overview

In data science, effective data visualization serves two critical functions: **exploration** (discovering non-obvious patterns, distributions, and paradoxes) and **explanation** (communicating complex multi-variable relationships clearly to decision-makers).

This project presents a rigorous, deep-dive visual investigation into the pricing dynamics of **53,940 diamonds** based on their physical dimensions and the classic **Four Cs**: **Carat**, **Cut**, **Color**, and **Clarity**. 

Through a progressive analytical pipeline spanning **Univariate**, **Bivariate**, and **Multivariate** exploration, this project resolves counter-intuitive market phenomena (such as Simpson's Paradox in diamond pricing) and demonstrates production-grade chart polishing and visual storytelling.

---

## Analytical Progression & Core Discoveries

### 1. Univariate Exploration
- **Price Distribution**: Diamond prices are heavily right-skewed, ranging from \$326 to \$18,823 with a long tail. Applying a **logarithmic transformation** ($\log_{10}$) revealed a bimodal distribution with distinct market clusters around \$1,000 and \$4,000–\$5,000.
- **Carat Weights**: Highly spiked at human-psychological round numbers (0.3 ct, 0.5 ct, 0.7 ct, 1.0 ct, 1.5 ct, 2.0 ct), indicating diamond cutters intentionally shape stones to hit marketable threshold sizes.
- **Categorical Quality Ratings**: Cut is predominantly skewed towards high quality (*Ideal* and *Premium* make up ~67% of inventory), while Color and Clarity follow bell-shaped distributions centered on intermediate grades (*G–H* and *SI1–VS2*).

### 2. Bivariate Exploration & The Pricing Paradox
- **Carat vs. Price**: Exhibits a strong non-linear, exponential trend. Because diamond volume scales with weight, a **cube-root transformation of carat** ($x^{1/3}$) paired with a **log transform of price** linearizes the relationship into a clean predictive trendline.
- **The Counter-Intuitive Quality Paradox**:
  - Examining raw bivariate boxplots of Cut, Color, and Clarity against Price suggests that *worse* clarity (e.g., I1, SI1) and *lower* color grades (e.g., J, I) command *higher* average prices than flawless (IF) or colorless (D) stones.
  - This counter-intuitive anomaly occurs because stone size (carat) acts as a powerful confounding variable: larger stones in the market tend to have lower clarity and color grades, yet their massive carat weight commands high absolute prices.

### 3. Multivariate Exploration: Resolving Simpson's Paradox
- By incorporating **color encodings**, **faceting**, and **point jittering**, multivariate scatter plots separate the confounding effect of carat weight.
- When holding carat constant on a transformed scale, the true market hierarchy immediately emerges:
  - For stones of identical carat weight, **flawless clarity (IF, VVS1)** and **top color (D, E)** consistently command exponential premiums over lower-grade alternatives.
  - Cut quality creates fine-grained price stratification, particularly in stones above 1.0 carat.

### 4. Explanatory Polishing & Storytelling
- Refined exploratory drafts into publication-ready visualizations:
  - Custom logarithmic tick labels (displaying real-world dollar amounts `$500`, `$1k`, `$2k`, `$5k`, `$10k` instead of raw log values).
  - High-contrast, colorblind-safe sequential and diverging palettes (Seaborn `viridis` and `rocket`).
  - Clear visual hierarchies, annotations highlighting benchmark weights, and descriptive axis labeling.

---

## Visualization Technique Compendium

Beyond the core diamond analysis notebooks, this repository includes modular technical deep-dives into specific statistical plotting paradigms:

| Practice Module | Focus Area | Key Visualizations |
|---|---|---|
| `Univariate_Exploration_Diamond_Data.ipynb` | Distribution analysis & scale transformation | Histograms, KDEs, Bar charts, log/sqrt scales |
| `Bivariate_Exploration_Diamond_Data.ipynb` | Relationship between variable pairs | Scatter plots with alpha jitter, Violin & Box plots, Heatmaps |
| `Multivariate_Exploration_Diamond_Data.ipynb` | Multi-dimensional interactions & paradox resolution | Encoded scatter matrices, FacetGrid conditioning |
| `Explanatory_Polishing_Diamond_Data.ipynb` | Presentation design & figure publishing | Custom tick formatters, palettes, annotations |
| `Categorical_vs_Categorical_...ipynb` | Discrete multi-variable structures | Clustered & stacked percentage bar charts |
| `Numerical_vs_Categorical_...ipynb` | Group comparison & variance distribution | Violin plots, box-and-whisker plots, swarm plots |
| `Numerical_vs_Numerical_...ipynb` | Correlation & continuous density | 2D Hexbins, contour plots, jittered scatter plots |
| `Scales_and_Transformations_...ipynb` | Non-linear feature normalization | Power transforms, reciprocal & log scaling |

---

## Datasets Included

1. `diamonds.csv`: 53,940 diamond records containing price and the 4 Cs (carat, cut, color, clarity, dimensions $x, y, z$, depth, table).
2. `fuel_econ.csv`: Multi-attribute vehicle efficiency dataset utilized for bivariate technique validation.
3. `pokemon.csv`: Multi-class attribute dataset utilized for categorical clustered bar and distribution testing.

---

## Tech Stack & Tools

- **Language**: Python 3
- **Data Manipulation**: Pandas, NumPy
- **Statistical Visualization**: Matplotlib, Seaborn
- **Transformations**: SciPy (log, cube-root, box-cox transforms)

---

## How to Explore

1. Clone this repository.
2. Open `Explanatory_Polishing_Diamond_Data.ipynb` to see the polished explanatory presentation plots that tie the entire diamond valuation story together.
3. Explore `Univariate`, `Bivariate`, and `Multivariate` notebooks sequentially to follow the end-to-end data discovery journey.
