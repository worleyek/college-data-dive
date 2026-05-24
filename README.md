# College Graduation Rate Prediction

## Overview

This project uses machine learning regression models to predict college graduation rates based on institutional characteristics such as tuition costs, alumni engagement, student demographics, faculty ratios, and expenditures.


Three regression models were trained and evaluated:

* Ridge Regression
* Lasso Regression
* Random Forest Regressor

Hyperparameter tuning and cross-validation were applied to optimize model performance.

---

## Objective

The goal of this project is to predict a college's graduation rate (`Grad.Rate`) using institutional and financial variables while comparing the performance of multiple regression techniques.

---

## Business Case

Colleges and universities face increasing pressure to improve student retention and graduation outcomes while managing financial and institutional resources effectively. Graduation rate is a key performance indicator used by prospective students, accreditation organizations, government agencies, and ranking systems to evaluate institutional success.

The findings from this project could help:

* university administrators identify areas that may influence student success,
* institutional researchers analyze trends across colleges,
* policymakers evaluate higher education effectiveness,
* and prospective students better understand factors associated with stronger graduation outcomes.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib

---

## Dataset Features

| Field | Description |
| :-------- | :-------- |
| Private | A factor with levels No and Yes indicating private or public university |
| Apps | Number of applications received |
| Accept | Number of applications accepted |
| Enroll | Number of new students enrolled |
| Top10perc Pct. | New students from top 10% of H.S. class |
| Top25perc: Pct. | New students from top 25% of H.S. class |
| F.Undergrad | Number of full-time undergraduates |
| P.Undergrad | Number of part-time undergraduates |
| Outstate | Out-of-state tuition |
| Room.Board | Room and board costs |
| Books | Estimated book costs |
| Personal | Estimated personal spending |
| PhD | Pct. of faculty with Ph.D.’s |
| Terminal | Pct. of faculty with terminal degree |
| S.F.Ratio | Student/faculty ratio |
| perc.alumni | Pct. alumni who donate |
| Expend | Instructional expenditure per student |
| Grad.Rate | Graduation rate |

Target Variable:

* `Grad.Rate`

---

## Machine Learning Models

### Ridge Regression

Used to reduce multicollinearity and stabilize coefficient estimates through L2 regularization.

### Lasso Regression

Used for feature selection and regularization through L1 regularization.

### Random Forest Regressor

Used to capture nonlinear relationships and interactions between institutional variables.

---

## Model Optimization

Hyperparameter tuning was performed using:

* `GridSearchCV` for Ridge and Lasso Regression
* `RandomizedSearchCV` for Random Forest Regression

Cross-validation (`cv=5`) was used during tuning to improve model generalization and reduce overfitting.

---

## Best Performing Model

The strongest overall model was the fine-tuned Random Forest Regressor.

Because this model achieved:

* the lowest MAE
* the lowest RMSE
* the highest R² score

it produced predictions closest to the actual graduation rates while minimizing large prediction errors.

## Tuned Random Forest Performance

| Metric | Value |
| ------ | ----- |
| MAE    | 7.86  |
| RMSE   | 10.16 |
| R²     | 0.561 |

---

## Strongest Predictors

The three strongest predictors identified by the tuned Random Forest model were:

1. `Outstate`
2. `perc.alumni`
3. `Top25perc`

These findings suggest that:

* higher out-of-state tuition,
* stronger alumni engagement,
* and stronger incoming academic performance

may all play important roles in graduation outcomes.

---

## Future Improvements

Potential future enhancements include:

* Adding additional regression models
* Building an interactive Streamlit dashboard
* **Investigating feature interactions and nonlinear effects**
* Deploying the model as a web application

---

## Conclusion

This analysis shows that institutional characteristics can be used to reasonably predict college graduation rates. After comparing multiple regression models, the fine-tuned Random Forest performed best, producing the lowest prediction error and the highest explanatory power. 

From a business perspective, the results suggest that graduation outcomes are most strongly influenced by factors such as out-of-state tuition levels, alumni engagement, and incoming student academic quality. These insights can help higher education institutions better understand the key drivers of student success and guide strategic decisions around admissions, funding allocation, and alumni relations.
