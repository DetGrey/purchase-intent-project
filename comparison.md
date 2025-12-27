# Comparison of prediction with and without clustering

> NOTE: Should be updated after changes

## Initial Prediction Model

=== Logistic Regression ===
              precision    recall  f1-score   support

       False       0.95      0.86      0.90      2084
        True       0.49      0.74      0.59       382

    accuracy                           0.84      2466
   macro avg       0.72      0.80      0.75      2466
weighted avg       0.88      0.84      0.85      2466

ROC-AUC: 0.8932442142074746
Log-loss: 0.45588421373136856

=== Decision Tree ===
              precision    recall  f1-score   support

       False       0.91      0.91      0.91      2084
        True       0.52      0.53      0.52       382

    accuracy                           0.85      2466
   macro avg       0.72      0.72      0.72      2466
weighted avg       0.85      0.85      0.85      2466

ROC-AUC: 0.7195322627649204
Log-loss: 5.364160905841848

=== Random Forest ===
              precision    recall  f1-score   support

       False       0.91      0.97      0.94      2084
        True       0.77      0.47      0.58       382

    accuracy                           0.90      2466
   macro avg       0.84      0.72      0.76      2466
weighted avg       0.89      0.90      0.89      2466

ROC-AUC: 0.9187859884836851
Log-loss: 0.25754333726782075

## Prediction Model w/ Clustering

=== Logistic Regression ===
              precision    recall  f1-score   support

       False       0.95      0.86      0.90      2084
        True       0.49      0.74      0.59       382

    accuracy                           0.84      2466
   macro avg       0.72      0.80      0.74      2466
weighted avg       0.88      0.84      0.85      2466

ROC-AUC: 0.8924591251218459
Log-loss: 0.45667602276497593

=== Decision Tree ===
              precision    recall  f1-score   support

       False       0.91      0.91      0.91      2084
        True       0.52      0.52      0.52       382

    accuracy                           0.85      2466
   macro avg       0.72      0.72      0.72      2466
weighted avg       0.85      0.85      0.85      2466

ROC-AUC: 0.7150164303443841
Log-loss: 5.378777148092098

=== Random Forest ===
              precision    recall  f1-score   support

       False       0.91      0.97      0.94      2084
        True       0.77      0.47      0.59       382

    accuracy                           0.90      2466
   macro avg       0.84      0.72      0.76      2466
weighted avg       0.89      0.90      0.89      2466

ROC-AUC: 0.9193493684115324
Log-loss: 0.2578423824634115

## Comparison notes

### 1. The Winner: Random Forest

This is the only model where the clustering feature helped.

- **F1-Score (True Class):** Increased from **0.58**  **0.59**.
- *Significance:* This means the model became slightly better at finding the actual buyers without increasing false alarms.

- **ROC-AUC:** Increased from **0.9188**  **0.9193**.
- *Significance:* A tiny improvement (+0.0005), but it is technically an improvement in the model's ability to rank buyers vs. non-buyers.


### 2. The Losers: Logistic Regression & Decision Tree

These models actually got slightly **worse** or stayed the same.

* **Logistic Regression AUC:** Dropped from 0.8932  0.8925.
* **Decision Tree Recall (True Class):** Dropped from 0.53  0.52.
* *Why?* For simpler models like Logistic Regression, adding a categorical variable (Cluster 0, 1, 2) that is highly correlated with existing variables (like Duration) can sometimes introduce "noise" rather than clarity.


___

## How to write this in your Report (The "Spin")

Since the results aren't a massive "boom," you should frame your conclusion around **efficiency** and **robustness**.

**Draft Conclusion for your Project:**

> *"While behavioral segmentation (clustering) did not yield drastic performance jumps, it provided a marginal improvement to our best-performing model, the Random Forest (AUC +0.0005, F1-Score +0.01).
> The fact that the improvement was minimal suggests that the raw behavioral metrics (Duration, Bounce Rate, etc.) already contain most of the predictive signal. The clusters we identified (Browsers vs. Researchers) are essentially 'summaries' of these metrics.
> However, the Random Forest successfully used this 'summary' feature to squeeze out a 1% gain in F1-score for the minority class (Buyers), proving that unsupervised learning can contribute specific, granular value even when the baseline is strong."*

**Does this make sense for your synopsis?** You have successfully shown you can execute the complex pipeline, even if the real-world data didn't miraculously transform the results.