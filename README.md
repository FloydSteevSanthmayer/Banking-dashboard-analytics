# Banking Dashboard

**Author:** Floyd Steev Santhmayer  
**Role:** Data Analyst

---

## Project Summary
This repository contains a Banking Dashboard project that demonstrates end-to-end analytical work: data ingestion, cleaning (ETL), exploratory data analysis (EDA), and business-focused visualization using Power BI. The goal is to provide actionable insights into client behavior, loan exposure, deposit composition, and client engagement to support data-driven decisions.

**Primary objectives**
- Provide concise KPIs for executive review (total clients, loans, deposits, fees).
- Enable deeper exploration of loan and deposit portfolios by income band, nationality, and engagement timeframe.
- Offer reproducible analysis artifacts for analysts to extend or operationalize.

---

## Data (Overview)
The analysis assumes a tabular dataset containing customer-level and account-level records. Typical fields include:
- `client_id` — unique identifier per client
- `account_type` — e.g., Bank Loan, Business Lending, Savings, Checking, Credit Card
- `product_amount` — numeric amount in base currency
- `currency` — currency code (e.g., USD)
- `nationality` — client nationality grouping
- `income_band` — categorical (Low / Mid / High)
- `engagement_years` — numeric (years of engagement)
- `gender` — Male / Female / Other
- `advisor` — assigned investment advisor
- `transaction_date` — timestamp of record

> **Note:** If your source dataset differs, adapt the column names or include a small, anonymized sample in `data/` for reproducibility.

---

## Analysis methodology
1. **Ingest** raw CSV or MySQL export into a working environment.
2. **Validate** schema and data types, handle missing values and duplicates.
3. **Transform** monetary fields to a consistent base currency and normalize account types.
4. **Enrich** data with derived fields (e.g., `engagement_band`, `tenure_years`).
5. **Aggregate** metrics at client and account granularity for KPI reporting.
6. **Visualize** using Power BI — pages included: Home, Loan Analysis, Deposit Analysis, Summary.

---

## Key Performance Indicators (KPIs)
The dashboard focuses on the following KPIs (displayed on the Home/Summary pages):
- Total Clients
- Total Loan (aggregate)
- Total Deposit (aggregate)
- Total Fees
- Bank Loan / Business Lending / Credit Card balances
- Savings / Checking / Foreign Currency balances
- Engagement accounts and tenure analysis

---

## Dashboard pages (screenshots included)
### ✅ Page 1: Home  
> Overview of the banking data with summary statistics and key visuals.  

<img src="powerbi/page1_home.png" alt="Page 1 - Home" width="700"/>

---

### ✅ Page 2: Loan Analysis  
> Insights into loan distribution, types, and customer segments.  

<img src="powerbi/page2_loan_analysis.png" alt="Page 2 - Loan Analysis" width="700"/>

---

### ✅ Page 3: Deposit Analysis  
> Breakdown of account balances, deposit types, and correlation patterns.  

<img src="powerbi/page3_deposit_analysis.png" alt="Page 3 - Deposit Analysis" width="700"/>

---

### ✅ Page 4: Summary  
> Final insights from EDA, including correlations and demographic trends.  

<img src="powerbi/page4_summary.png" alt="Page 4 - Summary" width="700"/>


---

## Reproducible run instructions (recommended)
1. Clone the repository
```bash
git clone https://github.com/YOUR-USERNAME/Banking-Dashboard.git
cd Banking-Dashboard
```
2. Create a Python virtual environment and install dependencies
```bash
python -m venv venv
source venv/bin/activate    # macOS / Linux
venv\Scripts\activate.bat # Windows
pip install -r requirements.txt
```
3. If your data is a MySQL dump:
```bash
mysql -u root -p banking_db < data/banking_dump.sql
```
4. Launch Jupyter to run EDA notebooks:
```bash
jupyter lab
```
5. Open the Power BI Desktop and load `.pbix` from `powerbi/` (if available). Update data source settings to point to your CSVs or database.

---

## Suggested `requirements.txt`
If not provided, include these packages for EDA and reproducibility:
```
pandas
numpy
matplotlib
jupyterlab
sqlalchemy
openpyxl
```

---

## File structure
```
.
├── data/                   # raw or sample datasets (CSV / SQL dump)
├── eda/                    # Jupyter notebooks for cleaning & analysis
├── powerbi/                # Power BI (.pbix) files or screenshots
├── images/                 # screenshots used in this README
├── README.md               # this file
└── LICENSE
```

---

## Best practices & recommendations
- **Anonymize** and include a small sample dataset in `data/` to allow external collaborators to run notebooks without sensitive data.
- **Version** `.pbix` files carefully — Power BI files can be large; consider storing on releases or an artifact store.
- **Document** any DAX measures and calculated columns in `powerbi/README_POWERBI.md`.
- **Add** a `RUN.md` with explicit database connection examples (sanitized credentials).

---

## Contact
Floyd Steev Santhmayer — Data Analyst  
Email: floydsteev.santhmayer@gmail.com

---


