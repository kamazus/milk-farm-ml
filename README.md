# Milk Farm ML 🐄

Machine learning project for selecting cows for a dairy farm based on two business requirements:

- predicted annual milk yield of at least 6,000 kg;
- high probability of producing tasty milk.

## Project Goal

The goal of the project is to help a farmer evaluate cows offered for purchase using historical farm data and machine learning models.

Two ML tasks were solved:

1. **Regression** — prediction of annual milk yield.
2. **Classification** — prediction of milk taste (`вкусно` / `не вкусно`).

## Data Analysis

The project includes:

- data preprocessing and cleaning;
- exploratory data analysis;
- analysis of numerical and categorical features;
- correlation analysis;
- feature engineering;
- model training and evaluation;
- prediction for new cows;
- final selection based on business criteria.

## Machine Learning

### Milk Yield Prediction

Several linear regression models were compared.

Best model:

- **R²:** 0.83
- **RMSE:** ~185 kg
- **MAE:** ~142 kg

Additional engineered features were used to improve prediction quality.

### Milk Taste Classification

A Logistic Regression model was trained to predict milk taste.

Baseline metrics:

- **Accuracy:** 0.65
- **Recall:** 0.85
- **Precision:** 0.66

Because predicting an actually bad-tasting milk as tasty is especially costly for the farmer, the classification threshold was increased to **0.8**.

At this threshold:

- **Precision:** 1.00
- critical false-positive errors on the test set: **0**
- Recall became very low, making the model highly conservative.

## Final Result

The regression model predicts that the considered cows can satisfy the required milk-yield level.

However, with the conservative classification threshold of 0.8, none of the candidate cows simultaneously satisfy both business requirements with sufficient confidence.

Therefore, the current recommendation is not to purchase any candidate based solely on the model predictions.

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Repository

Main notebook:

`milk_farm_ml.ipynb`
