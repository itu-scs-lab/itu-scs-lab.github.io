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
  document.addEventListener("DOMContentLoaded", function() {
    var searchInput = document.getElementById('course-search-input');
    if (searchInput) {
      searchInput.addEventListener('input', function() {
        var query = this.value.toLowerCase().trim();
        
        // Ders kartlarını ve tablo/liste elemanlarını tarar
        var courseItems = document.querySelectorAll('.teaching-container .course-card, .courses-grid .course-card, table tr, .card');
        
        courseItems.forEach(function(item) {
          // Tablo başlık satırını gizlememek için kontrol
          if (item.tagName === 'TR' && item.querySelector('th')) return;

          var text = item.textContent.toLowerCase();
          if (text.includes(query)) {
            item.style.display = '';
          } else {
            item.style.display = 'none';
          }
        });

        // Arama sonucunda boş kalan Yıl bloklarını/başlıklarını gizler
        var yearBlocks = document.querySelectorAll('.year-block, .year-divider');
        yearBlocks.forEach(function(block) {
          var parent = block.closest('.year-block') || block.parentElement;
          if (parent) {
            var visibleCards = parent.querySelectorAll('.course-card:not([style*="display: none"]), tr:not([style*="display: none"])');
            if (visibleCards.length === 0) {
              block.style.display = 'none';
            } else {
              block.style.display = '';
            }
          }
        });
      });
    }
  });
</script>
