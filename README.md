# predict churn modelling

source data = https://www.kaggle.com/datasets/adammaus/predicting-churn-for-bank-customers?resource=download

# EDA
- Kesimpulan
  - Data terlihat valid dan tidak ada kecacatan yang major/signifikan dan tidak ada null values
  - Dropped Feature (tidak berpengaruh sama sekali):
    - `Surname`
    - `RowNumber`
    - `CustomerId`
  - Less Correlation (<= 0.01):
    - `Tenure`
    - `HasCrCard`
    - `EstimatedSalary`
  - Dari fitur kategorikal, `Geography` dan `Gender` mungkin berguna untuk menjadi prediktor model
    - One Hot Encoding
      - `Geography` (is_france, is_spain, is_germany)
    - Label Encoding
      - `Gender` (Male -> 1 and Female -> 0).
  - Class Imbalance
    - Perbandingan data exited 1 dengan 0 tidak balance 80:20

# DATA PREPROCESSING
  - Outliers yang dihanlde hanya `CreditScore`
  - Oversampling dilakukan dengan metode SMOTE agar hasil 1:2

# MODELLING
  - Algoritma yang dicoba:
    - Logistic Regression
    - Decision Tree
    - XGBoost
    - Random Forest
    - AdaBoost