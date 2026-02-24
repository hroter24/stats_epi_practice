# 📊 100-Day Epidemiologic Statistics Challenge  
## Day 3 – Categorical Data: Risk, Risk Ratio, Odds Ratio, and Chi-Square

---

## Scenario

You are evaluating 1-year incidence of serious infection among patients with inflammatory bowel disease treated with:

- Biologic Therapy
- Standard Immunomodulator

### Study Data

| Outcome      | Biologic | Standard |
|--------------|----------|----------|
| Infection    | 42       | 25       |
| No Infection | 358      | 375      |
| Total        | 400      | 400      |

---

# Solutions

---

## a) Risk in Each Group

Risk formula:

$$
Risk = \frac{\text{Number with outcome}}{\text{Total in group}}
$$

### Biologic Group

$$
Risk_{biologic} = \frac{42}{400} = 0.105 = 10.5\%
$$

### Standard Group

$$
Risk_{standard} = \frac{25}{400} = 0.0625 = 6.25\%
$$

---

## b) Effect Measures

### Risk Difference (RD)

$$
RD = 0.105 - 0.0625 = 0.0425
$$

Interpretation:  
There are 4.25 additional infections per 100 patients treated with biologic therapy compared to standard therapy.

---

### Risk Ratio (RR)

$$
RR = \frac{0.105}{0.0625} = 1.68
$$

Interpretation:  
Patients receiving biologic therapy had 1.68 times the risk of infection compared to those receiving standard therapy.

---

### Odds Ratio (OR)

Biologic odds:

$$
\frac{42}{358} = 0.117
$$

Standard odds:

$$
\frac{25}{375} = 0.0667
$$

$$
OR = \frac{0.117}{0.0667} = 1.76
$$

Interpretation:  
The odds of infection were 1.76 times higher in the biologic group compared to standard therapy.

Note: Because infection risk is ~10%, the OR slightly overestimates the RR.

---

## c) Chi-Square Test

### Null Hypothesis (H₀)

Infection status is independent of treatment group.

### Alternative Hypothesis (H₁)

Infection status differs by treatment group.

### What is being tested?

Whether observed infection frequencies differ from expected frequencies under independence.

### When use Fisher’s Exact Test?

When expected cell counts are less than 5.  
Here, all cells are large, so chi-square is appropriate.

---

## d) Interpretation if p = 0.04

The association is statistically significant at α = 0.05.

However, statistical significance does not imply causation.  
Causal interpretation depends on study design, confounding control, and temporality.

---

## e) Most Clinically Interpretable Measure

Because this is cohort-style incidence data, the Risk Ratio is most clinically interpretable.

RR reflects relative probability and is preferred when incidence can be directly estimated.

Odds ratios are primarily used in:
- Case-control studies
- Logistic regression modeling

---

# Core Concepts Reinforced

- Risk vs Odds distinction
- Absolute vs relative measures
- OR inflation when outcomes are common
- Chi-square tests independence of categorical variables
- Statistical significance does not imply causation
- RR preferred for cohort incidence data

---

# Key Epidemiologic Principle

When outcome incidence is low (<10%), the odds ratio approximates the risk ratio.  
As incidence increases, the odds ratio increasingly exaggerates the relative risk.

---

