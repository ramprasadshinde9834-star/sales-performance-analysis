# Sales Performance Analysis Dashboard

A beginner-friendly retail analytics portfolio project using Python (pandas, Matplotlib, Seaborn) and Power BI. The goal is to understand sales trends, product/category performance, regional results, and profitability using transaction-level data.

## Business questions
1. How do sales change over time?
2. Which categories and regions contribute the most sales?
3. Do the highest-sales products also produce the highest profit?
4. Which products or categories show low or negative profit?
5. What practical actions should the business investigate based on the findings?

## Tools
- Python 3
- pandas
- Matplotlib
- Seaborn
- Jupyter Notebook
- Power BI Desktop (dashboard is an optional deliverable)

## Dataset
This project uses a Sample Superstore CSV. Dataset copies can differ in column names and data coverage.

Suggested source: [Sample Superstore dataset on Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final).

Download the CSV yourself and place it in `data/raw/`. The notebook currently expects `data/raw/Superstore.csv`; update `DATA_PATH` in the notebook if your file has a different name. Review the dataset's license and sharing terms before publishing the data or derivative files.

Raw data is intentionally excluded from Git by `.gitignore`.

## Repository structure
```text
sales-performance-analysis/
├── data/
│   ├── raw/                 # Local source data (not committed)
│   └── processed/           # Generated cleaned data and summaries
├── notebooks/
│   └── sales_analysis.ipynb
├── outputs/
│   └── charts/              # Generated charts
├── powerbi/                 # Add .pbix file and dashboard screenshots here
├── README.md
├── requirements.txt
└── .gitignore
```

## Setup
1. Clone or download this repository.
2. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   ```
   Windows:
   ```powershell
   .venv\Scripts\activate
   ```
   macOS/Linux:
   ```bash
   source .venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   python -m pip install -r requirements.txt
   ```
4. Download the CSV and place it in `data/raw/`.
5. Open `notebooks/sales_analysis.ipynb`, update `DATA_PATH` to your exact filename, and run all cells in order.

## Cleaning approach
The notebook:
- standardizes column names and common aliases;
- trims whitespace in text fields;
- parses available date columns;
- converts Sales, Profit, Quantity, and Discount to numeric where present;
- removes exact duplicate rows;
- excludes rows without a valid order date for time-based analysis and rows without a valid Sales value;
- records the number of rows affected by cleaning steps;
- flags negative/zero sales for review rather than automatically removing potentially meaningful transactions.

The raw file is not overwritten. These are initial rules and should be reviewed against the chosen dataset version.

## Metrics
- Total Sales = sum of Sales
- Total Profit = sum of Profit, if available
- Distinct Orders = count of unique Order ID, if available
- Distinct Customers = count of unique Customer ID, if available
- Profit Margin = Total Profit / Total Sales × 100, when available and Total Sales is nonzero

Definitions should be confirmed against the exact source file. Do not compare results across dataset versions without checking date range and row-level differences.

## Visualizations
The notebook generates:
- monthly sales trend;
- sales by category;
- sales by region;
- product profitability tables where fields exist.

Charts are saved to `outputs/charts/`.

## Power BI dashboard plan
Once the cleaned CSV is generated:
1. Open Power BI Desktop.
2. Select **Get data → Text/CSV** and load `data/processed/superstore_cleaned.csv`.
3. Check data types, especially Order Date, Sales, and Profit.
4. Create KPI cards for Total Sales, Total Profit, Distinct Orders, and Profit Margin.
5. Add a line chart for monthly sales, bar charts for sales by category and region, and a product profitability visual.
6. Add slicers for date, region, category, and customer segment if those fields are present.
7. Cross-check the dashboard's totals against the Python outputs.
8. Save the `.pbix` file under `powerbi/` and add a screenshot if appropriate.

## Limitations
- Dataset copies may vary in columns, dates, and row counts.
- Descriptive analysis shows patterns, not causation.
- Negative profit or sales values may be valid and should be investigated rather than silently discarded.
- Recommendations should be based on observed results, not assumptions.

## Results
Add your validated findings here after running the notebook:
- Sales trend:
- Leading category:
- Leading region:
- Product profitability insight:
- Recommended action:
- Caveat/limitation:

## Author
Add your name or portfolio profile here.
