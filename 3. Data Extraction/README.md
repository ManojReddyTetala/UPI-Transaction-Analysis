# Stage 3 — Data Extraction

## Objective

The objective of this stage is to extract relevant information from the UPI transaction dataset for further analysis.

## Platform and Tools

- Google Colab
- VS Code
- Python
- Pandas

## Input Dataset

`Dataset(1).csv`

The dataset contains **250,000 transactions and 27 columns**.

## Operations Performed

1. Loaded the dataset using Pandas.
2. Converted the `time_stamp` column into datetime format.
3. Extracted the date from the timestamp.
4. Extracted the month from the timestamp.
5. Extracted the year from the timestamp.
6. Extracted the week number from the timestamp.
7. Extracted the day of the month from the timestamp.
8. Extracted the day name from the timestamp.
9. Selected the required transaction-related columns for further analysis.
10. Combined the selected transaction attributes with the derived temporal attributes.
11. Displayed the extracted dataset structure and sample transactions.

## Extracted Information

### Transaction Information

- transaction id
- timestamp
- transaction type
- merchant category
- amount (INR)
- transaction status
- sender age group
- receiver age group
- sender state
- sender bank
- receiver bank
- device type
- network type
- fraud flag
- hour of day
- day of week
- weekend indicator

### Derived Temporal Information

- date
- month
- year
- week number
- day of month
- day name

## Results

- Original rows: **250,000**
- Original columns: **27**
- Transaction attributes selected: **17**
- Derived temporal attributes: **6**
- Extracted rows: **250,000**
- Final extracted attributes: **23**
- Timestamp converted to datetime: **Yes**
- Date extracted: **Yes**
- Month extracted: **Yes**
- Year extracted: **Yes**
- Week number extracted: **Yes**
- Day of month extracted: **Yes**
- Day name extracted: **Yes**

## Output

The extracted dataset contains the required transaction, time, fraud, location, device, network, and status information along with additional temporal attributes derived from the timestamp.

The extracted temporal fields make it possible to perform further analysis based on **date, month, year, week, day, and day of the week** in the subsequent stages of the project.

## Conclusion

The required fields were successfully extracted from the UPI transaction dataset. The timestamp was converted into datetime format, and useful temporal information including **date, month, year, week number, day of month, and day name** was derived.

The selected transaction attributes and derived temporal information provide the required foundation for the subsequent **data validation, cleaning, aggregation, analysis, and visualization stages**.
