---
layout: page
permalink: /teaching/
title: teaching
description: Undergraduate and graduate courses offered at ITU SCS Lab.
nav: true
nav_order: 6
calendar: false
---

<input 
  type="text" 
  id="course-search-input" 
  class="form-control my-3 filter-search-input" 
  placeholder="Type to filter..." 
  style="max-width: 320px; border-radius: 6px;"
  onkeyup="filterTeachingCourses()"
>

{% include courses.liquid %}

<script>
function filterTeachingCourses() {
  var input = document.getElementById('course-search-input');
  var filter = input.value.toLowerCase().trim();
  
  // Tablo satırlarını, kartları ve listeleri hedefle
  var rows = document.querySelectorAll('table tr, .course-card, .courses-list li');

  for (var i = 0; i < rows.length; i++) {
    var row = rows[i];
    
    // Tablo başlıklarını (TH) atla
    if (row.querySelector('th')) continue;

    var text = row.textContent || row.innerText;
    if (text.toLowerCase().indexOf(filter) > -1) {
      row.style.display = "";
    } else {
      row.style.display = "none";
    }
  }
}
</script>
