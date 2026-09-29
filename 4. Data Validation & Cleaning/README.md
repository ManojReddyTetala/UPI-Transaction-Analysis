# Stage 4 — Data Validation & Cleaning

## Objective

The objective of this stage is to validate the dataset and identify or handle missing values, duplicate records, invalid values, and data type issues.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas

## Input Dataset

`upi_transactions_2024.csv`

The dataset contains 250,000 rows and 17 columns.

## Operations Performed

1. Validated the original dataset dimensions.
2. Checked the data types of important columns.
3. Converted the `timestamp` column to datetime format.
4. Checked for missing values.
5. Checked for duplicate rows and removed them if present.
6. Checked for negative transaction amounts.
7. Checked for invalid `fraud_flag` values.
8. Validated transaction types and transaction statuses.
9. Performed final validation of the dataset.
10. Displayed a sample cleaned record.

## Validation Results

- Rows: 250,000
- Columns: 17
- Missing values: 0
- Duplicate rows: 0
- Negative amounts: 0
- Invalid fraud flags: 0
- Timestamp converted to datetime: Yes

## Categorical Values Identified

### Transaction Types
- Bill Payment
- P2M
- P2P
- Recharge

### Transaction Statuses
- FAILED
- SUCCESS

## Conclusion

The dataset passed the validation checks performed in this stage. No missing values, duplicate rows, negative transaction amounts, or invalid fraud flag values were found. The timestamp was successfully converted to datetime format, and the validated dataset is ready for the next stage.
