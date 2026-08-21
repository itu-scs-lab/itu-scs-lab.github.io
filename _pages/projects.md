---
layout: page
title: projects
permalink: /projects/
description: Ongoing and completed research projects on safety-critical control, predictive frameworks, and autonomous systems.
nav: true
nav_order: 3
display_categories: false
horizontal: true
---

<input type="text" id="project-search-input" class="form-control my-3 filter-search-input" placeholder="Type to filter (e.g., ongoing, completed, ITU)..." style="max-width: 340px; border-radius: 6px;">

<div class="projects">
{% assign sorted_projects = site.projects | sort: "importance" %}

{% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      <div class="col" data-org="{{ project.organization }}" data-status="{{ project.status }}" data-keywords="{{ project.keywords | join: ',' }}">
        {% include projects_horizontal.liquid %}
      </div>
    {% endfor %}
    </div>
  </div>
{% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      <div class="col" data-org="{{ project.organization }}" data-status="{{ project.status }}" data-keywords="{{ project.keywords | join: ',' }}">
        {% include projects.liquid %}
      </div>
    {% endfor %}
  </div>
{% endif %}
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var projectCols = document.querySelectorAll('.projects .col, .projects .row > div');

    projectCols.forEach(function(col) {
      var card = col.querySelector('.card') || col;
      var cardBody = card.querySelector('.card-body') || card;

      var orgData = col.getAttribute('data-org');
      var statusData = col.getAttribute('data-status');
      var keywordsData = col.getAttribute('data-keywords');

      // Üst Başlık Şeridi (Kurum + Durum Rozeti)
      if (!card.querySelector('.project-header-meta')) {
        var metaContainer = document.createElement('div');
        metaContainer.className = 'project-header-meta';

        // 1. Kurum Rozeti
        if (orgData && orgData.trim() !== '') {
          var orgBadge = document.createElement('span');
          orgBadge.className = 'project-org-badge';
          orgBadge.innerHTML = '<i class="fa-solid fa-building-columns"></i> ' + orgData.trim();
          metaContainer.appendChild(orgBadge);
        }

        // 2. Durum Rozeti (Ongoing / Completed)
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

      // 3. Keywords Rozetleri (Kartın En Altına)
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
