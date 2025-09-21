---
layout: default
title: "From Victim to Defender: Predictive Analytics for Fraud Detection"
permalink: /projects/fraud-detection/
---

[← Back to Home]({{ site.baseurl }}/)

# From Victim to Defender: Predictive Analytics for Fraud Detection

<div class="badges">
  <span class="badge">Python</span>
  <span class="badge">ML</span>
  <span class="badge">Imbalanced Data</span>
  <span class="badge alt">Evaluation</span>
</div>

**Summary.** Built a fraud classifier for credit card transactions to cut financial losses, protect customers, and reduce manual review load. Addressed extreme class imbalance and integrated the model into real-time monitoring for automatic flagging.

---

## Dataset & Setup
- **Sources:** Transaction logs (timestamp, amount, merchant), labeled historical frauds, customer behavior profiles, shared fraud patterns (industry consortium)
- **Notes:** Aggregated into a secure data lake; heavy class imbalance; leakage checks

## Approach
- **EDA:** fraud by type/merchant; spending frequency & amounts; geographic variance
- **Feature engineering:** transaction frequency, avg/median ticket, velocity, geo variance
- **Modeling:** baseline Logistic Regression → Decision Trees (interpretability) → **Ensemble** (stacked/averaged) for robustness; resampling (over/under) for balance
- **Validation:** stratified split; **Precision/Recall/F1** and **AUC-ROC** emphasized; threshold tuning

## Results
| Metric | Value (headline) |
|---|---:|
| Detection rate (recall on fraud) | **> 90%** identified |
| Precision / false positives | Tuned via thresholding for ops-friendly rates |
| Overall | Strong AUC-ROC; balanced F1 after resampling & ensembling |

**Visuals**
- Confusion matrix  
  ![Confusion Matrix]({{ site.baseurl }}/assets/img/projects/fraud-detection/cm.png)
- PR/ROC curves  
  ![ROC & PR]({{ site.baseurl }}/assets/img/projects/fraud-detection/roc_pr.png)

## Deployment
- **Real-time scoring** in the transaction stream; high-risk auto-flagged for review/hold, low-risk pass-through
- **Feedback loop:** analyst outcomes and customer feedback fed back for retraining

## Impact
- **Loss reduction** via early, accurate flags
- **Customer trust** improved (fewer missed frauds, fewer unnecessary declines)
- **Operational efficiency:** less manual triage, clearer alert quality

## Lessons & Next
- Data quality is king; **regular model refresh** to track evolving fraud
- Explore **federated learning** and **richer streaming features** (device, session, network)
- Add **explainability** slices for auditability and regulator transparency
