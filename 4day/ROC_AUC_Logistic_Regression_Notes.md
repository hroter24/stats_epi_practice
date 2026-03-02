# ROC Curves and AUC --- Logistic Regression Notes

## 1. Foundations: The Confusion Matrix

For a binary outcome (e.g., disease vs no disease), logistic regression
produces predicted probabilities.\
To classify predictions into 0 or 1, we choose a threshold (often 0.5).

After classification, results fall into a 2×2 table:

                           Actual Positive       Actual Negative
  ------------------------ --------------------- ---------------------
  **Predicted Positive**   True Positive (TP)    False Positive (FP)
  **Predicted Negative**   False Negative (FN)   True Negative (TN)

### Definitions

-   **True Positive (TP)**: Model correctly predicts disease.
-   **False Positive (FP)**: Model predicts disease, but patient does
    not have it.
-   **False Negative (FN)**: Model predicts no disease, but patient
    actually has it.
-   **True Negative (TN)**: Model correctly predicts no disease.

------------------------------------------------------------------------

## 2. Key Rates Used in ROC Curves

### Sensitivity (True Positive Rate, TPR)

$$
\text{Sensitivity} = \frac{TP}{TP + FN}
$$

Interpretation:\
Among people who truly have the disease, how many did we correctly
detect?

------------------------------------------------------------------------

### Specificity

$$
\text{Specificity} = \frac{TN}{TN + FP}
$$

Interpretation:\
Among people without disease, how many did we correctly rule out?

------------------------------------------------------------------------

### False Positive Rate (FPR)

$$
\text{FPR} = 1 - \text{Specificity} = \frac{FP}{FP + TN}
$$

This is what appears on the x-axis of the ROC curve.

------------------------------------------------------------------------

## 3. How Thresholds Build the ROC Curve

Logistic regression outputs probabilities between 0 and 1.

Example predictions:

  Patient   Predicted Probability
  --------- -----------------------
  A         0.92
  B         0.81
  C         0.60
  D         0.40
  E         0.15

If threshold = 0.50\
→ classify A, B, C as positive

If threshold = 0.80\
→ classify A, B as positive

If threshold = 0.10\
→ almost everyone classified as positive

------------------------------------------------------------------------

## 4. What Happens When You Move the Threshold?

-   Very low threshold → Sensitivity ≈ 1, FPR ≈ 1\
-   Very high threshold → Sensitivity ≈ 0, FPR ≈ 0

The ROC curve is created by:

1.  Starting with threshold = 1\
2.  Gradually lowering it\
3.  Calculating TPR and FPR at each step\
4.  Plotting FPR (x-axis) vs TPR (y-axis)

------------------------------------------------------------------------

## 5. What AUC Actually Means

**AUC = Area Under the ROC Curve**

$$
\text{AUC} = P(\text{model ranks a random positive higher than a random negative})
$$

If AUC = 0.80:

There is an 80% probability that a randomly selected diseased patient
will receive a higher predicted probability than a randomly selected
non-diseased patient.

AUC measures discrimination, not calibration.

------------------------------------------------------------------------

## 6. Interpreting AUC Values

  AUC          Interpretation
  ------------ -------------------
  0.50         No discrimination
  0.60--0.70   Poor
  0.70--0.80   Acceptable
  0.80--0.90   Excellent
  \>0.90       Outstanding

------------------------------------------------------------------------

## 7. Clinical / Epidemiologic Framing

-   High sensitivity preferred when missing disease is dangerous\
-   High specificity preferred when false positives cause harm

The ROC curve shows all possible tradeoffs.

AUC summarizes overall discrimination, but threshold choice determines
clinical utility.

------------------------------------------------------------------------

## 8. What AUC Does NOT Tell You

-   It does NOT tell you the optimal threshold.
-   It does NOT measure calibration.
-   It does NOT reflect prevalence-adjusted performance.
-   It does NOT reflect clinical consequences.

------------------------------------------------------------------------

## 9. Conceptual Summary

-   Logistic regression → probabilities\
-   Threshold → classification\
-   Threshold movement → sensitivity/specificity pairs\
-   Plotting those pairs → ROC curve\
-   Area under that curve → AUC\
-   AUC = probability of correct ranking
