# Stage 8 — Results & Interpretation

## 1. Stage Objective

The purpose of this stage is to present the results obtained from the UPI transaction analysis and interpret what those results mean in relation to the project problem statement.

This stage brings together the findings from the previous stages and provides a final interpretation of the transaction and fraud patterns identified in the dataset.

---

## 2. Project Problem Statement

The project aims to analyze UPI transaction data to understand:

- Transaction patterns
- Transaction behaviour
- Transaction amounts
- Fraudulent and non-fraudulent transactions
- Characteristics associated with observed fraudulent transactions

The main analytical question is:

> **What patterns can be identified in UPI transactions, and what characteristics are associated with fraudulent transactions?**

---

## 3. Dataset Used

**Dataset:** `upi_transactions_2024.csv`

The dataset contains **2,50,000 transactions** and includes information related to:

- Transaction ID
- Timestamp
- Transaction type
- Merchant category
- Transaction amount
- Transaction status
- Sender and receiver age groups
- Sender state
- Sender and receiver banks
- Device type
- Network type
- Fraud flag
- Hour of day
- Day of week
- Weekend indicator

---

## 4. Platform and Libraries

### Platform

- Google Colab
- VS Code

### Programming Language

- Python

### Libraries

- **Pandas** — used for loading the dataset and calculating analytical results.

Matplotlib was used in Stage 7 for visualization; Stage 8 uses the calculated results from the analysis and does not require additional visualization libraries.

---

## 5. Results Covered

The following results are calculated from the dataset:

### Overall Transaction Results

- Total number of transactions
- Total transaction amount
- Average transaction amount
- Minimum transaction amount
- Maximum transaction amount

### Fraud Results

- Number of fraudulent transactions
- Number of non-fraudulent transactions
- Percentage of fraudulent transactions

### Transaction Behaviour

- Most common transaction type
- Most common merchant category
- Most active transaction hour
- Most commonly used device type
- Most commonly used network type
- Most active day of the week

### Fraud Patterns

Fraudulent transactions are examined across:

- Transaction type
- Merchant category
- Hour of day
- Device type
- Network type
- Sender state

---

## 6. Interpretation

The results are interpreted using the patterns identified during the Data Analysis and Data Visualization stages.

The interpretation focuses on:

1. Understanding the overall transaction behaviour.
2. Understanding the distribution of transaction amounts.
3. Comparing fraudulent and non-fraudulent transactions.
4. Identifying categories with higher observed transaction activity.
5. Identifying categories with higher observed numbers of fraud cases.
6. Understanding time-based transaction and fraud patterns.
7. Understanding the distribution of transactions and fraud cases across devices, networks, and sender states.

The results describe patterns and associations present in the dataset. They should not be interpreted as proof that a particular transaction type, device, network, state, or merchant category causes fraud.

---

## 7. Relationship to the Project Problem

The analysis answers the project problem by combining:

**Raw UPI Data → Data Processing → Aggregation → Analysis → Visualization → Results → Interpretation**

The project therefore moves beyond simply displaying graphs. The final stage explains what the calculated results and visual patterns indicate about UPI transaction behaviour and observed fraudulent transaction patterns.

---

## 8. Final Conclusion

The UPI Transaction Analysis project successfully analyses a large transaction dataset through a structured eight-stage data pipeline.

The project examines transaction behaviour, transaction amounts, transaction categories, time-based activity, device and network usage, and fraudulent transaction patterns.

The final results provide measurable findings from the dataset, while the visualizations from Stage 7 make those findings easier to compare and understand.

Overall, the project demonstrates the use of Python and Pandas to transform raw UPI transaction data into structured analytical results and meaningful interpretations.

---

## 9. Output Files

The Stage 8 folder contains:

```text
08_Results_and_Interpretation/
├── README.md
├── 08_results_and_interpretation.py
└── Output.pdf
```

### `08_results_and_interpretation.py`

Contains the Python code used to calculate and display the numerical results.

### `Output.pdf`

Contains the Stage 8 results, problem statement, interpretation, key findings, and final conclusion.

---

## 10. Important Note

The numerical values in the results are generated directly from `upi_transactions_2024.csv` by the Stage 8 Python code.

The interpretation is based on the observed dataset patterns. No causal conclusion is made from the descriptive analysis.
