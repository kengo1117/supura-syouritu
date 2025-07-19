<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>スプラトゥーン3 勝率チェッカー</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body {
      font-family: sans-serif;
      max-width: 600px;
      margin: 2rem auto;
      padding: 1rem;
      background: linear-gradient(to bottom right, #c1f1ff, #fcd3ff);
    }
    input, select, button {
      margin: 0.5rem 0;
      padding: 0.5rem;
      width: 100%;
      font-size: 1rem;
    }
    .chart-container {
      margin-top: 2rem;
      background: white;
      padding: 1rem;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }
    canvas {
      max-width: 100%;
    }
    .ranking {
      margin-top: 2rem;
      background: #fff3c4;
      padding: 1rem;
      border-radius: 8px;
    }
    .ranking h3 {
      margin-top: 0;
      color: #2563eb;
    }
    .ranking ol {
      padding-left: 1.2rem;
    }
  </style>
</head>
<body>
  <h1 style="color:#2563eb; font-size: 1.5rem; text-align:center;">スプラトゥーン3 勝率チェッカー</h1>

  <div>
    <input id="weaponName" placeholder="武器名" />
    <select id="weaponType">
      <option>シューター</option>
      <option>ローラー</option>
      <option>チャージャー</option>
      <option>マニューバー</option>
      <option>ブラスター</option>
    </select>
    <select id="battleRule">
      <option>レギュラーマッチ</option>
      <option>ガチエリア</option>
      <option>ガチヤグラ</option>
      <option>ガチホコ</option>
      <option>ガチアサリ</option>
    </select>
    <input id="wins" type="number" placeholder="勝ち数" />
    <input id="losses" type="number" placeholder="負け数" />
    <button onclick="addData()" style="background:#2563eb;color:white;">追加</button>
    <button onclick="clearData()" style="background:#ef4444;color:white;margin-top:0.5rem;">データをリセット</button>
  </div>

  <div id="charts"></div>
  <div id="ranking" class="ranking"></div>

  <script>
    let data = {};

    window.onload = function() {
      const saved = localStorage.getItem("winrateData");
      if (saved) {
        data = JSON.parse(saved);
        renderCharts();
        renderRanking();
      }
    };

    function saveData() {
      localStorage.setItem("winrateData", JSON.stringify(data));
    }

    function clearData() {
      if (confirm("すべてのデータを削除しますか？")) {
        data = {};
        localStorage.removeItem("winrateData");
        renderCharts();
        renderRanking();
      }
    }

    function addData() {
      const name = document.getElementById("weaponName").value.trim();
      const wins = parseInt(document.getElementById("wins").value);
      const losses = parseInt(document.getElementById("losses").value);
      const type = document.getElementById("weaponType").value;
      const rule = document.getElementById("battleRule").value;
      if (!name || isNaN(wins) || isNaN(losses)) return;

      if (!data[rule]) data[rule] = {};
      if (!data[rule][type]) data[rule][type] = [];
      data[rule][type].push({ name, wins, losses });

      document.getElementById("weaponName").value = "";
      document.getElementById("wins").value = "";
      document.getElementById("losses").value = "";

      saveData();
      renderCharts();
      renderRanking();
    }

    function renderCharts() {
      const container = document.getElementById("charts");
      container.innerHTML = "";

      Object.entries(data).forEach(([rule, types]) => {
        const ruleTitle = document.createElement("h2");
        ruleTitle.textContent = rule;
        ruleTitle.style.color = "#16a34a";
        container.appendChild(ruleTitle);

        Object.entries(types).forEach(([type, entries]) => {
          const div = document.createElement("div");
          div.className = "chart-container";
          const title = document.createElement("h3");
          title.textContent = type;
          title.style.color = "#2563eb";
          div.appendChild(title);

          const canvas = document.createElement("canvas");
          div.appendChild(canvas);

          const labels = entries.map(e => e.name);
          const winRates = entries.map(e => Math.round((e.wins / (e.wins + e.losses)) * 100));

          new Chart(canvas, {
            type: "bar",
            data: {
              labels: labels,
              datasets: [{
                label: "勝率",
                data: winRates,
                backgroundColor: "#60a5fa"
              }]
            },
            options: {
              responsive: true,
              animation: false,
              plugins: {
                legend: { display: false },
                title: { display: false }
              },
              scales: {
                y: {
                  beginAtZero: true,
                  max: 100,
                  ticks: {
                    callback: value => value + "%",
                    stepSize: 20
                  }
                }
              }
            }
          });

          container.appendChild(div);
        });
      });
    }

    function renderRanking() {
      const rankingContainer = document.getElementById("ranking");
      rankingContainer.innerHTML = "<h3>ルール別 勝率ランキング</h3>";

      Object.entries(data).forEach(([rule, ruleData]) => {
        let allWeapons = [];
        Object.values(ruleData).forEach(typeEntries => {
          typeEntries.forEach(e => {
            const total = e.wins + e.losses;
            if (total > 0) {
              const rate = Math.round((e.wins / total) * 100);
              allWeapons.push({ name: e.name, rate });
            }
          });
        });

        allWeapons.sort((a, b) => b.rate - a.rate);

        if (allWeapons.length > 0) {
          const section = document.createElement("div");
          section.innerHTML = `<h4 style="margin-bottom: 0.5rem; color:#16a34a;">${rule}</h4><ol>` +
            allWeapons.map(w => `<li>${w.name}：${w.rate}%</li>`).join("") +
            `</ol>`;
          rankingContainer.appendChild(section);
        }
      });
    }
  </script>
</body>
</html>
