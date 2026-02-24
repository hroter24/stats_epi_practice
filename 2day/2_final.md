# Day 2: Independent Samples t-Test

## Focus
Assumptions, variance testing, Welch correction, and effect size.

## Context
CRP levels (mg/L) after 12 weeks in rheumatoid arthritis treatment groups.

## Scenario Data
| Measure | Biologic (A) | Methotrexate (B) |
|---|---:|---:|
| n | 40 | 38 |
| Mean CRP (mg/L) | 3.2 | 5.1 |
| SD | 2.8 | 4.9 |

Given test outputs:
- Independent samples t-test: $t = -2.05$, $df = 58$, $p = 0.045$
- Levene's test: $F = 5.12$, $p = 0.027$

---

## Answers

### a) Hypotheses

Let:

- $\mu_A$ = mean CRP in the biologic group  
- $\mu_B$ = mean CRP in the methotrexate group  

Null hypothesis:

$$
H_0: \mu_A - \mu_B = 0
$$

Alternative hypothesis:

$$
H_1: \mu_A - \mu_B \neq 0
$$

This is a two-sided test of mean difference.

---

### b) Assumptions (Independent Samples t-Test)

- Independent observations  
- Approximate normality (or sufficiently large samples)  
- Equal variances (required for pooled-variance t-test)  
- Valid random sampling or randomization  

---

### c) Levene's Test Interpretation

Given:

- $p = 0.027 < 0.05$

Conclusion:

- Reject the equal-variance assumption  
- Group variances are unequal  

---

### d) Correct Test Choice

Use **Welch's t-test**, which does not assume equal variances.

Note: The p-value may change slightly under Welch's correction.

---

### e) Statistical Significance

Using the reported t-test:

- $p = 0.045 < 0.05$  
- Reject $H_0$ at $\alpha = 0.05$  
- There is evidence of a difference in mean CRP between treatments  

Because Levene's test is significant, this conclusion should be confirmed with Welch's t-test.

---

### f) Effect Size (Cohen's d)

Approximate pooled SD:

$$
SD_{\text{pooled}} \approx 3.95
$$

Cohen's d:

$$
d = \frac{3.2 - 5.1}{3.95} \approx -0.48
$$

Interpretation:

- Magnitude: $|d| = 0.48$ (moderate effect)  
- Sign: negative, indicating lower CRP in the biologic group  

---

### g) Results Paragraph (Journal Style)

At 12 weeks, mean CRP was lower in the biologic group (3.2 mg/L) than in the methotrexate group (5.1 mg/L). An independent samples t-test indicated a statistically significant difference ($t = -2.05$, $p = 0.045$). However, Levene's test suggested unequal variances ($p = 0.027$); therefore, Welch's correction is recommended. The standardized mean difference was moderate ($|d| = 0.48$), consistent with lower CRP in the biologic group.

---

## Key Concepts Reviewed

### Standard Deviation (SD)

Measures variability within a group.

$$
SD = \sqrt{\frac{\sum (x_i - \bar{x})^2}{n - 1}}
$$

---

### Standard Error (SE)

$$
SE = \frac{SD}{\sqrt{n}}
$$

Represents variability of the sample mean across repeated samples.

---

### t-Statistic

$$
t = \frac{\text{Mean difference}}{\text{Standard error of the difference}}
$$

Indicates how many standard errors the observed difference is from 0.

---

### Levene's Test

Tests equality of variances across groups.

Null hypothesis:

$$
H_0: \sigma_A^2 = \sigma_B^2
$$

If $p < 0.05$, prefer Welch's t-test.

---

### Cohen's d

$$
d = \frac{\bar{X}_A - \bar{X}_B}{SD_{\text{pooled}}}
$$

Common benchmarks:

- 0.2 = small  
- 0.5 = medium  
- 0.8 = large  

Effect size describes magnitude, not statistical significance.