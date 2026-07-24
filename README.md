# Online Retail Data Analysis (Python + SQL)

## Project Overview
This project explores the Online Retail Dataset from Kaggle, demonstrating an end-to-end data analysis pipeline. It utilizes Python for robust data cleaning, exploratory data analysis (EDA), and feature engineering, followed by exporting the structured data to SQLite for advanced, business-oriented SQL querying.

## Objectives
- Clean and preprocess messy, real-world transactional retail data.
- Strategically handle null values, duplicates, cancellations, and data anomalies.
- Perform exploratory data analysis (EDA) to uncover initial business trends.
- Engineer new, business-relevant features (e.g., revenue segmentation).
- Export cleaned data to SQLite to practice advanced SQL querying for actionable business insights.

## Tools & Technologies
- **Python**: Pandas, NumPy, Matplotlib, Seaborn, KaggleHub
- **Database**: SQLite
- **Visualization**: Power BI (Dashboarding)

## Dataset
- **Source**: [Kaggle Online Retail Dataset](https://www.kaggle.com/datasets/ulrikthygepedersen/online-retail-dataset)
- **Description**: A transnational dataset containing all transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail.

## Workflow
1. **Data Loading**: Ingested raw CSV data directly via KaggleHub.
2. **Data Cleaning & Anomaly Handling**: Addressed duplicates, invalid prices, and returns.
3. **Exploratory Data Analysis (EDA)**: Analyzed distributions, country breakdowns, and missing value patterns.
4. **Feature Engineering**: Created currency-adjusted and revenue-tiered features.
5. **Data Export**: Saved cleaned transactions and isolated refunds into separate CSVs for SQLite ingestion.
6. **SQL Business Querying**: Executed relational queries to extract top products, customer loyalty metrics, and geographic performance.

## Key Cleaning Tasks
- **Datetime Conversion**: Transformed `InvoiceDate` to a proper datetime format for time-series analysis.
- **Duplicate Removal**: Identified and dropped 5,268 exact duplicate records.
- **Invalid Transaction Handling**: Dropped records with negative `UnitPrice`, treating them as data entry errors.
- **Strategic Return Isolation**: Instead of blindly dropping negative `Quantity` values, they were segregated into a dedicated `data_refunds.csv` dataset for independent return-analysis.
- **Missing Value Strategy**: 
  - Dropped rows with missing `Description` (low impact, unreliable recovery).
  - **Retained** missing `CustomerID` records (~25% of data) to preserve overall transaction volume and highlight "guest checkout" behavior as a valid business insight.

## Feature Engineering
- **Currency Adjustment**: Created `UnitPriceInEuros` and `TotalUnitPriceInEuros` to standardize revenue metrics.
- **Revenue Segmentation**: Engineered a `TotalUnitRevenue` categorical feature using quantile-based binning (`Low`, `Mid`, `High`, `Very High` Revenue) to enable balanced grouping and targeted business strategies.

## SQL Skills Demonstrated
- `SELECT`, `WHERE`, `HAVING`, `GROUP BY`, `ORDER BY`
- Aggregate functions (`SUM`, `COUNT`, `MIN`, `MAX`)
- Subqueries and Common Table Expressions (CTEs)
- Date/Time extraction and manipulation (e.g., `strftime`)
- Conditional logic and data segmentation

## How to Run
1. Clone this repository.
2. Install required Python dependencies (`pandas`, `numpy`, `matplotlib`, `seaborn`, `kagglehub`).
3. Run the Jupyter Notebook to observe the step-by-step cleaning and EDA process.
4. The notebook will generate `data.csv` and `data_refunds.csv`, ready to be loaded into an SQLite database.
5. Execute the provided SQL scripts to replicate the business insights.

## Portfolio Value
This project demonstrates practical, end-to-end skills highly relevant to industry roles:
- **Data Preprocessing & EDA**: Transforming raw, messy data into a reliable analytical foundation.
- **Business Acumen**: Recognizing the difference between data errors (negative prices) and valid business events (returns), and handling them appropriately.
- **Database Design & SQL**: Structuring data and writing business-oriented queries to extract actionable insights (e.g., Pareto principle in product sales, customer loyalty rates).
- **Data Visualization**: Translating complex query results into clear, interactive Power BI dashboards for stakeholder decision-making.
