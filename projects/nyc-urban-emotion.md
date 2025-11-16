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
This project turns one month of NYC 311 complaints into a city-wide emotional map.  
Using the NRC Emotion Lexicon and a multinomial model in R, I quantify how often residents express anger, trust, anticipation, and other emotions, then show how those patterns shift across boroughs. The result is an interpretable view of “how the city feels” and whether emotional tone alone can predict where a complaint came from.

---

## Dataset & Setup
- **Source:** NYC Open Data – 311 Service Requests  
- **Timeframe:** January 1–31, 2024  
- **Text Fields Used:** Complaint description (free-form text)  
- **Tools:** R, tidyverse, ggplot2, tidymodels, igraph  
- **Emotions Extracted (NRC):** anger, anticipation, disgust, fear, joy, sadness, surprise, trust + positive/negative valence  
- **Note:** All data is public, anonymized, and sourced from NYC’s open data portal.

---

## Approach in Three Steps

1. **Emotion scoring.**  
   - Tokenized complaint text and joined tokens to the NRC lexicon.  
   - Calculated per-complaint emotion counts, shares, and a simple sentiment score.

2. **Aggregation by borough.**  
   - Rolled emotion shares up to the borough level.  
   - Created “emotion fingerprints” to summarize each borough’s typical mix.

3. **Multinomial modeling.**  
   - Trained a multinomial logistic regression to predict borough using only emotion shares.  
   - Inspected coefficients to see which emotions *push* a complaint toward each borough.

---


## Visual Story

### 1. Emotion fingerprints by borough

Each radar chart below shows the share of emotion-tagged tokens for one borough.

![Borough-level emotion fingerprints]({{ site.baseurl }}/assets/img/emotion_fingerprints_borough.png)

**Takeaway.**  
Anticipation dominates 311 complaints citywide (people are mostly asking for action), but secondary emotions differ. Brooklyn leans more negative, Manhattan shows relatively more trust, Queens has higher anger/disgust, and Staten Island’s smaller volume skews toward anticipation and trust.

---

### 2. Emotional Inequality Index (EII)

To see which emotions are geographically uneven, I defined an **Emotional Inequality Index**: variance of borough shares, normalized by the squared mean.
  
![Emotional Inequality Index across boroughs]({{ site.baseurl }}/assets/img/emotional_inequality_index.png)

**Takeaway.**  
Surprise, anticipation, and disgust are the most unequal emotions across boroughs. Sadness is rare and fairly flat everywhere. High-EII emotions are good candidates for monitoring localized frustration or service gaps.

---

### 3. Can emotions predict borough?

I trained a multinomial model on emotion shares + sentiment and evaluated it with a confusion matrix.

![Heatmap of borough prediction confusion matrix]({{ site.baseurl }}/assets/img/borough_model_confusion_matrix.png)

**Takeaway.**  
The model does noticeably better than random, especially for high-volume boroughs. Most errors are between Manhattan, Brooklyn, and Queens—places that share similar complaint language. Emotions alone don’t give exact location, but they carry real geographic signal.

---
### 4. What drives the model?

To keep things interpretable, I plotted the strongest positive/negative coefficients per borough.

![Top predictive emotion coefficients (from the multinomial model)]({{ site.baseurl }}/assets/img/borough_model_top_emotion_coefficients.png)

**Takeaway.**  
- Higher anticipation and trust push complaints toward Manhattan.  
- Strong negative tone pushes away from Manhattan and toward Brooklyn/Queens.  
- Staten Island is influenced mostly by anticipation/trust due to its smaller, cleaner signal.

Together, these plots act as an “emotional fingerprint” not just descriptively, but from the model’s point of view.

---

## What I Learned

- How to build an end-to-end **text mining pipeline in R**: cleaning, tokenization, emotion tagging, aggregation.  
- How to design **interpretable models** where coefficients tell a story instead of hiding inside a black box.  
- How to create a custom metric (EII) to capture **geographic inequality in emotions**.  
- How to turn technical outputs into **visuals and language that non-technical stakeholders can understand**.

---

## Repository
- **Code:** 


