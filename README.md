# Movie Revenue Forecasting

This project explores data-driven approaches to predict worldwide box office revenue for movies using metadata such as cast, crew, budget, and release dates. By leveraging machine learning models and feature engineering, the project highlights significant predictors and provides insights into movie revenue forecasting.

---

## **Overview**
In 2023, the film industry generated an estimated $77 billion. Studio executives are constantly seeking ways to maximize returns. Using metadata on over 3,000 films from **The Movie Database**, this project predicts box office revenue and identifies key factors contributing to success.

**Key Features of the Dataset**:
- **Target Variable**: `Revenue` (log-transformed for modeling).
- **Predictors**: Cast, crew, genres, budget, release dates, and more.
- **Source**: The Movie Database, with 3,000 rows and 23 columns.

---

### Data Cleaning & Preprocessing**
- Removed outliers and transformed highly skewed variables.
- Created over **80 new features** through feature engineering:
  - Dummy variables for genres, seasons, and collection status.
  - Extracted and imputed missing budget values using KNN.
  - Engineered metrics like `budget-runtime ratio`.

### Exploratory Data Analysis**
- **Univariate Analysis**:
  - Found `budget` and `popularity` to be right-skewed but strongly correlated with revenue.
- **Bivariate Analysis**:
  - Positive correlations between revenue, budget, runtime, and popularity.
- **Insights**:
  - Movies in collections and those released during winter/spring performed better on average.

---

## **Models Implemented**
### **Multiple Linear Regression**
- Found key predictors:
  - **Budget**: 53% revenue increase per unit rise.
  - **Popularity**: Movies in the "high popularity" category had ~200% higher revenue.
  - **Collection Status**: Belonging to a collection increased revenue by ~75%.
- **Test RMSE**: 2.19.

### **Bagging**
- Focused on reducing variance through ensemble methods.
- Found popularity and release date to be the most significant variables.
- **Test RMSE**: 2.19.

### **Random Forest**
- Performed 5-fold cross-validation and hyperparameter tuning.
- Found optimal predictors like `budget-runtime ratio` and `male cast count`.
- **Test RMSE**: 2.07 (best performing model).

### **Boosting**
- Tuned shrinkage and iterations for optimization.
- Found `budget`, `popularity`, and `runtime` to be critical predictors.
- **Test RMSE**: 2.24.

---

## **Key Insights**
**Significant Predictors**:
   - **Budget**: Strongest predictor of revenue.
   - **Popularity**: High popularity movies yield significantly higher returns.
   - **Release Dates**: Winter/spring releases perform better on average.
   - **Genre & Collection Status**: Movies in collections and thrillers show increased revenue potential.

**Model Performances**:
   - **Random Forest**: Best performing model (Test RMSE: 2.07).
   - Other models like bagging and linear regression had similar RMSEs but lacked robustness.

**Overfitting Issues**:
   - Some overfitting was observed, especially in Random Forest and Boosting models.

---
