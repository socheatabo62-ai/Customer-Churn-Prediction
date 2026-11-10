# Customer-Churn-Prediction

Group project for the Predictive Analysis course, Royal University of Phnom Penh.

## Goal
Identify customers who are most likely to churn (leave), so marketing teams can target retention and loyalty programs early.
Target variable: Customer Churn (Yes / No).

## Dataset
customer_churn_dataset_W7.csv. About 80% of customers did not churn and 20% did (imbalanced).
## What we did
1. Data cleaning: median imputation (numeric), mode imputation (categorical), IQR outlier capping using training data only to prevent data leakage.
2. Preprocessing: one-hot encoding, StandardScaler, 80/20 stratified train/test split.
3. Exploratory analysis: customers with longer tenure are less likely to churn; monthly charges are right-skewed.
4. Feature engineering: TotalCharges, MonthlyChargesPerAge, HighUsage (support calls > 3). Removed CustomerID.
5. Models: Logistic Regression (class_weight='balanced'), Decision Tree (max_depth=5), Random Forest (max_depth=10, 100 trees).

## Results
| Model | Precision | Recall | F1 | Accuracy |
|Logistic Regression| 0.24 | 0.58 | 0.34 | 0.55 |
|Decision Tree| 0.27 | 0.55 | 0.36 | 0.62 |
|Random Forest| 0.28 | 0.47 | 0.35 | 0.65 |

We chose Logistic Regression because it had the highest recall, which suits an early-warning system for churner.

## Limitations 
- Lowering the threshold increases recall but flags more customers who would not have churned.
- Model scores are modest (ROC AUC about 0.60), so there is room to improve.

