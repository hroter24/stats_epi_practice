# Day 1 – Statistical vs Clinical Significance

## Scenario

A randomized study compares systolic blood pressure reduction between:

- Treatment A (new antihypertensive)
- Treatment B (standard of care)

Sample size:

$$
n = 400 \text{ per group}
$$

### Results

- Mean reduction (A): 12.4 mmHg  
- Mean reduction (B): 11.8 mmHg  

Mean difference:

$$
\bar{X}_A - \bar{X}_B = 0.6 \text{ mmHg}
$$

Standard error:

$$
SE = 0.22
$$

$$
p = 0.006
$$

---

# Questions & Model Answers

## a) State the null and alternative hypotheses

$$
H_0: \mu_A - \mu_B = 0
$$

(No difference in mean reduction)

$$
H_1: \mu_A - \mu_B \neq 0
$$

(A difference exists)

---

## b) Interpret the p-value correctly

Assuming the null hypothesis is true, there is a 0.6% probability of observing a difference of 0.6 mmHg or more extreme due to sampling variability.

---

## c) Is this statistically significant? Why?

Yes.

$$
p = 0.006 < 0.05
$$

Reject $H_0$.

---

## d) Is this clinically significant?

Likely no.

A 0.6 mmHg difference is small and unlikely to meaningfully impact patient outcomes despite statistical significance.

---

## e) Compute a 95% Confidence Interval

Formula:

$$
\text{CI} = \text{Estimate} \pm 1.96 \times SE
$$

Calculation:

$$
0.6 \pm 1.96(0.22)
$$

$$
0.6 \pm 0.43
$$

$$
\text{95% CI} = (0.17, 1.03)
$$

Interpretation: The true effect is likely small in magnitude.

---

# Follow-Up Scenario

Assume:

$$
n = 400 \text{ per group}
$$

$$
\text{Mean difference} = 4.5 \text{ mmHg}
$$

$$
SE = 2.5
$$

$$
p = 0.07
$$

---

## a) Is this statistically significant?

No.

$$
p = 0.07 > 0.05
$$

Fail to reject $H_0$.

---

## b) Is this clinically meaningful?

Possibly yes.

A 4.5 mmHg reduction may be meaningful at a population level.

---

## c) Which error is most concerning?

Type II error (failing to detect a true effect).

---

## d) Recommended next step?

Increase sample size or improve precision to narrow the confidence interval.

---

# Core Concepts Reinforced

- Statistical significance ≠ Clinical significance  
- P-values condition on the null being true  
- Sample size affects precision, not magnitude  
- Wide confidence intervals signal imprecision  
- Failing to reject ≠ accepting the null  

---

# One-Sentence Principle

Large epidemiologic studies can detect very small effects because increased sample size reduces standard error, making statistical significance easier to achieve even for trivial differences.

---

# Day 1 Complete

**Difficulty:** Foundational  
**Focus:** Hypothesis testing, interpretation precision, clinical vs statistical meaning