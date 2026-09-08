# DAX Measures & Technical Implementation

This document highlights the key DAX calculations and Power BI features used in the Finance Analytics Dashboard.

## Core Measures

### Total Amount

```DAX
Total Amount =
SUM(finance_transactions[amount])
```

Calculates the total monetary value of transactions in the current filter context.

### Total Transactions

```DAX
Total Transactions =
COUNTROWS(finance_transactions)
```

Returns the number of transactions in the current filter context.

### Average Transaction Value

```DAX
Avg Transaction Value =
DIVIDE(
    [Total Amount],
    [Total Transactions],
    0
)
```

Calculates the average monetary value per transaction while safely handling division by zero.

### Total Fees

```DAX
Total Fees =
SUM(finance_transactions[fee_amount])
```

Calculates the total transaction fees generated.

### Total Tax

```DAX
Total Tax =
SUM(finance_transactions[tax_amount])
```

Calculates total tax associated with transactions.

---

## Time Intelligence

A dedicated Calendar table was created and related to the transaction table to support consistent date analysis and year-over-year comparisons.

### Previous Year Amount

```DAX
PY Amount =
CALCULATE(
    [Total Amount],
    SAMEPERIODLASTYEAR('Calendar Table'[Date])
)
```

### Amount YoY %

```DAX
Amount YoY % =
DIVIDE(
    [Total Amount] - [PY Amount],
    [PY Amount],
    0
)
```

The same previous-year and percentage-change approach was applied to other dashboard KPIs, including:

- Total Transactions
- Average Transaction Value
- Total Fees
- Total Tax

This allows the KPI cards to show current performance together with the change versus the previous year.

---

## Dynamic Field Parameter

A Power BI Field Parameter was created to allow users to change the metric being analysed without requiring separate visuals for every measure.

```DAX
Dynamic Metric = {
    ("Total Amount", NAMEOF('finance_transactions'[Total Amount]), 0),
    ("Total Fees", NAMEOF('finance_transactions'[Total Fees]), 1),
    ("Total Tax", NAMEOF('finance_transactions'[Total Tax]), 2),
    ("Total Transactions", NAMEOF('finance_transactions'[Total Transactions]), 3)
}
```

The parameter allows users to switch interactively between:

- Total Amount
- Total Fees
- Total Tax
- Total Transactions

The selected field parameter is used across relevant visuals to dynamically change the analysis.

---

## Dynamic Chart Titles

Because Power BI Field Parameters use grouped/composite-key metadata, directly applying `SELECTEDVALUE()` to the parameter display column can result in a composite-key error.

The chart title therefore retrieves the selected parameter while preserving the required field parameter grouping.

```DAX
Dynamic Chart Title =
VAR SelectedMetric =
    SELECTCOLUMNS(
        SUMMARIZE(
            'Dynamic Metric',
            'Dynamic Metric'[Dynamic Metric],
            'Dynamic Metric'[Dynamic Metric Fields]
        ),
        "MetricName", 'Dynamic Metric'[Dynamic Metric]
    )
RETURN
    CONCATENATEX(
        SelectedMetric,
        [MetricName],
        ", "
    ) & " by Month"
```

This dynamically produces titles such as:

- `Total Amount by Month`
- `Total Fees by Month`
- `Total Tax by Month`
- `Total Transactions by Month`

---

## Calendar Table

A dedicated date dimension was used rather than performing time analysis directly from the transaction date.

The Calendar table contains attributes including:

- Date
- Month
- Month Number
- Year

`Month Number` is used to ensure month names are displayed chronologically rather than alphabetically.

The Calendar table provides the foundation for:

- Year filtering
- Monthly trend analysis
- Previous-year calculations
- Year-over-year comparisons

---

## Power BI Features Implemented

Beyond the DAX measures, the report uses several Power BI capabilities:

- Power Query transformations
- Relational data modelling
- One-to-many relationships
- Dedicated date dimension
- DAX measures
- Time intelligence
- Field parameters
- Dynamic titles
- KPI cards
- Interactive slicers
- Cross-filtering
- Drill-through analysis
- Conditional formatting
- Power BI Service publishing
