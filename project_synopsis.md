# Project Synopsis - AAL Sales Analysis (Q4 2020)

## Objective

To analyze the Q4 2020 sales data of AAL (Australian Apparel Limited) across different Australian states and demographic groups, and provide data-driven recommendations to assist the CEO in making informed business expansion and investment decisions.

## Dataset

The dataset contains 7,559 sales records from October to December 2020, covering 7 Australian states (VIC, NSW, SA, QLD, TAS, NT, WA), 4 demographic groups (Kids, Men, Women, Seniors), and 3 time slots (Morning, Afternoon, Evening).

## Approach

### Data Wrangling
- Cleaned the dataset by stripping whitespace from column names and string values.
- Inspected for missing values using `isna()` and `notna()` — no missing values were found.
- Applied Min-Max Normalization on the Sales column to scale values between 0 and 1 for fair comparison.
- Used `GroupBy()` to aggregate sales by State, Group, and Time for meaningful analysis.

### Data Analysis
- Performed descriptive statistical analysis (mean, median, mode, standard deviation) on Sales and Unit columns.
- Identified VIC as the highest revenue state and WA as the lowest.
- All four demographic groups (Men, Women, Kids, Seniors) contribute nearly equally to total revenue.
- Generated weekly, monthly, and quarterly sales reports.

### Data Visualization
- Created bar charts for state-wise and group-wise sales comparisons.
- Used box plots for descriptive statistics of sales distribution.
- Used Seaborn distribution plots for Sales and Unit distributions.
- Built daily, weekly, and monthly trend charts to track sales over time.
- Created a heatmap showing the relationship between states and demographic groups.
- Seaborn was chosen as the primary visualization library due to its clean aesthetics and built-in support for statistical plotting.

## Key Findings

1. **VIC** dominates revenue generation, followed by **NSW** and **SA**.
2. **WA, NT, and TAS** are the lowest-performing states and need targeted sales programs.
3. All demographic groups contribute almost equally — the product portfolio is well-balanced.
4. **Morning** is the peak sales period; afternoon and evening are off-peak.
5. Sales remain relatively consistent across the quarter with no major dips.

## Recommendations

1. Prioritize expansion in VIC and NSW as proven high-revenue markets.
2. Launch targeted promotions and marketing campaigns in WA, NT, and TAS to boost revenue.
3. Implement hyper-personalization and Next Best Offer strategies during off-peak hours (afternoon/evening).
4. Continue the balanced product strategy across all demographic groups.
5. Use weekly sales reports for better inventory and staffing planning.

## Tools Used

Python, Pandas, NumPy, SciPy, Matplotlib, Seaborn, Jupyter Notebook, VS Code
