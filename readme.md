# AAL Sales Analysis - Q4 2020

## About This Repository

This is a **course-end assessment project** for the **Applied Data Science with Python**  The project analyzes Q4 2020 sales data for AAL (Australian Apparel Limited) to provide data-driven insights for business expansion decisions.

## Problem Statement

AAL is a well-known Australian clothing brand established in 2000, with branches across various states. The CEO wants to:

1. Identify the states generating the highest revenues.
2. Develop sales programs for states with lower revenues.

The task is to analyze the fourth quarter (Oct-Dec 2020) sales data on a state-by-state basis and provide actionable insights for the upcoming year.

> For the detailed problem statement with all requirements, see [problem_statement.md](problem_statement.md)

## Dataset

**File:** `AusApparalSales4thQrt2020.csv`

| Column | Description |
|--------|-------------|
| Date | Sale date (Oct - Dec 2020) |
| Time | Time of day (Morning, Afternoon, Evening) |
| State | Australian state (VIC, NSW, SA, QLD, TAS, NT, WA) |
| Group | Demographic group (Kids, Men, Women, Seniors) |
| Unit | Number of units sold |
| Sales | Revenue amount |

- **Records:** 7,559 rows
- **Period:** Q4 2020 (October, November, December)
- **Coverage:** 7 Australian states, 4 demographic groups, 3 time slots

## What Was Done

### 1. Data Wrangling
- Cleaned whitespace from column names and values
- Inspected for missing values using `isna()` and `notna()` (none found)
- Applied Min-Max normalization on the Sales column
- Used `GroupBy()` for state-wise and group-wise aggregation

### 2. Data Analysis
- Descriptive statistics (mean, median, mode, standard deviation) on Sales and Unit columns
- Identified highest and lowest performing states and demographic groups
- Generated weekly, monthly, and quarterly sales reports

### 3. Data Visualization
- State-wise sales by demographic group (bar chart)
- Group-wise sales across states (bar chart)
- Time-of-day peak/off-peak analysis (bar chart)
- Box plots for sales distribution
- Distribution plots for Sales and Unit
- Daily, weekly, and monthly trend charts
- Quarterly heatmap (State vs Group)

### 4. Report & Recommendations
- Summary report with key findings
- Actionable recommendations for the S&M team

## Tech Stack

| Tool / Library | Purpose |
|----------------|---------|
| Python 3.x | Programming language |
| Pandas | Data loading, cleaning, and aggregation |
| NumPy | Numerical computations |
| SciPy | Statistical functions |
| Matplotlib | Base plotting library |
| Seaborn | Statistical visualizations |
| Jupyter Notebook | Report generation (code + visuals + markdown) |
| VS Code | IDE with Jupyter extension |

## Project Structure

```
sales_analysis/
├── AusApparalSales4thQrt2020.csv    # Raw dataset
├── sales_analysis.ipynb              # Jupyter Notebook (main deliverable)
├── problem_statement.md              # Detailed problem statement & requirements
├── readme.md                         # This file
└── .gitignore                        # Git ignore rules
```

## How to Run

1. Install Python 3.x and pip
2. Install dependencies:
   ```bash
   pip install pandas numpy scipy matplotlib seaborn jupyter
   ```
3. Open `sales_analysis.ipynb` in VS Code (with Jupyter extension) or JupyterLab
4. Run all cells: `Ctrl+Shift+Enter`

## Export Notebook as PDF

1. Install nbconvert (if not already):
   ```bash
   pip install nbconvert
   ```
2. Export the notebook to HTML:
   ```bash
   python -m nbconvert --to html sales_analysis.ipynb
   ```
3. Open the generated `sales_analysis.html` in a browser
4. Press `Ctrl+P` → change destination to **"Save as PDF"** → Save

## Convert Markdown to Word Document

1. Install python-docx (if not already):
   ```bash
   pip install python-docx
   ```
2. Run this in terminal to convert any `.md` file to `.docx`:
   ```bash
   python -c "
   from docx import Document
   import re

   md_file = 'project_synopsis.md'   # change this to your .md file
   output_file = 'project_synopsis.docx'  # change this to your desired .docx name

   doc = Document()
   with open(md_file, 'r', encoding='utf-8') as f:
       for line in f:
           line = line.rstrip()
           if line.startswith('### '):
               doc.add_heading(line[4:], level=2)
           elif line.startswith('## '):
               doc.add_heading(line[3:], level=1)
           elif line.startswith('# '):
               doc.add_heading(line[2:], level=0)
           elif line.startswith('- '):
               doc.add_paragraph(re.sub(r'\*\*(.*?)\*\*', r'\1', line[2:]), style='List Bullet')
           elif re.match(r'^\d+\. ', line):
               doc.add_paragraph(re.sub(r'\*\*(.*?)\*\*', r'\1', re.sub(r'^\d+\. ', '', line)), style='List Number')
           elif line.strip():
               doc.add_paragraph(re.sub(r'\*\*(.*?)\*\*', r'\1', line))
   doc.save(output_file)
   print(f'{output_file} created successfully!')
   "
   ```
3. Change `md_file` and `output_file` variables to match your filenames
