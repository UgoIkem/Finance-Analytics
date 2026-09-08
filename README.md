# 📊 Finance Analytics Dashboard

An end-to-end **Power BI finance analytics project** designed to analyse financial transactions, customer behaviour, transaction performance, fees, taxes, and year-over-year trends.

The project covers the complete analytics workflow — from **data preparation and data modelling to DAX calculations, time intelligence, interactive dashboard development, and deployment to Power BI Service**.

## 🔗 Live Dashboard

[**View the Interactive Power BI Dashboard**](https://app.powerbi.com/view?r=eyJrIjoiMmQ0YmNjMGQtMTc3Mi00MTNmLTg1MTMtZjI0YTk1YTVkMmQyIiwidCI6IjQ2NWU4NmRmLWRiNWMtNDlmNi1hYjkyLTE1MmY2OGUzZjJjOSIsImMiOjl9)

---

## 📌 Project Overview

Financial transaction data can provide valuable insights into customer behaviour, transaction patterns, operational performance, and revenue-related metrics.

The objective of this project was to transform raw financial and customer data into an interactive analytical solution that enables users to:

- Monitor key financial KPIs
- Analyse monthly and yearly transaction trends
- Compare current performance against the previous year
- Investigate successful, failed, and pending transactions
- Analyse transaction performance across customer segments
- Identify geographic patterns across states
- Compare different transaction types
- Analyse customer demographic patterns
- Dynamically switch between financial metrics
- Drill through from summary-level insights to individual transaction records

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** — data modelling, DAX, and dashboard development
- **Power Query** — data preparation and transformation
- **DAX** — calculated measures and time-intelligence analysis
- **Power BI Service** — report publishing and online deployment
- **GitHub** — project documentation and portfolio hosting

---

## 🔄 Data Preparation

The data was prepared and transformed in **Power Query** before being loaded into the analytical model.

Key preparation steps included:

- Reviewing column quality and data types
- Handling missing and inconsistent values
- Preparing transaction and customer datasets
- Creating calculated attributes required for analysis
- Ensuring transaction dates were correctly formatted for time-based analysis
- Preparing tables for relationship-based modelling

---

## 🗂️ Data Model

The project uses a relational model rather than relying on a single flat table.

The core model consists of:

- **finance_transactions** — transaction-level financial data
- **customers** — customer demographic and segmentation attributes
- **Calendar Table** — dedicated date dimension for time-intelligence calculations
- **Dynamic Metric** — field parameter used to dynamically change the metric displayed in selected visuals

The `customers` and `Calendar Table` tables connect to the transaction table through one-to-many relationships, allowing customer and date attributes to filter transaction-level measures.

![Power BI Data Model](images/data-model.png)

The dedicated Calendar table supports consistent date filtering and previous-year comparisons across the report.

---

## 🧮 DAX & Time Intelligence

DAX measures were developed to calculate the dashboard's core financial KPIs and comparative metrics.

### Core KPIs

- **Total Amount**
- **Total Transactions**
- **Average Transaction Value**
- **Total Fees**
- **Total Tax**

Previous-year measures were created to support **year-over-year (YoY) performance analysis**.

Time-intelligence calculations compare current results against the corresponding period in the previous year, enabling the KPI cards to show both current performance and the percentage increase or decrease versus the previous year.

---

## 🔀 Dynamic Metric Analysis

A Power BI **Field Parameter** was implemented to allow users to dynamically switch between:

- Total Amount
- Total Fees
- Total Tax
- Total Transactions

The selected metric automatically updates the relevant dashboard visuals.

Dynamic titles were also implemented so that chart titles change according to the metric selected by the user.

This allows a single visual to support multiple analytical perspectives without duplicating charts.

---

## 📈 Dashboard Overview

![Finance Analytics Dashboard](images/dashboard-overview.png)

The main analysis page provides an executive-level view of financial and transaction performance.

### Key Analyses

**Monthly Trend Analysis**  
Tracks financial performance across months and highlights changes in transaction activity over time.

**Transaction Status Analysis**  
Breaks transactions into Success, Failed, and Pending categories to provide visibility into transaction outcomes.

**Customer Segment Analysis**  
Compares financial performance across Retail, Premium, SME, Corporate, and Wealth customer segments.

**Geographic Analysis**  
Analyses transaction performance across different states.

**Transaction Type Analysis**  
Compares transaction types across Amount, Fees, Tax, and Transaction Count.

**Gender Analysis**  
Provides an additional demographic view of transaction value.

### Interactive Filters

Users can filter and explore the dashboard by:

- Year
- Dynamic Metric
- Occupation
- Merchant Category

---

## 💡 Key Insights

Based on the 2024 dashboard view:

- **Total transaction value reached approximately $135.62M** across roughly **15K transactions**, with an average transaction value of approximately **$9.02K**.
- **Successful transactions accounted for approximately 85% of total transaction value**, making successful transactions the dominant contributor to overall financial activity.
- The **Retail customer segment generated approximately $74M**, substantially outperforming the other customer segments and representing the largest source of transaction value.
- **Premium and SME customers** were the next-largest segments, contributing approximately **$26M and $21M** respectively.
- **Maharashtra recorded the highest transaction value among the displayed states at approximately $19.7M**, followed by Karnataka and Gujarat.
- Transaction value was **relatively balanced across gender**, with female customers contributing approximately **51.3%** and male customers approximately **48.7%**.
- Compared with the previous year, **Total Amount and Average Transaction Value declined slightly**, while **Total Fees and Total Tax showed modest growth**, highlighting differences between transaction value performance and fee/tax generation.

These insights can be explored further through the report's interactive filters and dynamic metric selector.

---

## 🔎 Transaction-Level Analysis

![Transaction Details](images/transactions-page.png)

The Transactions page provides detailed transaction-level information for deeper investigation.

Users can move from aggregated dashboard insights to individual transaction records and review attributes including:

- Transaction ID
- Customer
- Transaction Date
- Transaction Type
- Transaction Status
- Gender
- Customer Segment
- State
- Transaction Amount
- Fees
- Tax

This provides a detailed analytical layer for investigating the individual transactions behind the aggregated dashboard results.

---

## 🎯 Analytical Capabilities Demonstrated

This project demonstrates practical experience in:

- Data cleaning and transformation
- Relational data modelling
- One-to-many table relationships
- Date dimension design
- DAX measure development
- Time-intelligence calculations
- Year-over-year analysis
- KPI development
- Field parameters
- Dynamic visual titles
- Interactive filtering
- Drill-through analysis
- Financial transaction analysis
- Customer segmentation
- Dashboard UI/UX design
- Power BI Service deployment

---

## 👤 Author

**Ugonna Ikem-Ede**

Data Analyst | SQL | Power BI | Tableau | Python | Excel
