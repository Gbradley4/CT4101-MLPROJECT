# CT4101-MLPROJECT

## Project Overview

This project investigates whether online browsing behaviour can be used to predict whether a shopping session will result in a purchase.

**Research Question:** Can a customer's online browsing behaviour be used to predict whether their shopping session will result in a purchase?

The project uses a binary classification approach, with `Revenue` as the target variable.

## Dataset

The project uses the **Online Shoppers Purchasing Intention Dataset** from the UCI Machine Learning Repository.

- **Observations:** 12,330
- **Variables:** 18 (17 input features and 1 target variable)
- **Target Variable:** `Revenue` (`True` = Purchase, `False` = No Purchase)
- **Source:** https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset
- **Licence:** Creative Commons Attribution 4.0 International (CC BY 4.0)

## Project Progress

### Milestone 1 — Project Proposal

**Completed**

Defined the research question, selected the dataset, identified the target variable and proposed classification models and evaluation methods.

### Milestone 2 — Data and Baseline Checkpoint

**Data Audit — Completed**

- Examined data types, missing values, duplicates and numerical ranges.
- Identified 125 exact duplicate records.
- Investigated outliers using quantiles and boxplots.
- Identified an imbalanced target variable.
- Investigated potential data leakage.

**Data Preprocessing — Completed**

- Removed 125 duplicate records, leaving 12,205 observations.
- Excluded `PageValues` from the initial feature set due to potential data leakage concerns.
- Applied `StandardScaler` to numerical features and `OneHotEncoder` to categorical features.
- Created a preprocessing pipeline using `ColumnTransformer` and `Pipeline`.
- Used an 80/20 stratified train/test split.

**Baseline Model — Completed**

Implemented a majority-class `DummyClassifier` to establish a baseline for future model comparisons.

| Evaluation Metric | Result |
|---|---|
| Accuracy | 84.35% |
| Precision | 0.00 |
| Recall | 0.00 |
| F1-score | 0.00 |

Although the baseline achieved 84.35% accuracy, it failed to identify any purchasing sessions. This demonstrates the limitations of accuracy when evaluating imbalanced classification datasets.

## Setup Instructions

1. Download or clone this GitHub repository.
2. Install Python and Jupyter Notebook.
3. Install the required packages using `pip install -r requirements.txt`.
4. Ensure the dataset is located at `Data/online_shoppers_intention.csv`.
5. Open `Milestone 2 - Attempt 2.ipynb` in Jupyter Notebook from the project directory.
6. Run all notebook cells in order.

## Planned Models

Future modelling will investigate:

- Logistic Regression
- K-Nearest Neighbours
- Decision Tree

These models will be compared with the majority-class baseline.

## Limitations

The dataset contains class imbalance, extreme numerical observations and session-level features that may not all be available during a real-time prediction.

Potential data leakage was considered during feature selection, and `PageValues` was excluded from the initial model.

## Assistance Declaration

ChatGPT was used to assist with 
- understanding lecture concept
- developing and explaining Python code, particularly explaining error messages when they arrised

## Dataset Reference

Sakar, C. & Kastro, Y. (2018). *Online Shoppers Purchasing Intention Dataset*. UCI Machine Learning Repository. https://doi.org/10.24432/C5F88Q


