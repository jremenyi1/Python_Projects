# DVD Rental Duration Regression

## Project Overview

This project evaluates multiple regression models to predict **DVD rental duration (in days)** using customer behaviour and rental characteristics. The aim is to identify a model that meets a business requirement of **mean squared error (MSE) ≤ 3**, while remaining interpretable and robust.

The project follows a complete supervised learning workflow, including data exploration, preprocessing, model comparison, evaluation, and interpretation.

---

## Dataset

**Raw data** – `rental_info.csv`

The dataset contains rental-related features such as:
- Rental rates and film length
- Customer rental behaviour
- Pre-engineered polynomial features (e.g. squared terms)

The target variable is **rental duration**, calculated as the difference between rental and return timestamps.

---

## Objective

- Predict the number of days a DVD is rented
- Engineer a meaningful target variable from timestamps
- Compare multiple regression models
- Select the best-performing model based on test-set MSE

---

## Methods

The following regression models were evaluated:

- Linear Regression  
- Ridge Regression  
- Lasso Regression  
- Decision Tree Regression  
- Random Forest Regression  
- Gradient Boosting Regression

Linear models were scaled using **StandardScaler** to ensure meaningful regularisation.

Key preprocessing steps include:
- Train–test split
- Feature scaling where appropriate
- Model pipelines to ensure clean and reproducible workflows

---

## Evaluation Metric
Models were evaluated using **Mean Squared Error (MSE)**, with a business constraint of **MSE ≤ 3**.  

---

## Key Result

- Multiple models achieved the business requirement of **MSE ≤ 3**
- Tree-based ensemble models outperformed linear approaches
- The final recommended model produced the lowest test-set MSE
- The model can support inventory planning and demand forecasting

**Random Forest Regression** achieved the lowest test error and satisfied the business constraint while remaining relatively interpretable via feature importance analysis.

---

## Feature Importance

Feature importance was analysed for:

- Random Forest
- Gradient Boosting

Both models highlighted rental price and film length features as the strongest predictors of rental duration.

---

## Conclusion

Random Forest Regression was selected as the final model due to:

- Lowest test MSE
- Ability to model non-linear relationships
- Minimal assumptions about data structure
- Clear feature importance interpretation

This project demonstrates practical model comparison, evaluation under constraints, and interpretability-focused decision-making.

---

## Tools & Skills

-- Python (pandas, numpy, matplotlib, scikit-learn)
- Regression modeling and evaluation
- Feature engineering from timestamps
- Pipeline-based ML workflows
- Model comparison and selection
- Cross-validation (K-Fold)
- Business-driven evaluation metrics

---

## Files in the Repository

- **project overview** – `README.md`
- **jupyter notebook** – `notebook.ipynb`
- **dataset** – `rental_info.csv`
- **jpg image** - dvd_image.jpg

---

## Notes

This is a **learning-focused project** emphasizing:

- Clean end-to-end regression workflow
- Correct preprocessing and evaluation
- Model comparison rather than heavy tuning

The focus is on clarity, correctness, and interpretability.