---
layout: page
permalink: /publications/
title: publications
description: Peer-reviewed journal articles, conference papers, and technical reports on safety-critical control systems.
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var pubEntries = document.querySelectorAll('.publications ol.bibliography > li, .publications .entry');

    pubEntries.forEach(function(entry) {
      var text = entry.textContent.toLowerCase();
      var badgeHTML = '';

      if (text.includes('journal') || text.includes('transactions') || text.includes('letters')) {
        badgeHTML = '<span class="pub-badge pub-badge-journal"><i class="fa-solid fa-file-lines"></i> Journal</span>';
      } else if (text.includes('conference') || text.includes('symposium') || text.includes('proceedings') || text.includes('toplantısı') || text.includes('congress')) {
        badgeHTML = '<span class="pub-badge pub-badge-conference"><i class="fa-solid fa-users"></i> Conference</span>';
      } else {
        badgeHTML = '<span class="pub-badge pub-badge-other"><i class="fa-solid fa-bookmark"></i> Publication</span>';
      }

      var titleElem = entry.querySelector('.title') || entry;
      if (titleElem && !entry.querySelector('.pub-badge')) {
        var badgeContainer = document.createElement('div');
        badgeContainer.className = 'pub-badge-wrapper';
        badgeContainer.innerHTML = badgeHTML;
        titleElem.parentNode.insertBefore(badgeContainer, titleElem);
      }
    });
  });
</script>
