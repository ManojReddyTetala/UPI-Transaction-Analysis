# Stage 2 — Data Acquisition & Filtering

## Objective

The objective of this stage is to acquire the raw UPI transaction dataset and apply relevant filters to obtain transaction subsets required for further analysis.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas

## Input Dataset

`Dataset(1).csv`

The raw dataset contains **250,000 UPI transactions** across **27 columns**.

## Operations Performed

1. Loaded the raw UPI transaction dataset using Pandas.
2. Checked the total number of transactions.
3. Inspected the transaction status values.
4. Filtered transactions with `Transaction Status = SUCCESS`.
5. Inspected the fraud flag values.
6. Filtered transactions with `Fraud Flag = 1`.
7. Displayed sample records from the filtered datasets.

## Filtering Conditions

### Successful Transactions

```python
df[df["Transaction Status"] == "SUCCESS"]
```

### Fraudulent Transactions

```python
df[df["Fraud Flag"] == 1]
```

## Results

- Total transactions: **250,000**
- Successful transactions: **221,993**
- Fraudulent transactions: **443**

The raw dataset contains some inconsistent representations in the transaction-status and fraud-flag fields, such as leading/trailing spaces, alternative text representations, and missing values. Therefore, these results represent the direct filtering of the raw dataset before the detailed validation and cleaning performed in the later stage.

## Output

The filtered successful-transaction and fraudulent-transaction subsets are used as inputs for subsequent stages of the project.

These subsets help focus the analysis on transaction outcomes and potentially fraudulent transactions while preserving the original raw dataset for validation and cleaning.

## Conclusion

The raw UPI transaction dataset was successfully acquired and inspected using Pandas. Filtering was performed based on transaction status and fraud flag to obtain relevant transaction subsets.

From the **250,000 raw transactions**, **221,993 transactions** were directly identified as `SUCCESS` and **443 transactions** were directly identified with `Fraud Flag = 1`.

The presence of inconsistent and missing values in the raw fields is retained for the subsequent **Data Validation & Cleaning** stage, where these data-quality issues are examined and handled systematically.
