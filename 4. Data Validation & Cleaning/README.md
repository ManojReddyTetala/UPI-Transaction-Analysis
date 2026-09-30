# Stage 4 — Data Validation & Cleaning

## Objective

The objective of this stage is to validate the dataset and identify or handle missing values, duplicate records, invalid values, data type issues, and additional noise introduced into the dataset.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas

## Input Dataset

The stage uses the noisy UPI transaction dataset:

`upi_transactions_2024_with_noise(1).csv`

The noisy dataset contains **250,000 rows and 27 columns**. The cleaned output contains **250,000 rows and 17 columns**.

## Noise / Dataset Modifications

The noisy dataset was modified by adding 10 additional device, session, and contextual attributes that were not part of the required transaction dataset. These fields were removed during cleaning:

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

The core 17 transaction columns were retained in the cleaned dataset.

The `timestamp` field was also standardized in the cleaned output to a consistent datetime representation (`YYYY-MM-DD HH:MM:SS`).

## Operations Performed

1. Validated the original noisy dataset dimensions.
2. Compared the noisy dataset with the required transaction schema.
3. Identified the 10 additional noise/device/session/context columns.
4. Removed the additional noise columns from the dataset.
5. Checked the data types of important columns.
6. Converted and standardized the `timestamp` column to datetime format.
7. Checked for missing values.
8. Checked for duplicate rows and removed them if present.
9. Checked for negative transaction amounts.
10. Checked for invalid `fraud_flag` values.
11. Validated transaction types and transaction statuses.
12. Performed final validation of the cleaned dataset.
13. Displayed a sample cleaned record.

## Validation Results

- Rows: 250,000
- Columns before cleaning: 27
- Columns after cleaning: 17
- Noise columns removed: 10
- Missing values: 0
- Duplicate rows: 0
- Negative amounts: 0
- Invalid fraud flags: 0
- Timestamp standardized: Yes

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

| Column | Category |
|---|---|
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

## Conclusion

The noisy dataset was successfully transformed into the required cleaned transaction dataset. The 10 additional device, session, network, and contextual noise columns were removed, while the 17 core transaction columns were retained. The cleaned dataset contains 250,000 rows with no missing values, duplicate rows, negative transaction amounts, or invalid fraud flag values. The timestamp was standardized to a consistent datetime representation, and the validated dataset is ready for the next stage.
