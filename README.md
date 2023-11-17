# Titanic - Learning from Disaster

The goal of this analysis is to predict the survival of passengers on the Titanic. The dataset underwent preprocessing and feature engineering to prepare it for modeling. Various transformations, including imputation, standardization, and one-hot encoding, were applied to handle missing values and convert categorical features.

## Feature Engineering and Preprocessing

The preprocessing pipeline included:
- Imputing missing values using median for numeric features and most frequent values for categorical features.
- Standardizing numeric features using StandardScaler.
- One-hot encoding categorical features with OneHotEncoder.

## Model Selection - Decision Tree

A Decision Tree model was chosen for its interpretability and ability to capture complex relationships in the data. The model was initially trained without hyperparameter tuning, resulting in an accuracy of 83%.

## Hyperparameter Tuning - Randomized Grid Search

To improve the model's performance, a randomized grid search was conducted to find optimal hyperparameters. The hyperparameter grid included various settings for criterion, splitter, max depth, min samples split, min samples leaf, and max features.

The best model obtained from the search was then evaluated on the test set.

## Model Evaluation Metrics

The following metrics were used to evaluate the Decision Tree model:
- Precision: 0.76
- Recall: 0.80
- F1 Score: 0.78

These metrics provide insights into the model's ability to correctly classify survivors and non-survivors. Precision measures the accuracy of positive predictions, recall measures the ability to capture all positive instances, and the F1 score balances precision and recall.

In conclusion, the Decision Tree model, after hyperparameter tuning, shows promising results in predicting passenger survival on the Titanic dataset.

# Data Dictionary

| Variable | Definition | Key |
| --- | --- | --- |
| survival | Survival | 0 = No, 1 = Yes |
| pclass | Ticket class | 1 = 1st, 2 = 2nd, 3 = 3rd |
| sex | Sex | |
| Age | Age in years | |
| sibsp | # of siblings / spouses aboard the Titanic | |
| parch | # of parents / children aboard the Titanic | |
| ticket | Ticket number | |
| fare | Passenger fare | |
| cabin | Cabin number | |
| embarked | Port of Embarkation | C = Cherbourg, Q = Queenstown, S = Southampton |

## Variable Notes

- **pclass:** A proxy for socio-economic status (SES)
  - 1st = Upper
  - 2nd = Middle
  - 3rd = Lower

- **age:** Age is fractional if less than 1. If the age is estimated, it is in the form of xx.5.

- **sibsp:** The dataset defines family relations in this way...
  - Sibling = brother, sister, stepbrother, stepsister
  - Spouse = husband, wife (mistresses and fiancés were ignored)

- **parch:** The dataset defines family relations in this way...
  - Parent = mother, father
  - Child = daughter, son, stepdaughter, stepson
  - Some children traveled only with a nanny, therefore parch=0 for them.
