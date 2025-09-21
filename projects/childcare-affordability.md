---
layout: default
title: "Childcare Affordability & Women’s Labor Participation"
permalink: /projects/childcare-affordability/
---

[← Back to Home]({{ site.baseurl }}/)

# Childcare Affordability & Women’s Labor Participation

<div class="badges">
  <span class="badge">EDA</span>
  <span class="badge">Dashboards</span>
  <span class="badge alt">Storytelling</span>
</div>

**Summary.** Analyzed how childcare cost burdens relate to female labor force participation (mothers with children under 6), using NDCP prices normalized by median household income (MHI). Built visual narrative (map, grouped bars, side-by-side normalization) to reveal affordability/participation inverse patterns.

---

## Dataset & Setup
- **Sources:** NDCP median childcare prices (infant/toddler/preschool) + **MHI**; **FLFPR** for mothers (20–64, child <6)
- **Key metric:** Affordability = childcare cost / MHI (by state)
- **Assumptions:** Full-time, annualized costs; unsubsidized market rates; state-level aggregation

## Findings
- **Infant care** is the costliest everywhere; often **2–6% of MHI** (many families still feel the pinch despite the 7% HHS benchmark)
- States with **higher affordability burdens** tend to have **lower maternal participation**
- Normalized comparisons (for top 10 least affordable) show clear inverse trend

**Visuals**
- Choropleth: state affordability disparities  
  ![Affordability Map]({{ site.baseurl }}/assets/img/projects/childcare-affordability/map.png)
- Grouped bars by care type; FLFPR line/column; normalized side-by-side chart  
  ![Charts]({{ site.baseurl }}/assets/img/projects/childcare-affordability/charts.png)

## Communication & Design
- Consistent palette (blue labor, teal cost, gray neutral), legible labeling, state abbreviations to reduce clutter
- Multiple deliverables: **interactive Tableau**, one-page **infographic**, and **slides** for policy briefings

## Ethics & Limits
- Public, PII-free data; documented transforms; normalized metrics labeled to avoid misinterpretation
- Urban/rural nuance and policy overlays (leave, subsidies, availability) not modeled in v1

## Impact
- Reframes affordability as an **economic participation** issue
- Clear narrative for **policy and planning** audiences

## Next
- Add richer **policy variables** (subsidies, availability, leave)
- **Time series** for pre/post-shock comparisons (e.g., COVID)
- Deeper causal exploration (instrumental variables / panel models)
