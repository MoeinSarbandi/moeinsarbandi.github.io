---
layout: course
title: NOLCO — Nonlinear Control Lab for Wind Turbines
description: A two-part lab on nonlinear control design for variable-speed wind turbines, covering aerodynamic torque/pitch control and PMSG electrical control, from feedback linearization to sliding mode and super-twisting algorithms.
instructor: Moein Sarbandi, Prof. Franck Plestan
year: 2025
term: Fall
location: École Centrale de Nantes — EU-CORE Master Programme
time: TBD
course_id: nolco
schedule:
  - week: 1
    date: TBD
    topic: "Part I — Aerodynamic control"
    description: Nonlinear model of the aerodynamic subsystem, region-III power regulation, input-output linearization, and robustness under disturbances. Progresses to first-order sliding mode control with an equivalent control term, a dynamic-gain variant, and a super-twisting algorithm to reduce chattering.
    materials:
      - name: Lab subject (Parts I & II)
        url: /assets/pdf/teaching/nolco/lab_subject.pdf

  - week: 2
    date: TBD
    topic: "Part II — Electrical part control (PMSG)"
    description: Introduces the permanent-magnet synchronous generator model and couples it with the aerodynamic subsystem. Covers input-output linearization for full electro-mechanical control, robustness to parameter uncertainty, and an adaptive super-twisting controller with a tuned adaptation law.
    materials:
      - name: Lab subject (Parts I & II)
        url: /assets/pdf/teaching/nolco/lab_subject.pdf
---

## Course Overview

NOLCO is a hands-on lab for the EU-CORE Master Programme (European Master on Control of Renewable Energy Systems), focused on designing nonlinear controllers for variable-speed wind turbines operating in Region III (rated power regulation). By the end of the lab, students will be able to:

- Derive and linearize the nonlinear aerodynamic model of a wind turbine rotor
- Design an input-output linearization controller for rotor-speed regulation
- Analyze closed-loop robustness under wind-speed disturbances and model uncertainty
- Design and tune first-order sliding mode and super-twisting controllers, including dynamic-gain variants
- Model a permanent-magnet synchronous generator (PMSG) in the dq-frame
- Design a coupled electro-mechanical control scheme integrating aerodynamic and electrical control
- Design and analyze an adaptive super-twisting controller under parameter uncertainty

## Prerequisites

- Nonlinear control theory (feedback linearization, Lyapunov stability)
- Sliding mode control fundamentals
- Basic familiarity with Simulink

## Materials

The full lab subject (Parts I and II) is attached to each session above, alongside the provided Simulink model used for evaluating all controllers.
