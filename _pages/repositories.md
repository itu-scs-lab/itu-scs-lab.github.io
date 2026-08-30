---
layout: page
permalink: /repositories/
title: Software
description: Open-source software toolboxes, algorithms, and research code developed by ITU SCS Lab.
nav: true
nav_order: 5
---

<!-- 1. GÖSTERGE METRİKLERİ -->
<div class="repo-metrics-row">
  <div class="repo-metric-box">
    <div class="metric-icon"><i class="fa-solid fa-code-fork"></i></div>
    <div class="metric-text">
      <span class="metric-title">Open-Source</span>
      <span class="metric-sub">Research Ecosystem</span>
    </div>
  </div>
  <div class="repo-metric-box">
    <div class="metric-icon"><i class="fa-solid fa-microchip"></i></div>
    <div class="metric-text">
      <span class="metric-title">Real-Time</span>
      <span class="metric-sub">HIL & Embedded Ready</span>
    </div>
  </div>
  <div class="repo-metric-box">
    <div class="metric-icon"><i class="fa-brands fa-github"></i></div>
    <div class="metric-text">
      <span class="metric-title">GitHub</span>
      <span class="metric-sub">Verified Toolboxes</span>
    </div>
  </div>
</div>

<!-- 2. ARAMA VE AÇILIR LİSTE FİLTRESİ -->
<div class="repo-toolbar">
  <input type="text" id="repo-search-input" class="repo-search-field" placeholder="Search toolboxes (e.g. Simulink, C++)...">
  <div class="repo-filter-group">
    <button id="filter-all-btn" class="filter-all-btn active" type="button">All</button>
    <select id="repo-tag-select" class="repo-select" aria-label="Filter by tag">
      <option value="all">Filter by Tag (All)</option>
    </select>
  </div>
</div>

<!-- 3. REPO KARTLARI GRİDİ -->
<div class="row row-cols-1 row-cols-md-2 g-4" id="repo-card-grid">

  <!-- REPO 1: AMPC -->
  <div class="col repo-item" data-tags="MPC, Simulink, Flight Control, Optimization">
    <div class="card repo-card">
      <div class="card-body">
        <div class="repo-top">
          <span class="badge-tag"><i class="fa-solid fa-cube me-1"></i> Toolbox</span>
          <a href="https://github.com/TalhaUlukir/AMPC" target="_blank" class="text-secondary"><i class="fa-brands fa-github fs-5"></i></a>
        </div>
        <h3 class="repo-heading">
          <a href="https://github.com/TalhaUlukir/AMPC" target="_blank">TalhaUlukir/AMPC</a>
        </h3>
        <p class="repo-desc">
          Algebraic Model Predictive Control (A-MPC) toolbox developed for Linear Time-Invariant (LTI) systems with closed-form solution structures for fast, real-time embedded execution.
        </p>
        <div class="repo-clone">
          <code>git clone https://github.com/TalhaUlukir/AMPC.git</code>
          <button title="Copy" onclick="navigator.clipboard.writeText('git clone https://github.com/TalhaUlukir/AMPC.git')"><i class="fa-regular fa-copy"></i></button>
        </div>
        <div class="repo-tags-wrap">
          <span class="pill-item"><i class="fa-solid fa-circle me-1" style="color: #e34c26;"></i> MATLAB</span>
          <span class="pill-item"><i class="fa-solid fa-diagram-project me-1"></i> Simulink Blockset</span>
          <span class="pill-item">Predictive Control</span>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- 4. JAVASCRIPT ETİKET TOPLAMA & FİLTRELEME -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const searchInput = document.getElementById('repo-search-input');
    const allBtn = document.getElementById('filter-all-btn');
    const tagSelect = document.getElementById('repo-tag-select');
    const repoCols = document.querySelectorAll('#repo-card-grid .repo-item');

    // Tagleri dinamik doldur
    const uniqueTags = new Set();
    repoCols.forEach(col => {
      const tags = col.getAttribute('data-tags');
      if (tags) {
        tags.split(',').forEach(t => {
          const clean = t.trim();
          if (clean) uniqueTags.add(clean);
        });
      }
    });

    Array.from(uniqueTags).sort().forEach(tag => {
      const opt = document.createElement('option');
      opt.value = tag.toLowerCase();
      opt.textContent = tag;
      tagSelect.appendChild(opt);
    });

    // Filtreleme
    function applyFilter() {
      const q = searchInput ? searchInput.value.toLowerCase().trim() : '';
      const selected = tagSelect ? tagSelect.value.toLowerCase() : 'all';

      repoCols.forEach(col => {
        const text = col.textContent.toLowerCase();
        const tags = (col.getAttribute('data-tags') || '').toLowerCase();
        const matchesQ = text.includes(q);
        const matchesTag = (selected === 'all') || tags.includes(selected);

        col.style.display = (matchesQ && matchesTag) ? '' : 'none';
      });

      if (selected === 'all') {
        allBtn.classList.add('active');
      } else {
        allBtn.classList.remove('active');
      }
    }

    if (searchInput) searchInput.addEventListener('input', applyFilter);
    if (tagSelect) tagSelect.addEventListener('change', applyFilter);
    if (allBtn) {
      allBtn.addEventListener('click', function() {
        if (tagSelect) tagSelect.value = 'all';
        applyFilter();
      });
    }
  });
</script>
