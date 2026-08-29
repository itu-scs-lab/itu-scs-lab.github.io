---
layout: page
permalink: /teaching/
title: teaching
description: Undergraduate and graduate courses offered at ITU SCS Lab.
nav: true
nav_order: 6
---

<!-- 1. DİNAMİK SEVİYE FİLTRE BUTONLARI -->
<div class="d-flex justify-content-between align-items-center flex-wrap gap-3 mb-4">
  <div class="course-filter-group">
    <button class="course-filter-btn active" data-filter="all">All</button>
    <button class="course-filter-btn" data-filter="undergraduate">Undergraduate</button>
    <button class="course-filter-btn" data-filter="graduate">Graduate</button>
    <button class="course-filter-btn" data-filter="special course">Special Course</button>
  </div>
</div>

<!-- 2. DERS KARTLARI GRİDİ -->
<div class="courses-hub-container">
  {% assign courses = site.teachings | default: site.courses | sort: "year" | reverse %}

  <div class="row row-cols-1 row-cols-md-2 g-4" id="courses-grid">
    {% for course in courses %}
      {% assign course_level = course.level | default: "Undergraduate" %}
      <div class="col course-col-item" data-level="{{ course_level | downcase }}">
        <div class="custom-course-card">
          
          <!-- Kart Üst Başlık & Rozetler -->
  <div class="course-card-top">
            <div class="course-code-badge">
              <i class="fa-solid fa-graduation-cap me-1"></i>
              {{ course.course_id | default: "COURSE" | upcase }}
            </div>
            
  <div class="course-meta-badges">
              <!-- Seviye Rozeti (Undergraduate / Graduate) -->
              <span class="course-level-badge level-{{ course_level | downcase | replace: ' ', '-' }}">
                {{ course_level }}
              </span>
              <!-- Dönem Rozeti -->
              <span class="course-term-badge">
                <i class="fa-regular fa-calendar me-1"></i>
                {{ course.term }} {{ course.year }}
              </span>
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

          <!-- Ek Bilgi Şeridi (Kredi, vb.) -->
  {% if course.credits %}
          <div class="course-extra-info">
            <span class="extra-pill"><i class="fa-solid fa-award me-1"></i>{{ course.credits }}</span>
          </div>
          {% endif %}

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

<!-- 3. FİLTRELEME SCRIPT'İ -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const filterBtns = document.querySelectorAll('.course-filter-btn');
    const courseItems = document.querySelectorAll('.course-col-item');

    filterBtns.forEach(btn => {
      btn.addEventListener('click', function() {
        filterBtns.forEach(b => b.classList.remove('active'));
        this.classList.add('active');

        const filter = this.getAttribute('data-filter');

        courseItems.forEach(item => {
          const itemLevel = item.getAttribute('data-level') || '';

          // Eski hatalı mantık:
// if (filter === 'all' || itemLevel.includes(filter))

// Düzeltilmiş kesin mantık:
if (filter === 'all' || itemLevel === filter) {
  item.style.setProperty('display', '', 'important');
} else {
  item.style.setProperty('display', 'none', 'important');
}
          }
        });
      });
    });
  });
</script>
