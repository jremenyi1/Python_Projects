# Dundee Housing Sites Dataset - Manual vs Automated Data Cleaning with Python

## Background Information

The dataset contains information on housing development sites in Dundee, including tenure types, site capacity, planning status, and projected housing delivery between 2024 and 2034.

## Aim

This project compares **manual data cleaning** with a **fully automated data-cleaning** workflow using the same real-world housing dataset.

The aim is to demonstrate how automation improves consistency, reproducibility, and scalability in data analysis while producing the same analytical insights.

## Data

The raw data, housingSites.csv dataset, includes 183 housing sites and 40 columns describing:

- Site address and developer
- Tenure type
- Site status (e.g. Under Construction)
- Site capacity
- Projected housing builds (2024–20234)

This type of data is commonly used for housing supply forecasting, planning analysis, and policy support.

## Manual Data Cleaning

**Notebook: HousingSites_Manual_DataCleaning.ipynb**

### Approach

The manual workflow focuses on exploratory data cleaning and analysis:
- Selection of analytically relevant columns
- Cleaning and standardisation of text fields (addresses, developers)
- Enforcement of appropriate data types
- Calculation of site capacity and projected build metrics
- Exploration of relationships between tenure type, site status, and housing delivery

### Key Observations

- Eight tenure types were identified
- Private tenure sites dominate total site capacity
- Registered Social Landlords contribute a significant proportion
- Sites under construction account for most near-term housing delivery
- A total of 1,412 projected housing units are expected between 2024 and 2027

### Limitations

While effective for exploration, this approach:

- Requires repeated manual effort
- Is harder to reproduce
- Does not scale well to larger or frequently updated datasets

## Automated Data Cleaning

**Notebook: HousingSites_Automation_DataCleaning.ipynb**

### Approach

The automated workflow uses reusable Python functions and logging to execute the entire pipeline from start to finish:

- Data loading and column filtering
- Text standardisation using consistent rules
- Conversion of tenure type and site status to categorical data
- Conversion of numeric fields to appropriate numeric types
- Automated calculation of key housing metrics
- Generation of clean datasets and summary outputs

All steps are executed via a single main() function.

## Outputs

- cleaned datasets
  - housing_sites_manual_cleaned.csv
  - housing_sites_automation_cleaned.csv
-single_metrics.csv – summary statistics
- cum_capacity_by_tenure.csv – site capacity by tenure type

This approach ensures consistent results with minimal manual intervention.


## Key Takeaway

This project illustrates why automation is essential for reliable data cleaning in real-world analysis.
Manual workflows support exploration, but automated pipelines provide the consistency and scalability required for professional data work.

## Files in the Repository
- raw data - housingSites.csv
- cleaned datasets
  - housing_sites_manual_cleaned.csv
  - housing_sites_automation_cleaned.csv
- additional output files from automated workflow
  - single_metrics.csv – summary statistics
  - cum_capacity_by_tenure.csv – site capacity by tenure type
- jupyter notebooks
  - HousingSites_Manual_DataCleaning.ipynb
  - HousingSites_Automation_DataCleaning.ipynb

