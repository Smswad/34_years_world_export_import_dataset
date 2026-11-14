# Group 7 Contributor & Agent Guidelines (Agents.md)

This document establishes the collaboration rules, code standards, and workflow protocols for **Group 7** working in the single shared Jupyter Notebook (`dataset_exploration_initial_analysis.ipynb`).

---

## 1. Group 7 Roster & Responsibility Matrix

| Student ID | Student Name | Role / Assigned Tasks | Status |
| :--- | :--- | :--- | :--- |
| **2023-2-60-036** | Shahil Mahmud Swad | *(To be assigned)* | Pending |
| **2024-1-60-073** | Arefin Bashar Ashik | *(To be assigned)* | Pending |
| **2024-1-60-132** | Alif Iftekhar Hasan Iftie | *(To be assigned)* | Pending |
| **2024-1-60-133** | Mahmuda Mushtari Uddin | *(To be assigned)* | Pending |
| **2024-1-60-138** | Farhan Islam | *(To be assigned)* | Pending |

> **Note:** Task assignments will be designated by the group members before implementation begins.

---

## 2. Single-Notebook Collaboration Rules

Because the entire team works inside `dataset_exploration_initial_analysis.ipynb`, follow these rules strictly to avoid merge conflicts and code breakage:

### Rule 1: Mandatory Code Cell Header
Every single code cell must begin with the standard contributor header block:

```python
# ==============================================================================
# Task [X]: [Task Title]
# Contributor: [Your Name / Student ID]
# Description: [Clear 1-2 line summary of what this code does]
# ==============================================================================
```

### Rule 2: Non-Destructive Data Operations
- Do **not** modify or overwrite the primary DataFrame (`df`) in place unless agreed upon by all members.
- When filtering, aggregating, or cleaning for your specific task, create a separate task-scoped variable:
  ```python
  # Good practice:
  df_task2 = df[['Export (US$ Thousand)', 'Import (US$ Thousand)']].dropna().copy()
  ```

### Rule 3: Output Display Limit
- **Never** set `pd.set_option('display.max_rows', None)`.
- Always keep row outputs constrained (e.g., `pd.set_option('display.max_rows', 10)` or `.head()`) to prevent inflating the `.ipynb` file to hundreds of thousands of lines of raw HTML.

### Rule 4: Visualization Standards
- Use `matplotlib.pyplot` and `seaborn`.
- Every chart must have:
  - Descriptive `plt.title(...)`
  - Explicit `plt.xlabel(...)` and `plt.ylabel(...)`
  - Clean layout via `plt.tight_layout()`

---

## 3. Git Version Control Workflow

1. **Pull Before Work:**
   Always sync your local branch with GitHub before editing the notebook:
   ```bash
   git pull origin main
   ```
2. **Clear Bloated Outputs Before Committing:**
   If your test run produced large plots or outputs, clear them or save the figures to an `assets/` or `figures/` folder.
3. **Descriptive Commit Messages:**
   Use conventional commit prefixes:
   - `feat(task-1): complete dataset description and feature dictionary`
   - `feat(task-2): add central tendency and dispersion summary tables`
   - `fix(notebook): resolve import path and plotting error`
4. **Push Changes:**
   ```bash
   git add dataset_exploration_initial_analysis.ipynb
   git commit -m "feat(task-X): [description]"
   git push origin main
   ```
