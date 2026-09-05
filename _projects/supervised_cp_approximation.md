---
layout: page
title: Data-Based Power-Coefficient Approximation for Floating Wind Turbines
description: Completed MSc project · EU-CORE · 2025
img: assets/img/supervision/cp_approximation_method.jpg
importance: 2
category: supervision
---

**Students:** Akbar Zai Jalil, Alam Sameer, and Adnan Nasir Isa<br>
**Supervisors:** Moein Sarbandi and Mohammad Mohammadi Shahir<br>
**Programme:** EU-CORE European Master Programme, École Centrale Nantes<br>
**Completed:** 2025

## Project focus

The aerodynamic power coefficient, $C_p$, is central to wind-turbine performance assessment and maximum-power-point tracking. This project investigated a data-based alternative to static analytical formulas and lookup tables by learning $C_p$ directly from high-fidelity OpenFAST simulation data.

## Methods and outcomes

The students trained and compared three regression approaches:

1. **Polynomial regression** for a smooth global approximation.
2. **Random forest regression** for nonlinear and noise-tolerant prediction.
3. **Radial basis function network** for accurate localized interpolation.

All three methods achieved strong agreement with the simulated reference data. The RBF model provided the best overall test-set accuracy and captured rapid variations in the power coefficient most effectively.

<div class="row">
  <div class="col-sm-6 mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/supervision/cp_approximation_models.jpg" title="Power-coefficient approximation models" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/supervision/cp_approximation_results.jpg" title="Power-coefficient approximation results" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">Compared model families and representative test-set predictions.</div>

**Related work:** M. Sarbandi, M. M. Shahir, M. A. Hamida, and F. Plestan, "Online Power Coefficient Estimation in Wind Turbines via Adaptive Sliding-Mode Observers," VSS 2026.

<a href="{{ '/assets/pdf/CpPDF.pdf' | relative_url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener">View project presentation (PDF)</a>
