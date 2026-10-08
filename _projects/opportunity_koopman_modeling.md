---
layout: page
title: From Local Linearization to Koopman Models for Wind Turbines
description: Compare classical local linearization with DMDc and EDMD across operating conditions.
project_id: Project 04
importance: 3
category: opportunity
status: Assigned
students:
  - Mritunjoy MOHANTA
  - Adrian Willian Frasson
topics: [Koopman operator, DMDc, EDMD, System identification]
---

**Supervisor:** Moein Sarbandi  
**Programme:** EU-CORE MSc  
**Status:** {{ page.status }}  
**Students:** {{ page.students | join: " and " }}

## Project objective

This project compares classical local linearization with data-driven Koopman representations of nonlinear wind-turbine dynamics. The central question is whether Koopman-based models can retain useful linear structure over a wider operating range than a conventional model linearized at one operating point.

## Main steps

1. Select a simplified nonlinear wind-turbine model and derive its classical local linearization.
2. Generate data at several wind speeds and operating conditions.
3. Construct alternative linear predictors using Dynamic Mode Decomposition with control (DMDc) and Extended Dynamic Mode Decomposition (EDMD).
4. Compare prediction accuracy, model order, computational complexity, and validity away from the nominal operating point.
5. If time allows, validate the most promising method using OpenFAST data and use the resulting model for controller design.

More advanced Koopman approaches can be explored according to the student’s progress and interests.

## Selected references

- M. Korda and I. Mezić, “Linear Predictors for Nonlinear Dynamical Systems: Koopman Operator Meets Model Predictive Control,” _Automatica_, 2018.
- J. Liu et al., “Maximum Wind Energy Extraction of Floating Offshore Wind Turbine Using Model Predictive Control with Data-Driven Linear Predictors,” _Energy_, 2025.
