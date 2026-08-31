---
layout: about
title: about
permalink: /
subtitle: Safety-Critical Systems Laboratory at Istanbul Technical University

profile:
  align: right
  image: group_logo.png
  image_circular: true

news: true
selected_papers: true
social: false
---

### Control • Safety • Reliability
**From control theory to safety-critical implementation.**

The Safety-Critical Systems Laboratory (SCS Lab) develops advanced methods in control, autonomy, safety, reliability, and high-integrity software for complex dynamical systems. Our research bridges rigorous theoretical foundations with real-time implementation, addressing constrained operation, uncertainty, faults, computational limitations, and verification challenges in safety-critical systems. By integrating control theory, system-level safety, and dependable embedded software, we aim to develop solutions that are robust, predictable, and suitable for deployment in demanding real-world applications.

<!-- HERO BUTONLARI -->
<div class="about-cta-group">
  <a href="{{ '/research/' | relative_url }}" class="hero-btn hero-btn-primary">
    <i class="fa-solid fa-flask"></i> Explore Research
  </a>
  <a href="{{ '/projects/' | relative_url }}" class="hero-btn hero-btn-secondary">
    <i class="fa-solid fa-diagram-project"></i> Explore Projects
  </a>
  <a href="{{ '/team/' | relative_url }}" class="hero-btn hero-btn-secondary">
    <i class="fa-solid fa-users"></i> Meet the Team
  </a>
</div>

<!-- OTOMATİK HABER LİSTESİ (LATEST NEWS - SON 3 HABER) -->
{% assign recent_news = site.news | sort: "date" | reverse %}
{% if recent_news.size > 0 %}
<div class="lab-news-card my-3">
  <div class="news-badge"><i class="fa-solid fa-bullhorn me-1"></i> Latest News</div>
  <div class="news-list-container">
    <ul class="news-list">
      {% for item in recent_news limit: 3 %}
      <li class="news-item">
        <span class="news-date">{{ item.date | date: "%b %Y" }}:</span>
        <span class="news-text">
          {% if item.inline %}
            {{ item.content | remove: '<p>' | remove: '</p>' | strip }}
          {% else %}
            <a href="{% if item.redirect %}{{ item.redirect }}{% else %}{{ item.url | relative_url }}{% endif %}" class="news-link"{% if item.redirect %} target="_blank"{% endif %}>
              {{ item.title }}
              <i class="fa-solid fa-arrow-right ms-1" style="font-size: 0.7rem;"></i>
            </a>
          {% endif %}
        </span>
      </li>
      {% endfor %}
    </ul>
  </div>
</div>
{% endif %}

<!-- 1. RESEARCH PILLARS -->
<section class="research-pillars-section">

  <div class="research-pillars-header">
    <h2 class="about-section-heading">Research Pillars</h2>
    <p class="research-pillars-intro">
      Our research is organized around three complementary pillars that connect
      control theory, system-level safety, and high-integrity implementation.
    </p>
  </div>

  <div class="research-focus-grid">

    <!-- Pillar 1 -->
  <div class="focus-card">
      <div class="focus-number">01</div>
      <div class="focus-accent"></div>

  <h3 class="focus-title">Control Systems & Autonomy</h3>

  <p class="focus-desc">
        Predictive, data-driven, robust, and nonlinear control for constrained
        and complex dynamical systems.
      </p>
    </div>

    <!-- Pillar 2 -->
  <div class="focus-card">
      <div class="focus-number">02</div>
      <div class="focus-accent"></div>

  <h3 class="focus-title">Safety, Risk & Reliability</h3>

  <p class="focus-desc">
        Fault diagnosis, resilient control, robust estimation, and safety-aware
        methods for dependable operation.
      </p>
    </div>

    <!-- Pillar 3 -->
  <div class="focus-card">
      <div class="focus-number">03</div>
      <div class="focus-accent"></div>

  <h3 class="focus-title">High-Integrity Software & V&V</h3>

  <p class="focus-desc">
        Model-based development, verification, testing, and certification-oriented
        engineering for high-integrity systems.
      </p>
    </div>

  </div>

  <div class="research-pillars-link">
    <a href="{{ '/research/' | relative_url }}">
      Explore Our Research
      <i class="fa-solid fa-arrow-right"></i>
    </a>
  </div>

</section>

<!-- 2. APPLICATION DOMAINS HIERARCHY -->
<h2 class="about-section-heading">Application Domains</h2>

<div class="domains-showcase-section">
  <div class="domains-cards-grid">
    <div class="domain-interactive-card">
      <div class="domain-icon-box"><i class="fa-solid fa-plane-up"></i></div>
      <div class="domain-card-name">Aerospace & Flight Systems</div>
    </div>
    <div class="domain-interactive-card">
      <div class="domain-icon-box"><i class="fa-solid fa-car"></i></div>
      <div class="domain-card-name">Automotive & ADAS</div>
    </div>
    <div class="domain-interactive-card">
      <div class="domain-icon-box"><i class="fa-solid fa-train"></i></div>
      <div class="domain-card-name">Rail & Guided Transit</div>
    </div>
    <div class="domain-interactive-card">
      <div class="domain-icon-box"><i class="fa-solid fa-robot"></i></div>
      <div class="domain-card-name">Robotics & Mechatronics</div>
    </div>
    <div class="domain-interactive-card">
      <div class="domain-icon-box"><i class="fa-solid fa-bolt"></i></div>
      <div class="domain-card-name">Energy & Process Systems</div>
    </div>
  </div>
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
