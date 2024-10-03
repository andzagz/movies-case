# movies-case
# ETL Project: Movie Data Analysis

This project aims to perform an ETL (Extraction, Transformation, and Load) process to collect, process, and analyze data related to movies.

## Project Structure

The project consists of a Python script utilizing the `pandas` and `requests` libraries to perform the following stages:

1. **Extraction**: Data collection from an API endpoint that provides information on movies.
2. **Transformation**: Processing the extracted data.
   2.1 The core logic relies on regular expressions (REGEX) to transform the data from the available endpoints.
       Key transformations include cleaning the "Budget" and "Year" fields according to their specific characteristics.
       2.1.1 The "Budget" field presents various challenges, such as differing currency symbols, units, missing values, ranges, and formats.
       2.1.1.1 The first function, `convert_million_to_number`, is designed to identify and standardize string values representing different units into a common number or unit.
       2.1.1.2 The second function, `extract_budget`, identifies the different currencies and ranges, applying a uniform pattern.
       2.1.1.3 The third function, `convert_to_usd`, converts all identified currencies into USD.
3. **Load**: Exporting the processed data to a CSV file.

## Usage

1. Clone this repository or download the Python script.
2. Run the script in a Python environment.

## Features

- Collects movie budget data from an API.
- Processes and cleans the collected data.

### Example Usage:
#### Functions Created:
- `extract_and_transform_budget(budget_df)`

**Purpose**: Extract and transform the budget values in the "Budget1" column and create the columns "Budget2," "Currency," "Value," and "USD Value."
**Example Application**:
```python
extract_and_transform_budget(df)
