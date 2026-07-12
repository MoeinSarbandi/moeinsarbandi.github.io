---
layout: page
title: "Comparison of Adaptive Gain Laws for a Rotor-Effective Wind Speed Estimator"
description: "Supervised Master's Project — EU-CORE Programme"
img: assets/img/supervision/rews_estimator_results.jpg
importance: 1
category: supervision
---

**Students:** Adham Ahmed, Reza Azizollahi
**Supervisor:** Moein Sarbandi
**Programme:** EU-CORE Master Programme, École Centrale de Nantes

Direct measurement of the rotor-effective wind speed (REWS) on a floating offshore wind
turbine is not possible in practice, yet it is a key input for both Region II torque/TSR
tracking and Region III pitch control. This project compared adaptive gain strategies for
a second-order sliding-mode observer (SOSMO) used to estimate REWS, addressing the
platform-motion nonlinearities and turbulence/wave-induced uncertainty that make
LiDAR- and learning-based alternatives less attractive for this task.

**Related publication:** Sarbandi, M., Viozelange, M., Hamida, M. A., and Plestan, F.:
*Wind speed estimation using second-order sliding-mode observers: simulation and
experimental validation on a floating offshore wind turbine*, Wind Energy Science, 11,
2405–2425, 2026. [DOI: 10.5194/wes-11-2405-2026](https://wes.copernicus.org/articles/11/2405/2026/wes-11-2405-2026.html)

The reduced-order observation model and the supertwisting-based estimator read as

$$
\dot{\mathbf{x}} = f(\mathbf{x}, \mathbf{u}) + \Delta(t), \qquad y = h(\mathbf{x}),
$$

$$
f(\mathbf{x}, \mathbf{u}) = \left[ \frac{1}{J}\left( \frac{\rho \pi R^3 v_r^2}{2\lambda} C_p(\lambda,\beta) - n_g \tau_g \right) \quad 0 \right]^\top, \qquad \Delta(t) = \left[ \delta(t) \quad f_v(t) \right]^\top,
$$

where the students' contribution was the adaptive-gain observer

$$
\dot{\hat{\mathbf{x}}} = f(\hat{\mathbf{x}}, \mathbf{u}) + \left[\frac{\partial \Phi}{\partial \hat{\mathbf{x}}}\right]^{-1} \begin{bmatrix} -K_1 |\hat{\omega}_r - \omega_r|^{1/2}\, \text{sign}(\hat{\omega}_r - \omega_r) \\ -K_2\, \text{sign}(\hat{\omega}_r - \omega_r) \end{bmatrix},
$$

dynamically adjusting $K_1$ and $K_2$ to prevent overestimation and mitigate chattering.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/supervision/rews_estimator_model.jpg" title="Observer model and adaptive-gain contribution" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The observer-based estimation model, with adaptive gains introduced to dynamically
    adjust the sliding-mode gains, preventing overestimation and mitigating chattering.
</div>

The students implemented and compared three gain strategies — a constant parameter,
a self-tuning parameter, and a fully auto-tuning scheme (six tuning parameters) — and
evaluated estimation accuracy and robustness across operating conditions.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/supervision/rews_estimator_results.jpg" title="Estimation results across gain strategies" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of the constant-gain, self-tuning, and auto-tuning strategies against the
    reference wind speed signal.
</div>

<a href="/assets/pdf/supervision/wind_speed_estimator_adaptive_gains.pdf" class="btn btn-sm z-depth-0" role="button" target="_blank">Download full presentation (PDF)</a>
