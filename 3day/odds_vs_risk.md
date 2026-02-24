# Risk vs Odds and Interpreting Odds Ratios

## Risk (Probability)

Risk is the proportion of individuals who experience an event.

$$
\text{Risk} = \frac{\text{Number with event}}{\text{Total population}}
$$

Example: If 20 out of 100 patients develop infection:

$$
\text{Risk} = \frac{20}{100} = 0.20
$$

Interpretation: 20% of patients developed infection.

---

## Odds

Odds compare the number with the event to the number without the event.

$$
\text{Odds} = \frac{\text{Number with event}}{\text{Number without event}}
$$

Using the same example:

$$
\text{Odds} = \frac{20}{80} = 0.25
$$

Risk uses the total population as the denominator.  
Odds use only the non-events as the denominator.

When outcomes are rare (roughly <10%), odds and risk are very similar.  
When outcomes are common, odds become noticeably larger than risk.

---

## Converting Between Risk and Odds

From probability to odds:

$$
\text{Odds} = \frac{p}{1 - p}
$$

From odds to probability:

$$
p = \frac{\text{Odds}}{1 + \text{Odds}}
$$

---

## Odds Ratios (OR)

An odds ratio compares the odds of an outcome between two groups.

$$
\text{OR} = \frac{\text{Odds in Group 1}}{\text{Odds in Group 2}}
$$

If $\text{OR} = 3$, interpretation:

- The **odds** of the outcome are 3 times higher in Group 1 than Group 2.
- This does **not** mean the probability (risk) is tripled.

For rare outcomes, the odds ratio can approximate the risk ratio.  
For common outcomes, the odds ratio can substantially overstate the relative risk.

---

## Key Takeaways

- Risk = event / total  
- Odds = event / non-event  
- OR compares odds between groups (not probability)  
- OR approximates RR only when the outcome is rare