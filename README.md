# UPI Transaction Analysis

## Data Analysis Essentials – Cornerstone Project

**Team Number:** 2

---

## 1. Project Overview

This project performs a complete data-analysis workflow on the **UPI Transactions 2024 Dataset** using Python.

The project follows a structured sequence from raw data loading and inspection through filtering, extraction, validation, aggregation, statistical analysis, visualization, and final interpretation.

### Project Workflow

```text
Dataset
   ↓
Data Loading and Reading
   ↓
Data Acquisition and Filtering
   ↓
Data Extraction
   ↓
Data Validation and Cleaning
   ↓
Data Aggregation and Representation
   ↓
Data Analysis
   ↓
Data Visualization
   ↓
Results and Interpretation
   ↓
Conclusion
```

The project uses **Pandas, NumPy, and Matplotlib** and contains stage-wise Jupyter notebooks, documentation, output PDFs, the dataset, team details, and review presentations.

---

## 2. Problem Statement

UPI transaction datasets contain a large number of individual records. Analysing these records directly can make it difficult to identify overall transaction behaviour and meaningful patterns.

This project addresses the following question:

> **What patterns can be identified in UPI transactions, and how are fraud-flagged transactions distributed across different transaction characteristics?**

The project analyses transaction types, amounts, status, merchant categories, time, devices, networks, sender states, and the fraud indicator available in the dataset.

The analysis is descriptive and is based on the supplied dataset. Observed relationships are not treated as proof of causation.

---

## 3. Objectives

The main objectives are:

1. Load and understand the UPI transaction dataset.
2. Inspect the structure, attributes, and data types.
3. Check missing values and duplicate records.
4. Filter transaction records into meaningful analysis views.
5. Extract useful information from transaction attributes.
6. Validate important fields before analysis.
7. Perform filtering, sorting, grouping, and aggregation using Pandas.
8. Calculate descriptive statistics and meaningful comparisons.
9. Analyse transaction behaviour across different categories.
10. Analyse the distribution of fraud-flagged transactions.
11. Examine fraud-flagged records across transaction type, merchant category, time, device, network, and sender state.
12. Create relevant visualizations using Matplotlib.
13. Interpret the numerical and visual results.
14. Summarize findings, limitations, and future scope.

---

## 4. Scope and Significance

The project focuses on descriptive and exploratory analysis of the supplied UPI transaction dataset.

The analysis covers:

- Transaction volume
- Transaction amounts
- Transaction status
- Transaction type
- Merchant category
- Fraud flag
- Hour of transaction
- Day of week
- Weekday/weekend behaviour
- Device type
- Network type
- Sender state
- Category-wise comparisons
- Fraud-related distributions

The project demonstrates how raw transaction records can be transformed into structured summaries, statistical results, and visual insights using Python.

---

## 5. Dataset Information

### Dataset Name

**UPI Transactions 2024 Dataset**

### Dataset Source

Kaggle:

https://www.kaggle.com/datasets/skullagos5246/upi-transactions-2024-dataset

### Dataset File

The project uses a modified noisy version of the dataset for the validation and cleaning stage.

```text
0. DataSet/upi_transactions_2024_with_noise(1).csv
```

After cleaning, the validated dataset is:

```text
0. DataSet/upi_transactions_2024(5).csv
```

### Dataset Size

| Property | Value |
| --- | ---: |
| Total records | **250,000** |
| Columns in noisy input | **27** |
| Columns after cleaning | **17** |
| Noise columns removed | **10** |
| Missing values | **0** |
| Duplicate records | **0** |

The noisy input contains 10 additional device, application, location, network, session, and contextual attributes. These fields were removed during Stage 4 so that the cleaned dataset contains the required 17 transaction attributes.

## 6. Dataset Attributes

The dataset contains 17 attributes:

| No. | Attribute            |
| --: | -------------------- |
|   1 | `transaction id`     |
|   2 | `timestamp`          |
|   3 | `transaction type`   |
|   4 | `merchant_category`  |
|   5 | `amount (INR)`       |
|   6 | `transaction_status` |
|   7 | `sender_age_group`   |
|   8 | `receiver_age_group` |
|   9 | `sender_state`       |
|  10 | `sender_bank`        |
|  11 | `receiver_bank`      |
|  12 | `device_type`        |
|  13 | `network_type`       |
|  14 | `fraud_flag`         |
|  15 | `hour_of_day`        |
|  16 | `day_of_week`        |
|  17 | `is_weekend`         |

---

### Additional Noise Attributes in the Modified Input

The modified noisy dataset contains the following 10 additional attributes. These were introduced as noise and removed during data validation and cleaning:

| Attribute | Category |
| --- | --- |
| `battery_level_pct` | Device |
| `app_version` | Application |
| `device_storage_free_gb` | Device |
| `screen_brightness_pct` | Device |
| `device_language` | Device / Context |
| `gps_accuracy_m` | Location / Context |
| `nearby_wifi_count` | Network / Context |
| `session_duration_sec` | Session |
| `notifications_last_hour` | Session / Context |
| `merchant_distance_km` | Location / Context |

The cleaned dataset retains the original 17 transaction attributes listed above.

---

## 7. Tools and Technologies

### Programming Language

- Python

### Libraries

- **Pandas** – data loading, inspection, filtering, grouping, sorting, aggregation, and analysis
- **NumPy** – numerical operations
- **Matplotlib** – data visualization

### Platforms and Tools

- Google Colab
- Jupyter Notebook
- Visual Studio Code
- GitHub

---

# 8. Stage-wise Project Implementation

## Stage 1 – Data Loading and Reading

### Purpose

To load the raw dataset and understand its initial structure before performing further operations.

### Operations performed

- Loaded the CSV using Pandas.
- Checked rows and columns.
- Displayed column names.
- Inspected sample records.
- Checked data types.
- Checked missing values.
- Checked duplicate records.
- Examined basic dataset information.

### Result

The dataset contains:

- **250,000 rows**
- **17 columns**
- **0 missing values**
- **0 duplicate records**

This verified dataset was used as the input for the next stage.

---

## Stage 2 – Data Acquisition and Filtering

### Purpose

To create useful filtered views from the complete dataset for subsequent analysis.

### Operations performed

- Created a working copy of the dataset.
- Selected relevant attributes.
- Filtered positive transaction amounts.
- Filtered successful transactions.
- Filtered fraud-flagged transactions.
- Compared record counts after filtering.

### Results

| Analysis View                | Records | Columns |
| ---------------------------- | ------: | ------: |
| Complete Dataset             | 250,000 |      17 |
| Positive Amount Transactions | 250,000 |      17 |
| Successful Transactions      | 237,624 |      17 |
| Fraud-Flagged Transactions   |     480 |      17 |

The positive-amount filter excluded no records.

### Transaction Status

| Status  |   Count |
| ------- | ------: |
| SUCCESS | 237,624 |
| FAILED  |  12,376 |

### Fraud Flag

| Category       |   Count |
| -------------- | ------: |
| Non-Fraudulent | 249,520 |
| Fraudulent     |     480 |

The filtered views were used in the following stages for focused analysis.

---

## Stage 3 – Data Extraction

### Purpose

To extract the attributes and time-related information required for analysis.

The project organised relevant fields such as:

- Transaction type
- Transaction amount
- Merchant category
- Transaction status
- Fraud flag
- Timestamp
- Hour
- Day
- Device type
- Network type
- Sender state

Timestamp-related information was prepared so that transaction behaviour could be analysed across time.

### How it supports the next stage

The extracted information was used for validation, grouping, aggregation, and time-based analysis.

---

## Stage 4 – Data Validation and Cleaning

### Purpose

To verify that the modified noisy input data is valid and consistent, remove the additional noise attributes, and prepare the 17-column dataset for analysis.

### Modified Input and Noise Removal

The validation stage starts with the modified noisy dataset containing **250,000 rows and 27 columns**.

The noisy input includes 10 additional device, application, location, network, session, and contextual attributes:

- `battery_level_pct`
- `app_version`
- `device_storage_free_gb`
- `screen_brightness_pct`
- `device_language`
- `gps_accuracy_m`
- `nearby_wifi_count`
- `session_duration_sec`
- `notifications_last_hour`
- `merchant_distance_km`

These 10 attributes were removed because they were introduced as noise and are not part of the required 17-column transaction dataset.

### Checks performed

- Compared the noisy input schema with the required transaction schema.
- Identified the additional noise columns.
- Removed the 10 noise columns.
- Checked missing values.
- Checked duplicate records.
- Checked transaction amounts.
- Checked fraud flag values.
- Checked transaction-related categorical fields.
- Standardized the `timestamp` field to an appropriate datetime type.

### Results

```text
Rows                   : 250,000
Columns before cleaning: 27
Noise columns removed  : 10
Columns after cleaning : 17
Missing values         : 0
Duplicate rows         : 0
Negative amounts       : 0
Invalid fraud flags    : 0
```

The cleaned dataset remained **250,000 × 17** after removing the additional noise attributes.

### How it supports the next stage

After noise removal and validation, the cleaned dataset was ready for grouping and aggregation.

---

## Stage 5 – Data Aggregation and Representation

### Purpose

To convert individual transaction records into meaningful category-level summaries.

Pandas grouping and aggregation were used for:

- Transaction counts
- Total transaction amounts
- Average transaction amounts
- Fraud counts
- Sender-state summaries
- Hourly summaries

### Transaction Type Summary

| Transaction Type |   Count | Total Amount | Average Amount |
| ---------------- | ------: | -----------: | -------------: |
| Bill Payment     |  37,368 |  ₹48,895,743 |      ₹1,308.49 |
| P2M              |  87,660 | ₹115,717,567 |      ₹1,320.07 |
| P2P              | 112,445 | ₹147,154,648 |      ₹1,308.68 |
| Recharge         |  12,527 |  ₹16,171,051 |      ₹1,290.90 |

### Merchant Category Summary

The analysis generated category-level summaries for merchant categories including Grocery, Food, Shopping, Fuel, Other, Utilities, Transport, Entertainment, Healthcare, and Education.

Examples:

| Merchant Category | Transactions | Total Amount | Average Amount |
| ----------------- | -----------: | -----------: | -------------: |
| Grocery           |       49,966 |  ₹58,277,893 |      ₹1,166.35 |
| Food              |       37,464 |  ₹19,919,402 |        ₹531.69 |
| Shopping          |       29,872 |  ₹76,863,207 |      ₹2,573.09 |
| Fuel              |       25,063 |  ₹38,982,575 |      ₹1,555.38 |
| Utilities         |       22,338 |  ₹52,742,482 |      ₹2,361.11 |

### Fraud Summary

| Category       |   Count | Total Amount | Average Amount |
| -------------- | ------: | -----------: | -------------: |
| Non-Fraudulent | 249,520 | ₹327,219,378 |      ₹1,311.40 |
| Fraudulent     |     480 |     ₹719,631 |      ₹1,499.23 |

### Sender-State Summary

The project generated sender-state summaries based on transaction count and transaction amount.

The five highest observed transaction-count states were:

| State         | Transactions |
| ------------- | -----------: |
| Maharashtra   |       37,427 |
| Uttar Pradesh |       30,125 |
| Karnataka     |       29,756 |
| Tamil Nadu    |       25,367 |
| Delhi         |       24,870 |

### Hourly Summary

A 24-hour transaction summary was generated.

The five highest observed transaction-count hours were:

| Hour | Transactions | Total Amount |
| ---: | -----------: | -----------: |
|   19 |       21,232 |  ₹28,223,522 |
|   18 |       20,064 |  ₹26,297,174 |
|   20 |       18,506 |  ₹23,822,014 |
|   17 |       18,340 |  ₹24,514,186 |
|   12 |       17,516 |  ₹23,406,280 |

### How it supports the next stage

These aggregated tables provide the numerical foundation for statistical analysis and visualization.

---

# 9. Stage 6 – Data Analysis

## Overall Transaction Statistics

| Metric                     |           Result |
| -------------------------- | ---------------: |
| Total transactions         |      **250,000** |
| Total transaction amount   | **₹327,939,009** |
| Average transaction amount |    **₹1,311.76** |
| Minimum transaction amount |          **₹10** |
| Maximum transaction amount |      **₹42,099** |

---

## Transaction Status Analysis

| Status  |   Count | Percentage |
| ------- | ------: | ---------: |
| SUCCESS | 237,624 |     95.05% |
| FAILED  |  12,376 |      4.95% |

---

## Transaction Type Analysis

| Transaction Type |   Count | Percentage |
| ---------------- | ------: | ---------: |
| P2P              | 112,445 |     44.98% |
| P2M              |  87,660 |     35.06% |
| Bill Payment     |  37,368 |     14.95% |
| Recharge         |  12,527 |      5.01% |

---

## Fraud Analysis

The dataset contains:

| Category       |       Count |
| -------------- | ----------: |
| Fraud-Flagged  |     **480** |
| Non-Fraudulent | **249,520** |

Fraud-flagged records represent approximately **0.19%** of the complete dataset.

The project analyses the `fraud_flag` already present in the dataset; it does not generate a new fraud label.

---

## Fraud by Transaction Type

| Transaction Type | Fraud Cases |
| ---------------- | ----------: |
| P2P              |         206 |
| P2M              |         167 |
| Bill Payment     |          77 |
| Recharge         |          30 |

This comparison shows how the available fraud-flagged records are distributed across transaction categories.

---

# 10. Stage 7 – Data Visualization

The numerical findings were converted into visual representations using Matplotlib.

The visualization stage includes analysis of:

1. Transaction Type Distribution
2. Transaction Status Distribution
3. Fraud vs Non-Fraud
4. Merchant Category Distribution
5. Transaction Activity by Hour
6. Device Type Distribution
7. Transactions by Network Type
8. Transaction Amount Distribution
9. Average Amount by Transaction Type
10. Fraud by Transaction Type
11. Fraud by Merchant Category
12. Fraud by Hour
13. Fraud by Device
14. Fraud by Network
15. Transactions by Day
16. Weekday vs Weekend
17. Fraud by Sender State
18. Average Amount: Fraud vs Non-Fraud

### Purpose

The visualizations make it easier to identify:

- Transaction distributions
- Category differences
- Amount patterns
- Time-based activity
- Fraud distributions
- Device and network distributions
- State-level differences

The visualization results were used in the final interpretation stage.

---

# 11. Stage 8 – Results and Interpretation

The final stage combines the numerical results and visualizations to interpret the patterns observed in the dataset.

## Key Observations

### Transaction Volume

P2P has the highest transaction count among the four transaction types in the supplied dataset.

### Transaction Status

Successful transactions account for **95.05%** of all records, while failed transactions account for **4.95%**.

### Transaction Amount

Transaction amounts range from **₹10 to ₹42,099**, with an overall average of **₹1,311.76**.

### Fraud Distribution

There are **480 fraud-flagged records** among 250,000 transactions, approximately **0.19%** of the dataset.

### Fraud by Transaction Type

Fraud-flagged records are distributed across P2P, P2M, Bill Payment, and Recharge transactions.

### Fraud by Hour

The highest observed hourly fraud count is at **hour 19**, with **43 fraud cases**.

### Fraud by Device

Android accounts for **364 fraud-flagged records** among the device categories.

### Fraud by Network

4G accounts for **282 fraud-flagged records** among the network categories.

### Fraud by Sender State

Maharashtra has **71 fraud-flagged records** among the sender states.

These are descriptive observations from this dataset and do not establish that any particular hour, device, network, or state causes fraud.

---

# 12. Overall Findings

The complete analysis established the following:

- The dataset contains **250,000 records**.
- The dataset contains **17 columns**.
- There are **0 missing values**.
- There are **0 duplicate records**.
- All transaction amounts are positive.
- There are **237,624 successful transactions**.
- There are **12,376 failed transactions**.
- P2P is the largest transaction category by count.
- The total transaction amount is **₹327,939,009**.
- The average transaction amount is **₹1,311.76**.
- The minimum transaction amount is **₹10**.
- The maximum transaction amount is **₹42,099**.
- There are **480 fraud-flagged records**.
- Fraud-flagged records represent approximately **0.19%** of the dataset.
- Fraud-flagged records were analysed across transaction type, merchant category, time, device, network, and sender state.
- Visualizations were created to communicate these findings.

---

# 13. Conclusion

The project demonstrates a complete practical data-analysis workflow using the UPI Transactions 2024 dataset.

The process began with raw transaction data and progressed through:

```text
Loading
   ↓
Inspection
   ↓
Filtering
   ↓
Extraction
   ↓
Validation
   ↓
Aggregation
   ↓
Statistical Analysis
   ↓
Visualization
   ↓
Interpretation
```

The analysis converted **250,000 transaction records and 17 attributes** into structured statistical summaries and visual findings.

The project provides an overall understanding of transaction volume, transaction status, transaction amounts, transaction types, and the distribution of fraud-flagged records across several available attributes.

---

# 14. Limitations

1. The analysis is based only on the supplied UPI transaction dataset.
2. The dataset represents a fixed collection of records rather than a live transaction stream.
3. The `fraud_flag` is an existing dataset attribute and is analysed rather than predicted.
4. The analysis is primarily descriptive.
5. Observed associations do not establish causation.
6. Patterns in this dataset should not automatically be generalized to all UPI transactions.

---

# 15. Future Scope

The project can be extended by:

- Using larger and continuously updated datasets.
- Building interactive dashboards.
- Performing advanced statistical analysis.
- Applying machine-learning techniques for fraud prediction.
- Comparing transaction patterns over longer periods.
- Developing real-time transaction monitoring.
- Evaluating predictive models using suitable classification metrics.
- Adding more transaction-level features.
- Comparing fraud patterns across multiple datasets.

---

# 16. Repository Structure

The actual repository is organized as follows:

```text
UPI_Transaction_Analysis/
│
├── README.md
├── requirements.txt
├── Team Details.md
│
├── 0. DataSet/
│   ├── upi_transactions_2024_with_noise(1).csv
│   └── upi_transactions_2024(5).csv
│
├── 1. Data Loading and Reading/
│   ├── 01_Data_Loading_Reading.ipynb
│   ├── README.md
│   └── Output.pdf
│
├── 2. Data Acquisition & Filtering/
│   ├── Data_Acquisition_and_Filtering.ipynb
│   ├── README.md
│   └── Output.pdf
│
├── 3. Data Extraction/
│   ├── Data_Extraction.ipynb
│   ├── README.md
│   └── Output.pdf
│
├── 4. Data Validation & Cleaning/
│   ├── Data_Validation_and_Cleaning.ipynb
│   ├── README.md
│   └── Output.pdf
│
├── 5. Data Aggregation & Representation/
│   ├── Data_Aggregation_and_Representation.ipynb
│   ├── README.md
│   └── Output.pdf
│
├── 6. Data Analysis/
│   ├── Data_Analysis.ipynb
│   ├── README.md
│   └── Output.pdf
│
├── 7. Data Visualization/
│   ├── Data_Visualization.ipynb
│   ├── README.md
│   └── Output.pdf
│
├── 8. Results & Interpretation/
│   ├── Results_and_Interpretation.ipynb
│   ├── README.md
│   └── Output.pdf
│
└── PPTs/
    ├── REVIEW - 1.pptx
    └── REVIEW - 2.pptx
```

---

# 17. Execution Instructions

## Install Dependencies

From the repository root:

```bash
pip install -r requirements.txt
```

The project requires:

```text
pandas
numpy
matplotlib
```

## Dataset Location

Ensure the modified noisy input and cleaned output are available at:

```text
0. DataSet/upi_transactions_2024_with_noise(1).csv
0. DataSet/upi_transactions_2024(5).csv
```

Stage 4 uses the noisy input, removes the 10 additional noise attributes, validates the remaining transaction data, and produces the cleaned 17-column dataset.

## Notebook Execution Order

Run the notebooks in the following order:

```text
1 → 2 → 3 → 4 → 5 → 6 → 7 → 8
```

This order preserves the logical dependency between the stages.

The notebooks can be executed using:

- Google Colab
- Jupyter Notebook
- Visual Studio Code

---

# 18. Team Details

## Team Number

**Team 2**

## Team Members

| Roll Number | Name                        |
| ----------- | --------------------------- |
| 25B11CS002  | K. Sri Sai Surya Manikanta  |
| 25B11CS005  | A. Divija Naga Sai Teja Sri |
| 25B11CS845  | Sana Jaswanthi              |
| 25B11CS946  | T. Manoj Reddy              |

---

# 19. Individual Responsibilities

### K. Sri Sai Surya Manikanta

- Data Loading and Reading
- Data Acquisition and Filtering

### A. Divija Naga Sai Teja Sri

- Data Extraction
- Data Validation and Cleaning

### Sana Jaswanthi

- Data Aggregation and Representation
- Data Analysis

### T. Manoj Reddy

- Data Visualization
- Results and Interpretation

All team members are expected to understand the complete project pipeline, including data preprocessing, Pandas operations, analysis, visualizations, results, and conclusions.

---

# 20. Project Deliverables

The repository contains:

- Dataset
- Eight stage-wise Jupyter notebooks
- Stage-wise README documentation
- Stage-wise output PDFs
- Main `README.md`
- `requirements.txt`
- Team details
- Review-1 presentation
- Review-2 presentation

The repository therefore contains the implementation, documentation, outputs, presentations, and supporting files required for the Data Analysis Cornerstone Project submission.
