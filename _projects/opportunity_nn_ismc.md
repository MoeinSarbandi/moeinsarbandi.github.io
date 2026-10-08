---
layout: page
title: Improving Adaptive Neural-Network Integral Sliding-Mode Control for Floating Wind Turbines
description: Improve an existing learning-based robust controller using OpenFAST data and hybrid offline-online learning.
project_id: Project 02
assignment_project_id: Project 03
image: /assets/img/student-projects/neural-network-control.webp
importance: 2
category: opportunity
status: Assigned
students:
  - Faten Jarrar
  - Aria Fatemi
topics: [Sliding-mode control, Neural networks, Adaptive control, OpenFAST]
---

**Supervisor:** Moein Sarbandi  
**Programme:** EU-CORE MSc  
**Status:** {{ page.status }}  
**Students:** {{ page.students | join: " and " }}

<figure class="student-project-hero" style="margin: 1.2rem 0 1.6rem;">
  <img src="{{ page.image | relative_url }}" alt="Neural-network control of a floating offshore wind turbine" loading="lazy" style="display: block; width: 100%; height: auto; border-radius: 0.6rem;">
</figure>

## Project objective

This project builds on an adaptive neural-network integral sliding-mode controller in which neural networks learn unknown floating-wind-turbine dynamics online without prior training. The goal is to reproduce the baseline controller, evaluate it systematically, and investigate practical improvements.

## Main steps

1. Implement the existing controller and test it at different wind speeds and operating conditions.
2. Assess tracking, robustness, control effort, and structural loads.
3. Introduce a warm start using neural-network weights initialized from previously collected OpenFAST data.
4. Compare online learning from random initialization, offline training, and offline training followed by online adaptation.
5. Explore extensions such as additional neurons or layers, alternative network structures, or higher-order sliding-mode control.

Strong results may support a research publication.

## Selected references

- Background material on the existing adaptive neural-network integral sliding-mode controller is available from the supervisor upon request.
- E. Vacchini et al., _IEEE Control Systems Letters_, 2023.
- N. Sacchi et al., _Journal of the Franklin Institute_, 2024.
