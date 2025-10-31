# Results — Diabetic Readmission Prediction

## Key Metrics (Test Set)
- **Best model:** Gradient Boosting  
- **Accuracy:** ~0.62  
- **Positive-class F1:** ~0.57  
- **Baselines:** Random Forest ~0.61 accuracy; KNN lower

## Statistically Significant Patterns
- **Gender × Readmission** — chi-square p ≈ **1.45e-7** → meaningful association  
- **Age Group × Length of Stay** — one-way ANOVA p ≈ **3.76e-257** → group means differ  
- **Prior Inpatient Visits vs Readmission** — Mann–Whitney U p ≈ **0** → distributions differ

## Feature Engineering Outcome
- **`high_utilization`** = 1 when outpatient + emergency + inpatient visits > 2; else 0  
- Shows significant association with readmission (p < 0.05) and aligns with intuition  
- **Decision:** include in the model; improves positive-class screening while remaining interpretable

## Top Drivers
- Prior inpatient visits  
- Overall utilization (incl. `high_utilization`)  
- Secondary signals from selected visit types and age

## Group-Level Snapshot
- **Age trend:** higher age groups show higher predicted readmission fractions  
- **Gender:** measurable differences across groups; thresholding should consider fairness

## Summary
Test accuracy is ~**0.62** with positive-class **F1 ~0.57**. **Prior inpatient visits** and **overall utilization** dominate; the engineered **`high_utilization`** feature is statistically significant and retained.
