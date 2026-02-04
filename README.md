# STAT364 Statistical Analysis Assignments

## Assignments' Overview
This repository contains comprehensive statistical analysis assignments completed for the **STAT364** course. The assignments focus on **Experimental Design**, **Linear Models**, and **ANOVA** techniques using **R**.

**Author:** Mürüvvet Eda Koyuncu
**Course:** STAT364 - Experimental Design
**Tools:** R, RStudio

---

## Assignment 1: One-Way Linear Model Analysis
**Topic:** Analysis of Detergent Filling Machine Deviations

### Objective
To investigate if six different filling machines place the same amount of detergent into cartons by analyzing deviation data.

### Key Methodologies
* **One-Way Linear Model:** Formulated as $y_{ij} = \mu + \alpha_j + \epsilon_{ij}$.
* **Parameter Estimation:** Constructed Design Matrices ($X$) and calculated Least Squares Estimators (LSE).
* **Hypothesis Testing:** Performed ANOVA F-tests to check for significant machine effects.
* **Post-hoc Analysis:** Conducted **Tukey’s HSD** to identify specific differences between machines.

### Results Summary
* **ANOVA Decision:** Reject $H_0$. There is a significant difference in mean fill amounts between machines ($F = 12.82$, $p < 0.05$).
* **Tukey's Test:** Machines 3 and 4 consistently filled significantly more detergent compared to Machines 1, 2, 5, and 6.
* **Conclusion:** The filling process is inconsistent; Machines 3 and 4 require calibration.

---

## Assignment 2: Factorial Design & Model Diagnostics
**Topic:** Demographic Factors Influencing Working Hours

### Objective
To analyze the relationship between working hours and demographic factors (Age, Gender, Region, Marital Status, Education) using a large survey dataset ($N > 50,000$).

### Key Methodologies
* **Data Cleaning:** Recoding categorical variables (Factors) and handling data types in R.
* **Factorial ANOVA:** Built a full factorial linear model including up to 5-way interactions.
* **Model Selection:** Used **Stepwise Regression (Backward/Forward)** based on **AIC** to optimize the model.
* **Diagnostics:**
    * **Heteroscedasticity:** Checked via Residual Plots and **Breusch-Pagan Test**.
    * **Normality:** Checked via Q-Q Plots and **Shapiro-Wilk Test**.
    * **Autocorrelation:** Checked via **Durbin-Watson Test**.

### Results Summary
* **Significant Factors:** Age, Gender, Region, Marital Status, and Education level all significantly impact working hours.
* **Interactions:** Significant two-way interactions were found (e.g., Age $\times$ Gender), indicating the effect of age on working hours differs by gender.
* **Diagnostics:** The model showed signs of heteroscedasticity and non-normality due to the massive sample size, but was deemed robust for analysis after model selection (AIC dropped from ~396k to ~247k).

---

## 🛠️ R Functions Used
`lm()`, `aov()`, `TukeyHSD()`, `model.matrix()`, `qr()`, `solve()`, `step()`, `AIC()`, `bptest()`, `dwtest()`, `shapiro.test()`.
