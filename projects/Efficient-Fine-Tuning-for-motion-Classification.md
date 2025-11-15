---
layout: default
title: "Efficient Fine-Tuning for Emotion Classification "
permalink: /projects/Efficient-Fine-Tuning-for-motion-Classification
---

[← Back to Home]({{ site.baseurl }}/)


# Efficient Fine-Tuning for Emotion Classification  
Python NLP | Transformer Fine-Tuning | Model Calibration  

## Summary  
Using the **GoEmotions** dataset of Reddit comments, this project compares **Full Fine-Tuning** and **Parameter-Efficient Fine-Tuning (PEFT)** via **LoRA adapters** on a multi-label emotion classification task.  
The analysis quantifies trade-offs between performance, efficiency, and calibration demonstrating that LoRA achieves near-parity with full fine-tuning while updating less than 10% of parameters.  

---

## Dataset & Setup  
**Source:** Google Research – [GoEmotions]([https://github.com/google-research/goemotions](https://research.google/blog/goemotions-a-dataset-for-fine-grained-emotion-classification/))  
**Samples:** 58k Reddit comments annotated for 28 fine-grained emotions  
**Labels:** Multi-label (average 1.3 emotions per comment)  
**Models:** distilbert-base-uncased,roberta-base (optional variant)  
**PEFT:** LoRA (r = 8, α = 16, dropout = 0.05)  
**Tools:** PyTorch, Hugging Face Transformers & PEFT, NumPy, Pandas, Matplotlib  
**Ethics:** Public Reddit corpus; anonymized and filtered for non-toxic content; educational use only  

---

## Approach  
**Pipeline Overview**  
1. **Data Preprocessing** – Convert raw GoEmotions splits into Parquet format with one-hot encoded labels.  
2. **Modeling** –  
   - *Full Fine-Tuning:* All parameters updated.  
   - *LoRA Fine-Tuning:* Trainable low-rank adapters injected into attention & feed-forward layers.  
3. **Evaluation Metrics** – Micro-/Macro-F1, per-label precision-recall AUC, Expected Calibration Error (ECE).  
4. **Calibration** – Per-label temperature scaling and reliability curves (Guo et al., 2017).  
5. **Explainability** – Per-label threshold analysis and token-level SHAP inspection (optional extension).  

---

## Results (Highlights)

### Performance Summary
<img width="1377" height="115" alt="image" src="https://github.com/user-attachments/assets/c600b27b-04fb-4f5e-8baf-e5df61d8c17f" />

### Visuals

![f1_vs_params]({{ site.baseurl }}/assets/img/f1_vs_params.png) 

![macro_f1_vs_params]({{ site.baseurl }}/assets/img/macro_f1_vs_params.png) 

![pr_auc_topk_full_vs_peft]({{ site.baseurl }}/assets/img/pr_auc_topk_full_vs_peft.png) 

---

## Interpretation 

The explainability results show that both models rely on meaningful emotional cues rather than noise or filler words.
Influential tokens consistently align with human intuition, with positive or negative emotion words driving predictions appropriately.
Token masking and SHAP-style analyses reveal stable, interpretable patterns across examples.
The LoRA model highlights nearly the same key tokens as the full fine-tuned model, indicating it preserves core decision logic.
Overall, the compact model remains trustworthy and behaviorally aligned while using far fewer trainable parameters.

---

## Repository  
**Code:** [goemotions-peft](https://github.com/HasnaaElid/Efficient-Fine-Tuning-for-Emotion-Classification) 

**Slides:** [Presentation (PDF)](assets/docs/SanaEssafi_DSC680_Project3.pdf) 

**Dataset:** [GoEmotions on Hugging Face](https://huggingface.co/datasets/go_emotions)  

---

## References  
- Hu et al. (2021). *LoRA: Low-Rank Adaptation of Large Language Models.* arXiv:2106.09685  
- Guo et al. (2017). *On Calibration of Modern Neural Networks.* ICML 2017.  
- Google Research (2020). *GoEmotions: A Dataset of Fine-Grained Emotions.*  
- Hugging Face Documentation (2024). *Transformers & PEFT Libraries.*

---

> “Efficient fine-tuning isn’t just faster—it’s how we make large models practical, interpretable, and sustainable.”  
