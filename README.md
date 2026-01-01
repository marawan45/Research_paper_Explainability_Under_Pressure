# Explainability Under Pressure  
A Study of XAI Methods on Imbalanced Data

## Overview
This repository supports an academic research study.
The study analyzes explainability under class imbalance.
The focus is explanation stability, not only accuracy.

The work targets high-risk classification tasks.
Fraud detection is the main use case.

## Research Motivation
Many real datasets are highly imbalanced.
Models may score well while explanations vary.
Unstable explanations reduce trust and safety.
This risk is often ignored in prior studies.

This project measures that risk directly.

## Research Questions
- How does imbalance affect model performance?
- How stable are SHAP and LIME explanations?
- Do models react differently to imbalance?
- Does explanation drift increase with severity?

## Dataset
Credit Card Fraud Detection dataset.
Each row is a transaction.
Labels are binary: normal or fraud.
Fraud cases are rare.

Only training data is resampled.
Test data remains unchanged.

## Imbalance Design
Five imbalance levels are used:
- 1:1 (balanced)
- 1:5
- 1:10
- 1:50
- 1:100

Random undersampling controls class ratios.
This isolates imbalance effects.

## Models
Three classifiers are evaluated.

- Logistic Regression  
  Linear baseline model.

- Random Forest  
  Non-linear ensemble model.

- XGBoost  
  Boosted tree model.

Hyperparameters are fixed.
This ensures fair comparison.

## Explainability Methods
Two post-hoc XAI methods are used.

- SHAP  
  Computes feature contribution values.

- LIME  
  Fits local surrogate models.

Explanations are generated multiple times.
This captures randomness and noise.

## Evaluation Metrics

### Performance Metrics
Metrics suited for imbalance are used.

- F1-score
- PR-AUC
- ROC-AUC
- Minority class recall

Accuracy is not reported.

### Explainability Metrics
Explanation quality is measured directly.

- Explanation Stability Score (ESS)  
  Measures ranking consistency.

- Feature Importance Drift (FID)  
  Measures top feature changes.

These metrics quantify explanation reliability.

## Experimental Procedure
1. Load and clean data.
2. Create imbalance levels.
3. Train models per level.
4. Evaluate performance.
5. Generate SHAP and LIME explanations.
6. Repeat explanations multiple times.
7. Compute stability metrics.
8. Save results and figures.

All steps are automated.

## Repository Structure
data/ Raw dataset
preprocessing/ Cleaned dataset
models/ Trained models
results/ Metrics and tables
plots/ Figures for the paper
xai/ Explanation artifacts


## Main Files
- Jupyter notebook with full pipeline
- Summary metrics CSV
- Saved model files
- Publication-ready plots

## Reproducibility
Random seeds are fixed.
Results can be reproduced.
All dependencies are standard.

## Intended Use
This code supports:
- Research papers
- Reproducibility checks

It is not production software.

## Citation
If you use this work, please cite the paper.
