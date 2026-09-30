---
layout: page
title: Data-Driven Control of a Wind Turbine Using a Linear Model
description: Compare modern data-driven controllers on a realistic wind-turbine benchmark.
project_id: Project 01
importance: 1
category: opportunity
topics: [Data-driven control, DeePC, Robust control, OpenFAST]
---

**Supervisor:** Moein Sarbandi  
**Programme:** EU-CORE MSc  
**Status:** Available

## Project objective

This project develops and compares discrete-time data-driven controllers for the NREL 5 MW wind turbine. It starts from a simplified linear model at one operating point, then treats the model as unknown and designs controllers directly from simulated input-state or input-output data.

## Main steps

1. Obtain a linear wind-turbine model from OpenFAST or a validated reference model.
2. Generate informative simulation data around a selected operating point.
3. Implement data-driven state-feedback control, Data-enabled Predictive Control (DeePC) using Hankel matrices, and robust $H_\infty$ control.
4. Compare reference tracking, disturbance rejection, control effort, robustness to noisy data, and sensitivity to model uncertainty.
5. Test the controllers at different wind speeds and study gain scheduling, adaptive control, or online data-driven control for a wider operating range.
6. If time allows, validate the most promising controller on the high-fidelity OpenFAST model.

## Expected background

Basic state-space control, MATLAB/Simulink, and an interest in data-driven control. Prior OpenFAST experience is useful but not required.

## Selected references

- C. De Persis and P. Tesi, “Formulas for Data-Driven Control: Stabilization, Optimality, and Robustness,” _IEEE Transactions on Automatic Control_, 2020.
- J. Coulson, J. Lygeros, and F. Dörfler, “Data-Enabled Predictive Control,” _European Control Conference_, 2019.
- H. J. van Waarde et al., “From Noisy Data to Feedback Controllers,” _IEEE Transactions on Automatic Control_, 2022.
- J. Jonkman et al., _Definition of a 5-MW Reference Wind Turbine for Offshore System Development_, NREL, 2009.
