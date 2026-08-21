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

<input type="text" id="project-search-input" class="form-control my-3 filter-search-input" placeholder="Type to filter..." style="max-width: 320px; border-radius: 6px;">

<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      <div class="col" data-org="{{ project.organization }}" data-keywords="{{ project.keywords | join: ',' }}">
        {% include projects_horizontal.liquid %}
      </div>
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      <div class="col" data-org="{{ project.organization }}" data-keywords="{{ project.keywords | join: ',' }}">
        {% include projects.liquid %}
      </div>
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->
{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->
{% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      <div class="col" data-org="{{ project.organization }}" data-keywords="{{ project.keywords | join: ',' }}">
        {% include projects_horizontal.liquid %}
      </div>
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      <div class="col" data-org="{{ project.organization }}" data-keywords="{{ project.keywords | join: ',' }}">
        {% include projects.liquid %}
      </div>
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    // 1. Kurum ve Keywords Rozetlerini Kartlara Enjekte Etme
    var projectCols = document.querySelectorAll('.projects .col');

    projectCols.forEach(function(col) {
      var card = col.querySelector('.card') || col;
      var cardBody = card.querySelector('.card-body') || card;

      var orgData = col.getAttribute('data-org');
      var keywordsData = col.getAttribute('data-keywords');

      // Kurum / Fon Rozeti (Başlığın Üstüne)
      if (orgData && orgData.trim() !== '' && !card.querySelector('.project-org-badge')) {
        var orgBadge = document.createElement('div');
        orgBadge.className = 'project-org-badge';
        orgBadge.innerHTML = '<i class="fa-solid fa-building-columns"></i> ' + orgData.trim();
        cardBody.insertBefore(orgBadge, cardBody.firstChild);
      }

      // Keywords Kapsülleri (Kartın En Altına)
      if (keywordsData && keywordsData.trim() !== '' && !card.querySelector('.project-keywords-container')) {
        var keywords = keywordsData.split(',');
        var container = document.createElement('div');
        container.className = 'project-keywords-container';

        keywords.forEach(function(kw) {
          if (kw.trim() !== '') {
            var pill = document.createElement('span');
            pill.className = 'project-keyword-pill';
            pill.textContent = kw.trim();
            container.appendChild(pill);
          }
        });

        cardBody.appendChild(container);
      }
    });

    // 2. Arama Filtresi (Keywords ve Kurum İsimleri Dahil Arama Yapar)
    var searchInput = document.getElementById('project-search-input');
    if (searchInput) {
      searchInput.addEventListener('input', function() {
        var query = this.value.toLowerCase().trim();
        projectCols.forEach(function(col) {
          var text = col.textContent.toLowerCase();
          col.style.display = text.includes(query) ? '' : 'none';
        });
      });
    }
  });
</script>
