# World Export & Import Dataset (1989 – 2023): Initial Exploration & Analysis

[![Course](https://img.shields.io/badge/Course-CSE303%3A%20Statistics%20%26%20Data%20Analysis-blue.svg)](#)
[![Team](https://img.shields.io/badge/Team-TariffTrackers%20(Group%207)-orange.svg)](#)
[![Python](https://img.shields.io/badge/Python-3.12%20%7C%203.14-green.svg)](#)
[![Dataset](https://img.shields.io/badge/Dataset-JSON%20Lines%20(8%2C096%20rows)-brightgreen.svg)](#)

---

## 1. Project & Team Information

- **Course:** CSE303 — Statistics & Data Analysis
- **Course Instructor:** Shartaz Sajid Nahid
- **Team Name:** **TariffTrackers**
- **Group Number:** Group 7
- **Dataset Source:** [Kaggle: World Export and Import Dataset (1989 - 2023)](https://www.kaggle.com/datasets/muhammadtalhaawan/world-export-and-import-dataset)

### Group 7 Roster (TariffTrackers)

| Student ID | Student Name | Role / Assigned Tasks | Status |
| :--- | :--- | :--- | :--- |
| **2023-2-60-036** | **Shahil Mahmud Swad** | Group Leader, Introduction, Dataset Description & Task 1 | Active |
| **2024-1-60-138** | **Farhan Islam** | Task 2 (Central Tendency & Dispersion) & Task 3 (Distribution, Shape & Visualizations) | Active |
| **2024-1-60-132** | **Alif Iftekhar Hasan Iftie** | Task 4 (Categorical Variable Analysis & Visualizations) | Active |
| **2024-1-60-073** | **Arefin Bashar Ashik** | Task 5 (Relationships Between Variables & Visualizations) | Active |
| **2024-1-60-133** | **Mahmuda Mushtari Uddin** | Task 6 (Data Quality Assessment), Task 7 (Key Insights & Modeling) & Conclusion | Active |

---

## 2. Project Overview & Real-World Problem

This project presents an end-to-end exploratory data analysis (EDA) of global bilateral trade flows and customs tariff protections spanning 34 years (**1988 through 2021**). Sourced from United Nations Comtrade and World Bank WITS databases, the dataset captures macroeconomic commerce, applied vs. Most Favored Nation (MFN) tariff policies, and trade growth dynamics across **265 sovereign countries and regional economic blocs**.

### Key Dataset Dimensions:
- **Total Observations:** `8,096` records
- **Total Variables:** `33` features
- **Data Storage Format:** JSON Lines (`.json` with 1 record per line for streaming efficiency)

---

## 3. Analytical Roadmap (The 7 Core Tasks)

The analysis is fully implemented in [`dataset_exploration_initial_analysis.ipynb`](./dataset_exploration_initial_analysis.ipynb) adhering to all guidelines specified in the course project instructions:

```
├── Task 1: Dataset Description & Feature Dictionary
├── Task 2: Central Tendency & Dispersion Analysis (Mean vs. Median Skewness)
├── Task 3: Distribution & Shape Analysis (Log Histograms, Boxplots & IQR Outliers)
├── Task 4: Categorical Variable Analysis (Top Partners & Global Trade Trajectory)
├── Task 5: Relationships Between Variables (Export vs Import Scatterplots & Correlation Analysis)
├── Task 6: Data Quality Assessment (Missing Value Audits & Anomaly Verification)
└── Task 7: Key Insights & Future Predictive Modeling Formulations
```

### Analytical Summary of Tasks:

1. **Task 1: Dataset Description & Feature Dictionary**
   - Detailed breakdown of all 33 features categorized by statistical data type: Numerical Continuous (e.g. Export, Import, Growth rates, Tariff shares), Numerical Discrete (Year, Tariff lines), and Categorical Nominal (Partner Name).
   - Rendered in a structured Markdown table within the notebook.

2. **Task 2: Central Tendency & Dispersion**
   - Calculates **Mean, Median, Mode, Variance, Standard Deviation, and IQR** for all continuous trade and tariff metrics.
   - Highlights the profound **Mean vs. Median divergence**: Mean Export ($142B) is ~100× larger than Median Export ($1.56B), demonstrating extreme economic concentration where global trade turnover is dominated by a few superpower economies.

3. **Task 3: Distribution & Shape Analysis**
   - **Histograms with KDE Overlays:** Generated for trade values and tariff indicators. Logarithmic transformation ($\log_{10}$) is applied to reveal the underlying log-normal power-law distribution of global trade.
   - **Boxplots:** Visualize dispersion, quartiles, and long heavy positive tails.
   - **Outlier Detection:** Computed via the $1.5 \times \text{IQR}$ rule, finding ~13.8% of trade volume entries in the extreme upper bracket.

4. **Task 4: Categorical Variable Analysis**
   - Evaluates country/regional representation across 265 unique trade partners.
   - Bar chart visualization of top exporting economies (USA, China, Germany, Japan, and major economic unions).
   - Time series trajectory showing global trade expansion from 1988 to 2021 and highlighting the severe trade volume imbalance between major powers and small developing nations.

5. **Task 5: Relationships Between Variables**
   - **Export vs. Import Correlation ($r = 0.994$):** Demonstrates near-perfect linear scaling; high-exporting nations simultaneously act as the world's primary import absorbers.
   - **Applied (AHS) vs. MFN Tariffs ($r = 0.530$):** Shows that national preferential tariff reductions are structurally calibrated against baseline MFN commitments.
   - **Bivariate Scatterplots & Correlation Matrix:** Evaluates trade reciprocity and the negative relationship between protective tariffs and gross commercial exchange ($r = -0.073$).

6. **Task 6: Data Quality Assessment**
   - **Duplicate Records:** `0` duplicate rows (100% unique records).
   - **Missing Data Rationales:** Explains why `World Growth (%)` and `Country Growth (%)` are missing in 3,686 rows (1988 base year lacks a 1987 prior-year comparison, plus unrecorded bilateral statistics in specific states).
   - Constant feature identification (`Export Product Share (%)` and `Import Product Share (%)` are constant at 100% for aggregate trade).

7. **Task 7: Key Macroeconomic Insights & Future Predictive Modeling**
   - Synthesizes findings on long-term trade globalization, tariff liberalization trends, and economic inequality.
   - Evaluates candidate features for future regression (e.g., forecasting next-period export volume using tariff burden and trade momentum) and clustering (unsupervised K-Means to segment countries into distinct trade blocs).

---

## 4. Repository Structure

```plaintext
├── dataset_exploration_initial_analysis.ipynb   # Main collaborative Jupyter Notebook (Tasks 1-7)
├── 34_years_world_export_import_dataset.json    # Full dataset in unformatted JSON Lines format
├── requirements.txt                             # Python dependencies for the project
├── Instructions.md                              # Detailed task roadmap & faculty specifications
├── Agents.md                                    # Contributor workflow rules, headers & git guidelines
├── README.md                                    # Project overview & documentation
└── .gitignore                                   # Ignore rules for raw CSV files and PDFs
```

---

## 5. Getting Started (Setup & Execution)

### Step 1: Clone the Repository
```bash
git clone https://github.com/Smswad/34_years_world_export_import_dataset.git
cd 34_years_world_export_import_dataset
```

### Step 2: Install Dependencies
Ensure you are using Python 3.10+ (recommended Python 3.12 or 3.14):
```bash
pip install -r requirements.txt
```
*Or install directly:*
```bash
pip install pandas numpy matplotlib seaborn scipy
```

### Step 3: Run the Analysis
Launch Jupyter Notebook or open the project in VS Code:
```bash
jupyter notebook dataset_exploration_initial_analysis.ipynb
```
Run all cells from top to bottom. The setup cell automatically loads the JSON Lines dataset and restricts row display to 10 rows (`display.max_rows = 10`) to keep execution fast and lightweight.

---

## 6. Submission & Presentation Deliverables

- [x] **Jupyter Notebook:** Completely structured with contributor cell headers and code for Tasks 1 to 7.
- [x] **Dataset:** Formatted as JSON Lines (`34_years_world_export_import_dataset.json`).
- [ ] **Formal Report (PDF):**
  - Cover page featuring team name **TariffTrackers (Group 7)** and all 5 student names & IDs.
  - Index / Table of Contents page.
  - Formatted numerical summary tables matching Tasks 1–7.
  - Written analysis interpreting the real-world meaning of all findings.
- [ ] **10-Minute Group Presentation (15 Nov):** Equal speaking time (~2 minutes per member) across the 7 analytical sections.
