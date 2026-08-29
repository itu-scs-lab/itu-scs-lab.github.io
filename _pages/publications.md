---
layout: page
permalink: /publications/
title: publications
description: Peer-reviewed journal articles, conference papers, and technical reports on safety-critical control systems.
nav: true
nav_order: 2
---

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<div class="pub-top-dashboard">
  <div class="pub-search-side">
    {% include bib_search.liquid %}
  </div>

  <div class="pub-chart-side">
    <div class="chart-wrapper">
      <canvas id="pubStackedChart"></canvas>
    </div>
  </div>
</div>

<div class="publications">
{% bibliography %}
</div>

<script>
  function initPubChart() {
    var pubEntries = document.querySelectorAll('.publications ol.bibliography > li');
    if (!pubEntries.length) return;

    var yearlyData = {};

    pubEntries.forEach(function(entry) {
      // 1. Elemanın kendisindeki veya çocuk elemanlarındaki tüm sınıf ve öznitelikleri topla
      var fullClasses = entry.className + ' ' + (entry.querySelector('.entry') ? entry.querySelector('.entry').className : '');
      fullClasses = fullClasses.toLowerCase();

      // 2. Doğrudan BibTeX @article ve @inproceedings kontrolü
      var isJournal = fullClasses.includes('article');
      var isConf = fullClasses.includes('inproceedings') || fullClasses.includes('proceedings') || fullClasses.includes('conference');

      // 3. Yılı Yakala
      var yearMatch = entry.textContent.match(/\b(20\d{2})\b/);
      var year = yearMatch ? yearMatch[0] : 'Other';

      if (!yearlyData[year]) {
        yearlyData[year] = { journal: 0, conference: 0, other: 0 };
      }

      var badgeHTML = '';

      if (isJournal) {
        yearlyData[year].journal++;
        badgeHTML = '<span class="pub-badge pub-badge-journal"><i class="fa-solid fa-file-lines"></i> Journal</span>';
      } else if (isConf) {
        yearlyData[year].conference++;
        badgeHTML = '<span class="pub-badge pub-badge-conference"><i class="fa-solid fa-users"></i> Conference</span>';
      } else {
        yearlyData[year].other++;
        badgeHTML = '<span class="pub-badge pub-badge-other"><i class="fa-solid fa-bookmark"></i> Pub</span>';
      }

      // Sol Rozeti Yerleştir
      var existingWrapper = entry.querySelector('.pub-badge-wrapper');
      if (existingWrapper) {
        existingWrapper.innerHTML = badgeHTML;
      } else {
        var badgeContainer = document.createElement('div');
        badgeContainer.className = 'pub-badge-wrapper';
        badgeContainer.innerHTML = badgeHTML;
        entry.insertBefore(badgeContainer, entry.firstChild);
      }
    });

    // Grafik Çizimi
    var years = Object.keys(yearlyData).sort();
    var journalCounts = years.map(function(y) { return yearlyData[y].journal; });
    var confCounts = years.map(function(y) { return yearlyData[y].conference; });

    var canvas = document.getElementById('pubStackedChart');
    if (!canvas) return;
    var ctx = canvas.getContext('2d');
    
    var isDark = document.documentElement.getAttribute('data-theme') === 'dark';
    var journalColor = isDark ? '#2dd4bf' : '#0f766e';
    var confColor = isDark ? '#818cf8' : '#4338ca';
    var textColor = isDark ? '#94a3b8' : '#64748b';

    new Chart(ctx, {
      type: 'bar',
      data: {
        labels: years,
        datasets: [
          {
            label: 'Journal',
            data: journalCounts,
            backgroundColor: journalColor,
            borderRadius: 3,
            maxBarThickness: 24
          },
          {
            label: 'Conference',
            data: confCounts,
            backgroundColor: confColor,
            borderRadius: 3,
            maxBarThickness: 24
          }
        ]
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          x: {
            stacked: true,
            grid: { display: false },
            ticks: { color: textColor, font: { size: 11, weight: '600' } }
          },
          y: {
            stacked: true,
            display: false,
            beginAtZero: true
          }
        },
        plugins: {
          legend: {
            display: true,
            position: 'top',
            align: 'end',
            labels: {
              boxWidth: 8,
              boxHeight: 8,
              usePointStyle: true,
              color: textColor,
              font: { size: 10, weight: '600' }
            }
          }
        }
      }
    });
  }

  if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', initPubChart);
  } else {
    initPubChart();
  }
</script>
