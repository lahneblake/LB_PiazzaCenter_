[LB_Guide (4).html](https://github.com/user-attachments/files/27681580/LB_Guide.4.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Piazza Center Weekly Overview</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #f7f6f3;
    --surface: #ffffff;
    --surface2: #f2f0ec;
    --border: #e4e1d9;
    --border2: #d0cdc3;
    --text: #1a1916;
    --text2: #5c5a54;
    --text3: #9b9890;
    --mon: #92400e;
    --mon-bg: #fef3c7;
    --mon-border: #f59e0b;
    --sx: #1e3a5f;
    --sx-bg: #dbeafe;
    --sx-border: #3b82f6;
    --thu: #064e3b;
    --thu-bg: #d1fae5;
    --thu-border: #10b981;
    --fri: #3730a3;
    --fri-bg: #ede9fe;
    --fri-border: #7c3aed;
    --radius: 10px;
    --radius-sm: 6px;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    font-size: 15px;
    line-height: 1.6;
  }

  .topbar {
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    padding: 0 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 56px;
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .topbar-left {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .logo-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--text);
  }

  .topbar-title {
    font-size: 14px;
    font-weight: 600;
    letter-spacing: -0.01em;
    color: var(--text);
  }

  .topbar-sub {
    font-size: 13px;
    color: var(--text3);
    font-family: 'DM Mono', monospace;
  }

  .layout {
    display: flex;
    min-height: calc(100vh - 56px);
  }

  .sidebar {
    width: 200px;
    flex-shrink: 0;
    background: var(--surface);
    border-right: 1px solid var(--border);
    padding: 20px 12px;
    position: sticky;
    top: 56px;
    height: calc(100vh - 56px);
    overflow-y: auto;
  }

  .sidebar-label {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: .1em;
    text-transform: uppercase;
    color: var(--text3);
    padding: 0 8px;
    margin-bottom: 6px;
    margin-top: 16px;
  }

  .sidebar-label:first-child { margin-top: 0; }

  .nav-btn {
    display: flex;
    align-items: center;
    gap: 8px;
    width: 100%;
    padding: 7px 8px;
    border: none;
    background: none;
    border-radius: var(--radius-sm);
    cursor: pointer;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--text2);
    text-align: left;
    transition: background .12s, color .12s;
  }

  .nav-btn:hover { background: var(--surface2); color: var(--text); }

  .nav-btn.active {
    background: var(--text);
    color: #fff;
    font-weight: 500;
  }

  .nav-dot {
    width: 7px;
    height: 7px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .nav-prog {
    margin-left: auto;
    font-size: 10px;
    font-family: 'DM Mono', monospace;
    opacity: .7;
  }

  .main {
    flex: 1;
    padding: 32px 36px;
    max-width: 820px;
  }

  .page { display: none; }
  .page.active { display: block; }

  .page-header {
    margin-bottom: 28px;
  }

  .page-eyebrow {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: .1em;
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  .page-title {
    font-size: 26px;
    font-weight: 600;
    letter-spacing: -0.03em;
    line-height: 1.2;
    margin-bottom: 6px;
  }

  .page-desc {
    font-size: 14px;
    color: var(--text2);
  }

  .progress-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 24px;
  }

  .progress-track {
    flex: 1;
    height: 4px;
    background: var(--border);
    border-radius: 2px;
    overflow: hidden;
  }

  .progress-fill {
    height: 4px;
    border-radius: 2px;
    width: 0%;
    transition: width .3s ease;
  }

  .progress-text {
    font-size: 12px;
    font-family: 'DM Mono', monospace;
    color: var(--text3);
    white-space: nowrap;
  }

  .reset-link {
    font-size: 12px;
    color: var(--text3);
    background: none;
    border: none;
    cursor: pointer;
    text-decoration: underline;
    font-family: 'DM Sans', sans-serif;
    padding: 0;
  }

  .reset-link:hover { color: var(--text2); }

  .section-group {
    margin-bottom: 8px;
  }

  .group-heading {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: .1em;
    text-transform: uppercase;
    color: var(--text3);
    padding: 12px 0 6px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 2px;
  }

  .check-item {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 11px 0;
    border-bottom: 1px solid var(--border);
    transition: opacity .15s;
  }

  .check-item:last-child { border-bottom: none; }

  .check-item input[type=checkbox] {
    width: 16px;
    height: 16px;
    margin-top: 2px;
    flex-shrink: 0;
    accent-color: var(--text);
    cursor: pointer;
  }

  .check-body { flex: 1; }

  .check-title {
    font-size: 14px;
    font-weight: 500;
    color: var(--text);
    line-height: 1.4;
    display: flex;
    align-items: center;
    gap: 6px;
    flex-wrap: wrap;
  }

  .check-note {
    font-size: 12px;
    color: var(--text3);
    margin-top: 3px;
    line-height: 1.5;
  }

  .check-item.done .check-title {
    text-decoration: line-through;
    color: var(--text3);
  }

  .check-item.done .check-note { opacity: .5; }

  .tag {
    font-size: 10px;
    font-weight: 600;
    padding: 2px 7px;
    border-radius: 99px;
    letter-spacing: .02em;
    white-space: nowrap;
  }

  .tag-breast { background: #fef3c7; color: #92400e; }
  .tag-dropbox { background: #dbeafe; color: #1e3a5f; }
  .tag-emr { background: #ede9fe; color: #3730a3; }
  .tag-nurse { background: #d1fae5; color: #064e3b; }
  .tag-urgent { background: #fee2e2; color: #991b1b; }

  .tip {
    background: var(--surface2);
    border-left: 3px solid var(--border2);
    border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
    padding: 12px 16px;
    font-size: 13px;
    color: var(--text2);
    line-height: 1.6;
    margin: 16px 0;
  }

  .tip strong { color: var(--text); font-weight: 600; }

  /* Overview grid */
  .week-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 10px;
    margin-bottom: 24px;
  }

  .day-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 14px 12px;
    cursor: pointer;
    transition: border-color .15s, transform .1s;
  }

  .day-card:hover { border-color: var(--border2); transform: translateY(-1px); }

  .day-card-name {
    font-size: 13px;
    font-weight: 600;
    margin-bottom: 3px;
  }

  .day-card-theme {
    font-size: 11px;
    color: var(--text3);
    margin-bottom: 10px;
    font-family: 'DM Mono', monospace;
  }

  .day-card-tasks {
    font-size: 11px;
    color: var(--text2);
    line-height: 1.8;
  }

  .color-mon { color: var(--mon); }
  .color-sx  { color: var(--sx); }
  .color-thu { color: var(--thu); }
  .color-fri { color: var(--fri); }

  .fill-mon { background: var(--mon-bg); }
  .fill-sx  { background: var(--sx-bg); }
  .fill-thu { background: var(--thu-bg); }
  .fill-fri { background: var(--fri-bg); }

  .bar-mon { background: var(--mon-border); }
  .bar-sx  { background: var(--sx-border); }
  .bar-thu { background: var(--thu-border); }
  .bar-fri { background: var(--fri-border); }

  .dot-mon { background: var(--mon-border); }
  .dot-sx  { background: var(--sx-border); }
  .dot-thu { background: var(--thu-border); }
  .dot-fri { background: var(--fri-border); }

  .eyebrow-mon { color: var(--mon); }
  .eyebrow-sx  { color: var(--sx); }
  .eyebrow-thu { color: var(--thu); }
  .eyebrow-fri { color: var(--fri); }

  .overview-intro {
    font-size: 14px;
    color: var(--text2);
    line-height: 1.7;
    margin-bottom: 20px;
  }

  @media (max-width: 700px) {
    .sidebar { display: none; }
    .main { padding: 20px 16px; }
    .week-grid { grid-template-columns: 1fr 1fr; }
    .topbar-sub { display: none; }
  }
</style>
</head>
<body>

<div class="topbar">
  <div class="topbar-left">
    <div class="logo-dot"></div>
    <span class="topbar-title">Piazza Center Weekly Overview</span>
  </div>
  <span class="topbar-sub">student clinical assistant</span>
</div>

<div class="layout">
  <nav class="sidebar">
    <div class="sidebar-label">Navigation</div>
    <button class="nav-btn active" onclick="show('overview', this)">
      <div class="nav-dot" style="background:#888"></div>
      Overview
    </button>

    <div class="sidebar-label">Checklists</div>
    <button class="nav-btn" onclick="show('mon', this)" id="nav-mon">
      <div class="nav-dot dot-mon"></div>
      Monday
      <span class="nav-prog" id="nprog-mon">0/14</span>
    </button>
    <button class="nav-btn" onclick="show('tue', this)" id="nav-tue">
      <div class="nav-dot dot-sx"></div>
      Tuesday
      <span class="nav-prog" id="nprog-tue">0/11</span>
    </button>
    <button class="nav-btn" onclick="show('wed', this)" id="nav-wed">
      <div class="nav-dot dot-sx"></div>
      Wednesday
      <span class="nav-prog" id="nprog-wed">0/12</span>
    </button>
    <button class="nav-btn" onclick="show('thu', this)" id="nav-thu">
      <div class="nav-dot dot-thu"></div>
      Thursday
      <span class="nav-prog" id="nprog-thu">0/20</span>
    </button>
    <button class="nav-btn" onclick="show('fri', this)" id="nav-fri">
      <div class="nav-dot dot-fri"></div>
      Friday
      <span class="nav-prog" id="nprog-fri">0/10</span>
    </button>

    <div class="sidebar-label">Reference</div>
    <button class="nav-btn" onclick="show('glossary', this)">
      <div class="nav-dot" style="background:#888"></div>
      Glossary
    </button>
    <button class="nav-btn" onclick="show('contacts', this)">
      <div class="nav-dot" style="background:#888"></div>
      Contacts
    </button>
    <button class="nav-btn" onclick="show('notes', this)">
      <div class="nav-dot" style="background:#e879a0"></div>
      My Notes
    </button>
    <button class="nav-btn" onclick="show('training', this)">
      <div class="nav-dot" style="background:#0891b2"></div>
      Training
    </button>
  </nav>

  <main class="main">

    <!-- OVERVIEW -->
    <div id="page-overview" class="page active">
      <div class="page-header">
        <div class="page-eyebrow" style="color:#888">your week at a glance</div>
        <div class="page-title">Weekly Schedule</div>
        <div class="page-desc">Tap any day card to open its full checklist.</div>
      </div>
      <div class="week-grid">
        <div class="day-card" onclick="show('mon', document.getElementById('nav-mon'))">
          <div class="day-card-name color-mon">Monday</div>
          <div class="day-card-theme">admin + prep</div>
          <div class="day-card-tasks">Pack surgery bags<br>Place orders<br>Send pre-op packets<br>Request clearances<br>Return unused implants</div>
        </div>
        <div class="day-card" onclick="show('tue', document.getElementById('nav-tue'))">
          <div class="day-card-name color-sx">Tuesday</div>
          <div class="day-card-theme">surgery day</div>
          <div class="day-card-tasks">Confirm OR supplies<br>Vitals + tray assist<br>Post-op calls<br>Chart import to PN<br>Schedule post-ops</div>
        </div>
        <div class="day-card" onclick="show('wed', document.getElementById('nav-wed'))">
          <div class="day-card-name color-sx">Wednesday</div>
          <div class="day-card-theme">surgery day</div>
          <div class="day-card-tasks">Same as Tuesday<br>Build pre-op charts<br>Upload Dropbox photos<br>ISC orders + notes</div>
        </div>
        <div class="day-card" onclick="show('thu', document.getElementById('nav-thu'))">
          <div class="day-card-name color-thu">Thursday</div>
          <div class="day-card-theme">consults + post-ops</div>
          <div class="day-card-tasks">Room setup<br>Vitals + sizing<br>Photos<br>Consents<br>Blue Note tasks</div>
        </div>
        <div class="day-card" onclick="show('fri', document.getElementById('nav-fri'))">
          <div class="day-card-name color-fri">Friday</div>
          <div class="day-card-theme">notes + filing</div>
          <div class="day-card-tasks">Receive sx center notes<br>File into EMR<br>Post-op calls (Wed pts)<br>Prep for next week</div>
        </div>
      </div>
      <div class="tip"><strong>Ongoing every day:</strong> Document everything in the EMR the same day. Monitor communications. Respond to urgent patient questions with clinical staff guidance.</div>
    </div>

    <!-- MONDAY -->
    <div id="page-mon" class="page">
      <div class="page-header">
        <div class="page-eyebrow eyebrow-mon">Monday</div>
        <div class="page-title">Admin + Prep</div>
        <div class="page-desc">No patients today. Set the whole week up.</div>
      </div>
      <div class="progress-row">
        <div class="progress-track"><div class="progress-fill bar-mon" id="bar-mon"></div></div>
        <span class="progress-text" id="lbl-mon">0 / 14</span>
        <button class="reset-link" onclick="resetDay('mon',14)">Reset</button>
      </div>

      <div class="section-group">
        <div class="group-heading">Surgery bag packing</div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Pull implants for each surgery patient</div><div class="check-note">Confirm cc, profile, and brand match the implant selection sheet exactly.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Pack GalaFlex / Strattice / mesh if ordered</div><div class="check-note">Flat pieces go inside the pre-op chart. 3D GalaShape goes in the large plastic transport box.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Pack surgical garments and bras <span class="tag tag-breast">breast</span></div><div class="check-note">Match garment size to patient. Confirm bra has been ordered and arrived.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Label each bag with patient initials + date of surgery</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Orders and supplies</div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Return unused implants from last week</div><div class="check-note">Schedule FedEx pickup. Use correct return packaging per manufacturer.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Place implant orders for upcoming surgeries</div><div class="check-note">Check 2–3 weeks out. Order early — shipping takes time.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Order GalaFlex / Strattice / Revolve if needed <span class="tag tag-breast">breast</span></div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Order hernia repair mesh if co-case scheduled</div><div class="check-note">We are responsible for this product being at the surgery center day-of.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Order surgical bras <span class="tag tag-breast">breast patients</span></div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Pre-op prep</div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Send pre-op packets + consents to upcoming patients</div><div class="check-note">Email from EHR. Include instructions, consents, and prescription info.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Send medical records requests for clearances</div><div class="check-note">Enter other providers into the system. Send clearance requests.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Forward clearances received → Surgery Center + Anesthesia <span class="tag tag-dropbox">Dropbox</span></div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Send mammogram / lab orders if applicable</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('mon',14,this)"><div class="check-body"><div class="check-title">Build any pre-op charts that haven't been started</div><div class="check-note">Check inside front cover checklist. Add consult note, photos, implant selection sheet, etc.</div></div></div>
      </div>
    </div>

    <!-- TUESDAY -->
    <div id="page-tue" class="page">
      <div class="page-header">
        <div class="page-eyebrow eyebrow-sx">Tuesday</div>
        <div class="page-title">Surgery Day</div>
        <div class="page-desc"></div>
      </div>
      <div class="progress-row">
        <div class="progress-track"><div class="progress-fill bar-sx" id="bar-tue"></div></div>
        <span class="progress-text" id="lbl-tue">0 / 11</span>
        <button class="reset-link" onclick="resetDay('tue',11)">Reset</button>
      </div>

      <div class="section-group">
        <div class="group-heading">Morning</div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Confirm surgery bags delivered to surgery center</div><div class="check-note">Packed Friday or Monday. Verify they physically arrived.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Review today's OR schedule</div><div class="check-note">Know each patient's name, procedure, and any flags (revision, tissue pathology, co-case).</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Procedure support (under direct supervision)</div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Pre-procedure vitals for in-office cases</div><div class="check-note">BP, HR, temperature. Document in chart before procedure begins.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Assist with procedure tray setup <span class="tag tag-nurse">nurse leads</span></div><div class="check-note">Under nurse direction only. Sterile field: instruments, drapes, local anesthetic per Dr. Piazza's formula.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Instrument sterilization after procedures</div><div class="check-note">Clean immediately after use. Follow autoclave protocol and log the cycle.</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Documentation</div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Import surgical charts into Symplast <span class="tag tag-emr">EMR</span></div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Scan paper documents into chart</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Create ISC / Dr. Cady orders + 2-week note</div><div class="check-note">Email all required documentation and photos to ISC.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Schedule post-op appointments for today's surgical patients</div><div class="check-note">1-week and 2-week post-ops minimum.</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Next day (do Wednesday morning)</div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">1-day post-op calls for Monday's surgical patients</div><div class="check-note">Ask about pain, fever, swelling, bleeding, drain output. Document in chart. Escalate anything abnormal immediately.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('tue',11,this)"><div class="check-body"><div class="check-title">Document post-op call notes in EHR same day <span class="tag tag-emr">EMR</span></div></div></div>
      </div>
    </div>

    <!-- WEDNESDAY -->
    <div id="page-wed" class="page">
      <div class="page-header">
        <div class="page-eyebrow eyebrow-sx">Wednesday</div>
        <div class="page-title">Surgery Day</div>
        <div class="page-desc"></div>
      </div>
      <div class="progress-row">
        <div class="progress-track"><div class="progress-fill bar-sx" id="bar-wed"></div></div>
        <span class="progress-text" id="lbl-wed">0 / 12</span>
        <button class="reset-link" onclick="resetDay('wed',12)">Reset</button>
      </div>

      <div class="section-group">
        <div class="group-heading">Morning</div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Confirm surgery bags at surgery center</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Review today's OR schedule</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">1-day post-op calls for Tuesday's patients</div><div class="check-note">Document results in EHR same day.</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Procedure support (under direct supervision)</div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Pre-procedure vitals for in-office cases</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Assist with tray setup under nurse direction <span class="tag tag-nurse">nurse leads</span></div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Instrument sterilization after procedures</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Documentation</div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Import surgical charts into Symplast <span class="tag tag-emr">EMR</span></div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Scan paper documents into chart</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Create ISC / Dr. Cady orders + 2-week note</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Schedule post-op appointments for today's patients</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Pre-op chart building (for next week's surgeries)</div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Build pre-op charts for upcoming patients</div><div class="check-note">Add all required documents per the front cover checklist. Consult note, photos, implant sheet, etc.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('wed',12,this)"><div class="check-body"><div class="check-title">Export + upload pre-op photos to Dropbox for Inspire <span class="tag tag-dropbox">Dropbox</span></div><div class="check-note">Canfield Mirror → export to P:\6_Pre-op\ISC Photos Sent → upload to "The Piazza Center" folder. Name: M_DD_YYYY Initials.</div></div></div>
      </div>
    </div>

    <!-- THURSDAY -->
    <div id="page-thu" class="page">
      <div class="page-header">
        <div class="page-eyebrow eyebrow-thu">Thursday</div>
        <div class="page-title">Consults + Post-Ops</div>
        <div class="page-desc">Patient-facing day. Room must be fully ready before the first patient arrives.</div>
      </div>
      <div class="progress-row">
        <div class="progress-track"><div class="progress-fill bar-thu" id="bar-thu"></div></div>
        <span class="progress-text" id="lbl-thu">0 / 20</span>
        <button class="reset-link" onclick="resetDay('thu',20)">Reset</button>
      </div>

      <div class="section-group">
        <div class="group-heading">Room setup (before first patient)</div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Turn on lamp</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Connect AirPlay to show graphic on TV</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Implant sizers wiped clean and set out</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Measuring tools in the drawer</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Mirror wiped clean</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Orchid in place and looking fresh</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Picture frames straightened on wall</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Clothes bin stocked — gown, robe, slippers</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Scale and BP cuff on and zeroed</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Dr. Piazza's markers and papers set out</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Implant / GalaFlex selection forms ready</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Correct consent documents pulled per patient procedure type</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Each patient visit</div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Vitals: height, weight, BP — document in chart</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Check medications and allergies are up to date in chart</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Implant sizing if new breast patient <span class="tag tag-breast">breast</span></div><div class="check-note">Have patient try sizers in bra. Document preferred cc and profile on implant selection form.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Photos taken in correct layout for procedure type</div><div class="check-note">Breast minimum: AP, bilateral lateral, bilateral oblique. Consistent distance and lighting every time.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Look up past implants if revision case</div><div class="check-note">Check chart first. If not found, call manufacturer — see Contacts tab.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Consents signed and loaded into chart <span class="tag tag-nurse">nurse witnesses</span></div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Note sent for any follow-up tasks</div><div class="check-note">Internal communication/task platform used to message Dr. Piazza, front desk, and other team members. Not patient-facing.</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">After each patient</div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Reset room — wipe sizers, restock bin, reset forms</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('thu',20,this)"><div class="check-body"><div class="check-title">Chart documented before next patient <span class="tag tag-emr">EMR</span></div></div></div>
      </div>
    </div>

    <!-- FRIDAY -->
    <div id="page-fri" class="page">
      <div class="page-header">
        <div class="page-eyebrow eyebrow-fri">Friday</div>
        <div class="page-title">Notes + Filing</div>
        <div class="page-desc">Surgery center notes come back. File everything and close out the week.</div>
      </div>
      <div class="tip"><strong>What are surgery center notes?</strong> After surgery the facility generates operative notes, anesthesia records, and nursing documentation. These come back to the practice and need to be filed in the correct patient chart in the EMR so Dr. Piazza and the care team can reference them.</div>
      <div class="progress-row">
        <div class="progress-track"><div class="progress-fill bar-fri" id="bar-fri"></div></div>
        <span class="progress-text" id="lbl-fri">0 / 10</span>
        <button class="reset-link" onclick="resetDay('fri',10)">Reset</button>
      </div>

      <div class="section-group">
        <div class="group-heading">Filing surgery center notes</div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Collect all notes returned from surgery center</div><div class="check-note">Check fax, email, and any physical documents.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Match each document to correct patient chart</div><div class="check-note">Verify by name, DOB, and date of service — not just name alone.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Scan paper documents into digital format</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Upload into correct location in EMR <span class="tag tag-emr">EMR</span></div><div class="check-note">Operative note, anesthesia record, and nursing documentation each go in their own section.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Verify every this-week surgery patient has a complete chart</div><div class="check-note">Nothing missing before the weekend.</div></div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Closing out the week</div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">1-day post-op calls for Wednesday's patients</div><div class="check-note">Document in EHR. Escalate any concerns before the weekend.</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Confirm next week's surgery bags are packed or scheduled</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Confirm all outstanding clearances followed up</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Confirm all implant / product orders placed for next week</div></div></div>
        <div class="check-item"><input type="checkbox" onchange="tick('fri',10,this)"><div class="check-body"><div class="check-title">Blue Note any unresolved items to the team before leaving</div></div></div>
      </div>
    </div>

    <!-- GLOSSARY -->
    <div id="page-glossary" class="page">
      <div class="page-header">
        <div class="page-eyebrow" style="color:#888">reference</div>
        <div class="page-title">Glossary</div>
        <div class="page-desc">Procedures, terms, materials, and systems you'll encounter in this role.</div>
      </div>

      <div class="section-group">
        <div class="group-heading">Procedures Dr. Piazza performs</div>

        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Breast augmentation</div>
          <div class="check-note">The most common procedure at the practice. Implants (saline or silicone) are placed under the breast tissue or chest muscle to increase size and improve shape. Dr. Piazza is known as one of Austin's top breast surgeons.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Breast augmentation revision</div>
          <div class="check-note">Surgery to correct or improve a previous breast augmentation — replacing old implants, fixing asymmetry, correcting complications (like capsular contracture), or changing size/profile. These patients often have implant records you'll need to track down.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Breast lift (mastopexy)</div>
          <div class="check-note">Removes excess skin and reshapes breast tissue to raise and firm sagging breasts. Often combined with augmentation. No implant is used for a lift alone.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Breast reduction</div>
          <div class="check-note">Removes excess breast tissue, fat, and skin to reduce size and relieve physical symptoms (back pain, rashes, posture issues). Insurance may cover this — that's why the insurance card is required for all breast surgery patients.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Fat transfer breast augmentation</div>
          <div class="check-note">Uses the patient's own fat (harvested via liposuction) to add volume to the breasts instead of implants. Revolve system is often used to process the fat before injection.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Tummy tuck (abdominoplasty)</div>
          <div class="check-note">Removes excess skin and fat from the abdomen and tightens the abdominal muscles. One of the most popular body procedures at the practice, especially post-pregnancy.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Mommy makeover</div>
          <div class="check-note">A customized combination of procedures (typically breast augmentation or lift + tummy tuck + liposuction) done in one OR session to address post-pregnancy body changes. Major surgery with longer OR time.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Liposuction</div>
          <div class="check-note">Removes stubborn pockets of fat from areas like the abdomen, flanks, thighs, and arms using a thin tube (cannula). Often combined with other procedures. Revolve may be used when fat is being transferred.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Hip lift / waistline reshaping</div>
          <div class="check-note">Contouring procedures that target the hips, flanks, and waistline using liposuction and/or fat transfer to create a more defined figure.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Gynecomastia surgery</div>
          <div class="check-note">Removes excess breast tissue in men (a condition called gynecomastia). Involves liposuction and/or direct tissue excision. One of the main procedures under the "For Men" category.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Blepharoplasty</div>
          <div class="check-note">Eyelid surgery — removes excess skin and/or fat from upper or lower eyelids. Can be cosmetic or functional (when drooping lids affect vision). Done under local anesthetic with sedation.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Lip lift</div>
          <div class="check-note">Shortens the distance between the nose and upper lip by removing a small strip of skin under the nose. Creates a more lifted, youthful lip appearance. In-office surgical procedure.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Otoplasty</div>
          <div class="check-note">Ear reshaping surgery — typically to pin back ears that stick out or correct ear shape. Done under local anesthetic.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Facial / body scar revision</div>
          <div class="check-note">Surgical or laser treatment to improve the appearance of scars from injury or previous surgery. Involves excision, repositioning, or resurfacing depending on the scar type.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Facial lesion excision</div>
          <div class="check-note">Surgical removal of a growth, cyst, mole, or other lesion on the face. Excised tissue is often sent to pathology — check the tissue algorithm in the chart.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Inverted nipple repair</div>
          <div class="check-note">Minor in-office procedure to correct nipples that are retracted inward. Done under local anesthetic.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Saline implant deflation</div>
          <div class="check-note">In-office procedure where saline implants are deflated (drained) in preparation for revision surgery. Done with a needle — you set up the tray and document the visit.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Aveli</div>
          <div class="check-note">A minimally invasive in-office procedure to treat cellulite. A small device severs the fibrous bands under the skin that cause the dimpled appearance. Done under local anesthetic.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">P-Shot</div>
          <div class="check-note">Platelet-Rich Plasma (PRP) injection for male sexual wellness. Blood is drawn, spun in a centrifuge to isolate PRP, then injected. You may assist with blood draw setup and centrifuge.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Seroma aspiration</div>
          <div class="check-note">A seroma is a pocket of fluid that can form after surgery. Aspiration = draining it in clinic with a needle and syringe. You set up the sterile field; Dr. Piazza performs the aspiration. Document the volume removed.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Ear piercing</div>
          <div class="check-note">Offered as a clinical service at the practice. You set up the tray and assist. Document and charge accordingly.</div>
        </div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Types of breast implants</div>

        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Saline implants</div>
          <div class="check-note">Silicone shell filled with sterile salt water. If they rupture, the saline is safely absorbed by the body. Can be filled after insertion, allowing a smaller incision. Deflation is visible immediately. Manufactured by Mentor and Allergan.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Silicone gel implants</div>
          <div class="check-note">Silicone shell pre-filled with cohesive silicone gel. Feel more like natural breast tissue. Most popular type at this practice. If they rupture, the gel usually stays within the shell ("silent rupture") — requires MRI to detect. Made by Mentor, Allergan, and Sientra.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Motiva implants</div>
          <div class="check-note">A newer generation of silicone implants Dr. Piazza uses and features prominently on the website. Known for a progressive gel that feels very natural, a smooth surface, and a microchip for tracking. Considered a premium option.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Implant profile</div>
          <div class="check-note">How far the implant projects forward from the chest wall. Options typically include low, moderate, moderate plus, high, and ultra-high profile. Dr. Piazza selects profile based on the patient's chest width and desired look. Documented on the implant selection sheet.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Implant cc (volume)</div>
          <div class="check-note">The size of the implant measured in cubic centimeters. Ranges typically from ~150cc to 800cc+. During sizing, you help the patient try different cc options using sizer implants in a bra to find their preferred volume.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Implant manufacturers</div>
          <div class="check-note">The three main brands Dr. Piazza uses: Mentor, Allergan (AbbVie), and Sientra. Motiva is an additional brand for premium silicone. When looking up a patient's old implants, you'll call the manufacturer with patient name, DOB, and approximate surgery date.</div>
        </div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Common clinical terms</div>

        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">H&P (History and Physical)</div>
          <div class="check-note">A standard medical document that summarizes a patient's medical history, current medications, allergies, and physical exam findings. Must be completed and signed by Dr. Piazza within 30 days of surgery (the 2-week update note refreshes this).</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">PMH / PSH</div>
          <div class="check-note">PMH = Past Medical History (chronic conditions, diagnoses). PSH = Past Surgical History (previous surgeries). Both are verified at the pre-op visit and must be up to date in the EHR.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Capsular contracture</div>
          <div class="check-note">A complication where scar tissue (capsule) around a breast implant tightens and hardens, causing firmness, distortion, or pain. A common reason patients come in for revision surgery.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Seroma</div>
          <div class="check-note">A collection of fluid (serum) that builds up under the skin after surgery. Looks like swelling or a soft lump. Treated with aspiration in clinic — you'll see this regularly at post-op visits.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Local anesthetic</div>
          <div class="check-note">Medication (like lidocaine ± epinephrine) injected to numb a specific area before an in-office procedure. Dr. Piazza mixes his own formula — you draw it up per his instructions. Less is more; never waste product.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">DOS (date of surgery)</div>
          <div class="check-note">The scheduled date of a patient's surgical procedure. Used when naming Dropbox folders, labeling surgery bags, and organizing documentation.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Consult note</div>
          <div class="check-note">The clinical note Dr. Piazza writes after the initial consultation describing the patient's concerns, exam findings, and surgical plan. Goes into the pre-op chart and is sent to the surgery center.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Standing orders</div>
          <div class="check-note">Pre-approved protocols that allow certain prescriptions or actions to be carried out without a new order each time. For example, the nurse sends certain pre-op prescriptions per standing orders. Know what's on the list.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Hibiclens</div>
          <div class="check-note">An antiseptic skin wash patients use at home the night before and morning of surgery to reduce infection risk. Instructions are printed and included in the pre-op packet.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Tissue pathology</div>
          <div class="check-note">When tissue is removed during surgery (e.g. a capsule, lesion, or skin), it may be sent to a pathology lab for analysis. The Pathology/Tissue Algorithm in the pre-op chart determines when this applies. If applicable, the patient's insurance card must be in the chart.</div>
        </div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Surgical materials</div>

        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">GalaFlex</div>
          <div class="check-note">A resorbable scaffold mesh used in breast surgery to support the lower breast pocket or reinforce tissue. Gradually absorbs into the body over ~12–18 months. Often used in revision augmentation or mastopexy. You order it, confirm it arrives, and pack it in the surgery bag. Flat pieces go inside the chart; 3D GalaShape goes in the transport box.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Strattice</div>
          <div class="check-note">An acellular dermal matrix (ADM) made from porcine (pig) tissue. Used to support implant placement or reinforce thin tissue in revision surgery. Integrates into the patient's own tissue over time. Flat pieces go inside the pre-op chart; 3D pieces go in the transport box.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">AlloClae</div>
          <div class="check-note">A newer acellular dermal matrix (ADM) product Dr. Piazza uses — similar purpose to Strattice. Featured on the website as an option for breast procedures requiring tissue support.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Revolve</div>
          <div class="check-note">A closed-loop fat processing system used during fat transfer procedures. Harvested fat is filtered and purified through the Revolve system before being re-injected into the breast or body.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Hernia repair mesh</div>
          <div class="check-note">Used in co-cases with General Surgery for hernia repairs done at the same time as a tummy tuck or body procedure. The Piazza Center is responsible for having this product at the surgery center on the day of surgery — it's your job to order it and confirm it's there.</div>
        </div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Safety protocols</div>

        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">DVT prophylaxis</div>
          <div class="check-note">DVT = Deep Vein Thrombosis (blood clot, usually in a leg vein). Surgical patients are at elevated risk. The team confirms a prevention plan before surgery: compression stockings, sequential compression devices (SCDs) in the OR, blood thinners if indicated. Your job is confirming the DVT assessment sheet is completed, signed by Dr. Piazza, and in the Inspire Dropbox.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Tobacco / nicotine cessation</div>
          <div class="check-note">Nicotine significantly impairs wound healing and increases surgical complications. Patients must confirm cessation before surgery. This is documented in the pre-op chart and is part of the safety protocol checklist.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Cardiac clearance</div>
          <div class="check-note">Patients with cardiac history or risk factors need clearance from a cardiologist before surgery. You send the clearance request and follow up. For last-minute needs, there's a direct contact protocol — ask the team for that info.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Tissue pathology protocol</div>
          <div class="check-note">The practice has a specific algorithm to determine when removed tissue must be sent to pathology. The Pathology/Tissue Algorithm document lives in the pre-op chart. If pathology is indicated, insurance card goes in the chart too.</div>
        </div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Systems</div>

        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">EMR (Electronic Medical Record)</div>
          <div class="check-note">The practice's electronic medical record system — where all patient charts, surgical records, appointments, documentation, and prescriptions live. The practice is transitioning to a new EMR; follow the team's guidance on which system is current.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Blue Note</div>
          <div class="check-note">Internal practice communication platform — like a clinical task/messaging system. Used to send notes to Dr. Piazza, front desk, and other team members. Not patient-facing. Learn the templates used for common tasks.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Canfield Mirror</div>
          <div class="check-note">Photo documentation software used for clinical before/after photos. You use it to search patient charts, select photos, and export them for Inspire and the pre-op chart. Export destination: P:\6_Pre-op\ISC Photos Sent.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Dropbox for Business</div>
          <div class="check-note">Used to send pre-op documents and photos to Inspire Surgical Center (ISC). Each patient gets a folder named with initials + DOS (e.g. 1_11_2026 SS). Login: nursing@thepiazzacenter.com. See Contacts tab for full login info.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">ISC / Inspire Surgical Center</div>
          <div class="check-note">The exclusive surgery center where Dr. Piazza performs all OR cases. Dr. Cady is the anesthesiologist. You send them pre-op documentation, clearances, and photos via Dropbox. Surgery bags also go here before each OR day.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Symplast</div>
          <div class="check-note">The practice's EMR and practice management platform — used for scheduling, patient communication, charting, and document management. You import surgical charts and scan documents into Symplast after each surgery day.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Telemedicine platform</div>
          <div class="check-note">Virtual visit platform used for remote pre-op or follow-up appointments when patients can't come in person. Used especially for traveling patients — the practice has a dedicated concierge program for out-of-town patients.</div>
        </div></div>
      </div>
    </div>

    <!-- CONTACTS -->
    <div id="page-contacts" class="page">
      <div class="page-header">
        <div class="page-eyebrow" style="color:#888">reference</div>
        <div class="page-title">Key Contacts</div>
        <div class="page-desc">Numbers and info you'll reach for regularly.</div>
      </div>

      <div class="section-group">
        <div class="group-heading">Implant manufacturers — for looking up old implants</div>
        <div class="tip">When a patient is a revision case, you need the specs of their existing implants. Check the chart first for OR stickers. If not found, call the manufacturer with the patient's name, DOB, and approximate surgery date.</div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Mentor</div>
          <div class="check-note" style="font-size:14px; font-family:'DM Mono',monospace; color:var(--text)">1-800-636-8673</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Allergan / AbbVie</div>
          <div class="check-note" style="font-size:14px; font-family:'DM Mono',monospace; color:var(--text)">1-800-624-4261</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Sientra</div>
          <div class="check-note" style="font-size:14px; font-family:'DM Mono',monospace; color:var(--text)">1-888-708-0808</div>
        </div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Dropbox</div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Login</div>
          <div class="check-note">URL: dropbox.com/business<br>Username: nursing@thepiazzacenter.com<br>Password: Spr1ng.2026##<br>Skip 2FA setup if prompted.</div>
        </div></div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Photo folder naming convention</div>
          <div class="check-note" style="font-family:'DM Mono',monospace; font-size:13px; color:var(--text)">M_DD_YYYY Initials<br><span style="color:var(--text3)">e.g. 1_11_2026 SS (Suzy Smith, Jan 11)</span></div>
        </div></div>
      </div>

      <div class="section-group">
        <div class="group-heading">Photo export path</div>
        <div class="check-item" style="cursor:default"><div class="check-body">
          <div class="check-title">Canfield Mirror export destination</div>
          <div class="check-note" style="font-family:'DM Mono',monospace; font-size:13px; color:var(--text)">P:\6_Pre-op\ISC Photos Sent</div>
        </div></div>
      </div>
    </div>

    <!-- NOTES -->
    <div id="page-notes" class="page">
      <div class="page-header">
        <div class="page-eyebrow" style="color:#e879a0">my notes</div>
        <div class="page-title">Notes &amp; Reminders</div>
        <div class="page-desc">Jot down anything you need to remember or ask later. Notes save automatically in your browser.</div>
      </div>

      <div class="section-group">
        <div class="group-heading">Questions for Dr. Piazza</div>
        <div style="margin-bottom:10px">
          <textarea id="note-drp" placeholder="Write anything you want to ask Dr. Piazza — procedures, protocols, anything you're unsure about..." oninput="saveNote('drp')" style="width:100%;min-height:120px;padding:12px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--text);background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);resize:vertical;line-height:1.6;outline:none;transition:border-color .15s" onfocus="this.style.borderColor='var(--border2)'" onblur="this.style.borderColor='var(--border)'"></textarea>
        </div>
      </div>

      <div class="section-group">
        <div class="group-heading">Monday — things to remember</div>
        <textarea id="note-mon" placeholder="Admin tasks, orders to place, anything extra for Monday..." oninput="saveNote('mon')" style="width:100%;min-height:100px;padding:12px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--text);background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);resize:vertical;line-height:1.6;outline:none;transition:border-color .15s" onfocus="this.style.borderColor='var(--mon-border)'" onblur="this.style.borderColor='var(--border)'"></textarea>
      </div>

      <div class="section-group">
        <div class="group-heading">Tuesday — things to remember</div>
        <textarea id="note-tue" placeholder="Surgery day notes, patient flags, anything to follow up on..." oninput="saveNote('tue')" style="width:100%;min-height:100px;padding:12px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--text);background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);resize:vertical;line-height:1.6;outline:none;transition:border-color .15s" onfocus="this.style.borderColor='var(--sx-border)'" onblur="this.style.borderColor='var(--border)'"></textarea>
      </div>

      <div class="section-group">
        <div class="group-heading">Wednesday — things to remember</div>
        <textarea id="note-wed" placeholder="Surgery day notes, chart building reminders, Dropbox tasks..." oninput="saveNote('wed')" style="width:100%;min-height:100px;padding:12px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--text);background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);resize:vertical;line-height:1.6;outline:none;transition:border-color .15s" onfocus="this.style.borderColor='var(--sx-border)'" onblur="this.style.borderColor='var(--border)'"></textarea>
      </div>

      <div class="section-group">
        <div class="group-heading">Thursday — things to remember</div>
        <textarea id="note-thu" placeholder="Consult day notes, specific patients, sizing reminders..." oninput="saveNote('thu')" style="width:100%;min-height:100px;padding:12px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--text);background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);resize:vertical;line-height:1.6;outline:none;transition:border-color .15s" onfocus="this.style.borderColor='var(--thu-border)'" onblur="this.style.borderColor='var(--border)'"></textarea>
      </div>

      <div class="section-group">
        <div class="group-heading">Friday — things to remember</div>
        <textarea id="note-fri" placeholder="Filing notes, end-of-week loose ends, next week prep..." oninput="saveNote('fri')" style="width:100%;min-height:100px;padding:12px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--text);background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);resize:vertical;line-height:1.6;outline:none;transition:border-color .15s" onfocus="this.style.borderColor='var(--fri-border)'" onblur="this.style.borderColor='var(--border)'"></textarea>
      </div>

      <div class="section-group">
        <div class="group-heading">General / ongoing notes</div>
        <textarea id="note-gen" placeholder="Anything that doesn't fit a specific day — protocols you're learning, things to look up, running lists..." oninput="saveNote('gen')" style="width:100%;min-height:140px;padding:12px 14px;font-family:'DM Sans',sans-serif;font-size:13px;color:var(--text);background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);resize:vertical;line-height:1.6;outline:none;transition:border-color .15s" onfocus="this.style.borderColor='var(--border2)'" onblur="this.style.borderColor='var(--border)'"></textarea>
        <div style="font-size:11px;color:var(--text3);margin-top:6px;font-family:'DM Mono',monospace">notes save automatically as you type</div>
      </div>
    </div>

    <!-- TRAINING -->
    <div id="page-training" class="page">
      <div class="page-header">
        <div class="page-eyebrow" style="color:#0891b2">training</div>
        <div class="page-title">Training Tutorials</div>
        <div class="page-desc">Add steps to each section, edit them, check them off as you learn. Everything saves automatically.</div>
      </div>
      <div id="training-root"></div>
    </div>

  </main>
</div>

<script>
  var totals = { mon:14, tue:11, wed:12, thu:20, fri:10 };

  /* ── NOTES ── */
  function saveNote(key) {
    var el = document.getElementById('note-' + key);
    if (el) localStorage.setItem('pc_note_' + key, el.value);
  }
  function loadNotes() {
    ['drp','mon','tue','wed','thu','fri','gen'].forEach(function(k) {
      var el = document.getElementById('note-' + k);
      var saved = localStorage.getItem('pc_note_' + k);
      if (el && saved) el.value = saved;
    });
  }

  /* ── NAV ── */
  function show(id, btn) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('page-' + id).classList.add('active');
    if (btn) btn.classList.add('active');
    window.scrollTo(0,0);
  }

  /* ── CHECKLISTS ── */
  function tick(day, total, cb) {
    var li = cb.closest('.check-item');
    if (li) li.classList.toggle('done', cb.checked);
    updateProg(day, total);
  }
  function updateProg(day, total) {
    var page = document.getElementById('page-' + day);
    if (!page) return;
    var checked = page.querySelectorAll('input[type=checkbox]:checked').length;
    var bar = document.getElementById('bar-' + day);
    var lbl = document.getElementById('lbl-' + day);
    var nprog = document.getElementById('nprog-' + day);
    if (bar) bar.style.width = Math.round(checked / total * 100) + '%';
    if (lbl) lbl.textContent = checked + ' / ' + total;
    if (nprog) nprog.textContent = checked + '/' + total;
  }
  function resetDay(day, total) {
    var page = document.getElementById('page-' + day);
    if (!page) return;
    page.querySelectorAll('input[type=checkbox]').forEach(cb => cb.checked = false);
    page.querySelectorAll('.check-item').forEach(li => li.classList.remove('done'));
    updateProg(day, total);
  }

  /* ── TRAINING ── */
  var TR_KEY = 'pc_training_v2';

  var defaultSections = [
    {
      id: 'preop', title: 'Pre-op Training',
      steps: [
        {id:'p1', text:'Learn what documents go inside the pre-op chart', note:'Consult note, progress note, pathology algorithm, insurance card, pre-op photos, implant selection sheet.', done:false},
        {id:'p2', text:'Practice building a pre-op chart start to finish', note:'Use the inside front cover checklist. Shadow a completed chart first.', done:false},
        {id:'p3', text:'Learn how to send pre-op packets to patients via Symplast', note:'Instructions, consents, and prescription info sent from Symplast.', done:false},
        {id:'p4', text:'Practice exporting photos from Canfield Mirror and uploading to Dropbox', note:'Export to P:\\6_Pre-op\\ISC Photos Sent → upload to "The Piazza Center" Dropbox folder.', done:false},
        {id:'p5', text:'Learn how to send documents to Surgery Center via Dropbox', note:'Consult note, H&P, pre-op orders, DVT assessment, implant selection form, insurance card.', done:false},
        {id:'p6', text:'Learn how to enter clearance requests and outside providers in Symplast', note:'', done:false},
        {id:'p7', text:'Understand the pre-op prescription process and standing orders', note:'Know which prescriptions go out routinely and how to verify they were sent.', done:false},
        {id:'p8', text:'Learn the DVT assessment sheet — where it goes and who signs it', note:'', done:false},
        {id:'p9', text:'Complete a pre-op visit start to finish with supervision', note:'Vitals, meds/allergy check, consents, caregiver info, post-op scheduling, text patient confirmation.', done:false}
      ]
    },
    {
      id: 'postop', title: 'Post-op Training',
      steps: [
        {id:'po1', text:'Learn the 1-day post-op call script', note:'What to ask: pain level, fever, swelling, bleeding, drain output. Know what needs escalation.', done:false},
        {id:'po2', text:'Practice documenting a post-op call in Symplast', note:'Know exactly where the call note goes and what format to use.', done:false},
        {id:'po3', text:'Learn how to schedule post-op appointments in Symplast', note:'1-week and 2-week minimum. Know the appointment types.', done:false},
        {id:'po4', text:'Shadow a post-op visit with a breast patient', note:'Observe vitals, wound check, drain documentation, and patient education.', done:false},
        {id:'po5', text:'Shadow a post-op visit with a body procedure patient', note:'Tummy tuck, lipo, or mommy makeover. Note differences in wound care.', done:false},
        {id:'po6', text:'Learn how to import surgical charts and scan documents into Symplast', note:'', done:false},
        {id:'po7', text:'Learn the post-op instructions packet — what goes in it and how to print it', note:'Comprehensive packet + 24–48 hr guidelines + Dr. Piazza\'s note card.', done:false}
      ]
    },
    {
      id: 'frontdesk', title: 'Front Desk — Check-in & Check-out',
      steps: [
        {id:'fd1', text:'Learn how to pull up the daily schedule in Symplast', note:'Know where to find the patient list, appointment types, and any flags.', done:false},
        {id:'fd2', text:'Practice checking a patient in', note:'Verify name, DOB, insurance, update demographics, confirm appointment type.', done:false},
        {id:'fd3', text:'Practice checking a patient out', note:'Schedule follow-ups, confirm post-op dates, hand off printed materials.', done:false},
        {id:'fd4', text:'Learn how to book appointments in Symplast', note:'Consults, post-ops, pre-ops, and in-office procedures each have different types.', done:false},
        {id:'fd5', text:'Understand the flow for new consults vs. returning post-ops', note:'New consult = full intake, photos, sizing if breast. Post-op = vitals, wound check.', done:false}
      ]
    },
    {
      id: 'roomsetup', title: 'Room Setup Training',
      steps: [
        {id:'rs1', text:'Complete room setup independently (consult room)', note:'Lamp on, AirPlay connected, sizers wiped, tools in drawer, mirror wiped, orchid ready, frames straight, bin stocked, scale and BP cuff zeroed.', done:false},
        {id:'rs2', text:'Learn procedure tray setup for in-office cases', note:'Know what instruments go on the tray for each procedure type. Under nurse direction only.', done:false},
        {id:'rs3', text:'Learn local anesthetic draw-up process', note:'Dr. Piazza\'s formula. Less is more — never waste product. Label the syringe.', done:false},
        {id:'rs4', text:'Learn instrument sterilization and autoclave protocol', note:'Clean immediately after use. Run the autoclave cycle. Log each cycle.', done:false},
        {id:'rs5', text:'Practice room reset between patients', note:'Wipe sizers, restock bin, reset forms, re-check equipment.', done:false}
      ]
    },
    {
      id: 'comms', title: 'Types of Communication Training',
      steps: [
        {id:'c1', text:'Learn the internal communication / task system', note:'How to send notes to Dr. Piazza, the nurse, and front desk. Know the templates.', done:false},
        {id:'c2', text:'Learn how to send patient-facing messages from Symplast', note:'Prescription confirmations, appointment reminders, and follow-up instructions.', done:false},
        {id:'c3', text:'Understand what you can and cannot communicate to patients independently', note:'Clinical questions go to the nurse or Dr. Piazza. Scheduling you can handle.', done:false},
        {id:'c4', text:'Learn how to use the telemedicine platform for virtual visits', note:'Setting up the link, confirming the patient has it, and any in-room prep.', done:false},
        {id:'c5', text:'Learn how to communicate with the surgery center (ISC)', note:'What gets sent via Dropbox vs. email. Know Dr. Cady\'s role.', done:false}
      ]
    }
  ];

  function loadTraining() {
    var saved = localStorage.getItem(TR_KEY);
    return saved ? JSON.parse(saved) : JSON.parse(JSON.stringify(defaultSections));
  }

  function saveTraining(data) {
    localStorage.setItem(TR_KEY, JSON.stringify(data));
  }

  function uid() {
    return 's' + Math.random().toString(36).slice(2,9);
  }

  function renderTraining() {
    var data = loadTraining();
    var root = document.getElementById('training-root');
    root.innerHTML = '';

    data.forEach(function(section, si) {
      var done = section.steps.filter(s => s.done).length;
      var total = section.steps.length;

      var sg = document.createElement('div');
      sg.className = 'section-group';
      sg.style.marginBottom = '24px';

      // Section header row
      var hrow = document.createElement('div');
      hrow.style.cssText = 'display:flex;align-items:center;gap:10px;padding:10px 0 8px;border-bottom:1px solid var(--border);margin-bottom:4px;';

      var htitle = document.createElement('div');
      htitle.style.cssText = 'font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.07em;color:var(--text3);flex:1;';
      htitle.textContent = section.title;

      var hprog = document.createElement('span');
      hprog.style.cssText = 'font-size:11px;font-family:"DM Mono",monospace;color:var(--text3);';
      hprog.textContent = done + '/' + total;

      hrow.appendChild(htitle);
      hrow.appendChild(hprog);
      sg.appendChild(hrow);

      // Steps
      section.steps.forEach(function(step, stpi) {
        var item = document.createElement('div');
        item.className = 'check-item' + (step.done ? ' done' : '');
        item.style.cssText = 'display:flex;align-items:flex-start;gap:10px;padding:9px 0;border-bottom:1px solid var(--border);';

        var cb = document.createElement('input');
        cb.type = 'checkbox';
        cb.checked = step.done;
        cb.style.cssText = 'margin-top:2px;flex-shrink:0;accent-color:#0891b2;width:14px;height:14px;cursor:pointer;';
        cb.onchange = function() {
          var d = loadTraining();
          d[si].steps[stpi].done = cb.checked;
          saveTraining(d);
          renderTraining();
        };

        var body = document.createElement('div');
        body.style.cssText = 'flex:1;min-width:0;';

        // Editable title
        var titleEl = document.createElement('div');
        titleEl.contentEditable = 'true';
        titleEl.style.cssText = 'font-size:13px;font-weight:500;color:var(--text);outline:none;padding:1px 4px;margin:-1px -4px;border-radius:4px;cursor:text;' + (step.done ? 'text-decoration:line-through;opacity:.45;' : '');
        titleEl.textContent = step.text;
        titleEl.title = 'Click to edit';
        titleEl.onfocus = function() { this.style.background = 'var(--surface2)'; };
        titleEl.onblur = function() {
          this.style.background = '';
          var d = loadTraining();
          d[si].steps[stpi].text = this.textContent.trim();
          saveTraining(d);
        };

        // Editable note
        var noteEl = document.createElement('div');
        noteEl.contentEditable = 'true';
        noteEl.style.cssText = 'font-size:11px;color:var(--text3);margin-top:3px;outline:none;padding:1px 4px;margin-left:-4px;border-radius:4px;cursor:text;min-height:16px;line-height:1.5;' + (step.done ? 'opacity:.4;' : '');
        noteEl.textContent = step.note || '';
        noteEl.setAttribute('data-placeholder', 'Add a note...');
        noteEl.title = 'Click to edit note';
        noteEl.onfocus = function() { this.style.background = 'var(--surface2)'; };
        noteEl.onblur = function() {
          this.style.background = '';
          var d = loadTraining();
          d[si].steps[stpi].note = this.textContent.trim();
          saveTraining(d);
        };

        // Delete button
        var del = document.createElement('button');
        del.textContent = '×';
        del.title = 'Delete step';
        del.style.cssText = 'background:none;border:none;color:var(--text3);font-size:16px;cursor:pointer;padding:0 2px;flex-shrink:0;line-height:1;margin-top:0px;opacity:0;transition:opacity .15s;';
        item.onmouseenter = function() { del.style.opacity = '1'; };
        item.onmouseleave = function() { del.style.opacity = '0'; };
        del.onclick = function() {
          if (!confirm('Delete this step?')) return;
          var d = loadTraining();
          d[si].steps.splice(stpi, 1);
          saveTraining(d);
          renderTraining();
        };

        body.appendChild(titleEl);
        body.appendChild(noteEl);
        item.appendChild(cb);
        item.appendChild(body);
        item.appendChild(del);
        sg.appendChild(item);
      });

      // Add step button
      var addBtn = document.createElement('button');
      addBtn.style.cssText = 'display:flex;align-items:center;gap:6px;margin-top:10px;padding:6px 12px;border:1px dashed var(--border2);border-radius:var(--radius-sm);background:none;color:var(--text3);font-size:12px;font-family:"DM Sans",sans-serif;cursor:pointer;transition:color .12s,border-color .12s;';
      addBtn.innerHTML = '<span style="font-size:16px;line-height:1">+</span> Add step';
      addBtn.onmouseenter = function() { this.style.color='#0891b2'; this.style.borderColor='#0891b2'; };
      addBtn.onmouseleave = function() { this.style.color='var(--text3)'; this.style.borderColor='var(--border2)'; };
      addBtn.onclick = function() {
        var d = loadTraining();
        d[si].steps.push({ id: uid(), text: 'New step — click to edit', note: '', done: false });
        saveTraining(d);
        renderTraining();
      };

      sg.appendChild(addBtn);
      root.appendChild(sg);
    });

    // Add section button
    var addSecBtn = document.createElement('button');
    addSecBtn.style.cssText = 'display:flex;align-items:center;gap:8px;margin-top:8px;padding:10px 16px;border:1px dashed var(--border2);border-radius:var(--radius);background:none;color:var(--text3);font-size:13px;font-family:"DM Sans",sans-serif;cursor:pointer;width:100%;justify-content:center;transition:color .12s,border-color .12s;';
    addSecBtn.innerHTML = '<span style="font-size:18px;line-height:1">+</span> Add new training section';
    addSecBtn.onmouseenter = function() { this.style.color='#0891b2'; this.style.borderColor='#0891b2'; };
    addSecBtn.onmouseleave = function() { this.style.color='var(--text3)'; this.style.borderColor='var(--border2)'; };
    addSecBtn.onclick = function() {
      var title = prompt('Name for this training section:');
      if (!title) return;
      var d = loadTraining();
      d.push({ id: uid(), title: title.trim(), steps: [] });
      saveTraining(d);
      renderTraining();
    };
    root.appendChild(addSecBtn);
  }

  loadNotes();
  renderTraining();
</script>
</body>
</html>
