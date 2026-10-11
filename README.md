# Diabetes Prediction using Logistic Regression, LDA and QDA

Mini project for **CSE3141 Predictive Analytics** (Manipal University Jaipur).

Predicts whether a patient has diabetes from 8 medical measurements (Pima Indians Diabetes dataset, 768 patients) and compares three classifiers: Logistic Regression, Linear Discriminant Analysis (LDA) and Quadratic Discriminant Analysis (QDA).

## What is covered
- Data cleaning: hidden missing values (impossible zeros), median imputation, IQR outlier analysis
- EDA: class balance, histograms, box plots, correlation heatmap, scatter plot
- Feature engineering and selection (ANOVA F-score, cross-validated comparison of feature sets)
- Models: Logistic Regression, LDA, QDA, majority-class baseline
- Validation: stratified train/test split, 5-fold cross-validation, grid search, overfitting check
- Metrics: accuracy, precision, recall, F1, AUC-ROC, RMSE, MAE, confusion matrix, ROC curve
- Interpretation: odds ratios, covariance comparison, threshold tuning, ethics and limitations

## Results (held-out test set, 154 patients)
| Model | Accuracy | Recall | F1 | AUC |
|---|---|---|---|---|
| Baseline (majority) | 0.649 | 0.000 | 0.000 | 0.500 |
| Logistic Regression | 0.688 | 0.481 | 0.520 | 0.810 |
| LDA | 0.701 | 0.537 | 0.558 | 0.804 |
| QDA | 0.721 | 0.593 | 0.598 | 0.780 |

Cross-validated AUC favours the linear models (LR 0.844, LDA 0.845, QDA 0.832), so they are the more reliable choice. See the notebook for details.

## Project structure
```
data/diabetes.csv                      raw dataset (no header row)
notebooks/Diabetes_Prediction_Project.ipynb   full analysis with explanations
results/                               saved figures and metrics.json
requirements.txt
```

## How to run
```bash
pip install -r requirements.txt
cd notebooks
jupyter notebook Diabetes_Prediction_Project.ipynb   # then Run All
```

## Dataset source
Smith et al. (1988), Pima Indians Diabetes Database, originally from the National Institute of Diabetes and Digestive and Kidney Diseases. CSV copy: https://github.com/jbrownlee/Datasets
