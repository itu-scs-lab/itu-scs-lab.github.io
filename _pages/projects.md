---
layout: page
title: projects
permalink: /projects/
description: Ongoing and completed research projects on safety-critical control, predictive frameworks, and autonomous systems.
nav: true
nav_order: 3
display_categories: false
horizontal: false
---

<input type="text" id="project-search-input" class="form-control my-3 filter-search-input" placeholder="Type to filter (e.g., ongoing, completed, TUBITAK)..." style="max-width: 340px; border-radius: 6px;">

<div class="projects">
{% assign sorted_projects = site.projects | sort: "importance" %}

  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-2 g-4">
  {% for project in sorted_projects %}
    <div class="col" data-org="{{ project.organization }}" data-status="{{ project.status }}" data-keywords="{{ project.keywords | join: ',' }}">
      {% include projects.liquid %}
    </div>
  {% endfor %}
  </div>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var projectCols = document.querySelectorAll('.projects .col, .projects .grid-item');

    projectCols.forEach(function(col) {
      var card = col.querySelector('.card') || col;
      var cardBody = card.querySelector('.card-body') || card;

      var orgData = col.getAttribute('data-org');
      var statusData = col.getAttribute('data-status');
      var keywordsData = col.getAttribute('data-keywords');

      // 1. Üst Meta Şeridi (Kurum + Durum Rozeti)
      if (!card.querySelector('.project-header-meta')) {
        var metaContainer = document.createElement('div');
        metaContainer.className = 'project-header-meta';

        // Kurum Rozeti
        if (orgData && orgData.trim() !== '') {
          var orgBadge = document.createElement('span');
          orgBadge.className = 'project-org-badge';
          orgBadge.innerHTML = '<i class="fa-solid fa-building-columns"></i> ' + orgData.trim();
          metaContainer.appendChild(orgBadge);
        }

        // Durum Rozeti (Ongoing / Completed)
        if (statusData && statusData.trim() !== '') {
          var statusBadge = document.createElement('span');
          var isCompleted = statusData.trim().toLowerCase() === 'completed';

          if (isCompleted) {
            statusBadge.className = 'project-status-badge status-completed';
            statusBadge.innerHTML = '<i class="fa-solid fa-circle-check"></i> Completed';
            card.classList.add('card-completed');
          } else {
            statusBadge.className = 'project-status-badge status-ongoing';
            statusBadge.innerHTML = '<i class="fa-solid fa-arrows-rotate"></i> Ongoing';
          }
          metaContainer.appendChild(statusBadge);
        }

        var titleElem = cardBody.querySelector('.card-title') || cardBody.firstChild;
        cardBody.insertBefore(metaContainer, titleElem);
      }

      // 2. Keywords Kapsülleri (Kartın En Altına)
      if (keywordsData && keywordsData.trim() !== '' && !card.querySelector('.project-keywords-container')) {
        var keywords = keywordsData.split(',');
        var container = document.createElement('div');
        container.className = 'project-keywords-container';

        keywords.forEach(function(kw) {
          var cleanKw = kw.trim();
          if (cleanKw.length > 0) {
            var pill = document.createElement('span');
            pill.className = 'project-keyword-pill';
            pill.textContent = cleanKw;
            container.appendChild(pill);
          }
        });

        cardBody.appendChild(container);
      }
    });

    // Arama Filtresi
    var searchInput = document.getElementById('project-search-input');
    if (searchInput) {
      searchInput.addEventListener('input', function() {
        var query = this.value.toLowerCase().trim();
        projectCols.forEach(function(col) {
          var text = col.textContent.toLowerCase();
          var status = (col.getAttribute('data-status') || '').toLowerCase();
          col.style.display = (text.includes(query) || status.includes(query)) ? '' : 'none';
        });
      });
    }
  });
</script>
