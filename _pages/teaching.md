---
layout: page
permalink: /teaching/
title: teaching
description: Undergraduate and graduate courses offered at ITU SCS Lab.
nav: true
nav_order: 6
calendar: false
---

<div class="teaching-container">
  {% assign years = site.teaching | map: 'year' | uniq | sort | reverse %}
  
  {% for year in years %}
    {% if year %}
      <!-- Yıl Ayraç Şeridi -->
      <div class="year-divider">
        <h2 class="year-title">{{ year }}</h2>
        <div class="year-line"></div>
      </div>

    <!-- Ders Kartları Grid Bloğu -->
  <div class="courses-grid">
        {% assign courses = site.teaching | where: 'year', year %}
        {% for course in courses %}
          <div class="course-card">
            <div class="course-card-body">
              <h3 class="course-title">
                {% if course.inline %}
                  {{ course.title }}
                {% else %}
                  <a href="{{ course.url | relative_url }}">{{ course.title }}</a>
                {% endif %}
              </h3>

  <div class="course-meta">
                {% if course.term %}
                  <span class="badge course-badge"><i class="fa-solid fa-calendar-days"></i> {{ course.term }}</span>
                {% endif %}
                {% if course.role %}
                  <span class="course-role">• {{ course.role }}</span>
                {% endif %}
              </div>

  {% if course.description %}
                <p class="course-description">{{ course.description }}</p>
              {% endif %}
            </div>
          </div>
        {% endfor %}
      </div>
    {% endif %}
  {% endfor %}
</div>
