# Stage 2 — Data Acquisition & Filtering

## Objective

The objective of this stage is to acquire the raw UPI transaction dataset and apply relevant filters to obtain subsets required for further analysis.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas

## Input Dataset

`upi_transactions_2024.csv`

The raw dataset contains 250,000 UPI transactions.

## Operations Performed

1. Loaded the raw UPI transaction dataset using Pandas.
2. Checked the total number of transactions.
3. Filtered transactions with `transaction_status = SUCCESS`.
4. Filtered transactions with `fraud_flag = 1`.
5. Displayed sample records from the filtered datasets.

## Filtering Conditions

### Successful Transactions

```python
df[df["transaction_status"] == "SUCCESS"]
```

### Fraudulent Transactions

```python
df[df["fraud_flag"] == 1]
```

## Results

- Total transactions: 250,000
- Successful transactions: 237,624
- Fraudulent transactions: 480

## Output

The filtered datasets are used as inputs for subsequent stages of the project.

## Conclusion

The raw UPI transaction dataset was successfully acquired and filtered according to transaction status and fraud flag. The resulting subsets provide the required data for further extraction, cleaning, aggregation, and analysis.
