Cancer Mortality Prediction Using Linear Regression

This project analyzes socioeconomic, demographic, and healthcare coverage variables to understand their predictive impact on U.S. cancer mortality rates. Using R and a multi-step statistical modeling workflow, the goal was to identify which factors most strongly influence cancer death rates and to build a reliable linear regression model using data-driven feature selection.

Project Overview

The dataset includes a cancer death rate outcome variable (TARGET_deathRate) and a variety of potential predictors related to poverty, insurance coverage, employment, median income, incidence rates, and demographic information.
The project follows these major steps:

Exploratory Data Analysis (EDA)

Model Creation

Model Selection via Stepwise AIC (stepAIC)

Diagnostic Testing & Assumption Checking

Transformations & Final Model Evaluation

Exploratory Data Analysis

EDA was conducted to identify trends, outliers, and issues such as multicollinearity, which can distort linear regression estimates.

Key findings:

Strong correlations identified between

Poverty % ↔ Private Coverage %

Poverty % ↔ Median Income

Public Coverage % ↔ Median Income

Public Coverage % ↔ Private Coverage %

Scatter plots indicated expected trends:

Higher poverty → higher death rates

Higher median income → lower death rates

Higher incidence rates → higher death rates

Multivariate scatter plots highlighted joint effects (e.g., poverty and public coverage increasing together with death rate)

Modeling Approach

A multiple linear regression model was built using 7 predictors:

povertyPercent

PctPublicCoverage

PctEmpPrivCoverage

PctPrivateCoverage

studyPerCap

medIncome

MedianAge

The initial model showed:

5 variables statistically significant at p < 0.05

2 variables (studyPerCap, MedianAge) not significant

R² ≈ 0.264, meaning ~26% of variation in cancer death rates explained by the model

Model Selection (stepAIC)

Stepwise model selection using Akaike Information Criterion (AIC) was applied to identify the most parsimonious model.

Results:

stepAIC removed 2 predictors: studyPerCap and MedianAge

Final model retained 5 significant predictors

Model performance remained stable with R² ≈ 0.263

This method ensured the model captured essential predictors while eliminating noise.

Diagnostic Testing

Diagnostics were performed to evaluate regression assumptions:

Residuals vs Fitted Plot: Slight heteroscedasticity observed

Q-Q Plot: Deviations from normality

Lagged Residuals Plot: No autocorrelation pattern

Cook’s Distance & Hat Values: One influential observation identified

These diagnostics suggested that a transformation could improve model fit.

Box-Cox Transformation

A Box-Cox transformation was applied to the response variable:

Optimal λ ≈ 0.75

Model re-estimated with transformed target

Coefficient significance remained consistent

R² stable at ~0.263

Final Insights

Only 5 predictors significantly influence cancer death rates:
povertyPercent, PctPublicCoverage, PctEmpPrivCoverage, PctPrivateCoverage, and medIncome

Two predictors were consistently non-significant: studyPerCap, MedianAge

Public and employer‐provided insurance coverage showed positive correlations with death rate—an unexpected and noteworthy finding that may warrant further investigation

The final model provides a statistically sound, interpretable framework but explains only about 26% of variation in cancer mortality, suggesting additional non-included factors likely play a role

Technologies Used

R

dplyr, ggplot2, MASS, rms, lmtest

stepAIC, fastbw, Box-Cox transformation

Standard linear regression diagnostics & visualization tools

Links: 
- [Code](https://github.com/Brianwitarsa/Cancer-Mortality-Prediction-With-Linear-Regression-StepAIC/blob/main/FinalProjectLinearModels.html)
- [Report](https://github.com/Brianwitarsa/Cancer-Mortality-Prediction-With-Linear-Regression-StepAIC/blob/main/Final%20Project%20Report%20Linear%20Models.pdf)
