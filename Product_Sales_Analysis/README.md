# Product Sales Analysis

## Overview


## Aim
- How many customers were there for each approach?
- What does the spread of the revenue look like overall? And for each method?
- Was there any difference in revenue over time for each of the methods?
- Based on the data, which method would you recommend we continue to use? Some of these methods take more time from the team so they may not be the best for us to use if the results are similar.

## Data Validation:
### Describe validation and cleaning steps for every column in the data
The dataset contains 15000 rows and 8 columns before cleaning and validataion. I have validated all the columns against the criteria in the dataset table:

- **week:** Data type is integer. There are no missing values in this column. There are 6 unique values: '1', '2', '3', '4', '5', '6'. These numbers show the weeks since the product was launched. NO changes were made.
- **sales_method:** Data type is object. There are no missing values in this column. There are 3 categories in the original dataset, but inconsistent typing was found in the categories: 'Email', 'Call', 'Email + Call', 'em + call', 'email'. Data cleaning was done to correct inconsistent typing. Therefore, there are 3 categories in the final modified database: 'email', 'call' and 'email and call'.
- **customer_id:** Data type is object. There are no missing values in this column. These numbers are individual ID-s. No changes were made.
- **nb_sold:** Data type is integer. There are no missing values in this column. There are 10 unique values: '7', '8', '9', '10', '11', '12', '13', '14', '15', '16'. The unique values are the number of new products sold. No changes were made to this column.
- **revenue:** Data type is float. The values of this column ranged from 32.54 to 238.32. This column had 1074 (7.16%) missing values. I validated that the missing values come from all sales_method in equal distribution. Therefore, the rows with missing values for revenue were dropped.
- **years_as_customer:** Data type is integer. There are no missing values in this column. There are 42 unique values in this column and values range from 0 to 63 in the original dataframe. This column shows the number of years customer has been buying from this company. The company was founded in 1984, therefore the company is 41 years old in 2025. But 2 entries are larger than 41, we have 1 entry with the value of '47' and 1 entry with the value of '63'. Since these two values are errors, these values are dropped. After cleaning, there are 40 unique values in the final modified datframe and values ranges from 0 to 39.
- **nb_site_visits:** Data type is integer. There are no missing values in this column. There are 27 unique values in this column and values range from 12 to 41 in the original dataframe. No changes were made. But, in the modified dataframe, where missing values and impossible values were dropped, there are only 26 unique values range from 12 to 37.
- **state:** Data type is object. There are no missing values in this column. There are 50 state names. No changes were made.


After the data validation, the dataset contains 13924 rows and 8 columns without missing values.
