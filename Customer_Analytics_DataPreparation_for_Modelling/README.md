# Customer Analytics: Preparing Data for Modeling

## Backround Information
In this project, my main focus was to store the data much more efficiently, so you can create a model that predicts if course enrollees are looking for a job. I converted data types, created ordered categories, and filtered ordered categorical data to prepare it for modeling.

## Data


## Aim
The Head Data Scientist at Training Data Ltd. has asked you to create a DataFrame called ds_jobs_transformed that stores the data in customer_train.csv much more efficiently. Specifically, they have set the following requirements:

- Columns containing categories with only two factors must be stored as Booleans (bool).
- Columns containing integers only must be stored as 32-bit integers (int32).
- Columns containing floats must be stored as 16-bit floats (float16).
- Columns containing nominal categorical data must be stored as the category data type.
- Columns containing ordinal categorical data must be stored as ordered categories, and not mapped to numerical values, with an order that reflects the natural order of the column.
- The DataFrame should be filtered to only contain students with 10 or more years of experience at companies with at least 1000 employees, as their recruiter base is suited to more experienced professionals at enterprise companies.

If you call .info() or .memory_usage() methods on ds_jobs and ds_jobs_transformed after you've preprocessed it, you should notice a substantial decrease in memory usage.

## Result
The memory usage substatially decreased from 2.0+MB to 69.1kB after preprocessing the data for modeling.

## Files in the Repository
- Jupyter Notebook - notebook.ipynb
- raw data - customer_train.csv
- png image file - hr-image-small.png
