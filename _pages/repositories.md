---
layout: page
permalink: /repositories/
title: repositories
description: Open-source software toolboxes, algorithms, and research code developed by ITU SCS Lab.
nav: true
nav_order: 4
---

<!-- 1. GITHUB METRICS DASHBOARD -->
<div class="repo-dashboard-grid">
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

<!-- 2. SEARCH & DYNAMIC FILTER BAR -->
<div class="repo-toolbar my-4">
  <div class="repo-search-area">
    <input type="text" id="repo-search-input" class="repo-search-field" placeholder="Search toolboxes (e.g. Simulink, C++)...">
  </div>
  
  <div class="repo-filter-area">
    <button id="filter-all-btn" class="filter-all-btn active" type="button">All</button>
    <div class="select-wrapper">
      <select id="repo-tag-select" class="repo-dropdown-select" aria-label="Filter by tag">
        <option value="all">Filter by Tag (All)</option>
      </select>
    </div>
  </div>
</div>

<!-- 3. FEATURED RESEARCH TOOLBOXES -->
<div class="row row-cols-1 row-cols-md-2 g-4" id="custom-repo-grid">

  <!-- REPO 1: AMPC -->
  <div class="col repo-item" data-tags="MPC, Simulink, Flight Control, Optimization">
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
        <button class="copy-btn" title="Copy to clipboard" onclick="navigator.clipboard.writeText('git clone https://github.com/TalhaUlukir/AMPC.git')"><i class="fa-regular fa-copy"></i></button>
      </div>

  <div class="repo-tech-stack">
        <span class="tech-pill"><i class="fa-solid fa-circle" style="color: #e34c26;"></i> MATLAB</span>
        <span class="tech-pill"><i class="fa-solid fa-diagram-project"></i> Simulink Blockset</span>
        <span class="tech-pill">Predictive Control</span>
      </div>
    </div>
  </div>


</div>

<!-- 4. DİNAMİK DROPDOWN VE FİLTRELEME SCRIPT'İ -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const searchInput = document.getElementById('repo-search-input');
    const allBtn = document.getElementById('filter-all-btn');
    const tagSelect = document.getElementById('repo-tag-select');
    const repoCards = document.querySelectorAll('.repo-item');

    // 1. Sayfadaki kartlardan benzersiz tagleri toplayıp dropdown'a ekleme
    const uniqueTags = new Set();
    repoCards.forEach(card => {
      const tagsAttr = card.getAttribute('data-tags');
      if (tagsAttr) {
        tagsAttr.split(',').forEach(tag => {
          const cleanTag = tag.trim();
          if (cleanTag) uniqueTags.add(cleanTag);
        });
      }
    });

    // Alfabetik sıralayıp option olarak ekle
    Array.from(uniqueTags).sort().forEach(tag => {
      const option = document.createElement('option');
      option.value = tag.toLowerCase();
      option.textContent = tag;
      tagSelect.appendChild(option);
    });

    // 2. Filtre Uygulama Fonksiyonu
    function applyFilter() {
      const query = searchInput ? searchInput.value.toLowerCase().trim() : '';
      const selectedTag = tagSelect ? tagSelect.value.toLowerCase() : 'all';

      repoCards.forEach(card => {
        const text = card.textContent.toLowerCase();
        const tags = (card.getAttribute('data-tags') || '').toLowerCase();
        const matchesQuery = text.includes(query);
        const matchesTag = (selectedTag === 'all') || tags.includes(selectedTag);

        card.style.display = (matchesQuery && matchesTag) ? '' : 'none';
      });

      // Buton Aktiflik Durumu
      if (selectedTag === 'all') {
        allBtn.classList.add('active');
      } else {
        allBtn.classList.remove('active');
      }
    }

    // Arama Kutusu Dinleyicisi
    if (searchInput) {
      searchInput.addEventListener('input', applyFilter);
    }

    // Dropdown Seçim Dinleyicisi
    if (tagSelect) {
      tagSelect.addEventListener('change', applyFilter);
    }

    // "All" Butonu Dinleyicisi
    if (allBtn) {
      allBtn.addEventListener('click', function() {
        if (tagSelect) tagSelect.value = 'all';
        applyFilter();
      });
    }
  });
</script>
