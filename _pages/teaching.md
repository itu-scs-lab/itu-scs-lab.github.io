---
layout: page
permalink: /teaching/
title: teaching
description: Undergraduate and graduate courses offered at ITU SCS Lab.
nav: true
nav_order: 6
calendar: false
---

<input type="text" id="course-search-input" class="form-control my-3 filter-search-input" placeholder="Type to filter..." style="max-width: 320px; border-radius: 6px;">

{% include courses.liquid %}

<script>
  document.addEventListener('DOMContentLoaded', function() {
    var input = document.getElementById('course-search-input');
    if (input) {
      input.addEventListener('keyup', function() {
        var filter = this.value.toLowerCase().trim();
        // al-folio'nun ders başlıklarını ve paragraflarını yakalar
        var courses = document.querySelectorAll('.courses-list li, table tr, article, .card');

        courses.forEach(function(item) {
          if (item.querySelector('th')) return;
          var text = item.textContent || item.innerText;
          if (text.toLowerCase().indexOf(filter) > -1) {
            item.style.display = '';
          } else {
            item.style.display = 'none';
          }
        });
      });
    }
  });
</script>
