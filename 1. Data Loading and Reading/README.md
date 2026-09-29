# Stage 1 — Data Loading & Reading

## Objective

Load the raw UPI transaction dataset and inspect its initial structure before filtering, extraction, cleaning, aggregation, analysis, or visualization.

## Platform and Tools

- Google Colab — initial execution and inspection
- VS Code — project code organization and execution
- Python
- Pandas
- GitHub — final repository submission

## Input

`data/raw/upi_transactions_2024.csv`

## Operations Performed

1. Loaded the CSV dataset using `pandas.read_csv()`.
2. Checked the number of rows and columns.
3. Listed all column names.
4. Inspected data types.
5. Displayed the first five records.
6. Checked missing values.
7. Checked duplicate rows.

## Results

- Rows: **250,000**
- Columns: **17**
- Missing values: **0**
- Duplicate rows: **0**

## Columns

1. transaction id
2. timestamp
3. transaction type
4. merchant_category
5. amount (INR)
6. transaction_status
7. sender_age_group
8. receiver_age_group
9. sender_state
10. sender_bank
11. receiver_bank
12. device_type
13. network_type
14. fraud_flag
15. hour_of_day
16. day_of_week
17. is_weekend

## Conclusion

The UPI transaction dataset was successfully loaded and its initial structure was inspected. The dataset contains 250,000 records across 17 variables. No missing values or duplicate rows were identified during the initial inspection.
