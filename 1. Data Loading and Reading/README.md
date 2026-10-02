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

`Dataset(1).csv`

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
- Columns: **27**
- Missing values: **124,747**
- Duplicate rows: **0**

The raw dataset contains the main UPI transaction attributes along with additional device and environment-related attributes. The missing-value inspection was performed at the initial stage to understand the original data quality before any cleaning or transformation.

## Columns

### Core Transaction and Payment Attributes

1. Transaction ID
2. time_stamp
3. Transaction_Type
4. merchant category
5. amount_INR
6. Transaction Status
7. sender_agegroup
8. receiver_age_group
9. Sender State
10. sender bank
11. Receiver_Bank
12. device type
13. Network Type
14. Fraud Flag
15. hour of day
16. Day Of Week
17. is weekend

### Device and Environment Attributes

18. battery level %
19. App Version
20. device storage free gb
21. screen brightness %
22. Device Language
23. GPS accuracy m
24. nearby wifi count
25. session duration sec
26. notifications last hour
27. merchant distance km

## Missing-Value Inspection

The raw dataset contains **124,747 missing values** across the available fields.

These missing values are recorded during Stage 1 as part of the initial dataset inspection. They are not considered resolved at this stage. Missing-value handling and validation are performed in **Stage 4 — Data Validation & Cleaning**.

## Duplicate Inspection

The dataset contains **0 duplicate rows** based on a complete-row duplicate check.

## Conclusion

The UPI transaction dataset was successfully loaded and its initial structure was inspected. The dataset contains **250,000 records across 27 variables**.

The initial inspection identified **124,747 missing values** and **0 duplicate rows**. The dataset contains both core transaction attributes and additional device/environment-related attributes.

The results of this initial inspection provide the baseline for the following stages, where relevant fields are extracted, validated, cleaned, transformed, aggregated, analysed, and visualized.
