---
layout: page
title: research
permalink: /research/
description: Research in control systems, safety, reliability, and high-integrity software for safety-critical systems.
nav: true
nav_order: 2
---

<div class="research-intro">
  <p class="lead">
    SCS Lab conducts research on the analysis, control, safety, and verification of
    <strong>safety-critical dynamical systems</strong>. Our work is organized around
    three complementary research pillars, spanning rigorous theoretical foundations,
    system-level safety and reliability, and high-integrity implementation.
  </p>
</div>

<hr class="research-divider">

<!-- ========================================================= -->
<!-- 01 — CONTROL SYSTEMS & AUTONOMY                           -->
<!-- ========================================================= -->

<section class="research-pillar" id="control-systems-autonomy">

<div class="research-pillar-number">01</div>

## Control Systems & Autonomy

We develop advanced control and decision-making methods for complex dynamical systems
operating under constraints, uncertainty, nonlinearities, and limited computational
resources. Our research spans model-based and data-driven formulations, with emphasis
on methods suitable for real-time and safety-critical operation.

<div class="research-topics">

  <div class="research-topic">
    <h3>Predictive &amp; Constrained Control</h3>
    <p>
      Model Predictive Control (MPC), computationally efficient predictive formulations,
      constraint handling, and real-time optimization for systems with demanding operational
      and safety requirements.
    </p>
  </div>

  <div class="research-topic">
    <h3>Data-Driven Control</h3>
    <p>
      Data-driven predictive control, behavioral and subspace-based formulations, numerical
      conditioning, reduced-order representations, and computational methods for control
      directly from measured system data.
    </p>
  </div>

  <div class="research-topic">
    <h3>Robust &amp; Nonlinear Control</h3>
    <p>
      Robust, adaptive, and nonlinear control methods for systems subject to uncertainty,
      disturbances, nonlinear dynamics, and changing operating conditions.
    </p>
  </div>

  <div class="research-topic">
    <h3>Guidance, Autonomy &amp; Decision-Making</h3>
    <p>
      Guidance, trajectory generation, supervisory control, and autonomous decision-making
      methods that explicitly account for dynamic, operational, and safety constraints.
    </p>
  </div>

  <div class="research-topic">
    <h3>Real-Time Control Implementation</h3>
    <p>
      Control architectures and numerical methods designed with computational complexity,
      determinism, embedded implementation, and real-time execution requirements in mind.
    </p>
  </div>

</div>

</section>

<hr class="research-divider">

<!-- ========================================================= -->
<!-- 02 — SAFETY, RISK & RELIABILITY                           -->
<!-- ========================================================= -->

<section class="research-pillar" id="safety-risk-reliability">

<div class="research-pillar-number">02</div>

## Safety, Risk & Reliability

We investigate methods for maintaining safe and reliable operation in the presence of
faults, uncertainty, disturbances, and degraded system conditions. The objective is to
integrate safety and reliability considerations directly into estimation, control, and
system-level decision-making.

<div class="research-topics">

  <div class="research-topic">
    <h3>Fault Detection, Isolation &amp; Diagnosis</h3>
    <p>
      Model-based and data-driven methods for detecting, isolating, and diagnosing sensor,
      actuator, and system faults while distinguishing faults from uncertainty and external
      disturbances.
    </p>
  </div>

  <div class="research-topic">
    <h3>Fault-Tolerant &amp; Resilient Control</h3>
    <p>
      Active and passive fault-tolerant control, reconfiguration, degraded-mode operation,
      and resilient control architectures that preserve critical functionality following
      component or subsystem failures.
    </p>
  </div>

  <div class="research-topic">
    <h3>Safety-Aware Control</h3>
    <p>
      Control methods that explicitly incorporate safety constraints, safe operating regions,
      and risk-related requirements into the control design and online decision-making process.
    </p>
  </div>

  <div class="research-topic">
    <h3>Robust Estimation &amp; Monitoring</h3>
    <p>
      State and parameter estimation, sensor fusion, consistency monitoring, residual
      generation, and health-aware estimation for systems operating with uncertain or
      degraded measurements.
    </p>
  </div>

  <div class="research-topic">
    <h3>Risk &amp; Reliability Assessment</h3>
    <p>
      Systematic assessment of failure mechanisms, operational risk, reliability, and
      system-level safety margins to support the design and validation of safety-critical
      architectures.
    </p>
  </div>

</div>

</section>

<hr class="research-divider">

<!-- ========================================================= -->
<!-- 03 — HIGH-INTEGRITY SOFTWARE & V&V                        -->
<!-- ========================================================= -->

<section class="research-pillar" id="high-integrity-software-vv">

<div class="research-pillar-number">03</div>

## High-Integrity Software & V&V

We study the transition from control and safety algorithms to dependable embedded
implementations. Our work addresses model-based development, verification and
validation, testing, and certification-oriented engineering for high-integrity
software-intensive systems.

<div class="research-topics">

  <div class="research-topic">
    <h3>Model-Based Development</h3>
    <p>
      Systematic development of control and safety functions from executable models,
      including requirements traceability, architecture definition, implementation, and
      verification workflows.
    </p>
  </div>

  <div class="research-topic">
    <h3>Verification &amp; Validation</h3>
    <p>
      Verification and validation strategies for control and embedded software, including
      requirements-based testing, structural assessment, numerical validation, and
      system-level acceptance criteria.
    </p>
  </div>

  <div class="research-topic">
    <h3>SIL &amp; HIL Testing</h3>
    <p>
      Software-in-the-Loop (SIL) and Hardware-in-the-Loop (HIL) environments for evaluating
      functional behavior, timing, robustness, failure response, and real-time performance
      under representative operating conditions.
    </p>
  </div>

  <div class="research-topic">
    <h3>Formal &amp; Safety-Oriented Verification</h3>
    <p>
      Formal and semi-formal techniques for reasoning about system properties, constraints,
      failure behavior, and safety requirements throughout the development lifecycle.
    </p>
  </div>

  <div class="research-topic">
    <h3>Certification-Oriented Engineering</h3>
    <p>
      Development and assurance practices for high-integrity embedded systems with
      consideration of applicable safety and software standards across safety-critical
      application domains.
    </p>
  </div>

</div>

</section>

<hr class="research-divider">

<!-- ========================================================= -->
<!-- CROSS-PILLAR RESEARCH                                     -->
<!-- ========================================================= -->

<section class="research-cross-pillar">

## From Theory to Safety-Critical Implementation

The three research pillars are intentionally interconnected. Control performance alone
is insufficient for a safety-critical system; algorithms must also tolerate uncertainty
and faults, satisfy explicit safety requirements, execute predictably in real time, and
be supported by systematic verification and validation.

Our research therefore aims to connect:

<div class="research-flow">

**Theory & Modeling**
&nbsp; → &nbsp;
**Control & Estimation**
&nbsp; → &nbsp;
**Safety & Reliability**
&nbsp; → &nbsp;
**Real-Time Implementation**
&nbsp; → &nbsp;
**Verification & Validation**

</div>

This integrated perspective enables research outcomes to progress from mathematical
formulation toward dependable implementation in real safety-critical systems.

</section>

<hr class="research-divider">

<!-- ========================================================= -->
<!-- APPLICATION DOMAINS                                       -->
<!-- ========================================================= -->

<section class="research-applications">

## Application Domains

The laboratory's research pillars are domain-independent and are investigated across
a range of safety-critical and high-integrity applications.

<div class="domains-container">

  <span class="domain-pill">
    <i class="fa-solid fa-plane-up me-1"></i> Aerospace
  </span>

  <span class="domain-pill">
    <i class="fa-solid fa-car me-1"></i> Automotive
  </span>

  <span class="domain-pill">
    <i class="fa-solid fa-train me-1"></i> Rail Transportation
  </span>

  <span class="domain-pill">
    <i class="fa-solid fa-robot me-1"></i> Robotics &amp; Mechatronics
  </span>

  <span class="domain-pill">
    <i class="fa-solid fa-bolt me-1"></i> Energy &amp; Process Systems
  </span>

</div>

</section>
