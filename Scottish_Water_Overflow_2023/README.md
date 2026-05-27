# Scottish Water Overflow Events (2023) – Data Cleaning in Python

This project demonstrates a **reproducible, real-world data-cleaning pipeline** applied to reported wastewater overflow events submitted by Scottish Water to the Scottish Environment Protection Agency (SEPA).

The goal was to transform a raw, inconsistent CSV file into a **clean, analysis-ready dataset** suitable for time-based, categorical, and regulatory analysis.

## Project Overview

The original dataset contained multiple real-world data quality issues, including:
- malformed CSV structure (duplicate header rows)
- inconsistent categorical values
- mixed and incorrect datatypes
- invalid timestamps and sentinel strings (e.g. *"No Data"*, *"No Events"*)
- implausible numeric values
- missing or incomplete records

All cleaning steps were performed in **Python using pandas** and are fully reproducible.

## Key Data Cleaning Steps

### 1. Data Loading & File-Level Issues
- Corrected filename formatting issues that prevented successful loading
- Handled duplicated header rows through controlled CSV import parameters

### 2. Schema & Column Standardisation
- Standardised all column names to `snake_case`
- Improved readability, reproducibility, and downstream usability

### 3. Data Quality Assessment
- Checked for duplicate records (none detected)
- Systematically assessed missing values column by column
- Evaluated whether missing or invalid records should be retained or removed based on analytical relevance

### 4. Categorical Data Cleaning
- Normalised inconsistent categorical values (e.g. geographical regions)
- Reduced categories to valid, interpretable levels
- Converted appropriate columns to `category` dtype for efficiency and grouping

### 5. Numeric Validation
- Removed invalid and implausible numeric entries that would distort analysis
- Enforced appropriate numeric datatypes

### 6. Date & Time Processing
- Identified and removed records with invalid or placeholder timestamps
- Converted timestamps to `datetime64[ns]` and durations to `timedelta64[ns]`
- Validated that all events fell within the 2023 reporting period

### 7. Feature Engineering
- Derived a new monthly variable from event end times to support seasonal and trend analysis

## Final Dataset

After cleaning, the final dataset contains:
- **9,556 rows**
- **13 well-defined columns**
- Validated timestamps and durations
- Appropriate datatypes for all variables (`datetime`, `timedelta`, `category`, numeric)

The cleaned data is suitable for:
- time-series analysis of overflow events
- seasonal trend detection
- regional comparisons
- regulatory and compliance reporting

## Files in the Repository
- raw dataset - scottishWaterData2023.csv
- Jupyter notebook - Overflow2023.ipynb
- clean dataset - scottish_Water_2023_clean.csv
