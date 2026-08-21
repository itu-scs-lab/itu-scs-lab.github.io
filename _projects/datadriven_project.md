---
layout: page
title: Subspace Shaping & Conditioning in Data-Driven MPC
description: Developing numerically stable, constraint-compliant, and reproducible subspace shaping frameworks for data-driven predictive flight control.
img: assets/img/projects/deepc_conditioning.jpg
importance: 1
category: Predictive Control & Safety

# Rozetler ve Arama Filtresi İçin Metadata
organization: TUBITAK
status: ongoing
keywords: [Data-Driven Control, Model Predictive Control, Subspace Shaping, Conditioning, Automated Tuning, Reproducibility]
---

### Project Overview

In safety-critical systems (e.g., flight control in aviation), **Model Predictive Control (MPC)** stands out as one of the most powerful paradigms for safe, real-time decision-making. While data-driven approaches offer substantial advantages through their inherent resilience to unmodelled dynamics, low-excitation and noisy operational regimes cause **Hankel-type representations** to become ill-conditioned. This numerical bottleneck leads to inflated solve times, degraded stability margins, and heightened risks of constraint violations.

This project delivers a **subspace shaping and conditioning framework** that directly restructures data-derived matrices to restore numerical conditioning and guarantee constraint compliance.

---

### Key Work Packages

1. **Theoretical Foundations:** Deriving shaping operators with strict guarantees on recursive feasibility, stability margins, and constraint satisfaction.
2. **Algorithmic Library:** Designing a modular MATLAB/Simulink toolbox featuring sliding-window management, live data quality monitoring, and automated tuning.
3. **Aeronautical Validation:** Benchmarking performance against fixed-wing and rotorcraft scenarios across diverse noise and disturbance profiles.
4. **Open Science & Dissemination:** Releasing an open-source starter kit, automated benchmarking suites, and reproducible test scripts.

---

### Expected Outcomes

* **Numerical Conditioning:** Drastic reduction in Hankel matrix condition numbers and quadratic program (QP) solve times.
* **Tracking & Robustness:** Enhanced tracking precision with robust stability indicators under unmodelled aerodynamic disturbances.
* **Reproducibility:** Zero-manual-intervention automated tuning workflows supported by comprehensive benchmarking packages.
