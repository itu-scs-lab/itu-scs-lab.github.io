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
        
        // al-folio'nun varsayılan ders elemanları (Tablo satırları, kartlar, listeler)
        var items = document.querySelectorAll('.table tr, .courses-list > *, .course-card, .teaching-container .row > div');
        
        items.forEach(function(item) {
          // Tablo başlık satırını (th) filtre dışı bırak
          if (item.querySelector('th')) return;

          var text = item.textContent.toLowerCase();
          if (text.includes(query)) {
            item.style.display = '';
          } else {
            item.style.display = 'none';
          }
        });

        // Arama sonucunda boş kalan Yıl başlıklarını (h2 / .year-divider / .table-title) gizle
        var yearHeaders = document.querySelectorAll('h2, .year-title, .year-divider');
        yearHeaders.forEach(function(header) {
          // Başlıktan sonra gelen kapsayıcı alanı kontrol et
          var nextElem = header.nextElementSibling;
          if (nextElem) {
            var visibleItems = nextElem.querySelectorAll('tr:not([style*="display: none"]), .course-card:not([style*="display: none"]), div:not([style*="display: none"])');
            if (visibleItems.length === 0 && query !== '') {
              header.style.display = 'none';
            } else {
              header.style.display = '';
            }
          }
        });
      });
    }
  });
</script>
