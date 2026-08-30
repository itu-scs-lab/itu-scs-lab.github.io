---
layout: about
title: about
permalink: /
subtitle: Safety-Critical Systems Laboratory at Istanbul Technical University

profile:
  align: right
  image: scs-lab-logo.png
  image_circular: true
  more_info: >
    <p>ITU Ayazağa Campus</p>
    <p>Istanbul, Türkiye</p>

news: true
selected_papers: true
social: false
---

### Control • Safety • Reliability
**From control theory to safety-critical implementation.**

We develop deterministic control, robust estimation, and formal verification methodologies for safety-critical autonomous, robotic, and industrial systems. Operating at the convergence of modern control theory and high-integrity software engineering, our research bridges the gap between deep mathematical formulations and real-world-proven, real-time embedded deployment. Beyond conducting high-impact R&D compliant with rigorous safety standards (such as DO-178C and ISO 26262), the laboratory actively advances education through specialized university curricula and tailored industry training programs.

<!-- BUTONLAR (NET & GÖRÜNÜR) -->
<div class="about-cta-group">
  <a href="{{ '/projects/' | relative_url }}" class="hero-btn hero-btn-primary">
    <i class="fa-solid fa-diagram-project"></i> Explore Projects
  </a>
  <a href="{{ '/team/' | relative_url }}" class="hero-btn hero-btn-secondary">
    <i class="fa-solid fa-users"></i> Meet the Team
  </a>
</div>

<!-- 1. RESEARCH PILLARS -->
<h2 class="about-section-heading">Research Pillars</h2>

<div class="research-focus-grid">
  <!-- Pillar 1 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-microchip"></i></div>
    <h3 class="focus-title">01. Control & Autonomous Systems</h3>
    <p class="focus-desc">
      Constrained predictive control (MPC, DeePC, Algebraic MPC), adaptive guidance, INDI, and real-time flight control law synthesis.
    </p>
  </div>

  <!-- Pillar 2 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-shield-halved"></i></div>
    <h3 class="focus-title">02. Safety, Risk & Reliability</h3>
    <p class="focus-desc">
      Active Fault Detection and Isolation (FDI), robust state estimation (EKF), safety margins, and resilient deterministic architectures.
    </p>
  </div>

  <!-- Pillar 3 -->
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-list-check"></i></div>
    <h3 class="focus-title">03. High-Integrity Software & V&V</h3>
    <p class="focus-desc">
      Model-based development workflows, formal verification, Hardware-in-the-Loop (HIL) testing, and DO-178C / ISO 26262 compliance.
    </p>
  </div>
</div>

<!-- 2. APPLICATION DOMAINS HIERARCHY -->
<h2 class="about-section-heading">Application Domains</h2>

<div class="domains-container">
  <span class="domains-label"><i class="fa-solid fa-crosshairs me-1"></i> Primary:</span>
  <span class="domain-pill"><i class="fa-solid fa-plane-up me-1"></i> Aerospace & Autonomous Systems</span>
  <span class="domain-pill"><i class="fa-solid fa-robot me-1"></i> Robotics & Mechatronics</span>
  
  <span class="domains-label ms-3"><i class="fa-solid fa-layer-group me-1"></i> Critical Sectors:</span>
  <span class="domain-pill"><i class="fa-solid fa-train me-1"></i> Rail Transit</span>
  <span class="domain-pill"><i class="fa-solid fa-car me-1"></i> Automotive</span>
  <span class="domain-pill"><i class="fa-solid fa-bolt me-1"></i> Energy Systems</span>
</div>

<!-- 3. SEÇİLİ YAYINLAR DİKEY ROZET SCRIPTI -->
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
