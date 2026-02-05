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

## How many customers were there for each approach?
6 weeks ago, we launched a new product, a new line of office stationery. Our main focus is selling this new product. Since the way consumers buy new product is changing our sales tactics have to change too, and the executive team want to know the differences of the sales using 3 different sales strategies:
- **email:** Customers in this group received an email when the product line was launched, and a further email three weeks later. This required very little work for the team.
- **call:** Customers in this group were called by a member of the sales team. On average members of the team were on the phone for around thirty minutes per customer.
- **email and call:** Customers in this group were first sent the product information email, then called a week later by the sales team to talk about their needs and how this new product may support their work. The email required little work from the team, the call was around ten minutes per customer.
<img width="600" height="425" alt="image" src="https://github.com/user-attachments/assets/b8901b75-995b-4246-b439-5cd05d8acbe5" />

Based on the sales records from the last 6 weeks, the number of successful sales by call was almost twice as much than combination of email and call strategy. The successful sales in the email group was almost three times more than in the combination of email and call strategy.

## What does the spread of the revenue look like overall? And for each method?
Overall distribution of the Revenue by Sale according to number of customers shows 5 peaks. Majority of revenue per sale was under 120 USD.
<img width="600" height="425" alt="image" src="https://github.com/user-attachments/assets/7974d59d-36f0-4eca-beed-2901cae40575" />

