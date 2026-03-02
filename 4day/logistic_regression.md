# Logistic Regression — Quick Reference Guide

In a logistic regression, if your predictor is binary—like "case A" versus "case B"—the coefficient is always relative to a reference category. The software (or your design) picks one category as the baseline. The coefficient tells you how the odds change compared to that baseline.

So, if "case B" is your reference, the coefficient shows how the odds differ for "case A" compared to "case B." If the coefficient is positive, "case A" has higher odds of the outcome than "case B." If it’s negative, "case A" has lower odds. Always check
---

## 1. When to Use Logistic Regression

Use logistic regression when:

- The outcome is **binary** (0/1)
- Example: Hospitalized within 1 year (Yes/No)

It models the **probability of an event**, but does so through the **log-odds scale**.

---

## 2. Model Structure

$$
\text{logit}(p) = \beta_0 + \beta_1X_1 + \beta_2X_2 + \dots
$$

Where:

- \( p \) = probability of the event  
- logit(p) = log-odds  
- \( \beta_0 \) = intercept  
- \( \beta_i \) = coefficients  

Logit definition:

$$
\text{logit}(p) = \ln\left(\frac{p}{1-p}\right)
$$

---

## 3. Why Log-Odds?

Probability is bounded between 0 and 1.

Log-odds range from −∞ to +∞.

This allows:
- Linear modeling
- Additive effects
- Stable estimation

---

## 4. Interpreting the Intercept

The intercept \( \beta_0 \):

- Represents the **log-odds** of the outcome
- When all predictors = 0

Convert it:

1. Odds  
$$
\text{odds} = e^{\beta_0}
$$

2. Probability  
$$
p = \frac{\text{odds}}{1 + \text{odds}}
$$

Note: The intercept is often not clinically meaningful unless “0” values are meaningful.

---

## 5. Interpreting Coefficients

Each coefficient represents:

> The change in **log-odds** for a 1-unit increase in the predictor.

To interpret:

$$
\text{Odds Ratio (OR)} = e^{\beta}
$$

### Interpretation Rules

- OR > 1 → increases odds  
- OR < 1 → decreases odds  
- OR = 1 → no association  

Example:

If \( \beta = 0.58 \)

$$
e^{0.58} = 1.79
$$

Interpretation:

Patients on biologic therapy have 1.79 times the odds of hospitalization compared to standard treatment, adjusting for other variables.

---

## 6. Log-Odds vs Probability

Odds ratios multiply **odds**, not probability.

You cannot multiply baseline probability by the OR directly.

Correct process:

1. Compute log-odds  
2. Convert to odds:  
   $$
   e^{\text{logit}}
   $$
3. Convert to probability:  
   $$
   p = \frac{e^{\text{logit}}}{1 + e^{\text{logit}}}
   $$

---

## 7. Crude vs Adjusted Odds Ratios

**Crude OR**
- Effect of one predictor alone
- No adjustment

**Adjusted OR**
- Effect after including other predictors in the model

If crude OR ≠ adjusted OR → possible **confounding**

Example:

- Crude OR = 1.2  
- Adjusted OR = 1.79  

This suggests another variable was masking (suppressing) the treatment effect.

---

## 8. What Is Confounding?

A confounder:

- Is associated with the exposure
- Is associated with the outcome
- Distorts the true relationship

Confounding is not “bad” — ignoring it is.

Multivariable regression adjusts for confounders.

---

## 9. Standard Error (SE)

SE reflects:

- Uncertainty of the estimate
- Precision

Used to calculate confidence intervals:

$$
\beta \pm 1.96 \times SE
$$

Exponentiate limits to obtain CI for OR.

---

## 10. AUC (Area Under the Curve)

AUC measures **discrimination**, not calibration.

Discrimination =  
How well the model separates event vs non-event.

Interpretation:

- 0.5 → random  
- 0.7–0.8 → acceptable  
- 0.8–0.9 → excellent  

Example:

AUC = 0.74 → moderate discrimination.

Meaning:

The model ranks a hospitalized patient higher than a non-hospitalized patient 74% of the time.

---

## 11. Key Conceptual Shift

2×2 table → one exposure at a time  

Logistic regression → multiple predictors simultaneously  

Each coefficient represents:

The independent association of that variable, holding all others constant.

---

## 12. What Logistic Regression Does NOT Tell You

- Does not directly give risk ratios  
- Does not prove causality  
- Does not guarantee calibration  
- OR ≠ Risk Ratio (unless outcome is rare)

---

## Final Mental Model

1. Start with baseline log-odds (intercept)  
2. Add predictor contributions  
3. Convert to probability  
4. Interpret using odds ratios  
5. Adjusted = controlled for confounding  

Core takeaway:

Logistic regression models log-odds to estimate adjusted odds ratios for binary outcomes.