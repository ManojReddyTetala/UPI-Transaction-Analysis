# Stage 6 — Data Analysis

## Objective

The objective of this stage is to analyse the UPI transaction dataset and identify patterns related to transaction amounts, transaction status, transaction types, fraud, time, devices, and network types.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas

## Input Dataset

`upi_transactions_2024.csv`

The dataset contains 250,000 transactions.

## Analysis Performed

1. Analysed the overall transaction count and transaction amounts.
2. Calculated total, average, minimum, and maximum transaction amounts.
3. Analysed transaction status distribution.
4. Analysed transaction type distribution.
5. Calculated the number and percentage of fraudulent transactions.
6. Analysed fraud by transaction type.
7. Analysed fraud by merchant category.
8. Analysed fraud by transaction hour.
9. Analysed fraud by device type.
10. Analysed fraud by network type.

## Key Results

- Total transactions: 250,000
- Total transaction amount: ₹327,939,009
- Average transaction amount: ₹1,311.76
- Fraudulent transactions: 480
- Fraud percentage: 0.19%

## Analysis Areas

### Transaction Analysis

Transaction volume and transaction amount statistics were calculated to understand the overall transaction activity.

### Transaction Status Analysis

The distribution of successful and failed transactions was analysed.

### Transaction Type Analysis

Transactions were analysed across the available transaction types.

### Fraud Analysis

Fraudulent and non-fraudulent transactions were compared, and fraud patterns were analysed across transaction type, merchant category, hour, device type, and network type.

## Output

The analysis results provide the basis for identifying patterns and insights that will be presented visually in the Data Visualization stage.

## Conclusion

The UPI transaction dataset was successfully analysed using multiple transaction and fraud-related dimensions. The results provide the required analytical findings for the next stage, Data Visualization.
