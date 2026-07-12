---
layout: page
title: "Project 1"
description: "Comparing Adaptive Gain Laws for a REWS Estimator"
img: assets/img/supervision/rews_estimator_results.jpg
importance: 1
category: supervision
---

**Students:** Adham Ahmed, Reza Azizollahi

**Supervisor:** Moein Sarbandi

**Date:** 2025

**Programme:** EU-CORE Master Programme, École Centrale de Nantes

Direct measurement of the rotor-effective wind speed (REWS) on a floating offshore wind
turbine is not possible in practice, yet it is a key input for both Region II torque/TSR
tracking and Region III pitch control. The adaptive second-order sliding-mode observer
(ASOSMO) used here — estimating REWS from rotor-speed measurement alone — is from my
own prior work (see related publication below). Under a fixed observer structure, fixed
controller, and identical OpenFAST (NREL 5 MW FOWT) conditions, the students' task was
to compare different **adaptive gain laws** used to tune that same observer.

**Main Reference:** Sarbandi, M., Viozelange, M., Hamida, M. A., and Plestan, F.:
*Wind speed estimation using second-order sliding-mode observers: simulation and
experimental validation on a floating offshore wind turbine*, Wind Energy Science, 11,
2405–2425, 2026. [DOI: 10.5194/wes-11-2405-2026](https://wes.copernicus.org/articles/11/2405/2026/wes-11-2405-2026.html)

The observation model and supertwisting-based estimator read as

$$
\dot{\mathbf{x}} = f(\mathbf{x}, \mathbf{u}) + \Delta(t), \qquad y = h(\mathbf{x}),
$$

$$
\dot{\hat{\mathbf{x}}} = f(\hat{\mathbf{x}}, \mathbf{u}) + \left[\frac{\partial \Phi}{\partial \hat{\mathbf{x}}}\right]^{-1} \begin{bmatrix} -K_1 |\hat{\omega}_r - \omega_r|^{1/2}\, \text{sign}(\hat{\omega}_r - \omega_r) \\ -K_2\, \text{sign}(\hat{\omega}_r - \omega_r) \end{bmatrix}.
$$

**Adaptive gain laws compared.** Four strategies for tuning $K_1, K_2$ were evaluated
under identical conditions:

$$
\textbf{Reference — 6-parameter ASTW (Shtessel et al., 2012):} \quad
\dot{K}_1 = \begin{cases} \omega_1 \sqrt{\dfrac{\gamma}{2}}\,\text{sign}(|\sigma| - \mu), & K_1 > K_m \\ \eta, & K_1 \le K_m \end{cases}, \qquad K_2 = 2\varepsilon K_1
$$

$$
\textbf{Constant parameter } \alpha: \quad K_1 = K_{1,0} + \alpha \ \text{(fixed offline, no online adaptation)}
$$

$$
\textbf{Self-tuning parameter } \bar{\mu}: \quad \dot{K}_1 = \omega_1 \sqrt{\dfrac{\gamma}{2}}\,\text{sign}(|\sigma| - \bar{\mu}), \qquad K_2 = 2\varepsilon K_1
$$

$$
\textbf{Auto-Tuning:} \quad K_1, K_2 \text{ adjusted online from an estimate of the perturbation bound, without manual parameter choice}
$$

*(Please verify these four against your slide — I reconstructed the general form from
the standard adaptive-STA literature matching your labels, not a pixel copy of the
embedded equation images.)*

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/supervision/rews_estimator_model.jpg" title="Observer model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The adaptive-gain observer model used as the fixed baseline for the comparison.
</div>

The students implemented and compared these gain strategies under matched wind/wave
conditions, evaluating estimation accuracy and robustness.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/supervision/rews_estimator_results.jpg" title="Estimation results across gain strategies" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of the constant-gain, self-tuning, 6-parameter reference, and auto-tuning
    strategies against the reference wind speed signal.
</div>

<a href="/assets/pdf/supervision/wind_speed_estimator_adaptive_gains.pdf" class="btn btn-sm z-depth-0" role="button" target="_blank">Download full presentation (PDF)</a>
