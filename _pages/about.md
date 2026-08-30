---
layout: about
title: about
permalink: /
subtitle: Safety-Critical Systems Laboratory at Istanbul Technical University

profile:
  align: right
  image: group_logo.png
  image_circular: true

selected_papers: true
social: false
news: true
---

### Control • Safety • Reliability
**From control theory to safety-critical implementation.**

We develop deterministic control, state estimation, and rigorous verification methods for safety-critical autonomous, robotic, and industrial systems.

<div class="d-flex gap-2 my-3">
  <a href="{{ '/projects/' | relative_url }}" class="btn btn-sm btn-outline-primary fw-bold" style="border-radius: 6px; padding: 0.35rem 0.85rem;">Explore Projects</a>
  <a href="{{ '/team/' | relative_url }}" class="btn btn-sm btn-outline-secondary fw-bold" style="border-radius: 6px; padding: 0.35rem 0.85rem;">Meet the Team</a>
</div>

<!-- LATEST NEWS -->
<div class="lab-news-card my-4">
  <div class="news-badge"><i class="fa-solid fa-bullhorn me-1"></i> Latest News</div>
  <div class="news-content">
    <strong>August 2026:</strong> SCS Lab presented the <em>Algebraic MPC Toolbox: Theory and Realization</em> at the <strong>23rd IFAC World Congress</strong> in Busan, South Korea.
  </div>
</div>

<!-- 3 RESEARCH PILLARS -->
<h2 class="about-section-heading">Research Pillars</h2>

<div class="research-focus-grid">
  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-microchip"></i></div>
    <h3 class="focus-title">01. Control & Autonomous Systems</h3>
    <p class="focus-desc">
      Constrained predictive control (MPC, DeePC, Algebraic MPC), adaptive guidance, INDI, and real-time flight control law synthesis.
    </p>
  </div>

  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-shield-halved"></i></div>
    <h3 class="focus-title">02. Safety, Risk & Reliability</h3>
    <p class="focus-desc">
      Active Fault Detection and Isolation (FDI), robust state estimation (EKF), safety margins, and resilient deterministic architectures.
    </p>
  </div>

  <div class="focus-card">
    <div class="focus-icon-box"><i class="fa-solid fa-list-check"></i></div>
    <h3 class="focus-title">03. High-Integrity Software & V&V</h3>
    <p class="focus-desc">
      Model-based development workflows, formal verification, Hardware-in-the-Loop (HIL) testing, and DO-178C / ISO 26262 compliance.
    </p>
  </div>
</div>

<!-- APPLICATION DOMAINS HIERARCHY -->
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
