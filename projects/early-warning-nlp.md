---
layout: default
title: "Early-Warning NLP for Financial Fraud"
permalink: /projects/early-warning-nlp/
---

[← Back to Home]({{ site.baseurl }}/)

# Early-Warning NLP for Financial Fraud

<div class="badges">
  <span class="badge">Python</span>
  <span class="badge">Text Mining</span>
  <span class="badge">Weak Supervision</span>
  <span class="badge alt">Explainability</span>
</div>

**Summary.** Detecting early indicators of fraud and scam activity from CFPB consumer complaint narratives using weak labeling and lightweight text models (TF-IDF + Logistic Regression). Privacy is preserved with HMAC pseudonymization for common PII patterns.

---

## Dataset & Setup
- **Source:** CFPB Consumer Complaint Database (public, opt-in narratives)
- **Privacy:** CFPB-redacted narratives; additional HMAC tokens for emails/phones/long numbers
- **Artifacts:** PR curves, confusion matrices, daily trends, topic summaries

## Approach
- **Labeling:** regex-based weak LFs for ATO, Zelle/P2P, Phishing, CNP  
- **Modeling:** TF-IDF (char/word n-grams) + Logistic Regression, precision-first thresholds  
- **Evaluation:** PR/F1, operating-point selection (target precision ≥ 0.75), confusion matrices

## Results (highlights)
- ATO, Zelle/P2P, and CNP reach target precision ≥ 0.75 on held-out validation
- Clear term importances and interpretable errors aid analyst triage
- Daily trend charts surface shifts in complaint patterns

---

## Repository
- **Code:** [fraud-early-warning-nlp GitHub](https://github.com/HasnaaElid/fraud-early-warning-nlp)
- **PPT:** [Slides]({{ site.baseurl }}/assets/docs/early-warning.pdf)


