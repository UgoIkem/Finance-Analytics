# Data Source

## Dataset Overview

This project uses a financial transaction dataset containing transaction-level and customer-level information for analysing transaction performance, customer behaviour, financial metrics, and operational trends.

The dataset includes information related to:

- Transaction amounts
- Transaction dates
- Transaction types
- Transaction status
- Transaction fees and taxes
- Merchant categories
- Transaction channels
- Customer demographics
- Customer segments
- Occupation
- Geographic location

---

## Data Structure

The analytical model is built around two primary datasets:

### finance_transactions

Contains transaction-level records used for the financial and operational analysis, including:

- Transaction ID
- Customer ID
- Transaction date
- Transaction type
- Transaction status
- Transaction amount
- Fee amount
- Tax amount
- Merchant category
- Transaction channel

### customers

Contains customer-level attributes used to enrich the transaction analysis, including:

- Customer ID
- Customer name
- Gender
- Occupation
- Customer segment
- Annual income
- City
- State
- Date of birth
- Join date

The customer and transaction datasets are connected through `customer_id`, allowing transaction performance to be analysed across different customer attributes and segments.

---

## Data Preparation

The datasets were reviewed and transformed in **Power Query** before being loaded into the Power BI data model.

The preparation process included:

- Reviewing and assigning appropriate data types
- Checking data quality and consistency
- Handling missing or inconsistent values where required
- Preparing date fields for time-based analysis
- Structuring the datasets for relationship-based modelling
- Validating fields required for KPI and dimensional analysis

---

## Data Model

A relational data model was created in Power BI to support the analysis.

In addition to the transaction and customer tables, a dedicated **Calendar Table** was created to support:

- Year filtering
- Monthly trend analysis
- Previous-year calculations
- Year-over-year comparisons
- Time-intelligence measures

A **Dynamic Metric** field parameter was also implemented to allow users to interactively switch between Total Amount, Total Fees, Total Tax, and Total Transactions within selected report visuals.

---

## Data Usage

The dataset is used for educational and portfolio purposes to demonstrate an end-to-end Power BI analytics workflow, including:

- Data preparation
- Data modelling
- DAX calculations
- Time-intelligence analysis
- KPI development
- Dynamic field parameters
- Interactive dashboard design
- Drill-through analysis
- Power BI Service deployment
