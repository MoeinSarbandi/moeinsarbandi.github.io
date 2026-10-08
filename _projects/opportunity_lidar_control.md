---
layout: page
title: LiDAR-Based Wind Preview and Control of Wind Turbines
description: Reconstruct and assess wind preview from real LiDAR data; optionally explore feedforward control.
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

This project investigates how nacelle-mounted LiDAR measurements can be processed to estimate incoming wind before it reaches a turbine rotor. Our **main goal is wind-preview reconstruction and quality assessment from real measurement data**. As an optional extension, we may investigate whether the reconstructed preview improves wind-turbine control.

The project is inspired by the [IEA Wind Task 52 Lidar-Assisted Control (LAC) Summer Games 2026](https://zenodo.org/records/21728616), particularly its *6.2M Ultramarathon — Wind Preview Quality* discipline. We use the published material as a research benchmark; **participation in the competition is not required**.

## Phase 1: Wind-preview reconstruction and quality assessment (core project)

1. Load and explore the real LiDAR dataset: timestamps, line-of-sight wind speeds, beam identifiers, and measurement-validity flags.
2. Reproduce the provided `LDP_v3` wind-reconstruction baseline, then compare a few filtering or reconstruction methods.
3. Assess preview quality using **coherence** and **smallest detectable eddy size (SDES)**, alongside useful measures such as RMSE, bias, time alignment, and robustness to invalid measurements.
4. Explain the trade-offs among reconstruction accuracy, filtering, and useful preview timing; document the work in reproducible code and a joint report.

**Phase 1 alone is sufficient for this MSc project**, provided the implementation, evaluation, and discussion are thorough. **We will focus on completing this phase first.**

No **OpenFAST, ROSCO, Fortran, or 15 MW wind-turbine model** is needed for Phase 1. The released field dataset and Python or MATLAB tools are sufficient. Use only *current or past* LiDAR signals when reconstructing the wind; the provided reference wind signal is for **evaluation only**, not for constructing the online estimate.

## Phase 2: LiDAR-assisted control (optional extension)

**If Phase 1 is completed successfully and time permits**, we can test the estimated preview as a feedforward input alongside a conventional feedback controller. The 2026 example code includes a simplified turbine simulator (`SLOW`) that allows a first comparison of feedback-only and preview-assisted control without requiring OpenFAST.

Possible comparison criteria are rotor-speed variation, power fluctuations, pitch/control effort, and load measures available from the simplified model. This extension is **encouraged if feasible but not required**. Advanced aeroelastic simulations are beyond the initial scope.

## Getting started: official resources

**Use the `SummerGames2026` branch**, not the repository's default branch.

1. [Summer Games 2026 — official description and instructions (Zenodo)](https://zenodo.org/records/21728616). Begin with the *6.2M Ultramarathon / Wind Preview Quality* discipline.
2. [Official SummerGames2026 GitHub branch](https://github.com/IEAWindTask52/LidarAssistedControl/tree/SummerGames2026) and [README / getting-started instructions](https://github.com/IEAWindTask52/LidarAssistedControl/blob/SummerGames2026/README.md).
3. [Real LiDAR dataset — `DataSummerGames2026.mat`](https://github.com/IEAWindTask52/LidarAssistedControl/blob/SummerGames2026/UltraMarathon/data/DataSummerGames2026.mat).
4. [Python baseline — `RunUltraMarathon.py`](https://github.com/IEAWindTask52/LidarAssistedControl/blob/SummerGames2026/UltraMarathon/python/RunUltraMarathon.py) and [LiDAR reconstruction algorithm — `LDP_v3.py`](https://github.com/IEAWindTask52/LidarAssistedControl/blob/SummerGames2026/UltraMarathon/python/functions/LDP_v3.py).
5. [Python environment setup](https://github.com/IEAWindTask52/LidarAssistedControl/blob/SummerGames2026/UltraMarathon/python/setup/setup_python.py) and [requirements](https://github.com/IEAWindTask52/LidarAssistedControl/blob/SummerGames2026/UltraMarathon/python/setup/requirements.txt). A [MATLAB version](https://github.com/IEAWindTask52/LidarAssistedControl/blob/SummerGames2026/UltraMarathon/matlab/RunUltraMarathon.m) is also available.

**Suggested first milestone:** download and inspect the data, reproduce the provided baseline, and develop a small *preview-only* script for the core phase. Note that the full example runner also executes the `SLOW` turbine simulation for control assessment; this simulation is not needed to analyze preview quality.

For questions about the original software, the organizers maintain [GitHub discussions](https://github.com/IEAWindTask52/LidarAssistedControl/discussions).

## Selected references

- D. Schlipf et al., *IEA Wind Task 52 LAC Summer Games 2026*, Zenodo, 2026. [Benchmark and documentation](https://doi.org/10.5281/zenodo.21728616).
- F. Guo, D. Schlipf, and P. W. Cheng, “Evaluation of LiDAR-Assisted Wind Turbine Control under Various Turbulence Characteristics,” *Wind Energy Science*, 2023. [DOI](https://doi.org/10.5194/wes-8-149-2023).
- A. J. Russell et al., “LiDAR-Assisted Feedforward Individual Pitch Control of a 15 MW Floating Offshore Wind Turbine,” *Wind Energy*, 2024. [DOI](https://doi.org/10.1002/we.2891). *Further reading for advanced extensions; the 15 MW model is not needed for Phase 1.*
