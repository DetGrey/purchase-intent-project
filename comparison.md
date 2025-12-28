# Comparison of prediction with and without clustering

## Random Forest vs Tuned vs With Clusters

**=== Random Forest ===**
              precision    recall  f1-score   support

           0       0.90      0.98      0.94      2084
           1       0.79      0.40      0.53       382

    accuracy                           0.89      2466
   macro avg       0.84      0.69      0.74      2466
weighted avg       0.88      0.89      0.88      2466

Optimal Threshold: 0.5500
ROC-AUC: 0.9187859884836851
Log-loss: 0.25754333726782075

**=== Tuned Random Forest ===**
              precision    recall  f1-score   support

           0       0.97      0.86      0.91      2084
           1       0.53      0.84      0.65       382

    accuracy                           0.86      2466
   macro avg       0.75      0.85      0.78      2466
weighted avg       0.90      0.86      0.87      2466

Optimal Threshold: 0.3961
ROC-AUC: 0.9224432474801781
Log-loss: 0.2987712181596724

**=== Tuned Random Forest With Clusters ===**
              precision    recall  f1-score   support

           0       0.96      0.86      0.91      2084
           1       0.53      0.82      0.64       382

    accuracy                           0.86      2466
   macro avg       0.74      0.84      0.78      2466
weighted avg       0.90      0.86      0.87      2466

Optimal Threshold: 0.4016
ROC-AUC: 0.9191521540332224
Log-loss: 0.3020886686784614

## Comparison notes

Clustering shows Feature Redundancy.

The Clusters are just "Summaries": You created the clusters using variables like PageValues, Duration, and BounceRates.

The Random Forest is Smart: Random Forest is a powerful, non-linear model. It can already look at PageValues and Duration and figure out who the "High Value" users are.

The Result: When you added the "Cluster" column, you didn't give the model any new information. You just gave it a "noisy summary" of information it already had. Instead of helping, this extra variable essentially distracted the model slightly.