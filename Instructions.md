# CSE303: Initial Analysis of Dataset — Project Instructions

## 1. Project Overview & Deadlines
- **Course:** CSE303 (Statistics & Data Analysis)
- **Instructor:** Shartaz Sajid Nahid
- **Team Number:** Group 7
- **Project Title:** World Export & Import Dataset (1989 - 2023) — Initial Exploration & Analysis
- **Dataset Source:** [Kaggle: World Export and Import Dataset](https://www.kaggle.com/datasets/muhammadtalhaawan/world-export-and-import-dataset)
- **Presentation Date:** 15 November (Max 10 minutes per group, all members must present)
- **Deliverables:**
  1. Complete Jupyter Notebook (`dataset_exploration_initial_analysis.ipynb`)
  2. Dataset file in JSON Lines format (`34_years_world_export_import_dataset.json`)
  3. Formal Report (PDF including Cover Page, Index/Table of Contents, Analysis Tables, and Key Insights)

---

## 2. Team Information (Group 7)

| Student ID | Student Name | Assigned Tasks |
| :--- | :--- | :--- |
| **2023-2-60-036** | Shahil Mahmud Swad | *(To be assigned)* |
| **2024-1-60-073** | Arefin Bashar Ashik | *(To be assigned)* |
| **2024-1-60-132** | Alif Iftekhar Hasan Iftie | *(To be assigned)* |
| **2024-1-60-133** | Mahmuda Mushtari Uddin | *(To be assigned)* |
| **2024-1-60-138** | Farhan Islam | *(To be assigned)* |

---

## 3. Environment Setup & Required Libraries
Before executing the notebook or writing code, every contributor (and any Agentic AI assistant used) must ensure all required packages are installed in the active Python environment or Jupyter kernel.

### Quick Install Command:
```bash
pip install -r requirements.txt
```
or directly:
```bash
pip install pandas numpy matplotlib seaborn scipy
```

> **Note for Agentic AI / AI Assistants:**  
> When an agent initializes or executes code for this project, it must verify the environment and install any missing packages using the command above before executing notebook cells.

---

## 4. Dataset Characteristics
- **Observations (Rows):** 8,096 records
- **Features (Columns):** 33 variables
- **Time Horizon:** 1988 – 2021 (Global trade coverage across 200+ partner countries and regional blocs)
- **Primary Metrics:**
  - Trade Values: *Export (US$ Thousand)*, *Import (US$ Thousand)*
  - Shares & Advantage: *Export Product Share (%)*, *Import Product Share (%)*, *Revealed comparative advantage*
  - Growth: *World Growth (%)*, *Country Growth (%)*
  - Tariffs: Effectively Applied Tariffs (AHS) and Most Favored Nation (MFN) rates, totals, duty-free/dutiable shares

---

## 5. Step-by-Step Task Breakdown

### Task 1: Dataset Description
- **Real-World Context:** Global bilateral trade flows, tariff structures, and economic growth patterns.
- **Dimensionality:** Total observations (8,096) and total variables (33).
- **Feature Dictionary Table:** Construct a Markdown/LaTeX table with columns:
  - Feature Name
  - Data Type (`float64`, `int64`, `object`)
  - Description / Meaning
  - Statistical Classification (Numerical Continuous, Numerical Discrete, Categorical Nominal, Categorical Ordinal, Binary)

### Task 2: Central Tendency and Dispersion Analysis
- For all major continuous numerical features (Export, Import, AHS/MFN weighted averages, Growth rates):
  - Compute: **Mean**, **Median**, **Mode**, **Variance**, **Standard Deviation**, and **Interquartile Range (IQR)**.
  - Present values in a structured summary table.
  - **Discussion:** Compare Mean vs. Median to explain distribution skewness and extreme outliers in global trade values.

### Task 3: Distribution and Shape Analysis
- **Visualizations:**
  - Histograms with KDE (Kernel Density Estimation) overlays for continuous trade and tariff features.
  - Boxplots to visually inspect dispersion, median position, and heavy tails.
- **Distribution Interpretation:**
  - Evaluate skewness (right-skewed vs. symmetric) and kurtosis (heavy-tailed distributions).
- **Outlier Detection:**
  - Apply the IQR Rule:
    $$\text{Lower Bound} = Q1 - 1.5 \times \text{IQR}$$
    $$\text{Upper Bound} = Q3 + 1.5 \times \text{IQR}$$
  - Quantify the number and percentage of outliers for key metrics.

### Task 4: Categorical Variable Analysis
- Analyze categorical attributes (such as *Partner Name* and grouped *Year* eras).
- Create **Frequency Tables** of top trade partners and regions.
- Produce **Bar Charts** and/or **Pie Charts** showing category distribution.
- Comment on **imbalance in the data** (e.g., representation of high-volume trading nations vs. smaller economies).

### Task 5: Relationships Between Variables
- Bivariate scatterplots:
  - *Export (US$ Thousand)* vs. *Import (US$ Thousand)* (Trade Balance relationship).
  - *AHS Weighted Average (%)* vs. *Country Growth (%)* (Tariff protection impact on trade growth).
- Correlation Heatmap across continuous trade, growth, and tariff metrics to identify strong positive/negative associations.

### Task 6: Data Quality Assessment
- **Missing Values Audit:**
  - Quantify `NaN` counts and percentages per column.
  - Explain domain reasons for missing data (e.g., 1988 has no baseline year for growth rates; regional aggregates lack single-nation RCA).
- **Duplicate Records:** Check for and document any duplicated rows.
- **Unusual / Anomaly Values:** Check for negative values, zero-tariff records, or scale discrepancies, and document recommended handling strategies (e.g., imputation vs. filtering).

### Task 7: Key Insights & Future Predictive Modeling
- Synthesize major economic and statistical patterns observed from Tasks 1–6.
- Highlight features that show strong predictive power.
- Propose potential machine learning / predictive modeling directions (e.g., regression for predicting export volume, clustering countries by tariff dependency).

---

## 6. Report & Presentation Deliverable Checklist
- [ ] **Cover Page:** Course title, Group 7, Project Title, and all 5 member names & IDs.
- [ ] **Index / Table of Contents:** Clear section navigation matching Tasks 1–7.
- [ ] **Data Tables:** Numerical findings rendered in tables as requested by instructor.
- [ ] **10-Minute Presentation Preparation:** Equal speaking time distributed among all 5 members.
