---
layout: default
title: "Real-Time Fraud Detection & AML Architecture"
permalink: /projects/fraud-aml-architecture/
---

[← Back to Home]({{ site.baseurl }}/)

# Real-Time Fraud Detection & AML Architecture

<div class="badges">
  <span class="badge">Architecture</span>
  <span class="badge">Spark</span>
  <span class="badge">Kafka</span>
  <span class="badge alt">Hive/NiFi/Solr</span>
</div>

**Summary.** Designed a modular, scalable platform for **real-time fraud detection** and **AML compliance**—from ingestion to analytics and audit.

---

## Problem Context
- Rising fraud complexity (card abuse, identity theft, AML typologies)
- Batch-only/manual workflows can’t keep up; response time impacts losses, CX, and compliance

## High-Level Design
- **NiFi** → ingest from apps/ATMs/cores
- **Kafka** → streaming backbone to consumers (Actimize/rules, Spark, storage)
- **Spark + Hive** → large-scale analytics & pattern discovery
- **HBase** → behavior profiles (entity-centric features)
- **NoSQL** → scoring metadata for APIs/dashboards
- **Solr** → fast search for flagged transactions & audit trails
- **Jupyter + Spark** → analyst notebooks and ad hoc exploration

## Capabilities Delivered
- **Real-time scoring & alerts** (Kafka + rules/ML)
- **Behavior analytics** (HBase + Spark)
- **Compliance & auditability** (Hive + Solr; explainable signals)
- **Scalability** by design; modular services

- [View Architecture]({{ site.baseurl }}/assets/docs/DSC650HasnaaELidrissiWeek10_.pdf)

## Impact
- Faster detection, fewer losses
- Clear, auditable decisions supporting AML obligations
- Foundation for continuous model improvement

## Next
- Feature store standardization; model registry & CI/CD
- Stream enrichment (device, geo, network)
- Monitoring: drift, stability, and alert quality
