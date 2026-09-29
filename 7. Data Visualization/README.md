# Stage 7 — Data Visualization

## Objective

The objective of this stage is to represent the results of the UPI transaction analysis using graphical visualizations. The visualizations make transaction patterns, fraud patterns, time-based activity, and other categorical distributions easier to understand.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas
- Matplotlib

## Input Dataset

`upi_transactions_2024.csv`

## Visualizations Created

1. Transaction Type Distribution
2. Transaction Status Distribution
3. Fraudulent vs Non-Fraudulent Transactions
4. Transactions by Merchant Category
5. Transaction Activity by Hour
6. Transactions by Device Type
7. Transactions by Network Type
8. Distribution of Transaction Amounts
9. Average Transaction Amount by Transaction Type
10. Fraudulent Transactions by Transaction Type
11. Fraudulent Transactions by Merchant Category
12. Fraudulent Transactions by Hour
13. Fraudulent Transactions by Device Type
14. Fraudulent Transactions by Network Type
15. Transactions by Day of Week
16. Weekday vs Weekend Transactions
17. Top Sender States by Fraudulent Transactions
18. Average Transaction Amount: Fraud vs Non-Fraud

## Visualization Methods

### Bar Charts

Bar charts were used to compare transaction counts and fraud counts across categories such as transaction type, merchant category, device type, network type, day of week, and sender state.

### Line Charts

Line charts were used to show transaction activity and fraudulent transaction activity across different hours of the day.

### Histogram

A histogram was used to represent the distribution of transaction amounts.

## Analysis Support

The visualizations provide graphical evidence for the findings obtained during the Data Analysis stage. They help identify differences and patterns across transaction categories, time periods, fraud status, devices, networks, and transaction amounts.

## Output

The visualization results are stored in:

`Output.pdf`

The Python implementation is stored in:

`07_data_visualization.py`

The complete Google Colab notebook is used to execute the visualization cells.

## Conclusion

The Data Visualization stage successfully converted the analytical results into graphical representations. These visualizations provide the foundation for the final Results & Interpretation stage.
