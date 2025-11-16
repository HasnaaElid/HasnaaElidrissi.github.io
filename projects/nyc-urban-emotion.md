---
layout: default
title: "Urban Emotion Geography: Mapping NYC’s 311 Mood"
permalink: /projects/nyc-urban-emotion/
---

[← Back to Home]({{ site.baseurl }}/)

# Urban Emotion Geography: Mapping NYC’s 311 Mood

<div class="badges">
  <span class="badge">R</span>
  <span class="badge">Text Mining</span>
  <span class="badge">NLP</span>
  <span class="badge">Sentiment Analysis</span>
  <span class="badge alt">Machine Learning</span>
</div>

**Summary.**  
This project transforms NYC 311 complaints into a city-wide emotional map, showing how frustration, trust, anticipation, and other emotions vary across boroughs.  
Using tidyverse workflows, the NRC Emotion Lexicon, and a multinomial model, the analysis exposes distinct “emotional fingerprints” for each borough and evaluates how well emotion alone predicts geographic location.

---

## Dataset & Setup
- **Source:** NYC Open Data – 311 Service Requests  
- **Timeframe:** January 1–31, 2024  
- **Text Fields Used:** Complaint description (free-form text)  
- **Tools:** R, tidyverse, ggplot2, tidymodels, igraph  
- **Emotions Extracted (NRC):** anger, anticipation, disgust, fear, joy, sadness, surprise, trust + positive/negative valence  
- **Note:** All data is public, anonymized, and sourced from NYC’s open data portal.

---

## Project Goals
- Quantify the emotional landscape of NYC 311 complaints  
- Compare emotional patterns across boroughs  
- Develop interpretable visualizations for storytelling  
- Train a multinomial model predicting borough from emotion shares  
- Introduce a new metric: **Emotional Inequality Index (EII)**  
- Visualize emotional “fingerprints” for each borough

---

## Workflow

### **1. Data Cleaning & Tokenization**
- Lowercasing, whitespace cleanup  
- Tokenization with tidytext  
- Merging each token with NRC emotion categories  
- Counting emotion-tagged tokens per complaint  

### **2. Emotion Aggregation**
Computed for each complaint and then for each borough:
- total tokens  
- positive / negative sentiment  
- 8 basic emotions  
- emotion share: proportion of tokens labeled with that emotion  

### **3. Visualization**
![Borough-level emotion fingerprints]({{ site.baseurl }}/assets/img/emotion_fingerprints_borough.png)
  
![Emotional Inequality Index across boroughs]({{ site.baseurl }}/assets/img/emotional_inequality_index.png)

![Heatmap of borough prediction confusion matrix]({{ site.baseurl }}/assets/img/borough_model_confusion_matrix.png)

![Top predictive emotion coefficients (from the multinomial model)]({{ site.baseurl }}/assets/img/borough_model_top_emotion_coefficients.png)

### **4. Modeling**
A multinomial logistic regression was trained to answer:
> *Can we guess which borough a complaint came from based only on its emotional profile?*

Outputs include:
- Confusion matrix  
- Per-emotion coefficients  
- Borough-specific emotional drivers  

---
## Repository
- **Code:** 

## Key Findings

### **Distinct Emotional Signatures**
Each borough expresses a unique emotional fingerprint

