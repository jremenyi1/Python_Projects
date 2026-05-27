# Predictive Modeling for Agriculture


## Background

Machine learning can support decision-making in agriculture by helping farmers
select crops that are well suited to their soil conditions. However, measuring
multiple soil properties can be expensive and time-consuming, forcing farmers 
to prioritise which metrics to collect.

In this project, I analyse soil measurement data to determine which
**single soil feature** provides the strongest predictive signal for selecting
the optimal crop. The task is framed as a **multi-class classification** and 
**feature selection** problem using a simple baseline machine learning model.

---

## Objective

- Build a multi-class classification model to predict crop type
- Evaluate each soil feature **individually** under budget constraints
- Identify the single soil measurement that produces the **highest predictive accuracy**

The final result is stored as a dictionary called `best_predictive_feature`, containing:

- the best predictive feature name as the key
- the corresponding accuracy score as the value

---

## Data

**raw data** – `soil_measures.csv`

The dataset contains soil measurements from different fields and the
corresponding optimal crop for each field.

**Features:**

- `N` – Nitrogen content ratio
- `P` – Phosphorous content ratio
- `K` – Potassium content ratio
- `ph` – Soil pH value

**Target variable:**

- `crop` – Categorical crop type (22 classes)

---

## Approach

- Framed the task as a **multi-class classification** problem
- Used **Logistic Regression** as a baseline model
- Split data into training and test sets using **stratified sampling**
- Trained and evaluated models using **one feature at a time**
- Compared model performance using **accuracy**

---

## Key Result

Potassium (`K`) showed the strongest individual predictive signal.

```python
best_predictive_feature = {'K': 0.33}
```

---

## Skills Demonstrated

- Python (pandas, scikit-learn)
- Train/test splitting and stratification
- Multi-class classification
- Model evaluation (accuracy, confusion matrix, classification report)
- Feature selection fundamentals

---

## Files in the Repository

- **project overview** - `README.md`
- **Jupyter Notebook** – `notebook.ipynb`
- **raw data** – `soil_measures.csv`
- **image** - `farmer_in_a_field.jpg`

---

## Notes

This project was completed as part of a learning exercise and represents
my **first machine learning project**. The focus is on understanding core
machine learning concepts and the end-to-end workflow rather than
model optimisation or production-level performance.
