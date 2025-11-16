---
layout: default
title: "Data Quality Radar with PySpark"
permalink: /projects/data-quality-radar/
---

[← Back to Home]({{ site.baseurl }}/)

# Data Quality Radar (PySpark)

<div class="badges">
  <span class="badge">PySpark</span>
  <span class="badge">Big Data</span>
  <span class="badge">Data Quality</span>
  <span class="badge alt">Automation</span>
</div>

**Summary.**  
A production-style PySpark pipeline that profiles tabular data, detects schema drift, monitors missingness, analyzes numeric distribution changes, and simulates daily snapshot ingestion.  
Built using the Kaggle *Credit Card Fraud Detection* dataset, partitioned into synthetic “historical” and “current” snapshots.

---

## Project Motivation
Data reliability issues often appear *before* downstream teams notice.  
This project builds a **lightweight, Spark-based data quality monitor** that can be scheduled daily and raises alerts for:

- added/removed columns  
- type or nullability changes  
- sudden spikes in missing data  
- large shifts in numeric behavior (e.g., mean, stddev)

This mirrors the early-warning systems used in enterprise data engineering and fraud platforms.

---

## Dataset
- **Source:** Kaggle *Credit Card Fraud Detection* (`creditcard.csv`)  
- ~284k rows, 30 features  
- Mixed numeric + time-based columns  
- Partitioned into:
  - `snapshot_date=20240101`
  - `snapshot_date=20240201`  
  using median time as the split boundary

---


