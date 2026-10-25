# 🚗 EPA Automotive Fuel Economy & Emissions: A 10-Year Comparative Study (2008 vs. 2018)

## Project Overview

Over the past decade, automotive standards and environmental regulations have driven major engineering shifts in fuel efficiency, hybrid technologies, and alternative fuels. 

This project conducts an in-depth comparative analysis using data from the **U.S. Environmental Protection Agency (EPA)** to evaluate how vehicle fuel economy, powertrain design, and emissions profiles evolved between **2008 and 2018**.

By wrangling and harmonizing disparate multi-year schemas, handling complex dual-fuel entries, and linking continuous model lines, this project answers fundamental questions regarding automotive fleet modernization.

---

## Research Questions & Core Findings

### 1. Alternative Fuel Adoption
- **Question**: Are more unique vehicle models utilizing alternative fuel sources (Electricity, Ethanol, CNG) in 2018 compared to 2008, and by how much?
- **Finding**: Alternative fuel models grew substantially over the decade, increasing their fleet share by **6.75%**. Furthermore, the fuel composition transformed—shifting from CNG and early ethanol blends in 2008 to modern plug-in electric and flex-fuel architectures by 2018.

### 2. Efficiency Gains by Vehicle Class
- **Question**: How much did fuel economy improve across different vehicle categories (Compact, Midsize, Large, SUV, Station Wagon, Pickup)?
- **Finding**: Every single vehicle class that was tracked across both years demonstrated a measurable increase in average combined MPG. Smaller cars and station wagons showed the steepest efficiency gains, driven by turbocharged 4-cylinder engines replacing naturally aspirated V6s.

### 3. Characteristics of EPA SmartWay Vehicles
- **Question**: What characterizes EPA SmartWay-certified vehicles, and how did benchmarks shift?
- **Finding**: SmartWay vehicles consistently maintain lower engine displacement (smaller liters), fewer cylinders, and significantly higher greenhouse gas scores. By 2018, certification criteria tightened, introducing the *SmartWay Elite* tier for top-tier low-emission performers.

### 4. Determinants of Superior Fuel Economy
- **Question**: What powertrain features exhibit the strongest relationship with high combined MPG?
- **Finding**: Engine displacement (`displ`) and cylinder count (`cyl`) demonstrate strong inverse relationships with fuel efficiency. Vehicles in the top 50th percentile for MPG universally feature lower displacements (typically < 2.5L) and modernized multi-speed transmissions.

### 5. Longitudinal Model Tracking: Most Improved Vehicle
- **Question**: Among models manufactured continuously in both 2008 and 2018, which specific vehicle achieved the greatest MPG improvement?
- **Finding**: By tracking identical model lines that persisted across the 10-year span, the **Volvo XC90** achieved the highest efficiency gain, surging in combined MPG through powertrain hybridization and downsized engine design.

---

## Data Wrangling & Engineering Challenges

Harmonizing EPA records from 2008 and 2018 required resolving complex inconsistencies:

1. **Schema Standardization**: Filtered extraneous features and aligned column definitions between 2008 and 2018 standards (e.g., handling `Cert Region` vs. `Sales Area`).
2. **Dual-Fuel Slash Handling**: Vehicles capable of running on two fuels (e.g., Gasoline/Electricity or Gasoline/Ethanol) had values formatted with slashes (e.g., `24/32`). A custom splitting algorithm segregated each composite record into distinct, single-fuel rows for accurate vector math.
3. **Data Type Casting**: Converted string fields (`cyl`, `air_pollution_score`, `city_mpg`, `hwy_mpg`, `cmb_mpg`) to proper numeric datatypes while managing special character exceptions.
4. **Longitudinal Record Merging**: Performed inner joins on continuous model names between 2008 and 2018 datasets with custom column suffixes (`_2008`, `_2018`) to compute paired delta metrics (`mpg_change`).

---

## Tech Stack & Libraries

- **Language**: Python 3
- **Data Manipulation**: Pandas, NumPy
- **Data Visualization**: Matplotlib
- **Dataset Source**: U.S. EPA Office of Mobile Sources & National Vehicle and Fuel Emissions Laboratory

---

## Repository Structure

```
├── Data_Analysis_with_Fuel_Economy_Data.ipynb  # End-to-end analysis notebook
├── Description of economy fuel data.txt        # Attribute definitions & codes
├── Green Vehicle Guide Documentation.pdf       # EPA technical reference documentation
├── Fuel_Economy_Data/                          # Processed and raw stage datasets
│   ├── all_alpha_08.csv                        # Raw 2008 EPA dataset
│   ├── all_alpha_18.csv                        # Raw 2018 EPA dataset
│   ├── clean_08.csv / clean_18.csv             # Cleaned intermediate tables
│   └── combined_dataset.csv                    # Final merged longitudinal dataset
└── readme.md                                   # Project documentation
```

---

## How to Run

1. Clone this repository.
2. Ensure Python environment has `pandas`, `numpy`, and `matplotlib` installed.
3. Launch Jupyter Notebook and run `Data_Analysis_with_Fuel_Economy_Data.ipynb` to inspect all data cleaning steps, statistical aggregations, and visual plots.
