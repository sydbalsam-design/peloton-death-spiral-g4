<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Peloton Death Spiral — Interactive | UNC Kenan-Flagler</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>
<style>
  :root {
    --unc-blue: #4B9CD3;
    --unc-dark: #13294B;
    --red: #C0392B;
    --orange: #E67E22;
    --green: #27AE60;
    --yellow: #F1C40F;
    --gray-bg: #f0f2f6;
    --card: #ffffff;
    --border: #e0e4ea;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: 'Segoe UI', Arial, sans-serif; background: var(--gray-bg); color: #222; }

  /* ── HEADER ── */
  header {
    background: var(--unc-dark);
    color: white;
    padding: 16px 28px;
    display: flex;
    align-items: center;
    gap: 16px;
  }
  header .logo { font-size: 1.4rem; font-weight: 900; color: var(--unc-blue); letter-spacing: 1px; }
  header h1 { font-size: 1.05rem; font-weight: 700; }
  header p { font-size: 0.73rem; opacity: 0.7; margin-top: 2px; }

  .container { max-width: 1280px; margin: 0 auto; padding: 20px 16px; }

  /* ── SECTION LABELS ── */
  .section-label {
    font-size: 0.7rem;
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--unc-blue);
    margin-bottom: 8px;
    margin-top: 4px;
  }

  /* ── KPI ROW ── */
  .kpi-row {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 12px;
    margin-bottom: 20px;
  }
  .kpi {
    background: var(--card);
    border-radius: 10px;
    padding: 14px 16px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    border-left: 5px solid var(--unc-blue);
    transition: border-color 0.3s;
  }
  .kpi.red   { border-left-color: var(--red); }
  .kpi.orange{ border-left-color: var(--orange); }
  .kpi.green { border-left-color: var(--green); }
  .kpi.yellow{ border-left-color: var(--yellow); }
  .kpi label { font-size: 0.68rem; text-transform: uppercase; letter-spacing: 0.4px; color: #777; }
  .kpi .val  { font-size: 1.45rem; font-weight: 800; margin: 4px 0 2px; transition: color 0.3s; }
  .kpi .sub  { font-size: 0.7rem; color: #999; }

  /* ── SPIRAL METER ── */
  .spiral-meter-wrap {
    background: var(--card);
    border-radius: 10px;
    padding: 16px 20px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 20px;
  }
  .spiral-meter-wrap h3 { font-size: 0.88rem; font-weight: 700; color: var(--unc-dark); min-width: 160px; }
  .meter-bar-bg {
    flex: 1;
    height: 22px;
    background: linear-gradient(to right, #27AE60, #F1C40F, #E67E22, #C0392B);
    border-radius: 11px;
    position: relative;
    overflow: visible;
  }
  .meter-needle {
    position: absolute;
    top: -6px;
    width: 4px;
    height: 34px;
    background: var(--unc-dark);
    border-radius: 2px;
    transform: translateX(-50%);
    transition: left 0.5s cubic-bezier(.4,0,.2,1);
    box-shadow: 0 2px 6px rgba(0,0,0,0.3);
  }
  .meter-labels {
    display: flex;
    justify-content: space-between;
    font-size: 0.65rem;
    color: #888;
    margin-top: 4px;
  }
  .spiral-score-box {
    text-align: center;
    min-width: 80px;
  }
  .spiral-score-box .score { font-size: 2rem; font-weight: 900; transition: color 0.3s; }
  .spiral-score-box .score-label { font-size: 0.65rem; color: #888; text-transform: uppercase; }

  /* ── LAYOUT: SLIDERS + CHARTS ── */
  .main-grid {
    display: grid;
    grid-template-columns: 320px 1fr;
    gap: 18px;
    margin-bottom: 20px;
  }

  /* ── SLIDER PANEL ── */
  .slider-panel {
    background: var(--card);
    border-radius: 10px;
    padding: 18px 20px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    display: flex;
    flex-direction: column;
    gap: 0;
  }
  .slider-panel h3 {
    font-size: 0.88rem;
    font-weight: 700;
    color: var(--unc-dark);
    margin-bottom: 4px;
  }
  .slider-panel .panel-desc {
    font-size: 0.72rem;
    color: #888;
    margin-bottom: 14px;
    line-height: 1.5;
  }
  .year-block {
    border-radius: 8px;
    padding: 10px 12px;
    margin-bottom: 8px;
    border: 1.5px solid var(--border);
    transition: border-color 0.3s, background 0.3s;
  }
  .year-block.active { border-color: var(--unc-blue); background: #f0f7ff; }
  .year-block .year-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 6px;
  }
  .year-block .year-label { font-size: 0.82rem; font-weight: 700; color: var(--unc-dark); }
  .year-block .year-vals  { font-size: 0.7rem; color: #666; text-align: right; }
  .year-block .year-vals span { font-weight: 700; color: var(--unc-dark); }
  .year-block input[type=range] {
    width: 100%;
    accent-color: var(--unc-blue);
    cursor: pointer;
    height: 6px;
  }
  .year-block .range-labels {
    display: flex;
    justify-content: space-between;
    font-size: 0.6rem;
    color: #bbb;
    margin-top: 2px;
  }
  .reset-btn {
    margin-top: 10px;
    width: 100%;
    padding: 9px;
    background: var(--unc-dark);
    color: white;
    border: none;
    border-radius: 7px;
    font-size: 0.8rem;
    font-weight: 700;
    cursor: pointer;
    letter-spacing: 0.5px;
    transition: background 0.2s;
  }
  .reset-btn:hover { background: var(--unc-blue); }

  /* ── CHARTS PANEL ── */
  .charts-panel { display: flex; flex-direction: column; gap: 14px; }
  .chart-row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .chart-card {
    background: var(--card);
    border-radius: 10px;
    padding: 16px 18px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
  }
  .chart-card.full { grid-column: 1 / -1; }
  .chart-card h3 { font-size: 0.82rem; font-weight: 700; color: var(--unc-dark); margin-bottom: 2px; }
  .chart-card .desc { font-size: 0.68rem; color: #999; margin-bottom: 10px; }
  .chart-wrap { position: relative; height: 190px; }
  .chart-wrap.tall { height: 210px; }

  /* ── MECHANICS TABLE ── */
  .table-card {
    background: var(--card);
    border-radius: 10px;
    padding: 18px 22px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    margin-bottom: 20px;
    overflow-x: auto;
  }
  .table-card h3 {
    font-size: 0.9rem;
    font-weight: 700;
    color: var(--unc-dark);
    margin-bottom: 12px;
    border-bottom: 2px solid var(--unc-blue);
    padding-bottom: 6px;
  }
  table.data-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.78rem;
  }
  .data-table th {
    background: var(--unc-dark);
    color: white;
    padding: 7px 10px;
    text-align: right;
    font-weight: 600;
  }
  .data-table th:first-child { text-align: left; }
  .data-table td {
    padding: 7px 10px;
    border-bottom: 1px solid #eee;
    text-align: right;
    transition: background 0.3s;
  }
  .data-table td:first-child { text-align: left; font-weight: 600; }
  .data-table tr:nth-child(even) td { background: #f8f9fa; }
  .data-table .highlight td { background: #fff3cd !important; font-weight: 700; }
  .data-table .danger td { background: #fde8e8 !important; }
  .data-table .modified td { background: #e8f4fd !important; }

  /* ── CALLOUT BOX ── */
  .callout {
    background: #fff3cd;
    border: 1.5px solid #ffc107;
    border-radius: 10px;
    padding: 12px 18px;
    font-size: 0.82rem;
    line-height: 1.6;
    margin-bottom: 20px;
  }
  .callout strong { color: var(--unc-dark); }

  footer {
    text-align: center;
    font-size: 0.68rem;
    color: #bbb;
    padding: 14px;
    border-top: 1px solid var(--border);
  }

  @media (max-width: 900px) {
    .main-grid { grid-template-columns: 1fr; }
    .kpi-row { grid-template-columns: repeat(2, 1fr); }
    .chart-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<header>
  <div class="logo">🔱 UNC</div>
  <div>
    <h1>Peloton Interactive — Interactive Death Spiral Simulator</h1>
    <p>Drag the subscriber sliders to see how volume changes ripple through fixed costs, margins, and operating losses · Kenan-Flagler Business School</p>
  </div>
</header>

<div class="container">

  <!-- CALLOUT -->
  <div class="callout">
    <strong>📐 How this works (per your course slides):</strong> Peloton's fixed costs (SG&A + R&D) are largely <em>sticky</em> — they don't scale down proportionally with subscribers. When you reduce subscribers below actual levels, fixed costs get spread over fewer users → cost/subscriber rises → margins compress → losses deepen. That's the death spiral. Try dragging FY2022 or FY2023 subscribers <em>up</em> to see what could have broken the cycle.
  </div>

  <!-- KPI ROW -->
  <div class="section-label">📊 Live Scenario Metrics</div>
  <div class="kpi-row">
    <div class="kpi green">
      <label>Total Subscribers (Scenario)</label>
      <div class="val" id="kpi-total-subs">—</div>
      <div class="sub">Sum across all years</div>
    </div>
    <div class="kpi red" id="kpi-fc-card">
      <label>Avg Fixed Cost / Subscriber</label>
      <div class="val" id="kpi-avg-fc">—</div>
      <div class="sub" id="kpi-avg-fc-sub">vs. actual baseline</div>
    </div>
    <div class="kpi orange">
      <label>Total Operating Loss</label>
      <div class="val" id="kpi-op-loss">—</div>
      <div class="sub">FY2020–FY2025 scenario</div>
    </div>
    <div class="kpi" id="kpi-margin-card">
      <label>Worst-Year Gross Margin</label>
      <div class="val" id="kpi-margin">—</div>
      <div class="sub" id="kpi-margin-sub">Lowest margin year</div>
    </div>
    <div class="kpi yellow">
      <label>Spiral Severity Score</label>
      <div class="val" id="kpi-spiral">—</div>
      <div class="sub">0 = healthy · 100 = critical</div>
    </div>
  </div>

  <!-- SPIRAL METER -->
  <div class="spiral-meter-wrap">
    <h3>🌀 Death Spiral<br/>Severity Meter</h3>
    <div style="flex:1">
      <div class="meter-bar-bg">
        <div class="meter-needle" id="spiral-needle" style="left:0%"></div>
      </div>
      <div class="meter-labels">
        <span>Healthy</span><span>Caution</span><span>Danger</span><span>Critical</span>
      </div>
    </div>
    <div class="spiral-score-box">
      <div class="score" id="spiral-score-big">0</div>
      <div class="score-label">/ 100</div>
    </div>
  </div>

  <!-- MAIN GRID: SLIDERS + CHARTS -->
  <div class="main-grid">

    <!-- SLIDER PANEL -->
    <div class="slider-panel">
      <h3>🎛️ Subscriber Scenario Builder</h3>
      <p class="panel-desc">Drag each year's slider to set a hypothetical subscriber count. All metrics update instantly. <strong>Actual values are pre-loaded.</strong></p>

      <div id="slider-container"></div>

      <button class="reset-btn" onclick="resetToActual()">↺ Reset to Actual Data</button>
    </div>

    <!-- CHARTS PANEL -->
    <div class="charts-panel">
      <div class="chart-row">
        <div class="chart-card">
          <h3>📉 Subscribers vs. Actual</h3>
          <p class="desc">Blue = scenario · Gray dashed = actual baseline</p>
          <div class="chart-wrap"><canvas id="subChart"></canvas></div>
        </div>
        <div class="chart-card">
          <h3>💸 Fixed Cost per Subscriber</h3>
          <p class="desc">Rises as subscriber volume falls — the spiral engine</p>
          <div class="chart-wrap"><canvas id="fcChart"></canvas></div>
        </div>
      </div>
      <div class="chart-row">
        <div class="chart-card">
          <h3>📊 Operating Loss (Scenario)</h3>
          <p class="desc">Loss deepens when fixed costs can't be absorbed</p>
          <div class="chart-wrap"><canvas id="lossChart"></canvas></div>
        </div>
        <div class="chart-card">
          <h3>📈 Gross Margin %</h3>
          <p class="desc">Margin collapses as cost/sub rises relative to ARPU</p>
          <div class="chart-wrap"><canvas id="marginChart"></canvas></div>
        </div>
      </div>
      <div class="chart-row">
        <div class="chart-card full">
          <h3>🌀 Death Spiral Path — Cost/Sub vs. Subscribers</h3>
          <p class="desc">Each dot = one fiscal year. Spiral moves right→left (fewer subs) and down→up (higher cost). Arrows show direction of spiral.</p>
          <div class="chart-wrap tall"><canvas id="spiralChart"></canvas></div>
        </div>
      </div>
    </div>
  </div>

  <!-- DATA TABLE -->
  <div class="table-card">
    <h3>📋 Year-by-Year Scenario vs. Actual Breakdown</h3>
    <table class="data-table" id="data-table">
      <thead>
        <tr>
          <th>Fiscal Year</th>
          <th>Subscribers (M)</th>
          <th>Actual Subs (M)</th>
          <th>Fixed Costs ($M)</th>
          <th>FC / Subscriber ($)</th>
          <th>Revenue ($M)</th>
          <th>Op. Loss ($M)</th>
          <th>Gross Margin %</th>
          <th>Spiral Status</th>
        </tr>
      </thead>
      <tbody id="table-body"></tbody>
    </table>
  </div>

</div>

<footer>
  Data sourced from Peloton 10-K filings (FY2020–FY2025) [doc3][doc4] · Fixed costs = SG&A + R&D (sticky overhead) · UNC Kenan-Flagler Business School · Death Spiral framework per course materials
</footer>

<script>
// ─────────────────────────────────────────────
// REAL PELOTON DATA (from 10-K filings)
// FY = fiscal year ending June 30
// ─────────────────────────────────────────────
const YEARS = ['FY2020','FY2021','FY2022','FY2023','FY2024','FY2025'];

// Connected fitness subscribers (millions) — end of fiscal year
const ACTUAL_SUBS = [1.09, 2.33, 2.97, 3.08, 2.98, 2.66];

// Revenue ($M) — actual reported
const REVENUE = [1826, 4022, 3582, 2799, 2700, 2491];

// Gross Profit ($M) — actual reported
const GROSS_PROFIT = [748, 1462, 614, 826, 869, 892];

// Fixed Costs ($M) = SG&A + R&D (the "sticky" overhead)
// FY2020: ~$455+$89=544  FY2021: ~$839+$248=1087  FY2022: ~$1200+$360=1560
// FY2023: ~$900+$318=1218  FY2024: ~$700+$305=1005  FY2025: ~$580+$234=814
const FIXED_COSTS = [544, 1087, 1560, 1218, 1005, 814];

// Operating Loss ($M) — actual reported (negative = loss)
const OP_LOSS_ACTUAL = [-541, -283, -2828, -1261, -593, -116];

// Subscription ARPU per year (monthly sub revenue / avg subs * 12) — approx
const ARPU = [420, 468, 480, 492, 504, 516]; // annual $ per subscriber

// Slider min/max (millions)
const SLIDER_MIN = 0.5;
const SLIDER_MAX = 5.0;
const SLIDER_STEP = 0.05;

// ─────────────────────────────────────────────
// STATE
// ─────────────────────────────────────────────
let scenarioSubs = [...ACTUAL_SUBS];

// ─────────────────────────────────────────────
// CALCULATIONS
// ─────────────────────────────────────────────
function calcMetrics(subs) {
  return subs.map((s, i) => {
    const fc = FIXED_COSTS[i];
    const fcPerSub = (fc * 1e6) / (s * 1e6); // $ per subscriber
    const rev = REVENUE[i];
    const gp = GROSS_PROFIT[i];
    // Adjust gross profit proportionally if subs changed
    const subRatio = s / ACTUAL_SUBS[i];
    // Revenue scales with subs (subscription revenue ~60% of total, hardware ~40%)
    const adjRev = rev * (0.4 + 0.6 * subRatio);
    // Gross profit: subscription GP scales with subs, hardware GP stays
    const subGP = gp * 0.65 * subRatio;
    const hwGP  = gp * 0.35;
    const adjGP = subGP + hwGP;
    const grossMargin = (adjGP / adjRev) * 100;
    // Operating loss = gross profit - fixed costs (fixed costs don't scale much)
    // Fixed costs reduce slightly with subs (some variable component ~15%)
    const adjFC = fc * (0.85 + 0.15 * subRatio);
    const opLoss = adjGP - adjFC - (adjRev - adjGP) * 0; // already in GP
    // Simpler: op income = adjGP - adjFC
    const opIncome = adjGP - adjFC;
    return {
      subs: s,
      fc: adjFC,
      fcPerSub: (adjFC * 1e6) / (s * 1e6),
      rev: adjRev,
      gp: adjGP,
      grossMargin: grossMargin,
      opIncome: opIncome, // negative = loss
    };
  });
}

function spiralScore(metrics) {
  // Score 0-100 based on:
  // - avg FC/sub relative to ARPU (higher = worse)
  // - worst gross margin
  // - total op loss
  const avgFCperSub = metrics.reduce((a,m)=>a+m.fcPerSub,0)/metrics.length;
  const avgARPU = ARPU.reduce((a,b)=>a+b,0)/ARPU.length;
  const fcRatio = Math.min(avgFCperSub / avgARPU, 2); // 0-2 range
  const worstMargin = Math.min(...metrics.map(m=>m.grossMargin));
  const marginScore = Math.max(0, (40 - worstMargin) / 40); // 0-1
  const totalLoss = metrics.reduce((a,m)=>a + Math.min(0, m.opIncome),0);
  const lossScore = Math.min(Math.abs(totalLoss) / 6000, 1); // 0-1
  const raw = (fcRatio * 0.4 + marginScore * 0.3 + lossScore * 0.3) * 100;
  return Math.min(100, Math.max(0, Math.round(raw)));
}

// ─────────────────────────────────────────────
// BUILD SLIDERS
// ─────────────────────────────────────────────
function buildSliders() {
  const container = document.getElementById('slider-container');
  container.innerHTML = '';
  YEARS.forEach((yr, i) => {
    const block = document.createElement('div');
    block.className = 'year-block';
    block.id = `block-${i}`;
    block.innerHTML = `
      <div class="year-header">
        <span class="year-label">${yr}</span>
        <span class="year-vals">
          <span id="sval-${i}">${scenarioSubs[i].toFixed(2)}M</span>
          <span style="color:#bbb;font-weight:400"> / actual ${ACTUAL_SUBS[i].toFixed(2)}M</span>
        </span>
      </div>
      <input type="range" id="slider-${i}"
        min="${SLIDER_MIN}" max="${SLIDER_MAX}" step="${SLIDER_STEP}"
        value="${scenarioSubs[i]}"
        oninput="onSlider(${i}, this.value)"
      />
      <div class="range-labels"><span>${SLIDER_MIN}M</span><span>${SLIDER_MAX}M</span></div>
    `;
    container.appendChild(block);
  });
}

function onSlider(i, val) {
  scenarioSubs[i] = parseFloat(val);
  document.getElementById(`sval-${i}`).textContent = parseFloat(val).toFixed(2) + 'M';
  // Highlight if changed from actual
  const block = document.getElementById(`block-${i}`);
  block.classList.toggle('active', Math.abs(scenarioSubs[i] - ACTUAL_SUBS[i]) > 0.01);
  updateAll();
}

function resetToActual() {
  scenarioSubs = [...ACTUAL_SUBS];
  YEARS.forEach((_, i) => {
    document.getElementById(`slider-${i}`).value = ACTUAL_SUBS[i];
    document.getElementById(`sval-${i}`).textContent = ACTUAL_SUBS[i].toFixed(2) + 'M';
    document.getElementById(`block-${i}`).classList.remove('active');
  });
  updateAll();
}

// ─────────────────────────────────────────────
// CHARTS
// ─────────────────────────────────────────────
let charts = {};

function initCharts() {
  const m = calcMetrics(scenarioSubs);

  // Subscriber chart
  charts.sub = new Chart(document.getElementById('subChart'), {
    type: 'bar',
    data: {
      labels: YEARS,
      datasets: [
        {
          label: 'Scenario Subs (M)',
          data: scenarioSubs.map(s => +s.toFixed(3)),
          backgroundColor: scenarioSubs.map((s,i) => subColor(s,i)),
          borderRadius: 4,
          order: 1,
        },
        {
          label: 'Actual Subs (M)',
          data: ACTUAL_SUBS,
          type: 'line',
          borderColor: '#aaa',
          borderDash: [5,4],
          borderWidth: 2,
          pointRadius: 3,
          pointBackgroundColor: '#aaa',
          fill: false,
          tension: 0.3,
          order: 0,
        }
      ]
    },
    options: chartOpts('Subscribers (M)', false)
  });

  // FC per sub chart
  charts.fc = new Chart(document.getElementById('fcChart'), {
    type: 'line',
    data: {
      labels: YEARS,
      datasets: [
        {
          label: 'Scenario FC/Sub ($)',
          data: m.map(x => Math.round(x.fcPerSub)),
          borderColor: '#C0392B',
          backgroundColor: 'rgba(192,57,43,0.1)',
          fill: true,
          tension: 0.3,
          borderWidth: 2.5,
          pointRadius: 5,
          pointBackgroundColor: '#C0392B',
        },
        {
          label: 'Actual FC/Sub ($)',
          data: ACTUAL_SUBS.map((s,i) => Math.round((FIXED_COSTS[i]*1e6)/(s*1e6))),
          borderColor: '#aaa',
          borderDash: [5,4],
          borderWidth: 1.5,
          pointRadius: 3,
          fill: false,
          tension: 0.3,
        }
      ]
    },
    options: chartOpts('Fixed Cost per Subscriber ($)', false)
  });

  // Op Loss chart
  charts.loss = new Chart(document.getElementById('lossChart'), {
    type: 'bar',
    data: {
      labels: YEARS,
      datasets: [
        {
          label: 'Scenario Op. Income ($M)',
          data: m.map(x => Math.round(x.opIncome)),
          backgroundColor: m.map(x => x.opIncome < 0 ? 'rgba(192,57,43,0.75)' : 'rgba(39,174,96,0.75)'),
          borderRadius: 4,
        },
        {
          label: 'Actual Op. Income ($M)',
          data: OP_LOSS_ACTUAL,
          type: 'line',
          borderColor: '#aaa',
          borderDash: [5,4],
          borderWidth: 1.5,
          pointRadius: 3,
          fill: false,
          tension: 0.3,
        }
      ]
    },
    options: chartOpts('Operating Income ($M)', false)
  });

  // Gross Margin chart
  charts.margin = new Chart(document.getElementById('marginChart'), {
    type: 'line',
    data: {
      labels: YEARS,
      datasets: [
        {
          label: 'Scenario Gross Margin %',
          data: m.map(x => +x.grossMargin.toFixed(1)),
          borderColor: '#4B9CD3',
          backgroundColor: 'rgba(75,156,211,0.1)',
          fill: true,
          tension: 0.3,
          borderWidth: 2.5,
          pointRadius: 5,
          pointBackgroundColor: '#4B9CD3',
        },
        {
          label: 'Actual Gross Margin %',
          data: GROSS_PROFIT.map((gp,i) => +((gp/REVENUE[i])*100).toFixed(1)),
          borderColor: '#aaa',
          borderDash: [5,4],
          borderWidth: 1.5,
          pointRadius: 3,
          fill: false,
          tension: 0.3,
        }
      ]
    },
    options: chartOpts('Gross Margin (%)', false)
  });

  // Spiral scatter
  charts.spiral = new Chart(document.getElementById('spiralChart'), {
    type: 'scatter',
    data: {
      datasets: [
        {
          label: 'Scenario Path',
          data: m.map((x,i) => ({ x: +x.subs.toFixed(3), y: Math.round(x.fcPerSub), label: YEARS[i] })),
          borderColor: '#C0392B',
          backgroundColor: m.map((x,i) => spiralDotColor(i)),
          pointRadius: 10,
          pointHoverRadius: 13,
          showLine: true,
          tension: 0.3,
          borderWidth: 2,
        },
        {
          label: 'Actual Path',
          data: ACTUAL_SUBS.map((s,i) => ({ x: s, y: Math.round((FIXED_COSTS[i]*1e6)/(s*1e6)) })),
          borderColor: '#aaa',
          backgroundColor: 'rgba(180,180,180,0.5)',
          pointRadius: 5,
          showLine: true,
          borderDash: [5,4],
          borderWidth: 1.5,
          tension: 0.3,
        }
      ]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: {
        legend: { position: 'top', labels: { font: { size: 11 } } },
        tooltip: {
          callbacks: {
            label: (ctx) => {
              const d = ctx.raw;
              const yr = YEARS[ctx.dataIndex] || '';
              return `${yr}: ${d.x.toFixed(2)}M subs · $${d.y}/sub`;
            }
          }
        }
      },
      scales: {
        x: {
          title: { display: true, text: 'Connected Subscribers (M)', font: { size: 11 } },
          grid: { color: '#f0f0f0' },
          ticks: { font: { size: 10 } }
        },
        y: {
          title: { display: true, text: 'Fixed Cost per Subscriber ($)', font: { size: 11 } },
          grid: { color: '#f0f0f0' },
          ticks: { font: { size: 10 } }
        }
      }
    }
  });

  // Add year labels as annotations via afterDraw plugin
  Chart.register({
    id: 'yearLabels',
    afterDraw(chart) {
      if (chart.canvas.id !== 'spiralChart') return;
      const ctx2 = chart.ctx;
      const ds = chart.data.datasets[0];
      ds.data.forEach((pt, i) => {
        const meta = chart.getDatasetMeta(0);
        if (!meta.data[i]) return;
        const { x, y } = meta.data[i].getProps(['x','y'], true);
        ctx2.save();
        ctx2.font = 'bold 10px Segoe UI';
        ctx2.fillStyle = '#13294B';
        ctx2.textAlign = 'center';
        ctx2.fillText(YEARS[i], x, y - 14);
        ctx2.restore();
      });
    }
  });
}

function subColor(s, i) {
  const actual = ACTUAL_SUBS[i];
  if (s > actual * 1.05) return 'rgba(39,174,96,0.75)';
  if (s < actual * 0.95) return 'rgba(192,57,43,0.75)';
  return 'rgba(75,156,211,0.75)';
}

function spiralDotColor(i) {
  const colors = ['#27AE60','#4B9CD3','#F1C40F','#E67E22','#C0392B','#8e44ad'];
  return colors[i] || '#999';
}

function chartOpts(yLabel, stacked) {
  return {
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: { position: 'top', labels: { font: { size: 10 }, boxWidth: 12 } },
      tooltip: { mode: 'index', intersect: false }
    },
    scales: {
      x: { grid: { color: '#f0f0f0' }, ticks: { font: { size: 10 } } },
      y: {
        title: { display: true, text: yLabel, font: { size: 10 } },
        grid: { color: '#f0f0f0' },
        ticks: { font: { size: 10 } },
        stacked: stacked || false
      }
    }
  };
}

// ─────────────────────────────────────────────
// UPDATE ALL
// ─────────────────────────────────────────────
function updateAll() {
  const m = calcMetrics(scenarioSubs);
  const score = spiralScore(m);

  // KPIs
  const totalSubs = scenarioSubs.reduce((a,b)=>a+b,0);
  document.getElementById('kpi-total-subs').textContent = totalSubs.toFixed(2) + 'M';

  const avgFC = m.reduce((a,x)=>a+x.fcPerSub,0)/m.length;
  const actualAvgFC = ACTUAL_SUBS.reduce((a,s,i)=>a+(FIXED_COSTS[i]*1e6)/(s*1e6),0)/ACTUAL_SUBS.length;
  const fcEl = document.getElementById('kpi-avg-fc');
  fcEl.textContent = '$' + Math.round(avgFC).toLocaleString();
  const fcDiff = avgFC - actualAvgFC;
  document.getElementById('kpi-avg-fc-sub').textContent =
    (fcDiff >= 0 ? '▲ +$' : '▼ -$') + Math.abs(Math.round(fcDiff)).toLocaleString() + ' vs. actual';
  fcEl.style.color = fcDiff > 50 ? '#C0392B' : fcDiff < -50 ? '#27AE60' : '#222';

  const totalLoss = m.reduce((a,x)=>a+x.opIncome,0);
  document.getElementById('kpi-op-loss').textContent =
    (totalLoss < 0 ? '-$' : '+$') + Math.abs(Math.round(totalLoss)).toLocaleString() + 'M';

  const worstMargin = Math.min(...m.map(x=>x.grossMargin));
  const worstYear = YEARS[m.findIndex(x=>x.grossMargin===worstMargin)];
  const marginEl = document.getElementById('kpi-margin');
  marginEl.textContent = worstMargin.toFixed(1) + '%';
  document.getElementById('kpi-margin-sub').textContent = 'Worst year: ' + worstYear;
  marginEl.style.color = worstMargin < 15 ? '#C0392B' : worstMargin < 25 ? '#E67E22' : '#27AE60';
  const marginCard = document.getElementById('kpi-margin-card');
  marginCard.className = 'kpi ' + (worstMargin < 15 ? 'red' : worstMargin < 25 ? 'orange' : 'green');

  document.getElementById('kpi-spiral').textContent = score;
  document.getElementById('kpi-spiral').style.color = scoreColor(score);

  // Spiral meter
  document.getElementById('spiral-needle').style.left = score + '%';
  const scoreBig = document.getElementById('spiral-score-big');
  scoreBig.textContent = score;
  scoreBig.style.color = scoreColor(score);

  // Update charts
  charts.sub.data.datasets[0].data = scenarioSubs.map(s => +s.toFixed(3));
  charts.sub.data.datasets[0].backgroundColor = scenarioSubs.map((s,i) => subColor(s,i));
  charts.sub.update('none');

  charts.fc.data.datasets[0].data = m.map(x => Math.round(x.fcPerSub));
  charts.fc.update('none');

  charts.loss.data.datasets[0].data = m.map(x => Math.round(x.opIncome));
  charts.loss.data.datasets[0].backgroundColor = m.map(x => x.opIncome < 0 ? 'rgba(192,57,43,0.75)' : 'rgba(39,174,96,0.75)');
  charts.loss.update('none');

  charts.margin.data.datasets[0].data = m.map(x => +x.grossMargin.toFixed(1));
  charts.margin.update('none');

  charts.spiral.data.datasets[0].data = m.map((x,i) => ({ x: +x.subs.toFixed(3), y: Math.round(x.fcPerSub) }));
  charts.spiral.update('none');

  // Update table
  updateTable(m);
}

function scoreColor(s) {
  if (s >= 75) return '#C0392B';
  if (s >= 50) return '#E67E22';
  if (s >= 25) return '#F1C40F';
  return '#27AE60';
}

function updateTable(m) {
  const tbody = document.getElementById('table-body');
  tbody.innerHTML = '';
  m.forEach((row, i) => {
    const isModified = Math.abs(scenarioSubs[i] - ACTUAL_SUBS[i]) > 0.01;
    const isBad = row.opIncome < -500;
    const tr = document.createElement('tr');
    if (isModified) tr.className = 'modified';
    else if (isBad) tr.className = 'danger';

    const statusEmoji = row.opIncome > 0 ? '✅ Profitable' :
                        row.opIncome > -200 ? '⚠️ Caution' :
                        row.opIncome > -600 ? '🔴 Loss' : '💀 Critical';

    tr.innerHTML = `
      <td>${YEARS[i]}${isModified ? ' ✏️' : ''}</td>
      <td style="color:${scenarioSubs[i] < ACTUAL_SUBS[i] ? '#C0392B' : scenarioSubs[i] > ACTUAL_SUBS[i] ? '#27AE60' : '#222'};font-weight:700">${scenarioSubs[i].toFixed(2)}M</td>
      <td style="color:#888">${ACTUAL_SUBS[i].toFixed(2)}M</td>
      <td>$${Math.round(row.fc).toLocaleString()}M</td>
      <td style="color:${row.fcPerSub > 600 ? '#C0392B' : '#222'};font-weight:700">$${Math.round(row.fcPerSub).toLocaleString()}</td>
      <td>$${Math.round(row.rev).toLocaleString()}M</td>
      <td style="color:${row.opIncome < 0 ? '#C0392B' : '#27AE60'};font-weight:700">${row.opIncome < 0 ? '-$' : '+$'}${Math.abs(Math.round(row.opIncome)).toLocaleString()}M</td>
      <td style="color:${row.grossMargin < 20 ? '#C0392B' : row.grossMargin < 30 ? '#E67E22' : '#27AE60'};font-weight:700">${row.grossMargin.toFixed(1)}%</td>
      <td>${statusEmoji}</td>
    `;
    tbody.appendChild(tr);
  });
}

// ─────────────────────────────────────────────
// INIT
// ─────────────────────────────────────────────
buildSliders();
initCharts();
updateAll();
</script>
</body>
</html>
