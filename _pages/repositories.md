---
layout: page
permalink: /repositories/
title: repositories
description: Open-source software toolboxes, flight control algorithms, and research code developed by ITU SCS Lab.
nav: true
nav_order: 4
---

<!-- 1. GITHUB METRICS DASHBOARD -->
<div class="repo-dashboard-grid mb-5">
  <div class="repo-stat-card">
    <div class="stat-icon"><i class="fa-solid fa-code-fork"></i></div>
    <div class="stat-info">
      <span class="stat-value">Open-Source</span>
      <span class="stat-label">Research Ecosystem</span>
    </div>
  </div>
  <div class="repo-stat-card">
    <div class="stat-icon"><i class="fa-solid fa-microchip"></i></div>
    <div class="stat-info">
      <span class="stat-value">Real-Time</span>
      <span class="stat-label">HIL & Embedded Ready</span>
    </div>
  </div>
  <div class="repo-stat-card">
    <div class="stat-icon"><i class="fa-brands fa-github"></i></div>
    <div class="stat-info">
      <span class="stat-value">GitHub</span>
      <span class="stat-label">Verified Toolboxes</span>
    </div>
  </div>
</div>

<!-- 2. SEARCH & FILTER BAR -->
<div class="d-flex flex-wrap justify-content-between align-items-center gap-3 mb-4">
  <input type="text" id="repo-search-input" class="form-control filter-search-input" placeholder="Search toolboxes (e.g. MPC, Simulink, Kalman, C++)..." style="max-width: 380px; border-radius: 8px;">
  
  <div class="repo-filter-tags">
    <button class="filter-btn active" data-filter="all">All</button>
    <button class="filter-btn" data-filter="mpc">MPC & Control</button>
    <button class="filter-btn" data-filter="simulink">MATLAB/Simulink</button>
    <button class="filter-btn" data-filter="estimation">Estimation</button>
  </div>
</div>

<!-- 3. FEATURED RESEARCH TOOLBOXES -->
<div class="row row-cols-1 row-cols-md-2 g-4" id="custom-repo-grid">

  <!-- REPO 1: AMPC -->
  <div class="col repo-item" data-tags="mpc simulink flight-control">
    <div class="custom-repo-card">
      <div class="repo-card-header">
        <div class="repo-type-badge"><i class="fa-solid fa-cube"></i> Toolbox</div>
        <a href="https://github.com/TalhaUlukir/AMPC" target="_blank" class="repo-gh-link"><i class="fa-brands fa-github"></i></a>
      </div>
      <h3 class="repo-title">
        <a href="https://github.com/TalhaUlukir/AMPC" target="_blank">TalhaUlukir/AMPC</a>
      </h3>
      <p class="repo-description">
        Algebraic Model Predictive Control (A-MPC) toolbox developed for Linear Time-Invariant (LTI) systems with closed-form solution structures for fast, real-time embedded execution.
      </p>
      
  <div class="repo-install-snippet">
        <code>git clone https://github.com/TalhaUlukir/AMPC.git</code>
        <button class="copy-btn" onclick="navigator.clipboard.writeText('git clone https://github.com/TalhaUlukir/AMPC.git')"><i class="fa-regular fa-copy"></i></button>
      </div>

  <div class="repo-tech-stack">
        <span class="tech-pill"><i class="fa-solid fa-circle" style="color: #e34c26;"></i> MATLAB</span>
        <span class="tech-pill"><i class="fa-solid fa-diagram-project"></i> Simulink Blockset</span>
        <span class="tech-pill">Predictive Control</span>
      </div>
    </div>
  </div>

  <!-- REPO 2: DDMPC Conditioning & Subspace (Hazır Taslak) -->
  <div class="col repo-item" data-tags="mpc simulink">
    <div class="custom-repo-card">
      <div class="repo-card-header">
        <div class="repo-type-badge"><i class="fa-solid fa-wave-square"></i> Algorithms</div>
        <a href="https://github.com/TalhaUlukir" target="_blank" class="repo-gh-link"><i class="fa-brands fa-github"></i></a>
      </div>
      <h3 class="repo-title">
        <a href="https://github.com/TalhaUlukir" target="_blank">TalhaUlukir/DDMPC-Conditioning</a>
      </h3>
      <p class="repo-description">
        Subspace shaping and numerical conditioning routines for Data-Driven Predictive Control. Reduces Hankel matrix ill-conditioning under noisy operating regimes.
      </p>

  <div class="repo-install-snippet">
        <code>git clone https://github.com/TalhaUlukir/DDMPC-Conditioning.git</code>
        <button class="copy-btn" onclick="navigator.clipboard.writeText('git clone https://github.com/TalhaUlukir/DDMPC-Conditioning.git')"><i class="fa-regular fa-copy"></i></button>
      </div>

  <div class="repo-tech-stack">
        <span class="tech-pill"><i class="fa-solid fa-circle" style="color: #e34c26;"></i> MATLAB</span>
        <span class="tech-pill">Data-Driven MPC</span>
        <span class="tech-pill">Hankel Conditioning</span>
      </div>
    </div>
  </div>

  <!-- REPO 3: GNSS/INS Sensor Fusion (Hazır Taslak) -->
  <div class="col repo-item" data-tags="estimation simulink">
    <div class="custom-repo-card">
      <div class="repo-card-header">
        <div class="repo-type-badge"><i class="fa-solid fa-compass"></i> Navigation</div>
        <a href="https://github.com/TalhaUlukir" target="_blank" class="repo-gh-link"><i class="fa-brands fa-github"></i></a>
      </div>
      <h3 class="repo-title">
        <a href="https://github.com/TalhaUlukir" target="_blank">TalhaUlukir/Loosely-Coupled-INS</a>
      </h3>
      <p class="repo-description">
        Model-based loosely coupled GNSS/INS Kalman Filter integration architecture in Simulink targeting certifiable embedded flight control computers (DO-178C).
      </p>

  <div class="repo-install-snippet">
        <code>git clone https://github.com/TalhaUlukir/Loosely-Coupled-INS.git</code>
        <button class="copy-btn" onclick="navigator.clipboard.writeText('git clone https://github.com/TalhaUlukir/Loosely-Coupled-INS.git')"><i class="fa-regular fa-copy"></i></button>
      </div>

  <div class="repo-tech-stack">
        <span class="tech-pill"><i class="fa-solid fa-circle" style="color: #00599c;"></i> C / C++</span>
        <span class="tech-pill">Simulink</span>
        <span class="tech-pill">Kalman Filter</span>
      </div>
    </div>
  </div>

  <!-- REPO 4: UAV Flight Guidance (Hazır Taslak) -->
  <div class="col repo-item" data-tags="mpc flight-control">
    <div class="custom-repo-card">
      <div class="repo-card-header">
        <div class="repo-type-badge"><i class="fa-solid fa-plane-up"></i> Guidance</div>
        <a href="https://github.com/TalhaUlukir" target="_blank" class="repo-gh-link"><i class="fa-brands fa-github"></i></a>
      </div>
      <h3 class="repo-title">
        <a href="https://github.com/TalhaUlukir" target="_blank">TalhaUlukir/UAV-Guidance-Sim</a>
      </h3>
      <p class="repo-description">
        2D/3D route following, Non-linear L1 guidance, Vector Field navigation, and waypoint management simulation testbed for autonomous aerial vehicles.
      </p>

  <div class="repo-install-snippet">
        <code>git clone https://github.com/TalhaUlukir/UAV-Guidance-Sim.git</code>
        <button class="copy-btn" onclick="navigator.clipboard.writeText('git clone https://github.com/TalhaUlukir/UAV-Guidance-Sim.git')"><i class="fa-regular fa-copy"></i></button>
      </div>

  <div class="repo-tech-stack">
        <span class="tech-pill"><i class="fa-solid fa-circle" style="color: #e34c26;"></i> MATLAB</span>
        <span class="tech-pill">L1 Guidance</span>
        <span class="tech-pill">Path Following</span>
      </div>
    </div>
  </div>

</div>

<!-- REPO INTERACTION & FILTER JAVASCRIPT -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const searchInput = document.getElementById('repo-search-input');
    const filterBtns = document.querySelectorAll('.filter-btn');
    const repoCards = document.querySelectorAll('.repo-item');

    function applyFilter() {
      const query = searchInput ? searchInput.value.toLowerCase().trim() : '';
      const activeBtn = document.querySelector('.filter-btn.active');
      const filterValue = activeBtn ? activeBtn.getAttribute('data-filter') : 'all';

      repoCards.forEach(card => {
        const text = card.textContent.toLowerCase();
        const tags = (card.getAttribute('data-tags') || '').toLowerCase();
        const matchesQuery = text.includes(query);
        const matchesFilter = (filterValue === 'all') || tags.includes(filterValue);

        card.style.display = (matchesQuery && matchesFilter) ? '' : 'none';
      });
    }

    if (searchInput) {
      searchInput.addEventListener('input', applyFilter);
    }

    filterBtns.forEach(btn => {
      btn.addEventListener('click', function() {
        filterBtns.forEach(b => b.classList.remove('active'));
        this.classList.add('active');
        applyFilter();
      });
    });
  });
</script>
