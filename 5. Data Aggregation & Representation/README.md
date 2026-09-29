# Stage 5 — Data Aggregation & Representation

## Objective

The objective of this stage is to aggregate the UPI transaction data into meaningful summaries and represent the results in a structured form for further analysis.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas

## Input Dataset

`upi_transactions_2024.csv`

The dataset contains 250,000 rows and 17 columns.

## Operations Performed

1. Loaded the UPI transaction dataset using Pandas.
2. Aggregated transactions by transaction type.
3. Calculated transaction count, total transaction amount, and average transaction amount.
4. Aggregated transactions by merchant category.
5. Calculated transaction count, total amount, and average amount for merchant categories.
6. Aggregated transactions using the fraud flag.
7. Aggregated transactions by sender state.
8. Aggregated transactions by transaction hour.
9. Created summary representations for the aggregated datasets.

## Aggregations Created

### Transaction Type Summary
- Transaction count
- Total amount
- Average amount

### Merchant Category Summary
- Transaction count
- Total amount
- Average amount

### Fraud Summary
- Transaction count
- Total amount
- Average amount

### Sender State Summary
- Transaction count
- Total amount

### Hourly Summary
- Transaction count
- Total amount

## Results

- Transaction Type Summary: 4 groups
- Merchant Category Summary: 10 groups
- Fraud Summary: 2 groups
- State Summary: 10 groups
- Hourly Summary: 24 groups

## Output

The aggregated summaries provide structured information about transaction types, merchant categories, fraud status, sender states, and transaction hours.

## Conclusion

The UPI transaction dataset was successfully aggregated into multiple summary datasets. These representations provide organized information that can be used for detailed data analysis and visualization in the following stages.
