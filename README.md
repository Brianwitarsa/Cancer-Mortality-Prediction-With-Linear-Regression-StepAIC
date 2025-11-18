# Cancer Mortality Prediction Using Linear Regression

This project analyzes socioeconomic, demographic, and healthcare coverage variables to understand their predictive impact on U.S. cancer mortality rates. Using R, linear modeling, and stepwise AIC selection, the goal was to identify which factors most strongly influence cancer death rates and build a reliable regression model.

## Project Overview
- Exploratory Data Analysis (EDA)
- Model Creation
- Model Selection using stepAIC
- Diagnostic Testing
- Box-Cox Transformation
- Final Model Evaluation

## Exploratory Data Analysis
Key EDA findings:
- Strong correlations between several predictors, including:
  - PovertyPercent and PrivateCoverage
  - PovertyPercent and MedianIncome
  - PublicCoverage and MedianIncome
  - PublicCoverage and PrivateCoverage
- Higher poverty was associated with higher cancer death rates.
- Higher median income was associated with lower cancer death rates.
- Higher incidence rates were associated with higher death rates.
- Multicollinearity was identified as a major modeling concern.

## Modeling Approach
The initial model used 7 predictors:
- povertyPercent
- PctPublicCoverage
- PctEmpPrivCoverage
- PctPrivateCoverage
- studyPerCap
- medIncome
- MedianAge

Initial results:
- 5 predictors were statistically significant.
- studyPerCap and MedianAge were not significant.
- R-squared was approximately 0.264.

## Model Selection (stepAIC)
Results of stepAIC:
- Removed 2 predictors: studyPerCap and MedianAge.
- Final model retained 5 significant predictors.
- R-squared remained approximately 0.263.
- The final model was more efficient without loss of performance.

## Diagnostic Testing
Diagnostics performed:
- Residuals vs Fitted plot showed slight heteroscedasticity.
- Q-Q plot showed deviations from normality.
- Lagged residuals showed no autocorrelation.
- Cook’s distance and hat values revealed one influential point.

## Box-Cox Transformation
- Box-Cox transformation suggested lambda ≈ 0.75.
- Transformed model maintained similar results.
- R-squared remained stable near 0.263.

## Final Insights
- Five predictors significantly influenced cancer death rates.
- Two predictors (studyPerCap, MedianAge) were consistently not significant.
- Insurance-related predictors showed unexpected positive associations with death rates.
- The model explains about 26 percent of death rate variance.

## Technologies Used
- R
- dplyr
- ggplot2
- MASS
- rms
- lmtest
- stepAIC
- Box-Cox transformation
- Standard linear diagnostic tools

Links: 
- [Code](https://github.com/Brianwitarsa/Cancer-Mortality-Prediction-With-Linear-Regression-StepAIC/blob/main/FinalProjectLinearModels.html)
- [Report](https://github.com/Brianwitarsa/Cancer-Mortality-Prediction-With-Linear-Regression-StepAIC/blob/main/Final%20Project%20Report%20Linear%20Models.pdf)
