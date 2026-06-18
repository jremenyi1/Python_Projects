# Clustering Antarctic Penguin Species 

**Unsupervised Learning & K-Means, Python, 2025**

## Background

This project explores physical measurements of penguins
collected in Antarctica. The dataset does **not include
species labels**, making it suitable case for unsupervised
learning.

The goal is to investigate whetehr natural groupings
emerge from the data and whether these clusters plausibly
correspond to known penguin species.

The dataset is sourced from artwork and data by **Allison Horst.**

---

## Objective

- Explore penguin measurement data without using species labels
- Identify natural groupings using unsupervised learning
- Apply K-Means clustering to group similar observations
- Evaluate the impact of feature scaling on clustering results

---

## Data

**raw data** – `penguins.csv`

The dataset contains measurements from Antarctic penguins.

**Features used:**

- Culmen length (mm)
- Culmen depth (mm)
- Flipper length (mm)
- Body mass (g)
- Sex (categorical)

The dataset contains **no species labels**, which are intentionally excluded from the analysis.

---

## Approach

- Performed basic exploratory data analysis (missing values, distributions, basic stats)
- Converted the categorical `sex` variable into numeric values using one-hot encoding
- Applied **StandardScaler** because of the large differences in feature magnitudes
- Used **K-Means clustering** to group similar penguins
- Used the **elbow method (inertia)** to select the number of clusters
- Compared clustering results **with and without feature scaling**

---

## Key Result

- The elbow plot suggested an optimal choice of **3 clusters**
- Feature scaling had a clear impact on clustering performance
- Without scaling, larger-scale variables (e.g. body mass) 
dominated distance calculations
- With scaling, clusters were more balanced and interpretable
- The model grouped the data into three clear clusters, 
which likely correspond to the three known penguin species: 
**Adelie, Chinstrap, Gentoo**

This project demonstrates why preprocessing steps such as scaling
are critical for distance-based algorithms.

---

## Skills Demonstrated

- Python (pandas, matplotlib, scikit-learn)
- Unsupervised learning (K-Means clustering)
- Feature scaling (StandardScaler)
- One-hot encoding
- Elbow method for cluster selection (choosing k)
- Basic exploratory data analysis
- Interpretation clustering results

---

## Files in the Repository

- **project overview** - `README.md`
- **Jupyter Notebook** - `notebook.ipynb`
- **raw dataset** - `penguins.csv`

---

## Notes

This was a **learning-focused project** designed
to understand the practical workflow of unsupervised
learning.

The emphasis is on reasoning, preprocessing, and interpretation
rather than hyperparameter tuning or model optimisation.

---

## Data Source

Artwork and dataset by **Allison Horst**

Source repository: https://github.com/allisonhorst/penguins