---
layout: page
title: LiDAR-Based Wind Preview and Control of Wind Turbines
description: Process field LiDAR measurements and investigate preview-assisted feedforward control.
project_id: Project 04
assignment_project_id: Project 05
image: /assets/img/student-projects/lidar-wind-preview.webp
importance: 4
category: opportunity
status: Assigned
students:
  - Muhammad Sohail Ashraf
  - Ahmed Kazmi
topics: [LiDAR, Wind estimation, Feedforward control, Signal processing]
---

**Supervisor:** Moein Sarbandi  
**Programme:** EU-CORE MSc  
**Status:** {{ page.status }}  
**Students:** {{ page.students | join: " and " }}

<figure class="student-project-hero" style="margin: 1.2rem 0 1.6rem;">
  <img src="{{ page.image | relative_url }}" alt="LiDAR wind preview estimation and floating wind turbine control" loading="lazy" style="display: block; width: 100%; height: auto; border-radius: 0.6rem;">
</figure>

## Project objective

This project investigates how nacelle-mounted LiDAR measurements can estimate incoming wind before it reaches the rotor and how that preview can improve wind-turbine control.

## Phase 1: wind preview from field data

1. Process an available field-measured LiDAR dataset from an operating wind turbine.
2. Filter the measurements and reconstruct the incoming wind seen by the rotor.
3. Quantify accuracy, noise sensitivity, and useful preview time.
4. Compare signal-processing or data-driven reconstruction approaches.

This phase is the core project and can be completed as a standalone study.

## Phase 2: LiDAR-assisted control

If progress allows, the estimated wind preview will be used as a feedforward signal alongside a conventional feedback controller. Performance will be evaluated through rotor-speed regulation, power fluctuations, control effort, and structural loads.

## Selected references

- F. Guo, D. Schlipf, and P. W. Cheng, “Evaluation of LiDAR-Assisted Wind Turbine Control under Various Turbulence Characteristics,” _Wind Energy Science_, 2023.
- A. J. Russell et al., “LiDAR-Assisted Feedforward Individual Pitch Control of a 15 MW Floating Offshore Wind Turbine,” _Wind Energy_, 2024.
