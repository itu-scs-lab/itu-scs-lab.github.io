---
layout: page
title: research
permalink: /research/
description: Research in control systems, safety, reliability, and high-integrity software for safety-critical systems.
nav: true
nav_order: 2
---

<div class="research-page-container">

  <!-- GİRİŞ METNİ -->
  <div class="research-hero-banner">
    <p class="research-lead-text">
      SCS Lab conducts cutting-edge research on the analysis, control, safety, and verification of
      <strong>safety-critical dynamical systems</strong>. Our work is organized around three complementary pillars, spanning rigorous theoretical foundations, system-level safety and reliability, and high-integrity embedded implementation.
    </p>
  </div>

  <!-- ========================================================= -->
  <!-- 01 — CONTROL SYSTEMS & AUTONOMY                           -->
  <!-- ========================================================= -->
  <section class="research-pillar-section" id="control-systems-autonomy">
    <div class="pillar-header-group">
      <span class="pillar-num-badge">01</span>
      <div class="pillar-title-wrap">
        <h2 class="pillar-main-title">Control Systems & Autonomy</h2>
        <p class="pillar-sub-lead">
          Advanced control, optimization, and decision-making for complex dynamical systems operating under strict physical constraints, severe uncertainties, and limited embedded compute.
        </p>
      </div>
    </div>

 <div class="research-cards-grid">
      <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Predictive & Constrained Control</h3>
        <p class="topic-desc">
          Model Predictive Control (MPC), closed-form Algebraic MPC, constraint handling, and real-time embedded quadratic programming for mission-critical regimes.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Data-Driven Control</h3>
        <p class="topic-desc">
          Direct Data-Driven Predictive Control (DeePC), behavioral & subspace methods, numerical conditioning, and real-time control synthesis directly from input-output data.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Robust & Nonlinear Control</h3>
        <p class="topic-desc">
          Adaptive control, Incremental Nonlinear Dynamic Inversion (INDI), and sliding mode/Lyapunov-based strategies resilient to modeling inaccuracies and atmospheric disturbances.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Guidance & Autonomous Flight</h3>
        <p class="topic-desc">
          Constraint-aware trajectory generation, real-time lookahead adaptive L1 guidance, automatic landing architectures, and terrain-following guidance for autonomous vehicles.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Real-Time Implementation</h3>
        <p class="topic-desc">
          Microsecond-level deterministic execution, embedded code generation, and fixed-point mathematical formulations tailored for flight controllers and mission computers.
        </p>
      </div>
    </div>
  </section>

  <!-- ========================================================= -->
  <!-- 02 — SAFETY, RISK & RELIABILITY                           -->
  <!-- ========================================================= -->
  <section class="research-pillar-section" id="safety-risk-reliability">
    <div class="pillar-header-group">
      <span class="pillar-num-badge">02</span>
      <div class="pillar-title-wrap">
        <h2 class="pillar-main-title">Safety, Risk & Reliability</h2>
        <p class="pillar-sub-lead">
          Preserving stability, deterministic bounds, and functional integrity in the presence of sensor faults, actuator degradation, and extreme environmental uncertainties.
        </p>
      </div>
    </div>

  <div class="research-cards-grid">
      <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Fault Detection, Isolation & Diagnosis</h3>
        <p class="topic-desc">
          Model-based and statistical residual evaluation, sensor/actuator FDI, and active health monitoring to identify failures before unrecoverable loss of control occurs.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Fault-Tolerant & Resilient Control</h3>
        <p class="topic-desc">
          Active control reconfiguration, control allocation under damaged surfaces, and degraded-mode supervisory logic ensuring safe return-to-base and mission survival.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Safety-Aware Control & Barriers</h3>
        <p class="topic-desc">
          Control Barrier Functions (CBFs), reachability analysis, and flight envelope protection algorithms ensuring systems never exit verified safe operating subsets.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Robust Estimation & Sensor Fusion</h3>
        <p class="topic-desc">
          Augmented-state Extended Kalman Filtering (EKF), robust fault exclusion for multi-constellation GNSS/INS systems, and multi-rate state estimation.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Risk & Reliability Assessment</h3>
        <p class="topic-desc">
          Quantitative hazard evaluation, safety margins, Failure Modes and Effects Analysis (FMEA), and deterministic state machine safety monitors.
        </p>
      </div>
    </div>
  </section>

  <!-- ========================================================= -->
  <!-- 03 — HIGH-INTEGRITY SOFTWARE & V&V                        -->
  <!-- ========================================================= -->
  <section class="research-pillar-section" id="high-integrity-software-vv">
    <div class="pillar-header-group">
      <span class="pillar-num-badge">03</span>
      <div class="pillar-title-wrap">
        <h2 class="pillar-main-title">High-Integrity Software & V&V</h2>
        <p class="pillar-sub-lead">
          Systematic workflows translating mathematical control laws into verified, deterministic, and safety-certifiable embedded software architectures.
        </p>
      </div>
    </div>

  <div class="research-cards-grid">
      <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Model-Based Development (MBD)</h3>
        <p class="topic-desc">
          Executable models, automated C/C++ code generation, bidirectional requirements traceability, and rigorous architecture definition in MATLAB/Simulink pipelines.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Verification & Validation (V&V)</h3>
        <p class="topic-desc">
          Requirements-based testing, modified condition/decision coverage (MC/DC), static code analysis, and boundary numerical stress verification.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">SIL & HIL Real-Time Testing</h3>
        <p class="topic-desc">
          Software-in-the-Loop and Hardware-in-the-Loop testbeds with real-time target emulators evaluating jitter, latency, and fault-injection dynamics.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Formal & Safety Verification</h3>
        <p class="topic-desc">
          Theorem proving, model checking, and mathematical property proofs ensuring safety invariants are preserved under all possible states.
        </p>
      </div>

  <div class="research-subcard">
        <div class="card-accent-bar"></div>
        <h3 class="topic-title">Standards & Certification</h3>
        <p class="topic-desc">
          Aerospace (DO-178C / DO-331), automotive (ISO 26262), and industrial functional safety (IEC 61508) process compliance and artifact synthesis.
        </p>
      </div>
    </div>
  </section>

    <!-- ========================================================= -->
  <!-- CROSS-PILLAR RESEARCH PIPELINE                            -->
  <!-- ========================================================= -->
  <section class="research-pipeline-section">
    <h2 class="pipeline-heading">From Theory to Safety-Critical Implementation</h2>
    <p class="pipeline-sub">
      The three pillars form an integrated research lifecycle, connecting rigorous theory
      with dependable real-time implementation and verification.
    </p>

  <div class="pipeline-flow-container">

  <div class="flow-step">
        <span class="step-icon"><i class="fa-solid fa-square-root-variable"></i></span>
        <span class="step-text">Theory & Modeling</span>
      </div>

  <span class="flow-arrow"><i class="fa-solid fa-arrow-right"></i></span>

  <div class="flow-step">
        <span class="step-icon"><i class="fa-solid fa-microchip"></i></span>
        <span class="step-text">Control & Estimation</span>
      </div>

  <span class="flow-arrow"><i class="fa-solid fa-arrow-right"></i></span>

  <div class="flow-step">
        <span class="step-icon"><i class="fa-solid fa-shield-halved"></i></span>
        <span class="step-text">Safety & Reliability</span>
      </div>

  <span class="flow-arrow"><i class="fa-solid fa-arrow-right"></i></span>

  <div class="flow-step">
        <span class="step-icon"><i class="fa-solid fa-bolt"></i></span>
        <span class="step-text">Real-Time Implementation</span>
      </div>

  <span class="flow-arrow"><i class="fa-solid fa-arrow-right"></i></span>

  <div class="flow-step">
        <span class="step-icon"><i class="fa-solid fa-check-double"></i></span>
        <span class="step-text">V&V & Certification</span>
      </div>

  </div>
  </section>


  <!-- ========================================================= -->
  <!-- APPLICATION DOMAINS                                       -->
  <!-- ========================================================= -->
  <section class="research-domains-section">
    <h2 class="domains-title">Application Domains</h2>
    <p class="domains-sub">
      Our methodologies are developed for safety-critical systems across multiple engineering domains.
    </p>

  <div class="domains-grid">

  <div class="domain-card">
        <i class="fa-solid fa-plane-up"></i>
        <span>Aerospace & Flight Systems</span>
      </div>

  <div class="domain-card">
        <i class="fa-solid fa-car"></i>
        <span>Automotive & ADAS</span>
      </div>

  <div class="domain-card">
        <i class="fa-solid fa-train"></i>
        <span>Rail Transportation</span>
      </div>

  <div class="domain-card">
        <i class="fa-solid fa-robot"></i>
        <span>Robotics & Mechatronics</span>
      </div>

  <div class="domain-card">
        <i class="fa-solid fa-bolt"></i>
        <span>Energy & Process Systems</span>
      </div>

  </div>
  </section>

</div>
