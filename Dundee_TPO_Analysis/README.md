# Tree Preservation Orders (TPOs) in Dundee - Automated Data Analysis & Visualisation Pipeline

## Background Information

For this analysis I used the **Tree Preservation Order (TPO) data for Dundee**. TPOs are legal measures, which are used to protect trees that are considered important for environmental or community reasons.

This project shows how Python can be used to deliver reliable insights that support real-world decision-making.

## Aim

The main aim of the project is to understand:

- how tree protection has changed over time and
- how it varies across different areas.

This project demonstrates my shift from manual, exploratory data analysis - data cleaning, validation, exploratory analysis, and visual communication - toward **reproducible and scalable data workflows**.

## Data

The raw dataset, TPODundeeData.csv, contains records of Tree Preservation Orders issued in Dundee between 1982 and 2023.

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

### Trends Over Time

- TPO activity peaks between **2001 and 2014**

<img width="760" height="540" alt="image" src="https://github.com/jremenyi1/Python_Projects/blob/main/Dundee_TPO_Analysis/jpeg_files/TPO_trend_Original%20data.jpg" />

- After 2014, new TPOs become much less frequent
- Earlier periods of higher activity are also visible in the 1980s and early 1990s

<img width="760" height="540" alt="image" src="https://github.com/jremenyi1/Python_Projects/blob/main/Dundee_TPO_Analysis/jpeg_files/TPO_trend_Filtered%20data.jpg" />

### Area-Level Differences

- TPOs are unevenly distributed across Dundee

<img width="760" height="540" alt="image" src="https://github.com/jremenyi1/Python_Projects/blob/main/Dundee_TPO_Analysis/jpeg_files/TPO_area_bar_Original%20Data.jpg" />

- A small number of areas account for most protections
- Broad area labels dominate the dataset, which affects precision

<img width="760" height="540" alt="image" src="https://github.com/jremenyi1/Python_Projects/blob/main/Dundee_TPO_Analysis/jpeg_files/TPO_area_bar_Filtered%20Data.jpg?raw=true" />

### Timing Differences by Area

- Some areas show protection activity over many years

<img width="760" height="540" alt="image" src="https://github.com/jremenyi1/Python_Projects/blob/main/Dundee_TPO_Analysis/jpeg_files/TPO_are_box_Original%20Data.jpg?raw=true" />

- Others have TPOs concentrated in shorter time periods
- This may reflect differences in local development pressure or planning focus

<img width="760" height="540" alt="image" src="https://github.com/jremenyi1/Python_Projects/blob/main/Dundee_TPO_Analysis/jpeg_files/TPO_are_box_Filtered%20Data.jpg?raw=true" />

## Limitations

- Area names are inconsistent and sometimes too broad
- Records labelled only as “Dundee” may cover multiple locations
- Address-based grouping is less accurate than spatial analysis
- GIS tools would provide more precise geographic insights
- Understanding these limits is important when interpreting the results.

## Next Steps

- Improve area classification using full address fields
- Add map-based analysis
- Extend the workflow to support regular data updates

## Files in the Repository

- raw data - TPODundeeData.csv
- cleaned data - cleanedTPODataDundee.csv
- jupyter notebook - Dundee_TPO_Visualisation_Automation.ipynb
- output files 
   - TPO_trends_Original data.pdf and TPO_trends_Original data.jpg
   - TPO_trends_Filtered data.pdf and TPO_trends_Filtered data.jpg
   - TPO_area_bar_Original Data.pdf and TPO_area_bar_Original Data.jpg
   - TPO_area_bar_Filtered Data.pdf and TPO_area_bar_Filtered Data.jpg
   - TPO_area_box_Original Data.pdf and TPO_area_box_Original Data.jpg
   - TPO_area_box_Filtered Data.pdf and TPO_area_box_Filtered Data.jpg
