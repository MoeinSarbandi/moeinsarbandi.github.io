---
layout: page
title: "Comparing Adaptive Gain Laws for a REWS Estimator"
description: "Supervised Master's Project — EU-CORE Programme"
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
own prior work (see main reference below). Under a fixed observer structure, fixed
controller, and identical OpenFAST (NREL 5 MW FOWT) conditions, the students' task was
to compare three adaptive gain laws from the literature used to tune that same observer,
alongside a non-adaptive constant-gain baseline.

**Main Reference:** Sarbandi, M., Viozelange, M., Hamida, M. A., and Plestan, F.:
*Wind speed estimation using second-order sliding-mode observers: simulation and
experimental validation on a floating offshore wind turbine*, Wind Energy Science, 11,
2405–2425, 2026. [DOI: 10.5194/wes-11-2405-2026](https://wes.copernicus.org/articles/11/2405/2026/wes-11-2405-2026.html)

The observation model and supertwisting-based estimator read as

$$
\dot{\mathbf{x}} = f(\mathbf{x}, \mathbf{u}) + \Delta(t), \qquad y = h(\mathbf{x}),
$$

$$
\dot{\hat{\mathbf{x}}} = f(\hat{\mathbf{x}}, \mathbf{u}) + \left[\frac{\partial \Phi}{\partial \hat{\mathbf{x}}}\right]^{-1} \begin{bmatrix} -k_1 |\sigma|^{1/2}\, \text{sgn}(\sigma) \\ -k_2\, \text{sgn}(\sigma) \end{bmatrix}, \qquad \sigma = \hat{\omega}_r - \omega_r.
$$

**Three adaptive gain laws were compared for tuning $k_1, k_2$** (with $\psi = -\dot{\sigma}$, obtained via the online differentiator $\frac{s}{1+\tau s}$), alongside a non-adaptive constant-gain baseline:

1. **Shtessel et al. (2012) — reference adaptive law (6 parameters).**
   *(equation to be added once confirmed — see note below)*

2. **Mirzaei et al. (2022) — Self-Tuning ASTW (1 parameter + differentiator).**

   $$
   \dot{k}_1 = \begin{cases} \dfrac{\bar\mu}{|\psi|+\varepsilon}, & |\sigma|>\varepsilon \\[4pt] -k_1, & |\sigma|\le\varepsilon \end{cases}
   \qquad
   \dot{k}_2 = \begin{cases} \dfrac{\bar\mu}{2|\sigma|^{1/2}}, & |\sigma|>\varepsilon \\[4pt] -k_2, & |\sigma|\le\varepsilon \end{cases}
   $$

   $$
   \bar\mu = |k_1||\sigma|^{1/2} + |\psi| + |w|, \qquad \dot{w} = k_2\,\text{sgn}(\sigma)
   $$

3. **Mirzaei et al. (2024) — Auto-Tuning ASTW (0 parameters + differentiator).**

   $$
   \dot{k}_1(t) = \begin{cases} \dfrac{\alpha(t)}{|\psi|+\epsilon(t)}, & |\sigma(t)|>\epsilon(t) \\[4pt] -k_1(t), & |\sigma(t)|\le\epsilon(t) \end{cases}, \quad k_1(0)=k_{01}>0
   $$

   $$
   \dot{k}_2(t) = \begin{cases} \dfrac{\alpha(t)}{2|\sigma(t)|^{1/2}}, & |\sigma(t)|>\epsilon(t) \\[4pt] -k_2(t), & |\sigma(t)|\le\epsilon(t) \end{cases}, \quad k_2(0)=k_{02}>0
   $$

   $$
   \alpha(t) = k_1(t)|\sigma(t)|^{1/2} + |\psi| + |\Gamma_a|, \qquad
   \epsilon(t) = \left[\alpha(t) + |\psi| + w(t-T_e)\right]\cdot T_e + k_2(t)\cdot T_e^2
   $$

   $$
   \dot{\Gamma}_a = k_2(t)\,\text{sgn}(\sigma(t)), \qquad \Gamma_a(0)=0
   $$

*(Formula for the Shtessel et al. (2012) reference law will be added once confirmed against the original slide.)*

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/supervision/rews_estimator_model.jpg" title="Observer model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The adaptive-gain observer model used as the fixed baseline for the comparison.
</div>

The students implemented and compared these gain strategies, plus a constant-gain
baseline, under matched wind/wave conditions, evaluating estimation accuracy and
robustness.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/supervision/rews_estimator_results.jpg" title="Estimation results across gain strategies" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of the constant-gain baseline against the three adaptive gain laws,
    versus the reference wind speed signal.
</div>

<a href="/assets/pdf/supervision/wind_speed_estimator_adaptive_gains.pdf" class="btn btn-sm z-depth-0" role="button" target="_blank">Download full presentation (PDF)</a>
