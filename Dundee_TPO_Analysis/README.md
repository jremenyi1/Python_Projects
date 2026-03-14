# Tree Preservation Orders (TPOs) in Dundee - Automated Data Analysis & Visualisation Pipeline

## Background Information

For this analysis I used the **Tree Preservation Order (TPO) data for Dundee**. TPOs are legal measures, which are used to protect trees that are considered important for environmental or community reasons.

## Aim

The main aim of the project to understand:

- how tree protection has changed over time and
- how it varies across different areas.

This project demonstrates my shift from manual, exploratory data analysis - data cleaning, validation, exploratory analysis, and visual communication - toward **reproducible and scalable data workflows**.

## Data

The dataset contains records of Tree Preservation Orders issued in Dundee between 1982 and 2023.

- Time range: 1982–2023
- One row per TPO
- Key fields: address information, reference number, unique ID

The dataset was designed for spatial use, but this analysis **focuses on table-based insights**.

## Tools Used

- **pandas** – data cleaning and analysis
- **numpy** – logic and numeric checks
- **matplotlib & seaborn** – charts and visualisation
- **logging** – tracking each step of the analysis

## Analysis Process

### 1. Data Cleaning

The dataset required cleaning before analysis:

- removed missing and duplicate records
- standardised text fields for consistent grouping
- converted columns to correct data types
- extracted the year of protection from reference numbers and validated it

The cleaned dataset is saved as:

 - **cleanedTPODataDundee.csv**

This ensures the analysis is reproducible and easy to update.

### 2. Exploratory Data Analysis

The analysis focuses on two main questions:

- **How has TPO activity changed over time?**

- **How is TPO activity distributed across areas?**

To answer these, the project generates:

- line charts showing TPOs issued per year
- bar charts comparing counts by area
- boxplots showing how protection timing differs between areas

Charts are automatically saved as **PDF** and **JPEG** files.

## Key Insights

## Trends Over Time

- TPO activity peaks between 2001 and 2014
- After 2014, new TPOs become much less frequent
- Earlier periods of higher activity are also visible in the 1980s and early 1990s



## Files in the Repository
