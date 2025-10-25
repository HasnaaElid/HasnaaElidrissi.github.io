---
layout: default
title: "Graph-Based Insights into the Bilingual Brain"
permalink: /projects/bilingual-brain-graphs/
---

[← Back to Home]({{ site.baseurl }}/)

# Graph-Based Insights into the Bilingual Brain

<div class="badges">
  <span class="badge">Python</span>
  <span class="badge">fMRI</span>
  <span class="badge">Graph Analysis</span>
  <span class="badge alt">Machine Learning</span>
</div>

**Summary.**  
Using open fMRI data from Polish–English bilingual adults, this project applies graph theory and machine learning to study how the brain reorganizes during bilingual speech.  
Through correlation-based functional connectivity and explainable models, the analysis reveals how motor and attention networks coordinate when speaking in a non-native language.

---

## Dataset & Setup
- **Source:** [OpenNeuro ds004456 (Blasi et al., 2025)](https://doi.org/10.18112/openneuro.ds004456.v1.0.2)  
  - Forty-two Polish–English bilingual participants  
  - Tasks: *Alice* (reading aloud) vs *Articulation* (silent mouthing)
- **Atlas:** Schaefer-2018 (100 cortical parcels)
- **Tools:** NiLearn, NetworkX, scikit-learn, Python 3.11  
- **Ethics:** Publicly shared, anonymized data; educational analysis only

---

## Approach
- **Graph Construction:**  
  - Extracted time-series from 100 cortical regions  
  - Computed Pearson correlation matrices (189×100)  
  - Retained top-5 strongest connections per node for interpretability  
- **Graph Metrics:**  
  Degree (hubness), Betweenness (bridging), PageRank (global influence)  
- **Modeling:**  
  - Logistic Regression (L1/L2), Random Forest  
  - Subject-wise cross-validation (GroupKFold, n=5)  
  - Metrics: Accuracy, ROC–AUC  
- **Explainability:**  
  - Top coefficients mapped to brain regions  
  - Results interpreted via bilingual-control theory (Abutalebi & Green, 2013)

---

## Results (Highlights)
- **Network Findings:**  
  - Speech condition shows increased connectivity in right somatomotor and salience networks.  
  - Default-mode regions show reduced centrality, indicating stronger external focus.
    
- ## Modeling Performance

| Model                      | Accuracy | ROC–AUC | Notes                                                |
|---------------------------|:--------:|:-------:|------------------------------------------------------|
| Logistic Regression (L2)  |   0.45   |  0.38   | Weak global baseline                                 |
| Random Forest             |   0.28   |  0.26   | Overfit, low generalization                          |
| **L1 Logistic Regression**| **0.76** | **0.77**| Strongest, interpretable, right-lateralized control hubs |


---

## Visuals

| Figure                                                                                             | Description                                                                                       |
|----------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------|
| ![ROC Curve]({{ site.baseurl }}/assets/img/roc_l1_subjectwise.png) | **ROC Curve.** L1 Logistic Regression distinguishing *Alice* vs *Articulation* (AUC = 0.77). |
| ![Feature Importance]({{ site.baseurl }}/assets/img/coef_top_l1.png)| **Feature Importance.** Top predictive regions in somatomotor and salience networks. |
| ![Functional Graph (Alice)]({{ site.baseurl }}/assets/img/output_16_1.png) | **Functional Graph (Alice).** Nodes = cortical regions, edges = strongest co-fluctuations. |

---

## Interpretation
The results show that bilingual speech increases the coordination between **motor**, **salience**, and **executive-control** networks-especially in the right hemisphere.  
These findings align with bilingual control models, suggesting that speech hesitation reflects **neural coordination cost**, not linguistic deficiency.  
Graph-based modeling thus provides an interpretable, data-driven view of how the bilingual brain manages language switching under cognitive load.

---

## Repository
- **Code:** [bilingual-brain-graphs GitHub](https://github.com/HasnaaElid/bilingual-brain-graphs)   
- **PPT:** [Slides]({{ site.baseurl }}/assets/docs/Bilingual_Brain_Presentation.pdf)

---

## References
- Abutalebi, J., & Green, D. W. (2013). *Neural mechanisms of bilingual language control.* *Frontiers in Psychology, 4*, 399.  
- Bullmore, E., & Sporns, O. (2009). *Complex brain networks: Graph theoretical analysis of structural and functional systems.* *Nature Reviews Neuroscience, 10*, 186–198.  
- Blasi, V., et al. (2025). *OpenNeuro ds004456: Bilingual speech production dataset (v1.0.2).* [DOI](https://doi.org/10.18112/openneuro.ds004456.v1.0.2)  
- Uddin, L. Q. (2015). *Salience processing and insular cortical function and dysfunction.* *Nature Reviews Neuroscience, 16*, 55–61.

---
