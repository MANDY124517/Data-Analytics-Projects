# 💊 Clinical Trial Data Wrangling & Quality Assurance (Phase II Study)

## Project Overview

In healthcare analytics and clinical research, raw patient data frequently contains subtle errors, structural messiness, and recording inconsistencies that jeopardize statistical validity. 

This project performs end-to-end **Data Wrangling, Assessment, and Programmatic Cleaning** on a Phase II clinical trial dataset assessing the efficacy and safety of **Auralin** (an experimental oral insulin) compared to **Novodra** (an established injectable insulin) across 350 patients.

Using a rigorous **Define – Code – Test** workflow, this project addresses real-world data quality dimensions (completeness, validity, accuracy, consistency) and tidiness principles to transform messy operational tables into an audit-ready relational model.

---

## The Dataset Architecture

The raw study spans three interrelated datasets:

| Table | Records | Description | Primary Key / Relations |
|---|---|---|---|
| `patients.csv` | 503 | Demographic and contact records | `patient_id` |
| `treatments.csv` | 280 (pre-merge) | 24-week trial measurements: baseline HbA1c, final HbA1c, dosages | Maps to `patients` via name / ID |
| `adverse_reactions.csv` | 34 | Documented adverse events (e.g., hypoglycemia, injection site discomfort) | Maps to `patients` via name / ID |

---

## Identified Data Issues & Cleaning Strategy

Data auditing was conducted through visual assessment and programmatic querying (`info()`, `describe()`, regex pattern matching, cross-table integrity checks):

### 1. Data Quality Issues (Content Issues)
- **Missing Data (Completeness)**: Missing 70 patient records in `treatments` due to truncation — recovered by appending cutoff partition. Missing demographic contact data cataloged.
- **Erroneous Calculations (Accuracy)**: HbA1c change column contained calculation bugs where leading `4`s were transcribed as `9`s — recalculated programmatically via `hba1c_start - hba1c_end`.
- **Unit Discrepancies (Accuracy)**: Erroneous weight entry recorded in kilograms instead of pounds for patient Zaitseva — detected via outlier analysis and converted (`kg * 2.20462`).
- **Anomalous Measurement Errors (Validity)**: Patient height recorded as 27 inches instead of 72 inches — corrected via outlier detection.
- **Inconsistent Formats (Consistency)**:
  - Phone numbers varied wildly in punctuation, parentheses, dashes, and international prefixes — cleaned via regex extraction and normalized into unified 10/11-digit standards.
  - State names inconsistently represented as full names vs. 2-letter postal codes — mapped to standard US postal abbreviations.
  - Zip codes stored as floating-point numbers with trailing `.0` and dropped leading zeros — converted to zero-padded 5-digit strings.
- **Duplicate & Nickname Entries (Validity)**: Duplicate patient profiles with nicknames (e.g., Jake vs. Jacob) isolated and deduplicated. Default placeholder data ("John Doe") scrubbed.
- **Type Mismatches**: Converted assigned sex, states, and treatment categories to memory-efficient `category` datatypes; converted birthdates to `datetime`.

### 2. Data Tidiness Issues (Structural Issues)
- **Multiple Variables per Column**: `contact` column in `patients` contained both email and phone number — extracted into distinct, dedicated attributes using regular expressions.
- **Variables Stored in Column Headers**: Starting dose and ending dose for Auralin and Novodra were stored across separate drug-named columns — melted into tidy key-value pairs (`treatment`, `dose_start`, `dose_end`).
- **Data Redundancy**: Patient names duplicated across `treatments` and `adverse_reactions` — joined onto `patient_id` to maintain a normalized third normal form (3NF) relational design.
- **Fragmented Adverse Events**: `adverse_reactions` table merged directly into the `treatments` dataset to allow unified side-effect vs. dosage analysis.

---

## The Cleaning Framework: Define – Code – Test

For every identified flaw, the project rigorously adheres to a 3-step discipline:
1. **Define**: Formulate an exact verbal specification of the cleaning task and expected output.
2. **Code**: Execute atomic pandas transformations, string manipulations, and vector operations.
3. **Test**: Programmatically verify the fix (assertions, null checks, unique constraints, and distribution checks).

---

## Tech Stack & Libraries

- **Language**: Python 3
- **Data Wrangling**: Pandas, NumPy
- **Pattern Matching**: `re` (Regular Expressions)
- **Environment**: Jupyter Notebook

---

## Repository Structure

```
├── Data_Wrangle_Phase_II_Clinical_Trial_Dataset.ipynb  # Comprehensive wrangling notebook
├── patients.csv                                        # Raw patient demographic data
├── treatments.csv                                      # Raw clinical trial treatment data
├── adverse_reactions.csv                               # Raw recorded adverse events
└── README.md                                           # Project documentation & audit log
```

---

## Key Takeaways for Analytics & Research

- **Pipeline Repeatability**: Writing modular cleaning functions ensures that future trial cohorts can be ingested and cleansed programmatically.
- **Clinical Integrity**: Accurate dosage calculations and standardized HbA1c readings guarantee that downstream hypothesis testing and regulatory filings reflect true therapeutic effects.
