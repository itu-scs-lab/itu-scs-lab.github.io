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

{% assign raw_courses = site.teaching %}
{% if raw_courses == nil or raw_courses.size == 0 %}
  {% assign raw_courses = site.data.courses %}
{% endif %}

{% if raw_courses and raw_courses.size > 0 %}
  {% assign courses_by_year = raw_courses | group_by: "year" %}
  {% for year_group in courses_by_year %}
    {% if year_group.name and year_group.name != "" %}
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
    {% endif %}
  {% endfor %}
{% endif %}

</div>
