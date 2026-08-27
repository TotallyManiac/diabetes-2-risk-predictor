# Model Artifacts

| Artifact | Estimator | Key parameters | Input features |
|---|---|---|---|
| `best_rf.pkl` | Random Forest | `n_estimators=500`, `max_depth=5`, `random_state=42` | BMI, Age, HighBP, HighChol |
| `final_svm.pkl` | SVM (SVC) | `C=0.1`, `gamma=0.01`, `probability=True` | BMI, Age, HighBP, HighChol |

These pickled estimators were created with **scikit-learn 1.7.2**, which is pinned in `requirements.txt`.

## Reproducibility limitation

The original fitted preprocessing/scaler artifact was not supplied. The estimators therefore expect four already-preprocessed inputs. A stronger deployment implementation would save the fitted preprocessor and estimator together as one `Pipeline`.

> Only load pickle files from trusted sources.
