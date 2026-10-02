# Stage 4 — Data Validation & Cleaning

## Objective

The objective of this stage is to validate the noisy UPI transaction dataset and transform it into a clean, consistent dataset suitable for further aggregation, analysis, and visualization.

The validation focuses on identifying and handling missing values, duplicate records, invalid transaction values, data-type issues, inconsistent fields, and additional noise introduced into the dataset.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas
- NumPy

## Input Dataset

The stage uses the noisy UPI transaction dataset:

`Dataset(1).csv`

The noisy dataset contains **250,000 rows and 27 columns**.

After validation and cleaning, the output dataset contains **250,000 rows and 17 required transaction columns**.

## Noise / Dataset Modifications

The noisy dataset contains 10 additional device, session, application, network, and contextual attributes that are not required for the core transaction analysis.

These additional fields were removed during cleaning:

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

The required **17 core transaction columns** were retained in the cleaned dataset.

The `time_stamp` field was also converted and standardized into a consistent datetime representation for subsequent time-based analysis.

## Operations Performed

1. Loaded the noisy dataset using `pandas.read_csv()`.
2. Validated the original dataset dimensions.
3. Compared the available fields with the required transaction schema.
4. Identified the additional noise/device/session/context columns.
5. Removed the 10 unnecessary columns.
6. Checked the data types of important fields.
7. Converted the `time_stamp` field to datetime format.
8. Checked missing values before cleaning.
9. Handled the identified missing values in the required transaction fields.
10. Checked for duplicate rows.
11. Checked transaction amounts for negative or invalid values.
12. Checked `Fraud Flag` values for invalid entries.
13. Validated transaction types.
14. Validated transaction statuses.
15. Performed final validation of the cleaned dataset.
16. Displayed sample records from the cleaned dataset.

## Validation Results

| Validation Check             | Noisy Dataset | Cleaned Dataset |
| ---------------------------- | ------------: | --------------: |
| Rows                         |   **250,000** |     **250,000** |
| Columns                      |        **27** |          **17** |
| Missing values               |   **124,747** |           **0** |
| Duplicate rows               |         **0** |           **0** |
| Negative transaction amounts |             — |           **0** |
| Invalid fraud flags          |             — |           **0** |
| Timestamp standardized       |            No |         **Yes** |
| Noise columns                |        **10** |           **0** |

The **124,747 missing values** represent the missing data identified in the noisy input before cleaning. After the validation and cleaning operations, the required transaction dataset contains **0 missing values**.

## Categorical Values Identified

### Transaction Types

- Bill Payment
- P2M
- P2P
- Recharge

### Transaction Statuses

- FAILED
- SUCCESS

## Removed Noise Columns

| Column                    | Category           |
| ------------------------- | ------------------ |
| `battery level %`         | Device             |
| `App Version`             | Application        |
| `device storage free gb`  | Device             |
| `screen brightness %`     | Device             |
| `Device Language`         | Device / Context   |
| `GPS accuracy m`          | Location / Context |
| `nearby wifi count`       | Network / Context  |
| `session duration sec`    | Session            |
| `notifications last hour` | Session / Context  |
| `merchant distance km`    | Location / Context |

## Cleaned Dataset

The final cleaned dataset retains the 17 required transaction attributes:

1. `Transaction ID`
2. `time_stamp`
3. `Transaction_Type`
4. `merchant category`
5. `amount_INR`
6. `Transaction Status`
7. `sender_agegroup`
8. `receiver_age_group`
9. `Sender State`
10. `sender bank`
11. `Receiver_Bank`
12. `device type`
13. `Network Type`
14. `Fraud Flag`
15. `hour of day`
16. `Day Of Week`
17. `is weekend`

## Final Data Quality Status

After cleaning and validation:

- **250,000 records retained**
- **17 required columns retained**
- **124,747 raw missing values resolved**
- **0 missing values remaining**
- **0 duplicate rows**
- **0 negative transaction amounts**
- **0 invalid fraud-flag values**
- **Timestamp standardized**
- **10 unnecessary noise columns removed**
- Transaction types verified
- Transaction statuses verified

## Conclusion

The noisy UPI transaction dataset was successfully validated and transformed into the required clean transaction dataset.

The original dataset contained **250,000 rows and 27 columns**, including **10 additional device, application, session, network, and contextual fields**. These unnecessary fields were removed while retaining the **17 core transaction attributes** required for the project.

The initial validation identified **124,747 missing values** in the noisy dataset. After the cleaning process, the final dataset contains **0 missing values and 0 duplicate rows**. Transaction amounts, fraud flags, transaction types, transaction statuses, and timestamp information were also validated.

The resulting **250,000 × 17 cleaned dataset** provides a consistent and validated foundation for the next stages of **data aggregation, statistical analysis, visualization, and interpretation**.
