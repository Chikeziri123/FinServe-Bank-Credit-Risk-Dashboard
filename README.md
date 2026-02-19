# FinServe Bank – Credit Risk & Transaction Analytics Dashboard

## Project Overview

An interactive Power BI dashboard built for **FinServe Bank**, a fictional retail bank, to analyse client demographics, financial health, transaction patterns, and credit card performance across 2,000 customers. The dashboard enables data-driven decision-making for credit risk assessment, customer segmentation, and transaction monitoring.

https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/FINSERVE%20BANK.pbix 

## Business Problem

FinServe Bank needed a comprehensive view of its customer base to:
- Understand client demographics and income distribution across age groups and genders
- Assess loan risk exposure using a custom risk scoring model
- Monitor debt-to-income ratios and identify high-risk customer segments
- Track transaction volumes, trends, and failure rates across time periods and geographies
- Evaluate card brand performance (Visa, Mastercard, Amex, Discover) and credit utilisation

## Dashboard Pages

### 1. Demographics Dashboard
Overview of the client base including total clients (2,000), average yearly income ($45,716), average age (45), and per capita income ($23,142). Breakdowns by age group, credit score, yearly income band, DTI category, and risk score — all segmented by gender.
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/01%20Finserve%20Bank%20-%20demographics%20dasshboard.PNG 

### 2. Loan Risk Score Methodology
Documents the risk scoring model used across the dashboard. Factors include Credit Score, Yearly Income, Total Credit Cards, Current Debt, and Active Work Years. Classification: <50 = High Risk, 50–60 = Moderate, >60 = Low Risk.

### 3. Financial Health
Deep dive into the bank's debt exposure totalling $127.4M. Tracks total debt by age group and gender, average loan risk score (56.24), debt-to-income ratio (139.36), and client distribution across income groups, credit score groups, DTI categories, and risk score categories.
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/02%20Finserve%20Bank%20-%20Financial%20health.png 

### 4. Transactions
Analysis of 157,224 transactions worth $6.87M. Includes pass/fail rates, chip usage breakdown (chip 71%, swipe 17%, online 11%), monthly and time-of-day trends via a heatmap matrix, and geographic distribution by merchant state and city.
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/03%20Finserve%20Bank%20-%20Transactions.png

### 5. Card Details
Card brand performance comparison across Visa ($2.72M), Mastercard ($3.38M), Amex ($591K), and Discover ($182K). Includes cards issued by brand and type (credit/debit/prepaid), failed transaction analysis by card brand, and total credit limit distribution.
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/04%20Finserve%20Bank%20-%20Card%20Details.png 

## 🗂️ Data Model

The project uses a **star schema** with the following tables:

| Table | Type | Description |
|-------|------|-------------|
| `fact_transactions_data` | Fact | Transaction records with amount, errors, merchant details |
| `Dim_users_data` | Dimension | Client demographics — age, income, credit score, address |
| `Dim_cards_data` | Dimension | Card details — brand, type, credit limit, chip, expiry |
| `Dim_mcc_codes` | Dimension | Merchant Category Codes with descriptions |
| `calendar` | Dimension | Date table for time intelligence |
| `Transactions` | Measure Table | Custom DAX measures for transaction KPIs |
| `Failure Metric` | Measure Table | Custom DAX measures for failure analysis |
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/Finserve%20Bank%20-%20Data%20Model.png 

## DAX Measures
Below are some of the DAX measures used out the 45 dax measures created and calculated columns used across the dashboard:
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%201.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%202.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%203.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%204.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%205.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%206.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%207.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%208.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%209.jpeg 
https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/screenshots/DAX%2010.jpeg 

## Tools & Techniques

- **Power BI Desktop** — Data modelling, DAX measures, interactive visualisations
- **Power Query (M)** — Data cleaning, transformation, and shaping
- **DAX** — Calculated columns, measures, and KPIs (risk scoring, DTI ratios, aggregations)
- **Star Schema Design** — Optimised data model with fact and dimension tables

## Key Insights

1. **Gender Split**: Female clients (1,016) slightly outnumber males (984), with similar income and age distributions across both groups
2. **Risk Exposure**: Average loan risk score of 56.24 places the overall portfolio in the moderate risk zone
3. **High DTI Ratio**: Average DTI of 139.36 suggests clients carry debt significantly exceeding their income — a key area for risk management
4. **Transaction Method**: 71% of transactions use chip technology, indicating strong EMV adoption; online transactions at 11% represent a growth area
5. **Card Performance**: Mastercard leads in transaction volume ($3.38M), while Discover has the smallest footprint ($182K) with only 209 issued cards
6. **Transaction Success**: 98.26% pass rate (154,486 passed vs 2,738 failed) across all transactions

## Recommendations

1. **Tighten Lending Criteria for High-DTI Clients**: With an average DTI of 139.36, the bank should implement stricter debt-to-income thresholds for new loan approvals and consider restructuring options for existing high-DTI borrowers
2. **Target Moderate Risk Segment for Intervention**: The average risk score of 56.24 sits in the moderate zone — proactive engagement such as financial wellness programmes or credit counselling could prevent these clients from slipping into high risk
3. **Expand Online Transaction Infrastructure**: At only 11% of total transactions, online channels are underutilised. Investing in digital payment solutions and promoting online banking could reduce operational costs and improve customer experience
4. **Review Discover Card Strategy**: With only 209 cards issued and $182K in transactions, the bank should evaluate whether to invest in growing the Discover portfolio or reallocate resources toward higher-performing brands like Mastercard and Visa
5. **Investigate Failed Transactions**: Although the 98.26% pass rate is strong, the 2,738 failed transactions still represent potential revenue loss. A root cause analysis by card brand, merchant, and time period could reduce failure rates further
6. **Age-Targeted Products**: Develop tailored financial products for the 31–50 age group which represents the highest client concentration and debt volume, focusing on debt consolidation and savings incentives


## 📂 Repository Contents

```
├── FinServe_Bank_Dashboard.pbix    # Power BI dashboard file
├── README.md                       # Project documentation
├── screenshots/                    # Dashboard screenshots
│   ├── 01_demographics.png
│   ├── 02_risk_methodology.png
│   ├── 03_financial_health.png
│   ├── 04_transactions.png
│   ├── 05_card_details.png
│   └── 06_data_model.png
└── data/                           # Source data (if shareable)
    └── (add your CSV/Excel files here)
```

## How to Use

1. Download the `.pbix` file from this repository
2. https://github.com/Chikeziri123/FinServe-Bank-Credit-Risk-Dashboard/blob/main/FINSERVE%20BANK.pbix 
3. Open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
4. Explore the interactive filters — Loan Risk, Total Debt, Yearly Income, and Year
5. Navigate between pages using the sidebar buttons or tabs at the bottom

## 👤 Author

**Chikeziri Nnodum**
Senior Business Analyst | Data Analytics | Digital Transformation

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/chikeziri-nnodum/) 
---

*This project was built as part of my data analytics portfolio to demonstrate skills in data modelling, DAX, and business intelligence visualisation.*
