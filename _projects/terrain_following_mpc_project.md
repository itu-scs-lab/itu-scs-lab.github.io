---
layout: page
title: Real-Time Algebraic MPC for Terrain Following in High-Subsonic UAVs
description: Real-time altitude reference generation and terrain following via Algebraic Model Predictive Control, online Digital Elevation Models (DEM), and HIL validation.
img: assets/img/projects/terrain_following_mpc.png
importance: 3
category: Predictive Control & Safety

# Rozetler, Durum ve Arama Metadata
organization: Special Defence Company
status: ongoing
keywords: [Algebraic MPC, DEM, Terrain Following, Real-Time Optimization, 6-DOF, Hardware-in-the-Loop, Radar Stealth]
---

### Project Context & Motivation

Unmanned Aerial Vehicles (UAVs) operating in contested or hostile airspace face a critical operational trade-off: climbing to clear terrain mitigates collision risks but exposes the platform to ground-based radar detection. Maintaining **low-altitude, terrain-following (TF) flight** at high subsonic speeds minimizes radar cross-section (RCS) exposure and significantly enhances mission survivability, but requires instantaneous, terrain-aware flight envelope adaptation.

Conventional Model Predictive Control (MPC) often struggles with the millisecond-scale sampling requirements of high-speed flight due to iterative numerical quadratic programming (QP) overhead on embedded hardware. This project deploys **Algebraic Model Predictive Control (A-MPC)** fused with online **Digital Elevation Models (DEM)** to compute analytical/semi-analytical optimal control actions in real time.

---

### Key Innovations & Technical Methodology

* **Iterative-Free Algebraic Optimization (A-MPC):** Reformulates the constrained predictive control problem into an algebraic structure, eliminating numerical iterative solvers and enabling millisecond-scale update cycles on onboard flight computers.
* **Online DEM Environmental Perception:** Integrates rasterized elevation models (LiDAR, InSAR, photogrammetry) to construct forward-looking, predictive terrain safety corridors.
* **High-Subsonic Flight Dynamics & Coupling:** Explicitly accounts for cross-axis dynamic couplings and physical limits, including:
  * Climb and descent rate limits.
  * Pitch angle boundaries ($\theta_{\min}, \theta_{\max}$) and actuator rate/position saturation.
  * Normal load factor bounds ($N_z$) and acceleration limits under high dynamic pressure.
* **Robust Constraint Handling:** Formulates stochastic and robust bounds against GNSS/INS drift, DEM raster resolution tolerances, and surface interpolation artifacts.

---

### Validation & Implementation Framework

1. **High-Fidelity Simulation:** Comprehensive verification using nonlinear **Six-Degree-of-Freedom (6-DOF)** aircraft flight dynamics models across turbulent atmospheric profiles.
2. **Hardware-in-the-Loop (HIL) Testing:** Real-time embedded execution on target Flight Control Computers (FCC) to benchmark latency, CPU utilization, and numerical stability.
3. **Terrain-Aware Autonomy:** Demonstrating safe, covert, low-altitude flight paths that maximize radar masking in complex topographical environments.
