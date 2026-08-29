---
layout: page
permalink: /
title: about
nav: true
nav_order: 1
---

<!-- 1. HERO SECTION -->
<div class="about-hero-section">
  <div class="about-hero-text">
    <h1 class="lab-main-title">ITU SCS Lab</h1>
    <div class="lab-subtitle">Safety-Critical Systems Laboratory at Istanbul Technical University</div>
    <p class="lab-lead">
      Welcome to the <strong>Safety-Critical Systems Laboratory (SCS Lab)</strong> at Istanbul Technical University. 
      SCS Lab operates at the interdisciplinary intersection of Electrical & Electronics Engineering, Control Engineering, and Software Systems, conducting advanced studies on predictive control theory, software certification, and fault-tolerant architectures.
    </p>
  </div>
  <div class="about-hero-logo">
    <img src="{{ '/assets/img/group_logo.png' | relative_url }}" alt="ITU SCS Lab Logo">
  </div>
</div>

<!-- 2. CORE RESEARCH FOCUS (3 KARTLI GRID) -->
<h2 class="about-section-heading">Core Research Focus</h2>

<div class="research-focus-grid">
  <!-- Focus 1 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-microchip"></i></div>
    <h3 class="focus-title">Control Theory & Applications</h3>
    <p class="focus-desc">
      Advanced Predictive Control (MPC, DeePC), Incremental Nonlinear Dynamic Inversion (INDI), Control Barrier Functions (CBF), and real-time algebraic control laws.
    </p>
  </div>

  <!-- Focus 2 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-shield-halved"></i></div>
    <h3 class="focus-title">Risk & Reliability Management</h3>
    <p class="focus-desc">
      Safety margin analysis, fault detection & isolation (FDI), state machine architectures, and health monitoring for critical mission profiles.
    </p>
  </div>

  <!-- Focus 3 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-code-check"></i></div>
    <h3 class="focus-title">Software Quality Assurance</h3>
    <p class="focus-desc">
      High-integrity embedded software design, DO-178C model-based development workflows, formal verification, and validation strategies.
    </p>
  </div>
</div>

<!-- 3. TARGET DOMAINS -->
<div class="domains-container">
  <span class="domains-label"><i class="fa-solid fa-crosshairs me-1"></i> Target Domains:</span>
  <span class="domain-pill"><i class="fa-solid fa-plane-up me-1"></i> Aerospace Engineering</span>
  <span class="domain-pill"><i class="fa-solid fa-car me-1"></i> Automotive Systems</span>
  <span class="domain-pill"><i class="fa-solid fa-train me-1"></i> Railway Systems</span>
  <span class="domain-pill"><i class="fa-solid fa-atom me-1"></i> Nuclear Systems</span>
  <span class="domain-pill"><i class="fa-solid fa-flask me-1"></i> Chemical Processes</span>
</div>

<!-- 4. SELECTED PUBLICATIONS -->
<h2 class="about-section-heading">Selected Publications</h2>

<div class="publications">
  {% bibliography --query @*[selected=true]* %}
</div>

<a href="{{ '/publications/' | relative_url }}" class="view-all-pubs-btn">
  View all publications <i class="fa-solid fa-arrow-right"></i>
</a>

<!-- Sol Dikey Rozet Script'i (Home Sayfası İçin) -->
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
