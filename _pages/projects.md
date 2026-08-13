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
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
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
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var searchInput = document.getElementById('project-search-input');
    if (searchInput) {
      searchInput.addEventListener('input', function() {
        var query = this.value.toLowerCase().trim();
        var projectCols = document.querySelectorAll('.projects .row > div, .projects .card');
        
        projectCols.forEach(function(col) {
          var text = col.textContent.toLowerCase();
          if (text.includes(query)) {
            col.style.display = '';
          } else {
            col.style.display = 'none';
          }
        });
      });
    }
  });
</script>
