---
layout: page
title: Adaptive-Gain Laws for Rotor-Effective Wind-Speed Estimation
description: Completed MSc project · EU-CORE · 2025
img: assets/img/supervision/rews_estimator_model.jpg
importance: 1
category: supervision
---

**Students:** Adham Ahmed and Reza Azizollahi<br>
**Supervisor:** Moein Sarbandi<br>
**Programme:** EU-CORE European Master Programme, École Centrale Nantes<br>
**Completed:** 2025

## Project focus

Rotor-effective wind speed (REWS) cannot be measured directly on a floating offshore wind turbine, although it is an important input for both below-rated torque control and above-rated pitch control. This project compared adaptive-gain strategies for a second-order sliding-mode observer that estimates REWS using rotor-speed measurements.

The students implemented three adaptive laws from the literature and a constant-gain baseline under identical OpenFAST conditions. The comparison focused on estimation accuracy, robustness, gain evolution, and sensitivity to turbulent wind and platform motion.

## Methods and outcomes

- NREL 5 MW floating wind-turbine model in OpenFAST
- Adaptive second-order sliding-mode observation
- Matched wind and wave scenarios for all gain strategies
- Quantitative comparison using RMSE, error variance, and normalized error measures

<div class="row">
  <div class="col-sm-6 mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/supervision/rews_estimator_model.jpg" title="REWS estimator project" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/supervision/rews_estimator_results.jpg" title="REWS estimation results" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">Project formulation and comparison of the estimator gain strategies.</div>

**Related publication:** M. Sarbandi, M. Viozelange, M. A. Hamida, and F. Plestan, "Wind Speed Estimation Using Second-Order Sliding-Mode Observers: Simulation and Experimental Validation on a Floating Offshore Wind Turbine," _Wind Energy Science_, 2026. [DOI](https://doi.org/10.5194/wes-11-2405-2026)

<a href="{{ '/assets/pdf/WindPDF.pdf' | relative_url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener">View project presentation (PDF)</a>
