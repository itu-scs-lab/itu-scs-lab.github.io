---
layout: about
title: about
permalink: /
subtitle: Safety-Critical Systems Laboratory at Istanbul Technical University

profile:
  align: right
  image: group_logo.png
  image_circular: true # Logonun yuvarlak çerçeveye oturması için
  more_info: >
    <p>ITU Ayazağa Campus</p>
    <p>Istanbul, Türkiye</p>

selected_papers: true 
social: false 
---

Welcome to the **Safety-Critical Systems Laboratory (SCS Lab)** at Istanbul Technical University.

The **SCS Lab** is an advanced research, development, and training center dedicated to the theory, implementation, and verification of control engineering across all safety-critical applications. Operating at the intersection of Modern Control Theory, Dynamical Systems, Electrical & Electronics Engineering, and High-Integrity Software Architectures, our primary mission is to engineer deterministic, certifiable, and fault-tolerant solutions where system failure or performance degradation is not an option.

Our research spectrum spans the full continuum of control systems engineering—including classical control, state-space methods, optimal and adaptive control, robust control, nonlinear dynamics, modern data-driven methodologies, predictive control frameworks, and state estimation/sensor fusion architectures. We complement theoretical control synthesis with system identification, active fault detection and isolation (FDI), risk/reliability management, and certifiable model-based development pipelines complying with international safety standards (such as DO-178C, ISO 26262, and IEC 61508). These capabilities serve a broad domain of critical engineering fields, including autonomous aerial/ground/marine vehicles, robotics and mechatronics, rail transit, automotive systems, defense platforms, energy networks, and process automation.

Beyond academic research and high-impact R&D projects funded nationally and internationally, SCS Lab actively drives knowledge transfer to academia and industry. The laboratory develops and delivers comprehensive curricula across undergraduate, M.Sc., and Ph.D. levels, while also designing customized, high-level corporate training programs and technical workshops tailored to the specialized needs of industry partners and technology companies.

<!-- 1. CORE RESEARCH FOCUS -->
<h2 class="about-section-heading">Core Research Focus</h2>

<div class="research-focus-grid">
  <!-- Focus 1 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-microchip"></i></div>
    <h3 class="focus-title">Control Theory & Applications</h3>
    <p class="focus-desc">
      Advanced Predictive Control frameworks (Model Predictive Control - MPC, Data-Driven Predictive Control - DeePC), Incremental Nonlinear Dynamic Inversion (INDI), Control Barrier Functions (CBF), and robust control strategies for complex dynamic systems.
    </p>
  </div>

  <!-- Focus 2 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-shield-halved"></i></div>
    <h3 class="focus-title">Risk & Reliability Management</h3>
    <p class="focus-desc">
      Risk assessment methodologies, safety margin analysis, fault detection strategies, and deterministic state machine architectures designed to preserve overall system integrity.
    </p>
  </div>

  <!-- Focus 3 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-list-check"></i></div>
    <h3 class="focus-title">Software Quality Assurance</h3>
    <p class="focus-desc">
      High-integrity software design, verification and validation strategies, and rigorous testing methodologies tailored specifically for safety-critical domains.
    </p>
  </div>
</div>

<!-- 2. APPLICATION DOMAINS -->
<div class="domains-container">
  <span class="domains-label"><i class="fa-solid fa-crosshairs me-1"></i> Target Domains:</span>
  <span class="domain-pill"><i class="fa-solid fa-plane-up me-1"></i> Aerospace Engineering</span>
  <span class="domain-pill"><i class="fa-solid fa-car me-1"></i> Automotive Systems</span>
  <span class="domain-pill"><i class="fa-solid fa-train me-1"></i> Railway Systems</span>
  <span class="domain-pill"><i class="fa-solid fa-atom me-1"></i> Nuclear Systems</span>
  <span class="domain-pill"><i class="fa-solid fa-flask me-1"></i> Chemical Processes</span>
</div>

<!-- 3. SEÇİLİ YAYINLAR İÇİN DİKEY ROZET SCRİPT'İ -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    var pubEntries = document.querySelectorAll('.publications ol.bibliography > li');
    pubEntries.forEach(function(entry) {
      if (!entry.querySelector('.pub-badge')) {
        var badgeContainer = document.createElement('div');
        badgeContainer.className = 'pub-badge-wrapper';
        badgeContainer.innerHTML = '<span class="pub-badge pub-badge-journal"><i class="fa-solid fa-file-lines"></i> Journal</span>';
        entry.insertBefore(badgeContainer, entry.firstChild);
      }
    });
  });
</script>
