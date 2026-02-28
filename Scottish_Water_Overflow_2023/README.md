# Data Cleaning in Python
## Introduction
This technical report describes the preparation and the cleaning process of the 2023 overflow events dataset (‘scottishWaterData2023.csv’). The dataset contains the reported wastewater overflow events submitted by Scottish Water to Scottish Environment Protection Agency.
The aim of this task was to prepare the raw CSV file for structured reliable time-based and categorical analysis. The cleaning process addresses the following data-related issues: correcting file-level issues, standardising column names, converting datatypes, and handling missing or invalid values, and date-time formatting issues.
All cleaning steps were done in Python and are fully reproducible using the attached files.

Attached files:
-	Raw dataset: scottishWaterData2023.csv
-	Cleaned dataset: scottish_water2023_clean.csv
-	Python notebook: Overflow2023.ipynb

## Data Loading and Initial Challenges
### 1. Importing Libraries and Dataset
The cleaning process was performed in Python using the pandas library.
The original CSV file name contained an error:
•	scottishWaterData2023 .csv (a space before .csv).
This was corrected to scottishWaterData2023.csv prior to upload to Google Colab to prevent file-loading errors.
The dataset was initially imported using pd.read_csv() and stored as a pandas DataFrame.

### 2.Header Formatting Issue
Exploratory Data Analysis (EDA) using .head() revealed that the dataset contained two header rows, causing column names to be misaligned.

**Cleaning decision:**
The file was reloaded using:
pd.read_csv("scottishWaterData2023.csv", skiprows=1)
This ensured that the correct header row was used and that all columns aligned properly.

### 3. Exploratory Data Analysis (EDA)
After reloading:
- The dataset contained 10,050 rows and 12 columns
-	11 columns were object datatype, and only one column (Ellipse No.) was int64 datatype.

This confirmed that systematic datatype cleaning would be required before analysis.

### 4. Column Name Standardisation
To improve readability, consistency, and suitability for Python analysis, all column names were standardised using snake_case.
A dictionary mapping old column names to new ones was created and applied using:
overflow2023_df.rename(columns=newcols, inplace=True)

This step is essential for:
-	Avoiding syntax errors
-	Improving reproducibility
-	Making the dataset easier to interpret

### 5. Assessment of Duplicate Records and Missing Values
Duplicate records were checked using .duplicated() to ensure record uniqueness. No duplicates were detected.

Missing values were assessed using:
-	overflow2023_df.isna().sum()
Key findings:
-	network_wwtw: 4 missing values
-	overflow_start_datetime: 2 missing values
-	comments: 8,392 missing values

Each affected column was assessed individually to determine the most appropriate action.

## 6. Column-by-Column Data Cleaning
### 1. Identifier Columns
Columns such as:
-	licence_number
-	asset_id
-	asset_name
-	sw_meas_point_desc_evt
were converted from object datatype to string datatype.

This ensures identifiers are not misinterpreted as numerical values and remain stable during grouping and filtering operations.

### 2. Geographical Area (area_direction)
This column contained inconsistent capitalisation (e.g. “South”, “WEST”, “East”, “North”, “NORTH”, “SOUTH”, “EAST”).
Cleaning steps:
-	Converted all values to lowercase
-	Reduced categories to four valid values: north, south, east, west
-	Converted datatype from object to category for memory efficiency and grouping

This supports spatial comparison of overflow patterns.

### 3. Network Type (network_wwtw)
•	Contained only two valid categories
•	Included 4 missing values
**Cleaning decision:**

Rows with missing values were dropped due to their small number and limited analytical value. The column was then converted to category.

### 4. Number of Days with Data
The number_days_with_data column initially contained invalid values, including:
-	"Not Required"
-	"Not required"
-	Blank spaces
-	An implausible numeric value (435456)
**Cleaning decision:**

These records were filtered out, as they would distort any time-based or completeness analysis.
After filtering, the column was converted from object to int32.

## Date and Time Variables
### 1. Identifying Invalid Records
Three columns were analysed together:
-	overflow_start_datetime
-	overflow_end_datetime
-	overflow_duration_hms

Some records contained the strings "No Data" or "No Events" instead of timestamps.
Cross-checking confirmed that these records lacked valid data across all three fields.
**Cleaning decision:**

These rows were removed from the dataset.

### 2. Datatype Conversion
-	Start and end times were converted to datetime64[ns]
-	Durations were converted to timedelta64[ns]
-	Conversion errors were coerced to NaT, then removed
This enabled:
-	Time-series analysis
-	Calculation of event durations
-	Seasonal trend analysis

### 3. Date Range Validation
To ensure the dataset truly reflected 2023 events, start and end times were filtered to fall between:
-	2023-01-01 and 2023-12-31

This removed any out-of-scope or erroneous records.

### 4. New Variable: Month Extraction
A new variable, month_from_end, was derived from overflow_end_datetime.
This supports:
-	Monthly trend analysis
-	Seasonal comparisons
-	Visualisation of overflow frequency over time

## Comments Column
The comments column:
-	Contained 13 unique values
-	Had over 8,000 missing entries

Because comments are optional and qualitative, the column was kept unchanged for contextual reference rather than quantitative analysis.

## Final Cleaned Dataset Summary
After all cleaning steps, the final dataset contained:
-	9,556 rows
-	13 well-defined columns
-	No invalid dates or durations
-	Appropriate datatypes for all variables
Key datatypes included:
-	datetime64[ns] for timestamps
-	timedelta64[ns] for durations
-	category for grouping variables
-	Numeric types for counts and identifiers

## Conclusion
This data-cleaning exercise demonstrates how Python and pandas can be used to prepare real-world environmental datasets for robust analysis. Each cleaning decision was guided by the intended analytical goals, including temporal trends, spatial comparison, and regulatory insight.

**The resulting dataset is suitable for:**
-	Monitoring overflow behaviour
-	Identifying high-risk periods or regions
-	Supporting evidence-based water management and compliance reporting.

