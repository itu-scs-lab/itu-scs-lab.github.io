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

{% assign courses_by_year = site.teaching | group_by: "year" | sort: "name" | reverse %}
{% if courses_by_year.size == 0 %}
  {% assign courses_by_year = site.data.courses | group_by: "year" | sort: "name" | reverse %}
{% endif %}

{% for year_group in courses_by_year %}
  <div class="year-divider">
    <h2 class="year-title">{{ year_group.name }}</h2>
    <div class="year-line"></div>
  </div>

  <div class="courses-grid">
    {% for course in year_group.items %}
      <div class="course-card">
        <div class="course-card-body">
          <h3 class="course-title">
            {% if course.url %}
              <a href="{{ course.url }}">{{ course.title }}</a>
            {% else %}
              {{ course.title }}
            {% endif %}
          </h3>

   <div class="course-meta">
            {% if course.term %}
              <span class="badge course-badge"><i class="fa-solid fa-calendar-days"></i> {{ course.term }}</span>
            {% endif %}
            {% if course.instructor %}
              <span class="course-role">• {{ course.instructor }}</span>
            {% elsif course.role %}
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
{% endfor %}

</div>
