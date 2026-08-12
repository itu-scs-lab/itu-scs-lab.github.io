---
layout: page
permalink: /publications/
title: publications
description: Peer-reviewed journal articles, conference papers, and technical reports on safety-critical control systems.
nav: true
nav_order: 2
---
<style>
  /* Publications yıl başlıklarını hem gündüz hem gece modunda netleştirme */
  .publications h2.bibliography,
  .publications h2.year,
  h2.year {
    color: var(--global-text-color) !important;
    opacity: 1 !important;
    font-weight: 600 !important;
  }
</style>
<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>
