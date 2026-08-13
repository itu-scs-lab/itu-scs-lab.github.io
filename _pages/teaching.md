---
layout: page
title: teaching
permalink: /teaching/
description: Undergraduate and graduate courses offered at ITU SCS Lab.
nav: true
nav_order: 6
---

<div class="teaching-container">
  {% assign years = site.teaching | map: 'year' | uniq | sort | reverse %}
  {% for year in years %}
    
    <!-- Yıl Ayraç Şeridi (Hafif Renkli Yarı Şerit) -->
    <div class="year-divider">
      <h2 class="year-title">{{ year }}</h2>
      <div class="year-line"></div>
    </div>

    <!-- Ders Kartları Izgarası (Grid Block Yapısı) -->
    <div class="courses-grid">
      {% assign courses = site.teaching | where: 'year', year %}
      {% for course in courses %}
        <div class="course-card">
          <div class="course-card-body">
            <h3 class="course-title">
              {% if course.url %}
                <a href="{{ course.url | relative_url }}">{{ course.title }}</a>
              {% else %}
                {{ course.title }}
              {% endif %}
            </h3>
            
            {% if course.role or course.term or course.instructor %}
              <div class="course-meta">
                <span class="badge course-badge">
                  <i class="fa-solid fa-calendar-days"></i> {{ course.term }}
                </span>
                {% if course.role %}
                  <span class="course-role">• {{ course.role }}</span>
                {% endif %}
              </div>
            {% endif %}

            {% if course.description %}
              <p class="course-description">{{ course.description }}</p>
            {% endif %}
          </div>
        </div>
      {% endfor %}
    </div>

  {% endfor %}
</div>
