
**[Contact](#contact)**

<section class="hero">
  <img src="{{ site.baseurl }}/assets/img/portfolio_image.jpg" alt="Data Science Banner">
  <div class="hero__overlay">
    <div class="hero__content">
      <h1>Hasnaa Elidrissi</h1>
      <p>Data Science & Machine Learning </p>
        <p>fraud analytics · risk signals · storytelling</p>
      <p><a href="#projects" class="btn-sm">See projects</a></p>
    </div>
  </div>
</section>

<section class="section tile" markdown="1">
  
  Hi, I’m **Hasnaa Elidrissi** a **Data Analyst** pursuing my masters in **Data Science**🎓 passionate about solving problems with data.  
  I specialize in data analysis, machine learning, big data, and data storytelling transforming raw data into insights and communicating results with clarity.

---

## About Me 
- Academic background in Data Analytics & Data Science  
- Professional experience in fraud detection and risk analytics  
- Skilled in Python, SQL, Spark/PySpark, data visualization, and machine learning 
- Passionate about combining technical problem solving with clear reporting and communication 
<div class="profile">
  <!-- <img src="{{ site.baseurl }}/assets/img/profile.png" alt="Profile photo of Hasnaa Elidrissi"> -->
</div>
---

<section class="section tile" id="projects" markdown="1">
  
<h2> Featured Projects</h2>

<div class="cards">
  <article class="card" markdown="1">
<h3><a href="{{ site.baseurl }}/projects/Efficient-Fine-Tuning-for-motion-Classification">Efficient Fine-Tuning for Emotion Classification</a></h3>
<div class="badges">
  <span class="badge">NLP</span>
  <span class="badge">Transformer</span>
  <span class="badge">PEFT / LoRA</span>
  <span class="badge alt">Model Calibration</span>
</div>
Compared full and parameter-efficient fine-tuning (LoRA) of transformer models on the GoEmotions dataset to classify 28 nuanced emotions in Reddit comments.

**Outcome / Impact** 
- Applied temperature scaling to halve Expected Calibration Error (ECE).  
- Demonstrated efficient, interpretable, and deployable NLP modeling for real-world emotion analytics.
</article>

  <article class="card" markdown="1">
 <h3><a href="projects/fraud-detection">From Victim to Defender: Predictive Analytics for Fraud Detection </a></h3>
  <div class="badges">
    <span class="badge">ML</span>
    <span class="badge">Imbalanced Data</span>
    <span class="badge">Python</span>
    <span class="badge alt">Model Evaluation</span>
  </div>
  Applied machine learning to detect fraudulent transactions in a highly imbalanced dataset (≈0.13% positive class) with a focus on practical precision/recall trade-offs.

  **Outcome / Impact**
  - Random Forest balanced high precision with strong recall for real-world use.
  - Clear evaluation pipeline (PR/ROC, confusion matrix, threshold sensitivity).
  - Communicated operational trade-offs to minimize false positives.
  </article>

  <article class="card" markdown="1">
  <h3><a href="{{ site.baseurl }}/projects/early-warning-nlp">Early Warning NLP for Fraud Signals </a></h3>
  <div class="badges">
    <span class="badge">Text Mining</span>
    <span class="badge">Keyword/Topic Clusters</span>
    <span class="badge">Python</span>
    <span class="badge alt">Explainability</span>
  </div>
  Pipeline to surface early risk indicators from transaction memos and customer complaints; early clusters (e.g., “not authorized”, “fraudulent charges”) correlate with disputes.

  **Outcome / Impact**
  - Surfaced term clusters tied to dispute outcomes for proactive review.
  - Roadmap to scale data, improve interpretability, and explore multimodal.
  </article>

  <article class="card" markdown="1">
  <h3><a href="{{ site.baseurl }}/projects/amazon-sentiment"> Sentiment Analysis of Amazon Reviews </a></h3>
  <div class="badges">
    <span class="badge">NLP</span>
    <span class="badge">Classification</span>
    <span class="badge">TF-IDF</span>
    <span class="badge alt">SMOTE</span>
  </div>
  Predicted ratings from review text + metadata; identified drivers of satisfaction and dissatisfaction for product and marketing teams.

  **Outcome / Impact**
  - Strong predictive baseline; sentiment & helpfulness were key signals.
  - Practical guidance to monitor pain points and improve product feedback loops.
  </article>

  <article class="card" markdown="1">
<h3><a href="{{ site.baseurl }}/projects/nyc-urban-emotion/">Urban Emotion Geography: Mapping NYC’s 311 Mood</a></h3>

<div class="badges">
  <span class="badge">R</span>
  <span class="badge">NLP</span>
  <span class="badge">Sentiment Analysis</span>
  <span class="badge alt">Geospatial Analytics</span>
</div>

Analyzed NYC 311 complaints to map eight NRC emotion categories across boroughs, revealing unique “emotional fingerprints” through radar charts, heatmaps, and a borough-prediction model.

**Outcome / Impact**  
- Built an interpretable multinomial classifier using only emotional features.  
- Created portfolio-grade visualizations highlighting emotional inequality and borough-specific sentiment patterns.
</article>


  <article class="card" markdown="1">
  <h3><a href="{{ site.baseurl }}/projects/childcare-affordability"> Childcare Affordability & Workforce Participation</a></h3>
  <div class="badges">
    <span class="badge">EDA</span>
    <span class="badge">Data Storytelling</span>
    <span class="badge">Dashboards</span>
  </div>
  Analyzed affordability ratios vs. participation trends; presented insights for policy decision-making.

  **Outcome / Impact**
  - Showed link between higher childcare cost and lower participation.
  - Produced visuals and a narrative for non-technical stakeholders.
  </article>

  <article class="card" markdown="1">
  <h3><a href="{{ site.baseurl }}/projects/fraud-aml-architecture"> Real-Time Fraud Detection & AML Architecture</a></h3>
  <div class="badges">
    <span class="badge">Architecture</span>
    <span class="badge">Spark</span>
    <span class="badge">Kafka</span>
    <span class="badge alt">Hive / NiFi</span>
  </div>
  Designed scalable ingestion, storage, and detection pipelines for banking compliance and fraud monitoring.

  **Outcome / Impact**
  - End-to-end design from raw events to analytics/search layers.
  - Clear pathway to real-time scoring with enterprise tooling.
  </article>

  <article class="card" markdown="1">
  <h3><a href="{{ site.baseurl }}/projects/bilingual-brain-graphs"> Graph-Based Insights into the Bilingual Brain </a></h3>
  <div class="badges">
    <span class="badge">Python</span>
    <span class="badge">fMRI</span>
    <span class="badge">Graph Analysis</span>
    <span class="badge alt">Machine Learning</span>
  </div>
  <p>Open fMRI of Polish–English bilinguals. Built correlation-based functional graphs and applied explainable models to study network reorganization during speech.</p>
  <ul class="outcome">
    <li>Right-hemisphere somatomotor + salience networks more central during speech.</li>
    <li>L1 Logistic Regression: ~0.76 accuracy / 0.77 ROC–AUC (subject-wise CV).</li>
    <li>Interpretable brain-region contributions aligned with bilingual-control theory.</li>
  </ul>
  </article>

<article class="card" markdown="1">
<h3><a href="projects/eurosat-landuse">Satellite Land-Use Image Classifier (EuroSAT)</a></h3>
<div class="badges">
  <span class="badge">Computer Vision</span>
  <span class="badge">Transfer Learning</span>
  <span class="badge">Grad-CAM</span>

</div>
Built an interpretable deep-learning model that classifies ten land-use types 
(Residential, Industrial, Forest, River, etc.) from Sentinel-2 satellite RGB images 
using ResNet-50 / EfficientNet-B0 transfer learning and Grad-CAM visualization.

**Outcome / Impact**  
- Achieved **> 90 % accuracy** on balanced EuroSAT dataset.  
- Highlighted model attention on vegetation, water, and built areas for transparent predictions.  
- Demonstrated scalable, explainable outcome for **environmental monitoring and smart-city planning**.
</article>

</div>
</section>

<section class="section tile" markdown="1">

  
## Skills {#skills}
- **Programming & Tools:** Python, SQL, Spark/PySpark, R, Git/GitHub  
- **Data Analysis:** Data wrangling, exploratory data analysis (EDA), statistical testing 
- **Machine Learning:** Supervised & unsupervised learning, model evaluation, imbalanced data handling  
- **Big Data:** PySpark, Spark SQL, Hive, HDFS  
- **Visualization:** Tableau, Power BI, Matplotlib, Plotly  
- **Communication:** Reporting, presentations, data storytelling  

---

## Contact {#contact}
📧 Email: [elidrissihasnaa6@gmail.com](mailto:elidrissihasnaa6@gmail.com)  
💼 LinkedIn: [www.linkedin.com/in/hasnaa-elidrissi](https://www.linkedin.com/in/hasnaa-elidrissi)  
💻 GitHub: [github.com/Hasnaaelid](https://github.com/Hasnaaelid)  
📃 [Download my resume](){:.btn-sm}

---

</section>
