# UPI Transaction Analysis — Data Analysis Cornerstone Project

## 1. Project Title

# UPI Transaction Analysis

A complete data-analysis project covering **data loading, filtering, extraction, validation, cleaning, aggregation, statistical analysis, visualization, and interpretation** of UPI transaction data.

---

# 2. Project Overview

This project analyses a dataset containing **UPI transaction records** to understand transaction behaviour, transaction amounts, transaction status, transaction types, time-based activity, and the distribution of fraud-flagged transactions.

The project follows a structured **eight-stage data-analysis workflow**. Each stage builds on the output of the previous stage, allowing the raw transaction records to be transformed into meaningful numerical summaries, comparisons, visualizations, and final findings.

The overall workflow is:

```text
Data Loading
      ↓
Data Acquisition & Filtering
      ↓
Data Extraction
      ↓
Data Validation & Cleaning
      ↓
Data Aggregation & Representation
      ↓
Data Analysis
      ↓
Data Visualization
      ↓
Results & Interpretation
```

---

# 3. Problem Statement

UPI transactions generate large amounts of transaction-level data containing information about transaction type, amount, status, users, banks, devices, networks, time, location, and fraud indicators.

Analysing individual transaction records directly can make it difficult to identify overall patterns.

Therefore, this project aims to use Python and Pandas to:

- Understand the structure and quality of the transaction dataset.
- Extract relevant information.
- Validate and clean the data.
- Group and aggregate transactions.
- Calculate descriptive statistics.
- Compare transaction categories.
- Analyse transaction status.
- Examine transaction amounts.
- Analyse fraud-flagged transactions.
- Study fraud distribution across different attributes.
- Create meaningful visualizations.
- Interpret the resulting patterns.

---

# 4. Objectives

The main objectives of the project are:

1. Load and understand the UPI transaction dataset.
2. Inspect the structure, attributes, and data types.
3. Identify missing values and duplicate records.
4. Filter transaction records into meaningful analysis views.
5. Extract useful information from transaction attributes.
6. Derive useful temporal information from timestamps.
7. Validate important fields before analysis.
8. Clean unnecessary noise and inconsistent data.
9. Perform grouping, sorting, filtering, and aggregation using Pandas.
10. Calculate descriptive statistics and meaningful comparisons.
11. Analyse transaction behaviour across different categories.
12. Analyse the distribution of fraud-flagged transactions.
13. Examine fraud-flagged transactions across transaction type, merchant category, time, device, network, and sender state.
14. Create relevant visualizations using Matplotlib.
15. Interpret numerical and visual results.
16. Summarize findings, limitations, and future scope.

---

# 5. Scope and Significance

The project focuses on **descriptive and exploratory analysis** of the supplied UPI transaction dataset.

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
- Bank-related attributes
- Age-group attributes
- Time-based patterns
- Category-wise comparisons
- Fraud-related distributions

The project demonstrates how raw transaction records can be transformed into structured summaries, statistical results, and visual insights using Python.

---

# 6. Dataset Information

## Dataset

**UPI Transactions 2024 Dataset**

The project uses a transaction-level UPI dataset and introduces additional noisy/contextual fields for the data-validation and cleaning stage.

## Dataset Size

| Property                                 |       Value |
| ---------------------------------------- | ----------: |
| Total records                            | **250,000** |
| Columns in noisy input                   |      **27** |
| Required transaction columns             |      **17** |
| Additional noise columns                 |      **10** |
| Missing values identified in noisy input | **124,747** |
| Duplicate rows                           |       **0** |
| Rows after cleaning                      | **250,000** |
| Columns after cleaning                   |      **17** |
| Missing values after cleaning            |       **0** |

---

# 7. Dataset Attributes

The required transaction dataset contains the following 17 core attributes:

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

# 8. Tools and Technologies

## Programming Language

- Python

## Libraries

### Pandas

Used for:

- Reading CSV files
- Inspecting datasets
- Filtering records
- Sorting records
- Grouping data
- Aggregating values
- Data transformation
- Statistical summaries

### NumPy

Used for:

- Numerical operations
- Supporting analytical calculations

### Matplotlib

Used for:

- Creating charts
- Visualizing transaction patterns
- Comparing categories
- Presenting analysis results

## Platforms and Tools

- Google Colab
- VS Code
- Jupyter Notebooks
- GitHub

---

# 9. Project Methodology

The project was divided into eight stages so that the complete analysis could be performed systematically.

---

# Stage 1 — Data Loading & Reading

## Objective

The first stage focused on loading the raw dataset and understanding its initial structure before filtering, extraction, cleaning, aggregation, or analysis.

## Operations Performed

- Loaded the CSV dataset using `pandas.read_csv()`.
- Checked the number of rows and columns.
- Listed all column names.
- Inspected data types.
- Displayed sample records.
- Checked missing values.
- Checked duplicate records.

## Initial Results

The noisy input contains:

- **250,000 records**
- **27 columns**
- **124,747 missing values**
- **0 duplicate rows**

The dataset contains both the required transaction attributes and additional device/environment/session/context attributes.

The initial inspection establishes the baseline data quality before the later validation and cleaning stage.

---

# Stage 2 — Data Acquisition & Filtering

## Objective

The second stage focused on acquiring the dataset and creating useful transaction subsets for further analysis.

## Operations Performed

- Loaded the raw dataset using Pandas.
- Checked the total number of transactions.
- Inspected transaction-status values.
- Filtered successful transactions.
- Inspected fraud-flag values.
- Filtered fraud-flagged transactions.
- Displayed sample records from the filtered datasets.

## Filtering Conditions

### Successful Transactions

```python
df[df["Transaction Status"] == "SUCCESS"]
```

### Fraudulent / Fraud-Flagged Transactions

```python
df[df["Fraud Flag"] == 1]
```

## Results

- Total transactions: **250,000**
- Directly filtered successful transactions: **221,993**
- Directly filtered fraud-flagged transactions: **443**

The raw fields contain inconsistencies and missing values, so these are **direct raw-data filtering results**. Detailed validation and cleaning are performed in Stage 4.

---

# Stage 3 — Data Extraction

## Objective

The third stage focused on extracting the transaction information required for subsequent analysis.

## Operations Performed

- Loaded the dataset.
- Converted the timestamp field into datetime format.
- Extracted date.
- Extracted month.
- Extracted year.
- Extracted week number.
- Extracted day of month.
- Extracted day name.
- Selected the required transaction attributes.
- Created a focused extraction dataset.
- Displayed sample extracted records.

## Derived Temporal Attributes

The timestamp was used to derive:

- Date
- Month
- Year
- Week number
- Day of month
- Day name

These fields allow transactions to be studied across different time periods.

For example, transactions can later be grouped by:

- Month
- Date
- Week
- Day
- Day of week
- Weekend/weekday
- Hour

---

# Stage 4 — Data Validation & Cleaning

## Objective

The fourth stage focused on validating the dataset and transforming the noisy input into a clean dataset suitable for analysis.

## Noisy Dataset

The noisy dataset contains:

- **250,000 rows**
- **27 columns**

It includes 10 additional device, application, session, network, and contextual fields that are not required for the core transaction analysis.

## Noise Columns Removed

The following fields were removed:

- `battery level %`
- `App Version`
- `device storage free gb`
- `screen brightness %`
- `Device Language`
- `GPS accuracy m`
- `nearby wifi count`
- `session duration sec`
- `notifications last hour`
- `merchant distance km`

The required 17 transaction attributes were retained.

## Operations Performed

1. Validated dataset dimensions.
2. Compared available fields with the required transaction schema.
3. Identified the 10 additional noise fields.
4. Removed unnecessary columns.
5. Checked important data types.
6. Standardized the timestamp field.
7. Checked missing values.
8. Handled missing values.
9. Checked duplicate rows.
10. Checked transaction amounts.
11. Checked fraud-flag values.
12. Validated transaction types.
13. Validated transaction statuses.
14. Performed final validation.

## Validation Results

| Check                        | Noisy Input | Cleaned Output |
| ---------------------------- | ----------: | -------------: |
| Rows                         |     250,000 |        250,000 |
| Columns                      |          27 |             17 |
| Missing values               | **124,747** |          **0** |
| Duplicate rows               |       **0** |          **0** |
| Negative transaction amounts |           — |          **0** |
| Invalid fraud flags          |           — |          **0** |
| Timestamp standardized       |          No |        **Yes** |

## Result

The final cleaned dataset contains:

**250,000 rows × 17 required transaction attributes**

with:

- **0 missing values**
- **0 duplicate rows**
- **0 negative transaction amounts**
- **0 invalid fraud flags**

---

# Stage 5 — Data Aggregation & Representation

## Objective

Individual transaction records are difficult to compare directly. Therefore, the fifth stage grouped the validated data into meaningful categories and calculated summary values.

## Aggregations Performed

### Transaction Type

Calculated:

- Transaction count
- Total transaction amount
- Average transaction amount

### Merchant Category

Calculated:

- Transaction count
- Total amount
- Average amount

### Fraud Flag

Compared:

- Fraud-flagged transactions
- Non-fraudulent transactions

### Sender State

Calculated:

- Transaction count
- Transaction amount

### Hour of Day

Calculated:

- Transaction count
- Transaction amount

### Transaction Status

Calculated:

- Successful transactions
- Failed transactions
- Percentages

## Purpose

The aggregation stage converts individual transaction records into compact numerical tables.

These tables become the foundation for:

- Statistical analysis
- Category comparisons
- Fraud analysis
- Visualization

---

# Stage 6 — Data Analysis

The sixth stage used the validated and aggregated data to perform descriptive statistical analysis and comparisons.

## Overall Transaction Statistics

| Metric                     |           Result |
| -------------------------- | ---------------: |
| Total transactions         |      **250,000** |
| Total transaction amount   | **₹327,939,009** |
| Average transaction amount |    **₹1,311.76** |
| Minimum transaction amount |          **₹10** |
| Maximum transaction amount |      **₹42,099** |

These values provide an overall numerical summary of the transaction dataset.

## Transaction Status Analysis

| Status  |       Count | Percentage |
| ------- | ----------: | ---------: |
| SUCCESS | **237,624** | **95.05%** |
| FAILED  |  **12,376** |  **4.95%** |

This shows the distribution of successful and failed transactions.

## Transaction Type Analysis

| Transaction Type |       Count | Percentage |
| ---------------- | ----------: | ---------: |
| P2P              | **112,445** | **44.98%** |
| P2M              |  **87,660** | **35.06%** |
| Bill Payment     |  **37,368** | **14.95%** |
| Recharge         |  **12,527** |  **5.01%** |

P2P represents the largest transaction category by record count in the analysed dataset.

---

# Stage 6 — Fraud Analysis

The dataset contains an existing `fraud_flag` attribute.

## Fraud Distribution

| Category       |       Count |
| -------------- | ----------: |
| Fraud-flagged  |     **480** |
| Non-fraudulent | **249,520** |

Fraud-flagged records represent approximately **0.19%** of all 250,000 records.

The project analyses the distribution of these records rather than attempting to predict fraud.

## Fraud Comparisons

Fraud-flagged records were examined across:

- Transaction type
- Merchant category
- Hour
- Device type
- Network type
- Sender state

---

# Stage 7 — Data Visualization

## Objective

The seventh stage converts the numerical results into charts so that transaction patterns and comparisons can be understood more easily.

## Visualizations

The project includes visualizations covering relevant dimensions such as:

- Transaction type
- Transaction status
- Merchant category
- Transaction amounts
- Time-based transaction activity
- Fraud distribution
- Fraud by transaction type
- Fraud by merchant category
- Fraud by hour
- Fraud by device type
- Fraud by network type
- Fraud by sender state
- Transactions by network type

## Purpose

The visualizations make it easier to identify:

- Transaction distributions
- Category differences
- Amount patterns
- Time-based activity
- Fraud distributions
- Device and network distributions
- State-level differences

The charts were created with appropriate titles, labels, and legends and were used together with the numerical analysis in the final interpretation stage.

---

# Stage 8 — Results & Interpretation

The final stage combines the statistical results and visualizations to interpret the patterns observed in the dataset.

## Key Observations

### Transaction Volume

P2P has the highest transaction count among the four transaction types in the supplied dataset.

### Transaction Status

Successful transactions account for **95.05%** of the records, while failed transactions account for **4.95%**.

### Transaction Amount

Transaction amounts range from **₹10 to ₹42,099**, with an overall average of **₹1,311.76**.

### Fraud Distribution

There are **480 fraud-flagged records**, representing approximately **0.19%** of the 250,000 transactions.

### Fraud by Transaction Type

Fraud-flagged records are distributed across:

- P2P
- P2M
- Bill Payment
- Recharge

### Fraud by Hour

The highest observed hourly fraud count in the analysis is at **hour 19**, with **43 fraud cases**.

### Fraud by Device

**Android** accounts for **364 fraud-flagged records** among the device categories.

### Fraud by Network

**4G** accounts for **282 fraud-flagged records** among the network categories.

### Fraud by Sender State

**Maharashtra** accounts for **71 fraud-flagged records** among the sender-state categories.

These are **descriptive observations from the dataset**. They do not establish that a particular hour, device, network, or state causes fraud.

---

# 10. Overall Findings

The complete analysis established the following:

- **250,000** transaction records were analysed.
- The final required transaction dataset contains **17 core attributes**.
- The noisy input initially contained **27 columns**.
- **10 unnecessary noise/context columns** were removed during cleaning.
- The noisy input contained **124,747 missing values**.
- The cleaned dataset contains **0 missing values**.
- There are **0 duplicate rows**.
- All cleaned transaction amounts are positive.
- There are **237,624 successful transactions**.
- There are **12,376 failed transactions**.
- P2P is the largest transaction category by record count.
- Total transaction amount is **₹327,939,009**.
- Average transaction amount is **₹1,311.76**.
- Transaction amounts range from **₹10 to ₹42,099**.
- There are **480 fraud-flagged records**.
- Fraud-flagged records represent approximately **0.19%** of the dataset.
- Fraud-flagged records were examined across transaction type, merchant category, time, device, network, and sender state.
- Visualizations were created to communicate the numerical findings.

---

# 11. How the Stages Connect

The project was designed as a continuous workflow rather than eight unrelated notebooks.

### Stage 1 → Stage 2

The dataset structure and initial quality were inspected before creating useful filtered transaction views.

### Stage 2 → Stage 3

After filtering, relevant transaction information and temporal attributes were extracted for further processing.

### Stage 3 → Stage 4

The extracted and available transaction information was validated for consistency, completeness, and correctness.

### Stage 4 → Stage 5

After validation and cleaning, the dataset was ready for grouping and aggregation.

### Stage 5 → Stage 6

The aggregated tables became the basis for statistical analysis and meaningful comparisons.

### Stage 6 → Stage 7

The numerical findings were converted into charts to make important patterns easier to understand.

### Stage 7 → Stage 8

The visualizations and numerical results were interpreted together to produce the final findings and conclusions.

### Complete Workflow

```text
Raw Data
   ↓
Understand
   ↓
Filter
   ↓
Extract
   ↓
Validate & Clean
   ↓
Aggregate
   ↓
Analyse
   ↓
Visualize
   ↓
Interpret
   ↓
Conclude
```

---

# 12. Project Outcome

The project demonstrates a complete practical data-analysis workflow using UPI transaction data.

Starting with a noisy dataset containing **250,000 records and 27 columns**, the project systematically:

- Loaded the data
- Inspected its structure
- Identified data-quality issues
- Filtered relevant records
- Extracted transaction and temporal information
- Removed unnecessary noise fields
- Validated important attributes
- Handled missing values
- Checked duplicates and invalid values
- Grouped and aggregated transactions
- Calculated descriptive statistics
- Analysed fraud-flagged records
- Created visualizations
- Interpreted the results

The final cleaned dataset contains **250,000 records and 17 required transaction attributes**, with **0 missing values and 0 duplicate rows**.

The analysis provides a structured understanding of transaction volume, transaction status, transaction amounts, transaction types, time-based behaviour, and the distribution of fraud-flagged records across several dimensions.

---

# 13. Limitations

1. The analysis is based only on the supplied UPI transaction dataset.
2. The dataset represents a fixed collection of records rather than a live transaction stream.
3. The `fraud_flag` is an existing dataset attribute and is analysed rather than predicted.
4. The analysis is primarily descriptive.
5. Observed associations do not establish causation.
6. Patterns identified in this dataset should not automatically be generalized to all UPI transactions.
7. The results describe the supplied dataset and depend on the quality and coverage of the underlying records.

---

# 14. Future Scope

The project can be extended by:

- Using larger and continuously updated UPI datasets.
- Developing interactive dashboards.
- Performing advanced statistical analysis.
- Applying machine-learning techniques for fraud prediction.
- Comparing transaction patterns over longer periods.
- Developing real-time transaction monitoring.
- Evaluating predictive models using suitable classification metrics.
- Adding additional transaction-level features.
- Comparing fraud patterns across multiple datasets.
- Building automated reporting and monitoring systems.

---

# 15. Repository Structure

```text
UPI_Transaction_Analysis/
│
├── README.md
├── requirements.txt
├── Team Details.md
│
├── 0. DataSet/
│   ├── Dataset(1).csv
│   └── Cleaned Dataset
│
├── 1. Data Loading & Reading/
│   ├── Stage 1 Notebook
│   ├── README
│   └── Output
│
├── 2. Data Acquisition & Filtering/
│   ├── Stage 2 Notebook
│   ├── README
│   └── Output
│
├── 3. Data Extraction/
│   ├── Stage 3 Notebook
│   ├── README
│   └── Output
│
├── 4. Data Validation & Cleaning/
│   ├── Stage 4 Notebook
│   ├── README
│   └── Cleaned Dataset
│
├── 5. Data Aggregation & Representation/
│   ├── Stage 5 Notebook
│   ├── README
│   └── Output
│
├── 6. Data Analysis/
│   ├── Stage 6 Notebook
│   ├── README
│   └── Output
│
├── 7. Data Visualization/
│   ├── Stage 7 Notebook
│   ├── README
│   └── Output
│
├── 8. Results & Interpretation/
│   ├── Stage 8 Notebook
│   ├── README
│   └── Output
│
└── PPTs/
    ├── Review-1_PPT.pptx
    └── Review-2_PPT.pptx
```

---

# 16. Execution Instructions

## Step 1 — Install Dependencies

Open a terminal in the project directory and run:

```bash
pip install -r requirements.txt
```

## Step 2 — Open the Notebooks

The notebooks can be executed using:

- Google Colab
- Jupyter Notebook
- VS Code

## Step 3 — Verify Dataset Location

Make sure the required dataset is available in the repository's dataset folder.

## Step 4 — Execute the Project in Order

Run the stages in the following order:

```text
1 → 2 → 3 → 4 → 5 → 6 → 7 → 8
```

This maintains the intended dependency between the stages.

---

# 17. Team Details

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

# 18. Individual Responsibilities

### K. Sri Sai Surya Manikanta

- Data Loading & Reading
- Data Acquisition & Filtering

### A. Divija Naga Sai Teja Sri

- Data Extraction
- Data Validation & Cleaning

### Sana Jaswanthi

- Data Aggregation & Representation
- Data Analysis

### T. Manoj Reddy

- Data Visualization
- Results & Interpretation

All team members are responsible for understanding the complete project workflow, including data preprocessing, Pandas operations, analysis, visualization, results, and conclusions.

---

# 19. Final Conclusion

The project successfully demonstrates a complete data-analysis pipeline using UPI transaction data.

The workflow begins with raw and noisy transaction records and progresses systematically through:

```text
Loading
   ↓
Inspection
   ↓
Filtering
   ↓
Extraction
   ↓
Validation & Cleaning
   ↓
Aggregation
   ↓
Statistical Analysis
   ↓
Visualization
   ↓
Interpretation
```

The project analysed **250,000 transaction records**, transformed the noisy **27-column input into a validated 17-column transaction dataset**, resolved the identified missing-value issues, and produced structured statistical summaries and visualizations.

The final results provide descriptive insights into **transaction volume, transaction status, transaction amounts, transaction types, temporal behaviour, and fraud-flagged transaction distributions**.

The project therefore demonstrates how Python, Pandas, NumPy, and Matplotlib can be used to transform raw transaction data into an organized, validated, analysed, and visually interpretable data-analysis project.
