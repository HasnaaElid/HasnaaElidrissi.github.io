---
layout: default
title: "Satellite Land-Use Image Classifier (EuroSAT)"
permalink: /projects/eurosat-landuse/
---

[← Back to Home]({{ site.baseurl }}/)

# Satellite Land-Use Image Classifier (EuroSAT)

<div class="badges">
  <span class="badge">Python</span>
  <span class="badge">Computer Vision</span>
  <span class="badge">Transfer Learning</span>
</div>

**Summary.**  
Using Sentinel-2 RGB imagery from the public **EuroSAT** dataset, this project builds an interpretable deep-learning model that classifies **ten land-use and land-cover types** such as Residential, Industrial, Forest, and River.  
Through **transfer learning (ResNet-50 / EfficientNet-B0)** and **Grad-CAM visualization**, the analysis demonstrates how convolutional networks detect spatial patterns of vegetation, water, and built environments to support environmental monitoring.

---

## Dataset & Setup
- **Source:** [EuroSAT RGB (Helber et al., 2019)](https://madm.dfki.de/files/sentinel/EuroSAT.zip)  
  - ~27 000 images (64 × 64 RGB) across 10 balanced classes  
- **Classes:** Residential • Industrial • Highway • Forest • River • Pasture • Herbaceous • Sea/Lake • Annual Crop • Permanent Crop  
- **Tools:** TensorFlow / Keras, scikit-learn, matplotlib, seaborn, Python 3.11  
- **Hardware:** CPU or GPU (optional) — transfer learning converges quickly  
- **Ethics:** Publicly released dataset containing no PII; educational use only  

---

## Approach
- **Exploratory Analysis:**  
  Visualized a 4 × 4 grid of images and verified balanced class distribution and uniform brightness (≈ 0.42 ± 0.09).  

- **Baseline Model:**  
  - RGB color histograms (48-D) → Logistic Regression (L2)  
  - Validation accuracy ≈ 0.60 → color alone insufficient  

- **Transfer Learning Model:**  
  - Backbone: ResNet-50 (pre-trained ImageNet) + fine-tuned top layers  
  - Input size: 128 × 128 RGB  
  - Regularization: Dropout 0.2 • data augmentation  
  - Validation accuracy ≈ 0.93 • Test accuracy ≈ 0.91  

- **Explainability (Grad-CAM):**  
  Highlights model attention on vegetation for *Forest*, water for *River*, and rectilinear patterns for *Industrial*, aligning with human intuition.

---

## Results (Highlights)

| Model | Accuracy (val) | Notes |
|:--|:--:|:--|
| Logistic Regression (Color Histograms) | 0.60 | No spatial context |
| ResNet-50 (Transfer Learning) | 0.93 | Strong performance, interpretable |
| EfficientNet-B0 (Fine-tuned) | 0.94 | Slight gain, smaller footprint |

**Findings**
- Deep features capture spectral and spatial patterns unreachable by hand-crafted color stats.  
- Grad-CAM heatmaps confirm attention on semantically relevant regions, enhancing trust.  
- Most errors occur between *Residential* and *Industrial* classes.

---

## Visuals

| Figure | Description |
|:--|:--|
| ![Sample Tiles]({{ site.baseurl }}/assets/img/eurosat_samples.png) | **Sample Tiles.** Balanced examples from each class. |
| ![Confusion Matrix]({{ site.baseurl }}/assets/img/cm_val.png) | **Confusion Matrix.** Normalized validation results (ResNet-50). |
| ![Grad-CAM Overlay]({{ site.baseurl }}/assets/img/gradcam_overlay.png) | **Grad-CAM.** Model attention on vegetation for *Forest* class. |

---

## Interpretation
Transfer learning achieves > 90 % accuracy on small balanced remote-sensing datasets while remaining explainable via Grad-CAM.  
This supports the feasibility of lightweight, transparent AI for monitoring land-use change and urban expansion.

---

## Repository
- **Code:** [evolved-portfolio / 01_satellite-classifier on GitHub](https://github.com/HasnaaElid/evolved-portfolio/tree/main/01_satellite-classifier)  
- **PPT:** [Slides]({{ site.baseurl }}/assets/docs/EuroSAT_Project1_Slides.pdf)  
- **Artifacts:** `.h5`, `.tflite`, `.onnx`, Grad-CAM images in `artifacts/`

---

## References
- Helber, P. et al. (2019). *EuroSAT: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification.* IEEE JSTARS 12(7), 2217–2226.  
- Selvaraju, R. R. et al. (2017). *Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization.* ICCV.  
- Uddin, L. Q. (2015). *Salience Processing and Insular Cortical Function.* *Nature Reviews Neuroscience,* 16, 55–61.  

---
