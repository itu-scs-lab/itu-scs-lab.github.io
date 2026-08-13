---
layout: page
permalink: /publications/
title: publications
description: Peer-reviewed journal articles, conference papers, and technical reports on safety-critical control systems.
nav: true
nav_order: 2
---

<!-- Chart.js Kütüphanesi -->
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<div class="pub-header-container">
  <!-- Sol Taraf: Arama Kutusu -->
  <div class="pub-header-left">
    {% include bib_search.liquid %}
  </div>

  <!-- Sağ Taraf: Yıllara ve Türlere Göre Stacked Bar Chart -->
  <div class="pub-header-right">
    <div class="pub-stats-card">
      <div class="chart-wrapper">
        <canvas id="pubStackedChart"></canvas>
      </div>
    </div>
  </div>
</div>

<div class="publications">
{% bibliography %}
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var pubEntries = document.querySelectorAll('.publications ol.bibliography > li, .publications .entry');
    
    // Yıl ve Tür Verilerini Toplama
    var yearlyData = {}; // { "2023": { journal: 1, conference: 2 }, ... }

    pubEntries.forEach(function(entry) {
      var text = entry.textContent.toLowerCase();
      
      // Yıl Tespit Etme (Dört haneli sayı yakalama)
      var yearMatch = entry.textContent.match(/\b(20\d{2})\b/);
      var year = yearMatch ? yearMatch[0] : 'Other';

      if (!yearlyData[year]) {
        yearlyData[year] = { journal: 0, conference: 0, other: 0 };
      }

      var badgeHTML = '';

      if (text.includes('journal') || text.includes('transactions') || text.includes('letters')) {
        yearlyData[year].journal++;
        badgeHTML = '<span class="pub-badge pub-badge-journal"><i class="fa-solid fa-file-lines"></i> Journal</span>';
      } else if (text.includes('conference') || text.includes('symposium') || text.includes('proceedings') || text.includes('toplantısı') || text.includes('congress')) {
        yearlyData[year].conference++;
        badgeHTML = '<span class="pub-badge pub-badge-conference"><i class="fa-solid fa-users"></i> Conference</span>';
      } else {
        yearlyData[year].other++;
        badgeHTML = '<span class="pub-badge pub-badge-other"><i class="fa-solid fa-bookmark"></i> Pub</span>';
      }

      // Sol Dikey Rozeti Ekleme
      if (!entry.querySelector('.pub-badge')) {
        var badgeContainer = document.createElement('div');
        badgeContainer.className = 'pub-badge-wrapper';
        badgeContainer.innerHTML = badgeHTML;
        entry.insertBefore(badgeContainer, entry.firstChild);
      }
    });

    // Yılları Sıralama
    var years = Object.keys(yearlyData).sort();
    var journalCounts = years.map(function(y) { return yearlyData[y].journal; });
    var confCounts = years.map(function(y) { return yearlyData[y].conference; });

    // Chart.js Stacked Bar Chart Hazırlığı
    var ctx = document.getElementById('pubStackedChart').getContext('2d');
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
            borderRadius: 4,
            barThickness: 16
          },
          {
            label: 'Conference',
            data: confCounts,
            backgroundColor: confColor,
            borderRadius: 4,
            barThickness: 16
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
            ticks: { color: textColor, font: { size: 10, weight: '600' } }
          },
          y: {
            stacked: true,
            display: false, /* Temiz görünüm için Y ekseni çizgilerini sakla */
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
          },
          tooltip: {
            mode: 'index',
            intersect: false
          }
        }
      }
    });
  });
</script>
