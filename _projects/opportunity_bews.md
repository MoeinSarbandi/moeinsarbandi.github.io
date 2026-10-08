---
layout: page
title: Blade-Effective Wind-Speed Estimation for Wind Turbines
description: Extend rotor-effective wind-speed estimation to the wind experienced by individual blades.
project_id: Project 06
importance: 5
category: opportunity
status: Assigned
students:
  - Mohd Abddullah Khan
  - Mohammed Al-Hadi
topics: [Wind estimation, Observers, Individual pitch control, OpenFAST]
---

**Supervisor:** Moein Sarbandi  
**Programme:** EU-CORE MSc  
**Status:** {{ page.status }}  
**Students:** {{ page.students | join: " and " }}

## Project objective

Our previous work estimated rotor-effective wind speed, an equivalent wind speed over the full rotor. This project goes one step further by estimating the wind experienced by each individual blade, with potential applications in load reduction and individual pitch control.

## Main steps

1. Review blade-effective wind-speed estimators based on blade-root loads, pitch angle, rotor azimuth, and other turbine measurements.
2. Implement and validate an estimator on a wind-turbine simulation model.
3. Compare candidate approaches under wind shear, turbulence, measurement noise, and partial-wake conditions.
4. If time allows, validate the estimator in OpenFAST and investigate its integration with individual pitch control.

## Selected references

- M. Sarbandi, M. Viozelange, M. A. Hamida, and F. Plestan, “Wind Speed Estimation Using Second-Order Sliding-Mode Observers: Simulation and Experimental Validation on a Floating Offshore Wind Turbine,” _Wind Energy Science_, 2026. [DOI](https://doi.org/10.5194/wes-11-2405-2026)
- Y. Liu, A. K. Pamososuryo, R. Ferrari, T. G. Hovgaard, and J.-W. van Wingerden, “Blade Effective Wind Speed Estimation: A Subspace Predictive Repetitive Estimator Approach,” _European Control Conference_, 2021.
