# Stage 3 — Data Extraction

## Objective

The objective of this stage is to extract relevant information from the UPI transaction dataset for further analysis.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas

## Input Dataset

`upi_transactions_2024.csv`

The dataset contains 250,000 transactions and 17 original columns.

## Operations Performed

1. Loaded the dataset using Pandas.
2. Converted the `timestamp` column into datetime format.
3. Extracted the date from the timestamp.
4. Extracted the month from the timestamp.
5. Extracted the year from the timestamp.
6. Selected the required transaction-related columns for further analysis.
7. Displayed sample extracted transactions in vertical format.

## Extracted Information

The extraction includes:

- transaction id
- timestamp
- date
- month
- year
- transaction type
- merchant category
- amount
- transaction status
- fraud flag
- sender state
- device type
- network type
- hour of day
- day of week
- weekend indicator

## Results

- Original rows: 250,000
- Original columns: 17
- Extracted rows: 250,000
- Extracted columns: 16
- Timestamp converted to datetime: Yes
- Date extracted: Yes
- Month extracted: Yes
- Year extracted: Yes

## Output

The extracted dataset contains the required transaction, time, fraud, location, device, network, and status information needed for the subsequent stages of the project.

## Conclusion

The required fields were successfully extracted from the UPI transaction dataset. Date, month, and year information were derived from the timestamp, and the selected dataset is ready for the next stage of the project.
