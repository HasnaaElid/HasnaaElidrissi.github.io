---
layout: default
title: "Sentiment Analysis of Amazon Reviews"
permalink: /projects/amazon-sentiment/
---

[← Back to Home]({{ site.baseurl }}/)

# Sentiment Analysis of Amazon Reviews

<div class="badges">
  <span class="badge">NLP</span>
  <span class="badge">Classification</span>
  <span class="badge alt">TF-IDF/SMOTE</span>
</div>

**Summary.** Mined customer reviews to predict ratings and surface drivers of satisfaction/complaints, enabling teams to prioritize fixes and improve CX.

---

## Dataset & Setup
- **Kaggle** Amazon Product Reviews: text, ratings, helpfulness, timestamps
- **Preprocessing:** dropped redundant IDs; imputed missing; engineered **sentiment scores**, **TF-IDF**, **helpfulness ratio**; transformed timestamps
- **Imbalance:** addressed with **SMOTE** (for rating classes)

## Modeling & Evaluation
- Models tried: **Random Forest**, **XGBoost**, Logistic Regression
- Metrics: **Accuracy**, **F1**, **ROC-AUC** (multi-class via one-vs-rest)

## Results

| Metric    | Value   |
|---------:|---------:|
| Accuracy | **0.77** |
| ROC-AUC | **0.89** |

- Top predictors: **sentiment** and **helpfulness**; word count minimal
- EDA: 5-star skew; common positive terms (“love”, “great”), negative (“poor”, “bad”); rising review volume over time


## Reproducibility
- [View the Notebook]({{ site.baseurl }}/assets/docs/HasnaaElidrissiTermProjectMilestone3.html)

## Impact
- Identify systematic issues; prioritize product fixes and messaging
- Baseline for monitoring sentiment shifts by category/SKU

## Next
- Tune XGBoost; address mid-range (2–4 stars) confusion
- Better text handling (negation, sarcasm); consider **transformers**
- Multilingual expansion; human-in-the-loop validation

