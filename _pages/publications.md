---
layout: page
permalink: /publications/
title: publications
description: Peer-reviewed journal articles, conference papers, and technical reports on safety-critical control systems.
nav: true
nav_order: 3
---

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<!-- ÜST BLOK: Önce Arama Çubuğu, Altında Tam Genişlikte Grafik -->
<div class="pub-dashboard-stacked">
  <!-- 1. Arama Çubuğu (Üstte) -->
  <div class="pub-search-top">
    {% include bib_search.liquid %}
  </div>

  <!-- 2. Grafik Kutusu (Geniş / Altta) -->
  <div class="pub-chart-full">
    <div class="chart-wrapper-full">
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
      // 1. İtalik yayın adı alanını (em / i) veya genel metni al
      var emElem = entry.querySelector('em') || entry.querySelector('i');
      var venueText = emElem ? emElem.textContent.toLowerCase() : '';
      var fullText = entry.textContent.toLowerCase();

      // 2. Konferans Tespiti: Yalnızca yayın yeri kısmında (venue) aranır
      var isConf = venueText.startsWith('in ') || 
                   venueText.includes('conference') || 
                   venueText.includes('congress') || 
                   venueText.includes('symposium') || 
                   venueText.includes('proceedings') || 
                   venueText.includes('toplantı') ||
                   venueText.includes('toplantisi');

      // 3. Dergi Tespiti: Konferans değilse veya dergi ibaresi varsa
      var isJournal = !isConf;

      // 4. Yılı Yakala
      var yearMatch = fullText.match(/\b(20\d{2})\b/);
      var year = yearMatch ? yearMatch[0] : '2025';

      if (!yearlyData[year]) {
        yearlyData[year] = { journal: 0, conference: 0 };
      }

      var badgeHTML = '';

      if (isJournal) {
        yearlyData[year].journal++;
        badgeHTML = '<span class="pub-badge pub-badge-journal"><i class="fa-solid fa-file-lines"></i> Journal</span>';
      } else {
        yearlyData[year].conference++;
        badgeHTML = '<span class="pub-badge pub-badge-conference"><i class="fa-solid fa-users"></i> Conference</span>';
      }

      // Rozeti Güncelle / Ekle
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

    // 5. Grafik Çizimi
    var years = Object.keys(yearlyData).sort();
    var journalCounts = years.map(function(y) { return yearlyData[y].journal; });
    var confCounts = years.map(function(y) { return yearlyData[y].conference; });

    var canvas = document.getElementById('pubStackedChart');
    if (!canvas) return;
    var ctx = canvas.getContext('2d');

    if (window.myPubChart) {
      window.myPubChart.destroy();
    }

    var isDark = document.documentElement.getAttribute('data-theme') === 'dark';
    var journalColor = isDark ? '#2dd4bf' : '#0f766e';
    var confColor = isDark ? '#818cf8' : '#4338ca';
    var textColor = isDark ? '#94a3b8' : '#64748b';

    window.myPubChart = new Chart(ctx, {
      type: 'bar',
      data: {
        labels: years,
        datasets: [
          {
            label: 'Journal',
            data: journalCounts,
            backgroundColor: journalColor,
            borderRadius: 4,
            maxBarThickness: 36
          },
          {
            label: 'Conference',
            data: confCounts,
            backgroundColor: confColor,
            borderRadius: 4,
            maxBarThickness: 36
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
            ticks: { color: textColor, font: { size: 12, weight: '600' } }
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
              boxWidth: 10,
              boxHeight: 10,
              usePointStyle: true,
              color: textColor,
              font: { size: 11, weight: '600' }
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
