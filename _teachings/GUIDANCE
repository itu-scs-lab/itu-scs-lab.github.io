---
layout: course
title: Guidance and Route Following for Autonomous Aerial Vehicles
description: Mission-level command generation, guidance, and route-following methods for autonomous aerial vehicles. Examines coordinate systems, waypoint navigation, LOS, Pure Pursuit, L1 guidance, path following, trajectory tracking, Frenet frame, autopilot integration, and physical flight constraints in MATLAB/Simulink.
instructor: Dr. Talha Ulukır
year: 2026
term: Fall
location: XXX
time: TBA
course_id: MTHXXX
schedule:
  - week: 1
    date: Week 1
    topic: Otonom Hava Araçlarına Giriş; GNC Ayrımı ve Uçuş Mimarisi
    description: Introduction to autonomous aerial vehicles, distinction among Guidance, Navigation, and Control (GNC) layers, and autonomous flight architecture.
    materials:
      - name: Syllabus
        url: /assets/pdf/example_pdf.pdf
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 2
    date: Week 2
    topic: Koordinat Sistemleri ve Waypoint Navigation Temelleri
    description: Body, Inertial, NED, ENU, and LLA coordinate systems, frame transformations, waypoint transition logic, acceptance radius, and mission definition.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 3
    date: Week 3
    topic: Track, Heading ve Sideslip Ayrımı ile Rüzgâr Etkileri
    description: Differences between track angle, heading angle, and sideslip; ground track analysis and steady/gust wind effect interpretations.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 4
    date: Week 4
    topic: Line-of-Sight (LOS) Rehberleme
    description: LOS guidance principles, line-of-sight angle geometry, cross-track error formulation, and 2D route-following steering commands.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: Problem Set 1
        url: /assets/pdf/example_pdf.pdf

  - week: 5
    date: Week 5
    topic: Pure Pursuit ve Geometrik Rehberleme
    description: Target point tracking, look-ahead distance tuning, and geometric pursuit guidance algorithms.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 6
    date: Week 6
    topic: L1 Guidance Temelleri ve Yanal İvme / Roll Dönüşümü
    description: Non-linear L1 guidance logic, L1 distance selection, lateral acceleration command generation, and coordinated turn roll command synthesis.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: MATLAB Lab 1
        url: https://github.com/

  - week: 7
    date: Week 7
    topic: Path Following, Çapraz İz Hatası ve Path-Capture Davranışı
    description: 2D path following vs. tracking, cross-track error reduction, and asymptotic path-capture dynamics.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 8
    date: Week 8
    topic: Trajectory Tracking ve Zaman Parametreli Yörünge Takibi
    description: Time-parameterized trajectory tracking, reference profile generation, and feedforward steering design.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: Midterm Review
        url: /assets/pdf/example_pdf.pdf

  - week: 9
    date: Week 9
    topic: Frenet Frame ve Yol Koordinatlarında Hata Tanımı
    description: Curvilinear path coordinates, Frenet-Serret frame formulation, path curvature effects, and kinematic error dynamics.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 10
    date: Week 10
    topic: Vektör Alanı (Vector Field) ile Navigasyon ve Yol Takibi
    description: Vector field guidance methodology, convergence vector fields for straight-line and circular paths, and singularity handling.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: Problem Set 2
        url: /assets/pdf/example_pdf.pdf

  - week: 11
    date: Week 11
    topic: Üç Boyutlu Rehberleme ve İrtifa Profili Yönetimi
    description: 3D spatial guidance, altitude profile generation, climb/descent rate commands, and 3D trajectory tracking.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 12
    date: Week 12
    topic: Kısıtlar Altında Rehberleme Komut Sınırlama
    description: Vehicle envelope constraints; air speed, acceleration, turn radius, bank angle (roll), and yaw-rate limitation architectures.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 13
    date: Week 13
    topic: Otonom Görev Mimarisi ve Karar Verme Mekanizmaları
    description: Waypoint manager, flight mode manager, mission command generator, fallback modes, and high-level autonomous decision logic.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: MATLAB Lab 2
        url: https://github.com/

  - week: 14
    date: Week 14
    topic: MATLAB/Simulink Otonom Rota Takip Proje Değerlendirmesi
    description: End-to-end model-based simulation of autonomous mission profiles, cross-track tracking performance metrics, and project presentations.
    materials:
      - name: Project Guidelines
        url: /assets/pdf/example_pdf.pdf
---

## Course Overview

This course provides a comprehensive engineering foundation on autonomous flight architectures, mission-level guidance, and path-following algorithms for unmanned aerial vehicles (UAVs):

- **GNC Layering & Reference Frames:** Systematic breakdown of Guidance, Navigation, and Control hierarchies along with coordinate transformations across Body, Inertial, NED, ENU, and LLA systems.
- **Guidance & Route-Following Laws:** Theoretical formulation and comparative evaluation of Line-of-Sight (LOS), Pure Pursuit, non-linear L1 guidance, Vector Field methods, and Frenet-frame kinematic controllers.
- **Kinematics & Wind Interaction:** Real-time compensation of steady and turbulent wind regimes, course/track angle estimation, heading control, and sideslip suppression.
- **Envelope-Constrained Autopilot Integration:** Mapping 2D/3D guidance commands into inner/outer autopilot control loops under strict physical limits (airspeed, bank angle, load factor, turn radius, and yaw-rate bounds).
- **Mission Execution & Software Verification:** Implementing modular waypoint and mode managers in MATLAB & Simulink environments.

## Prerequisites

- **Required Background:** Linear Control Systems Theory, Classical Flight Dynamics & Kinematics, and Matrix Algebra.
- **Software Skills:** Working familiarity with MATLAB & Simulink for control and trajectory simulation.

## Course Learning Outcomes

1. Explain the operational distinctions among guidance, navigation, and control layers within autonomous flight architectures.
2. Formulate coordinate transformations across Body, Inertial, NED, ENU, and LLA frames.
3. Construct waypoint navigation, acceptance radius logic, and path-following topologies.
4. Synthesize and evaluate LOS, Pure Pursuit, and L1 non-linear guidance laws.
5. Account for wind triangles, ground track, heading angles, and sideslip variations.
6. Generate 2D and 3D flight guidance commands compatible with standard autopilot loops.
7. Enforce speed, acceleration, bank angle, and turn-rate limits during trajectory execution.
8. Implement end-to-end mission and mode management logic in MATLAB/Simulink.

## Textbooks & References

- *Small Unmanned Aircraft: Theory and Practice* by Randal W. Beard & Timothy W. McLain
- *Sensing and Control for Autonomous Vehicles* by Thor I. Fossen, Kristin Y. Pettersen, Henk Nijmeijer
- *Aircraft Control and Simulation: Dynamics, Controls Design, and Autonomous Systems* by Brian L. Stevens, Frank L. Lewis, Eric N. Johnson

## Grading

- Midterm Examination: 30%
- MATLAB / Simulink Simulation Term Project: 30%
- Final Examination: 40%
