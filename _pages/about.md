---
layout: about
title: about
permalink: /
subtitle: Safety-Critical Systems Laboratory at Istanbul Technical University

profile:
  align: right
  image: group_logo.png
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

The Safety-Critical Systems Laboratory (SCS Lab) develops advanced methods in control, autonomy, safety, reliability, and high-integrity software for complex dynamical systems.
Our research bridges rigorous theoretical foundations with real-time implementation, addressing the challenges of constrained operation, uncertainty, faults, and verification in safety-critical systems.

<!-- HERO BUTONLARI -->
<div class="about-cta-group">
  <a href="{{ '/projects/' | relative_url }}" class="hero-btn hero-btn-primary">
    <i class="fa-solid fa-diagram-project"></i> Explore Projects
  </a>
  <a href="{{ '/team/' | relative_url }}" class="hero-btn hero-btn-secondary">
    <i class="fa-solid fa-users"></i> Meet the Team
  </a>
</div>

<!-- OTOMATİK HABER ÇEKİCİ (LATEST NEWS) -->
{% assign latest_news = site.news | sort: "date" | reverse | first %}
{% if latest_news %}
<div class="lab-news-card my-3">
  <div class="news-badge"><i class="fa-solid fa-bullhorn me-1"></i> Latest News</div>
  <div class="news-content">
    <strong>{{ latest_news.date | date: "%b %Y" }}:</strong> {{ latest_news.content | remove: '<p>' | remove: '</p>' | strip }}
  </div>
</div>
{% endif %}

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

<!-- 2. APPLICATION DOMAINS -->

<h2 class="about-section-heading">Application Domains</h2>

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
    <i class="fa-solid fa-robot me-1"></i> Robotics & Mechatronics
  </span>

  <span class="domain-pill">
    <i class="fa-solid fa-bolt me-1"></i> Energy & Process Systems
  </span>

</div>
<!-- 3. AKILLI SEÇİLİ YAYINLAR ROZET MOTORU -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    var pubEntries = document.querySelectorAll('.publications ol.bibliography > li');
    pubEntries.forEach(function(entry) {
      if (!entry.querySelector('.pub-badge-wrapper')) {
        var emElem = entry.querySelector('em') || entry.querySelector('i');
        var venueText = emElem ? emElem.textContent.toLowerCase() : '';
        
        var isConf = venueText.startsWith('in ') || 
                     venueText.includes('conference') || 
                     venueText.includes('congress') || 
                     venueText.includes('symposium') || 
                     venueText.includes('proceedings') || 
                     venueText.includes('toplantı') ||
                     venueText.includes('toplantisi');

        var badgeHTML = isConf 
          ? '<span class="pub-badge pub-badge-conference"><i class="fa-solid fa-users"></i> Conference</span>'
          : '<span class="pub-badge pub-badge-journal"><i class="fa-solid fa-file-lines"></i> Journal</span>';

        var badgeContainer = document.createElement('div');
        badgeContainer.className = 'pub-badge-wrapper';
        badgeContainer.innerHTML = badgeHTML;
        entry.insertBefore(badgeContainer, entry.firstChild);
      }
    });
  });
</script>
