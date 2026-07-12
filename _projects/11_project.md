---
layout: page
title: "Project 2"
description: "Data-Based Power Coefficient (Cp) Approximation for FOWTs — Supervised Master's Project, EU-CORE Programme"
img: assets/img/supervision/cp_approximation_method.jpg
importance: 2
category: supervision
---

**Students:** Akbar Zai Jalil, Alam Sameer, Adnan Nasir Isa

**Supervisors:** Moein Sarbandi, Mohammad Mohammadi Shahir

**Date:** 2025

**Programme:** EU-CORE Master Programme, École Centrale de Nantes

The power coefficient (Cp) is the primary indicator of a wind turbine's aerodynamic
efficiency and is central to Maximum Power Point Tracking, but traditional approaches
rely on static formulas or pre-computed lookup tables that cannot adapt to real-world
operating conditions. This project explored a data-driven alternative, learning Cp
directly from high-fidelity OpenFAST simulation data.

**Main Reference:** Sarbandi, M., Shahir, M. M., Hamida, M. A., and Plestan, F.:
*Online Power Coefficient Estimation in Wind Turbines via Adaptive Sliding-Mode
Observers*, 18th International Workshop on Variable Structure Systems (VSS2026),
Exeter, UK, 2026. (Accepted; DOI to be added once published.)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/supervision/cp_approximation_method.jpg" title="Data-driven approximation approach" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Moving from fixed analytical Cp models to a data-based approximation that captures
    the non-linear relationship between Cp, tip-speed ratio, and blade pitch angle.
</div>

The students trained and compared three regression models:

1. **Polynomial Regression** — a smooth analytical approximation that captures global
   Cp trends across the operating range.
2. **Random Forest Regression** — a tree-based ensemble method, robust to noise and to
   local nonlinearities in the Cp surface.
3. **Radial Basis Function (RBF) Network** — offers high accuracy for nonlinear
   mapping, particularly effective for smooth, localized data interpolation.

On the test set, these reached R² of 95.0%, 95.6%, and 95.9% respectively, with the
RBF model best capturing rapid dynamic fluctuations in Cp.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/supervision/cp_approximation_results.jpg" title="Actual vs. predicted Cp" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Actual vs. predicted power coefficient for the three trained models, showing strong
    agreement across the operating range.
</div>

<a href="/assets/pdf/supervision/cp_data_driven_approximation.pdf" class="btn btn-sm z-depth-0" role="button" target="_blank">Download full presentation (PDF)</a>
