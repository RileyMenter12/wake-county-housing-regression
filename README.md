# Wake County Housing Price Regression Analysis

## Overview
This project explores how property characteristics influence housing prices in Wake County, North Carolina. Using a real estate dataset prepared by the Town of Cary GIS Group, we applied regression techniques to identify key predictors of sale values and evaluate the strengths and limitations of linear models for this problem.

The work was completed as part of **STAT170 (Regression Analysis)** at UC Riverside.

---

## Dataset
- Source: Town of Cary GIS Group (cleaned and modified dataset)
- Original size: ~285,000 observations and 62 variables
- Subset used: Reduced for processing speed and interpretability
- Response variable: `TotalSaleValue` (property sale price in $1000s)

### Key predictors examined:
- `TotalBldgSqft` — total building square feet  
- `DeedAcres` — acreage of the property  
- `BuiltBefore1990` — binary indicator of construction year  
- `LandValue` — assessed land value ($1000s)  
- `BldgValue` — assessed building value ($1000s)  
- `IsDetachedUnit` — binary indicator for detached units  

---

## Methods
1. **Exploratory Data Analysis (EDA):**  
   - Descriptive statistics and visualizations  
   - Distribution analysis of `TotalSaleValue`  
   - Box-Cox and square root transformation to approximate normality  

2. **Regression Modeling:**  
   - Initial multiple regression model  
   - Stepwise regression to refine predictors  
   - Log transformations of skewed predictors (`LandValue`, `DeedAcres`)  
   - Testing higher-order and interaction terms  

3. **Model Diagnostics:**  
   - Residual plots, Q-Q plots, and Shapiro-Wilk tests for normality  
   - Durbin-Watson test for independence  
   - VIF for multicollinearity  
   - ANOVA for comparing nested models  

---

## Findings
- **Insignificant predictors:** `TotalBldgSqft` and `IsDetachedUnit`  
- **Unexpected trend:** Larger acreage (`DeedAcres`) often associated with *lower* sale values  
- **Interactions:** Minimal improvement in predictive power  
- **Final model:** Achieved adjusted R² ≈ 0.40 after transformations and interaction terms  

---

## Limitations
- A reduced dataset may have excluded relevant patterns  
- House sale values not time-adjusted (temporal mismatches possible)  
- Linear regression assumptions violated in some cases  
- Excluded predictors (e.g., location, owner characteristics) may improve accuracy  

---

## Repository Contents
- `STAT170_group_project.Rmd` — full R Markdown with code, analysis, and write-up  
- `STAT170_group_project.pdf` — knitted report output  
