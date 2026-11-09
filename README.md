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

### Milestone 3 — Model Development and Comparison

**Completed**

Implemented three supervised classification models:

- Logistic Regression
- K-Nearest Neighbours (KNN)
- Decision Tree

Each model was evaluated using accuracy, precision, recall, F1-score and confusion matrices.

Parameter tuning was investigated using `GridSearchCV` with five-fold stratified cross-validation. The F1-score was used to select parameter settings.

**Model Comparison Results**

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Dummy Classifier | 84.35% | 0.00% | 0.00% | 0.00% |
| Logistic Regression | 84.31% | 48.28% | 3.66% | 6.81% |
| Tuned Logistic Regression | 64.89% | 27.87% | 78.27% | 41.10% |
| KNN (k=5) | 82.02% | 31.85% | 13.09% | 18.55% |
| Tuned KNN (k=3) | 80.70% | 30.22% | 17.80% | 22.41% |
| Decision Tree | 76.03% | 28.36% | 34.82% | 31.26% |

**Key Findings**

The tuned Logistic Regression model achieved the highest recall (78.27%) and F1-score (41.10%), making it the strongest model tested for identifying purchasing sessions according to these metrics.

However, it produced 774 false positives, demonstrating the trade-off between identifying more purchases and incorrectly predicting purchases.

KNN showed some improvement following parameter tuning, while both Decision Tree tuning experiments selected the default parameter settings.

An error analysis was conducted to compare false positives and false negatives across the models. Interactive visualisations were created using Plotly to support the comparison.

## Setup Instructions

1. Download the repository by clicking **Code → Download ZIP** on GitHub.
2. Extract the ZIP file to a folder on your computer.
3. Open Anaconda Prompt.
4. Navigate to the extracted project folder using:

   `cd /d "path_to_your_project_folder"`

5. Install the required Python packages:

   `pip install -r requirements.txt`

6. Launch Jupyter Notebook:

   `jupyter notebook`

7. Open the `.ipynb` notebook file in Jupyter.
8. Ensure the dataset is located at `Data/online_shoppers_intention.csv`.
9. Select **Kernel → Restart & Run All** to execute the notebook.

## Models Implemented

The following classification models have been implemented and evaluated:

- Dummy Classifier (baseline)
- Logistic Regression
- K-Nearest Neighbours
- Decision Tree

The models were compared using the same stratified train/test split and evaluation metrics.

## Limitations

The dataset contains class imbalance, extreme numerical observations and session-level features that may not all be available during a real-time prediction.

Potential data leakage was considered during feature selection, and `PageValues` was excluded from the initial feature set.

Although the tuned Logistic Regression model improved recall, it also produced a large number of false positives. This demonstrates the need to consider the practical consequences of incorrect predictions when selecting a model.

The findings are based on a single dataset and a limited set of model configurations. Further evaluation would be required before using the models in a real-world application.

## Assistance Declaration

ChatGPT was used to assist with:

- Understanding CT4101 lecture concepts and machine learning terminology.
- Explaining Python code, including helping to interpret and resolve error messages.
- Reviewing notebook structure, Markdown explanations and visualisations.
- Creating and updating the `README.md` document, particularly the setup instructions.

The Python code was executed in Jupyter Notebook, and the outputs and results were reviewed as part of the project.

## Dataset Reference

Sakar, C. & Kastro, Y. (2018). *Online Shoppers Purchasing Intention Dataset*. UCI Machine Learning Repository. https://doi.org/10.24432/C5F88Q


