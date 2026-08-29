---
layout: page
permalink: /teaching/
title: teaching
description: Undergraduate and graduate courses offered at ITU SCS Lab.
nav: true
nav_order: 6
---

<div class="courses-hub-container mt-4">
  {% assign courses = site.teachings | default: site.courses | sort: "year" | reverse %}

  <div class="row row-cols-1 row-cols-md-2 g-4">
    {% for course in courses %}
      <div class="col course-item-card">
        <div class="custom-course-card">
          
          <!-- Kart Üst Başlık & Rozetler -->
  <div class="course-card-top">
            <div class="course-code-badge">
              <i class="fa-solid fa-graduation-cap me-1"></i>
              {{ course.course_id | default: "COURSE" | upcase }}
            </div>
            <div class="course-term-badge">
              <i class="fa-regular fa-calendar me-1"></i>
              {{ course.term }} {{ course.year }}
            </div>
          </div>

          <!-- Ders Başlığı -->
  <h3 class="course-title">
            <a href="{{ course.url | relative_url }}">{{ course.title }}</a>
          </h3>

          <!-- Eğitmen Bilgisi -->
  {% if course.instructor %}
          <div class="course-instructor">
            <i class="fa-solid fa-chalkboard-user"></i>
            <span>{{ course.instructor }}</span>
          </div>
          {% endif %}

          <!-- Ders Özeti / Açıklama -->
  <p class="course-description">
            {{ course.description | truncate: 155 }}
          </p>

          <!-- Alt Buton Linki -->
  <div class="course-card-footer">
            <a href="{{ course.url | relative_url }}" class="course-btn">
              View Syllabus & Schedule <i class="fa-solid fa-arrow-right ms-1"></i>
            </a>
          </div>

  </div>
</div>
    {% endfor %}
  </div>
</div>
