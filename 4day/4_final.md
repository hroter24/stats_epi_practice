# 📊 100-Day Epidemiologic Statistics Challenge  
## Day 4 – Logistic Regression, Log-Odds, Odds Ratios, and AUC

---

## Scenario

Outcome: 1-year hospitalization (1 = Yes, 0 = No)

Predictors:
- Biologic (vs Standard)
- Age (per 10 years)
- Diabetes (Yes/No)

Logistic regression output:

| Variable | β | SE | p-value |
|----------|----|----|---------|
| Intercept | -2.10 | 0.40 | <0.001 |
| Biologic (vs Standard) | 0.58 | 0.22 | 0.009 |
| Age (per 10 yrs) | 0.35 | 0.08 | <0.001 |
| Diabetes (Yes) | 0.72 | 0.25 | 0.004 |

Model AUC = 0.74

---

# a) Logistic Regression Equation

Let:
- X1 = 1 if Biologic, 0 if Standard
- X2 = Age in 10-year units
- X3 = 1 if Diabetes = Yes, 0 if No

Logit model:

$$
\log\left(\frac{p}{1-p}\right)
=
-2.10 + 0.58X_1 + 0.35X_2 + 0.72X_3
$$

Core concept:
Logistic regression models **log-odds**, not probability directly.

---

# b) Biologic Coefficient Interpretation

β = 0.58

Odds Ratio:

$$
OR = e^{0.58} \approx 1.79
$$

Interpretation:
Holding age and diabetes constant, patients on biologic therapy have 1.79 times the odds of hospitalization compared to standard therapy.

Core concepts:
- Reference category = Standard (becuase it is 0)
- OR = exp(β)
- Interpretation is conditional on other covariates

---

# c) Age Effect

β = 0.35 (per 10-year increase)

$$
OR = e^{0.35} \approx 1.42
$$

Interpretation:
Each 10-year increase in age is associated with a 42% increase in odds of hospitalization, holding other variables constant.

Core concept:
Scaling matters (per 10 years, not per 1 year).

---

# d) Strongest Association

Odds Ratios:
- Diabetes: e^{0.72} ≈ 2.05
- Biologic: e^{0.58} ≈ 1.79
- Age (per 10 yrs): e^{0.35} ≈ 1.42

Strongest association (as parameterized): Diabetes.

Core concept:
Compare OR magnitude, not raw β alone (unless scales identical).

---

# e) Statistical Significance vs Causation

Statistical significance ≠ causation.

Even adjusted models may suffer from:
- Residual confounding
- Confounding by indication
- Model misspecification
- Unmeasured variables

Interpretation:
Association conditional on included covariates.

Core concept:
Adjustment reduces but does not eliminate confounding.

---

# f) AUC Interpretation

AUC = 0.74

Interpretation:
If you randomly select one hospitalized and one non-hospitalized patient, the model assigns a higher predicted risk to the hospitalized patient 74% of the time.

Discrimination scale:
- 0.5 = No discrimination
- 0.7–0.8 = Moderate
- >0.8 = Strong

Core concept:
AUC measures discrimination, not calibration.

---

# g) OR vs RR When Outcome Is Common

When outcome incidence is high (e.g., 40%):

- OR increasingly overestimates RR
- OR approximates RR only when outcome is rare (<10%)

Core concept:
OR inflation grows as outcome becomes common.

---

# Key Takeaways

- Logistic regression models log-odds.
- OR = exp(β).
- Interpretation is conditional on other variables.
- Reference category matters.
- Statistical significance does not imply causation.
- AUC measures discrimination ability.
- OR approximates RR only for rare outcomes.

---

Day 4 Complete