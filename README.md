# Alcohol Use, Passive Smoking, and Hypertension among U.S. Adults (NHANES 2015–2016)

## Overview
This repository contains materials for an applied statistical analysis of **hypertension** and its association with **alcohol use, active smoking, and passive smoking exposure** among U.S. adults using **NHANES 2015–2016** data. The project uses descriptive comparisons, age-stratified analyses, and a multivariable **logistic regression** model, and reports odds ratios, confidence intervals, and predictive performance metrics.

---

## Author
Poorna Sandamini Senaratne

---

## Study Objectives
- Define hypertension using measured systolic/diastolic blood pressure (NHANES protocols).
- Compare characteristics between hypertensive vs. non-hypertensive adults using two-sample tests.
- Conduct age-stratified analyses (20–39, 40–59, 60+ years) for smoking/alcohol vs. hypertension.
- Fit a multivariable logistic regression model adjusting for demographic and health covariates.
- Evaluate model performance using ROC/AUC, sensitivity, specificity, and a confusion matrix.

---

## Dataset
- **Source:** National Health and Nutrition Examination Survey (NHANES) 2015–2016
- **Population:** Adults aged 20–80 years
- **Final analytic sample:** *n = 4,003* (complete cases on outcome, exposures, and covariates)
---

## Key Variables

### Outcome
**Hypertension (binary)** based on measured blood pressure:
- HTN = 1 if any SBP ≥ 140 mmHg or any DBP ≥ 90 mmHg  
- HTN = 0 otherwise  
(derived from BPXSY1/BPXSY2 and BPXDI1/BPXDI2)

### Main Exposures
- **Alcohol use (past 12 months):** ≥ 12 drinks in past year (ALQ101) (Yes vs No/Other)
- **Active smoking:** smoked ≥ 100 cigarettes lifetime (SMQ020) (Yes vs No/Other)
- **Passive smoking exposure:** anyone smokes inside home (HIQ210) (Yes vs No)

### Covariates
- Age (RIDAGEYR) — continuous + age cohorts (20–39, 40–59, 60+)
- Gender (RIAGENDR)
- BMI (BMXBMI)
- Education (DMDEDUC2)
- Marital status (DMDMARTL)

---

## Methods Summary

### Descriptive & Group Comparisons
- Welch two-sample t-tests (age, BMI)
- Wilcoxon rank-sum tests (robust comparisons when needed)
- Chi-square tests of independence (behavioral exposures vs hypertension)

### Subgroup Analysis
- Age-stratified chi-square tests (20–39, 40–59, 60+), where cell counts permitted

### Multivariable Model
Logistic regression with:
- Outcome: Hypertension  
- Predictors: Smoking, Alcohol use, Passive smoking, BMI, Age, Gender, Education, Marital status  
- Reported: Odds ratios (OR), 95% confidence intervals, p-values

### Model Performance
- Confusion matrix (threshold = 0.5)
- Sensitivity, Specificity, Accuracy
- ROC curve and AUC

---

## Main Findings (High-level)
- **Age and BMI** were the strongest predictors of hypertension.
- After adjustment, **smoking, alcohol use, and passive smoking** showed weak or non-significant independent associations.
- The model achieved **moderate discrimination** (AUC ~ 0.74) but **low sensitivity** at the 0.5 threshold.
