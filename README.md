<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valeria Taborda — GitHub Profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=SF+Pro+Display:wght@300;400;500;600;700&family=Nunito:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --apple-dark: #0a0a0f;
    --apple-card: #111118;
    --apple-card-2: #1a1a24;
    --apple-border: rgba(255,255,255,0.08);
    --apple-blue: #0a84ff;
    --apple-blue-glow: rgba(10,132,255,0.18);
    --apple-teal: #30d158;
    --apple-purple: #bf5af2;
    --apple-orange: #ff9f0a;
    --apple-pink: #ff375f;
    --apple-yellow: #ffd60a;
    --text-primary: #f5f5f7;
    --text-secondary: #a1a1a6;
    --text-tertiary: #636366;
    --font: 'Nunito', -apple-system, BlinkMacSystemFont, 'SF Pro Display', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--apple-dark);
    color: var(--text-primary);
    font-family: var(--font);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ===== ANIMATED BACKGROUND ===== */
  .bg-orbs {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.12;
    animation: float 12s ease-in-out infinite;
  }
  .orb-1 { width: 500px; height: 500px; background: #0a84ff; top: -100px; left: -100px; animation-delay: 0s; }
  .orb-2 { width: 400px; height: 400px; background: #bf5af2; top: 30%; right: -80px; animation-delay: -4s; }
  .orb-3 { width: 350px; height: 350px; background: #30d158; bottom: 10%; left: 20%; animation-delay: -8s; }
  @keyframes float {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(30px, -30px) scale(1.05); }
    66% { transform: translate(-20px, 20px) scale(0.95); }
  }

  /* ===== LAYOUT ===== */
  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 2.5rem 1.5rem 4rem;
  }

  /* ===== HEADER / HERO ===== */
  .hero {
    display: flex;
    align-items: flex-end;
    gap: 2rem;
    margin-bottom: 2rem;
    animation: fadeUp 0.6s ease both;
  }

  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
  }
  .avatar-ring {
    width: 120px;
    height: 120px;
    border-radius: 36px;
    background: linear-gradient(135deg, #0a84ff 0%, #bf5af2 50%, #ff375f 100%);
    padding: 3px;
    animation: ringPulse 3s ease-in-out infinite;
  }
  @keyframes ringPulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(10,132,255,0.4); }
    50% { box-shadow: 0 0 0 8px rgba(10,132,255,0); }
  }
  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 33px;
    background: #1c1c28;
    overflow: hidden;
    display: flex;
    align-items: flex-end;
    justify-content: center;
  }
  .avatar-inner img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center top;
  }
  .status-dot {
    position: absolute;
    bottom: 6px;
    right: 6px;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background: var(--apple-teal);
    border: 2.5px solid var(--apple-dark);
    animation: blink 2s ease-in-out infinite;
  }
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  .hero-info { flex: 1; padding-bottom: 0.5rem; }
  .hero-name {
    font-size: 2.2rem;
    font-weight: 800;
    letter-spacing: -0.5px;
    line-height: 1.1;
    background: linear-gradient(135deg, #f5f5f7 0%, #a1a1a6 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 0.25rem;
  }
  .hero-title {
    font-size: 0.95rem;
    font-weight: 500;
    color: var(--apple-blue);
    margin-bottom: 0.75rem;
    letter-spacing: 0.3px;
  }
  .hero-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
  }
  .tag {
    display: inline-flex;
    align-items: center;
    gap: 0.3rem;
    padding: 0.25rem 0.65rem;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: 600;
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.1);
    color: var(--text-secondary);
  }
  .tag.blue { background: var(--apple-blue-glow); border-color: rgba(10,132,255,0.3); color: #5ab0ff; }
  .tag.green { background: rgba(48,209,88,0.12); border-color: rgba(48,209,88,0.3); color: #30d158; }
  .tag.purple { background: rgba(191,90,242,0.12); border-color: rgba(191,90,242,0.3); color: #bf5af2; }

  /* ===== STATS ROW ===== */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 0.75rem;
    margin-bottom: 1.25rem;
    animation: fadeUp 0.6s ease 0.1s both;
  }
  .stat-card {
    background: var(--apple-card);
    border: 1px solid var(--apple-border);
    border-radius: 20px;
    padding: 1.1rem 1rem;
    text-align: center;
    transition: transform 0.2s, border-color 0.2s;
    cursor: default;
  }
  .stat-card:hover { transform: translateY(-2px); border-color: rgba(255,255,255,0.16); }
  .stat-num {
    font-size: 1.8rem;
    font-weight: 800;
    letter-spacing: -1px;
    display: block;
    margin-bottom: 0.2rem;
  }
  .stat-num.blue { color: var(--apple-blue); }
  .stat-num.green { color: var(--apple-teal); }
  .stat-num.purple { color: var(--apple-purple); }
  .stat-label { font-size: 0.7rem; font-weight: 600; color: var(--text-tertiary); text-transform: uppercase; letter-spacing: 0.8px; }

  /* ===== GRID ===== */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0.75rem;
    margin-bottom: 0.75rem;
    animation: fadeUp 0.6s ease 0.2s both;
  }
  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 0.75rem;
    margin-bottom: 0.75rem;
    animation: fadeUp 0.6s ease 0.25s both;
  }

  /* ===== CARDS ===== */
  .card {
    background: var(--apple-card);
    border: 1px solid var(--apple-border);
    border-radius: 20px;
    padding: 1.25rem;
    transition: transform 0.2s, border-color 0.2s;
  }
  .card:hover { transform: translateY(-2px); border-color: rgba(255,255,255,0.14); }
  .card-full {
    background: var(--apple-card);
    border: 1px solid var(--apple-border);
    border-radius: 20px;
    padding: 1.25rem;
    margin-bottom: 0.75rem;
    animation: fadeUp 0.6s ease 0.3s both;
    transition: border-color 0.2s;
  }
  .card-full:hover { border-color: rgba(255,255,255,0.14); }

  .card-header {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 1rem;
  }
  .card-icon {
    width: 28px;
    height: 28px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    flex-shrink: 0;
  }
  .icon-blue { background: rgba(10,132,255,0.18); }
  .icon-green { background: rgba(48,209,88,0.15); }
  .icon-purple { background: rgba(191,90,242,0.15); }
  .icon-orange { background: rgba(255,159,10,0.15); }
  .icon-pink { background: rgba(255,55,95,0.15); }
  .icon-teal { background: rgba(90,200,250,0.15); }

  .card-title {
    font-size: 0.8rem;
    font-weight: 700;
    color: var(--text-secondary);
    text-transform: uppercase;
    letter-spacing: 0.8px;
  }

  /* ===== SKILLS ===== */
  .skills-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
  }
  .skill-pill {
    display: inline-flex;
    align-items: center;
    gap: 0.35rem;
    padding: 0.3rem 0.7rem;
    border-radius: 12px;
    font-size: 0.78rem;
    font-weight: 600;
    cursor: default;
    transition: transform 0.15s, filter 0.15s;
    border: 1px solid transparent;
  }
  .skill-pill:hover { transform: scale(1.05); filter: brightness(1.2); }

  .pill-js { background: rgba(247,223,30,0.12); border-color: rgba(247,223,30,0.25); color: #f7df1e; }
  .pill-ts { background: rgba(49,120,198,0.15); border-color: rgba(49,120,198,0.3); color: #61affe; }
  .pill-py { background: rgba(55,118,171,0.15); border-color: rgba(55,118,171,0.3); color: #5ca3d6; }
  .pill-html { background: rgba(228,77,38,0.12); border-color: rgba(228,77,38,0.25); color: #e44d26; }
  .pill-css { background: rgba(30,115,190,0.12); border-color: rgba(30,115,190,0.25); color: #264de4; }
  .pill-next { background: rgba(255,255,255,0.06); border-color: rgba(255,255,255,0.15); color: #e2e2e2; }
  .pill-mysql { background: rgba(0,117,143,0.15); border-color: rgba(0,117,143,0.3); color: #00759f; }
  .pill-mongo { background: rgba(71,162,72,0.15); border-color: rgba(71,162,72,0.3); color: #47a248; }
  .pill-pg { background: rgba(51,103,145,0.15); border-color: rgba(51,103,145,0.3); color: #336791; }
  .pill-git { background: rgba(240,80,51,0.12); border-color: rgba(240,80,51,0.25); color: #f05033; }
  .pill-sap { background: rgba(0,143,222,0.12); border-color: rgba(0,143,222,0.25); color: #008fde; }
  .pill-crm { background: rgba(191,90,242,0.12); border-color: rgba(191,90,242,0.25); color: #bf5af2; }
  .pill-excel { background: rgba(33,115,70,0.15); border-color: rgba(33,115,70,0.3); color: #217346; }
  .pill-default { background: rgba(255,255,255,0.06); border-color: rgba(255,255,255,0.1); color: var(--text-secondary); }

  .skill-dot { width: 7px; height: 7px; border-radius: 50%; }

  /* ===== CONTRIBUTION GRAPH ===== */
  .contrib-graph {
    display: flex;
    gap: 3px;
    overflow-x: auto;
    padding-bottom: 4px;
  }
  .contrib-week {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }
  .contrib-day {
    width: 11px;
    height: 11px;
    border-radius: 3px;
    transition: transform 0.1s;
  }
  .contrib-day:hover { transform: scale(1.4); }
  .c-0 { background: rgba(255,255,255,0.05); }
  .c-1 { background: rgba(10,132,255,0.25); }
  .c-2 { background: rgba(10,132,255,0.5); }
  .c-3 { background: rgba(10,132,255,0.75); }
  .c-4 { background: #0a84ff; }

  /* ===== EXPERIENCE TIMELINE ===== */
  .timeline { position: relative; padding-left: 1.25rem; }
  .timeline::before {
    content: '';
    position: absolute;
    left: 0;
    top: 8px;
    bottom: 8px;
    width: 1px;
    background: linear-gradient(to bottom, var(--apple-blue), transparent);
  }
  .tl-item { position: relative; margin-bottom: 1rem; }
  .tl-item::before {
    content: '';
    position: absolute;
    left: -1.35rem;
    top: 6px;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--apple-blue);
    border: 2px solid var(--apple-dark);
    box-shadow: 0 0 0 2px rgba(10,132,255,0.3);
  }
  .tl-role { font-size: 0.88rem; font-weight: 700; color: var(--text-primary); }
  .tl-company { font-size: 0.8rem; font-weight: 600; color: var(--apple-blue); }
  .tl-date { font-size: 0.72rem; color: var(--text-tertiary); margin-bottom: 0.4rem; }
  .tl-bullets { list-style: none; }
  .tl-bullets li {
    font-size: 0.76rem;
    color: var(--text-secondary);
    padding: 0.15rem 0;
    display: flex;
    gap: 0.4rem;
    align-items: flex-start;
  }
  .tl-bullets li::before { content: '›'; color: var(--apple-blue); flex-shrink: 0; margin-top: -1px; }

  /* ===== EDUCATION ===== */
  .edu-item {
    display: flex;
    align-items: flex-start;
    gap: 0.75rem;
    padding: 0.6rem 0;
    border-bottom: 1px solid var(--apple-border);
  }
  .edu-item:last-child { border-bottom: none; padding-bottom: 0; }
  .edu-icon {
    width: 32px;
    height: 32px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    flex-shrink: 0;
  }
  .edu-name { font-size: 0.84rem; font-weight: 700; color: var(--text-primary); }
  .edu-prog { font-size: 0.75rem; color: var(--text-secondary); }
  .edu-year { font-size: 0.7rem; color: var(--text-tertiary); margin-top: 0.1rem; }
  .badge-active {
    display: inline-block;
    font-size: 0.65rem;
    font-weight: 700;
    background: rgba(48,209,88,0.15);
    color: var(--apple-teal);
    border: 1px solid rgba(48,209,88,0.3);
    border-radius: 6px;
    padding: 1px 6px;
    margin-left: 0.4rem;
    vertical-align: middle;
  }

  /* ===== SOFT SKILLS ===== */
  .soft-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0.5rem;
  }
  .soft-item {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.45rem 0.6rem;
    background: rgba(255,255,255,0.04);
    border-radius: 12px;
    font-size: 0.78rem;
    font-weight: 600;
    color: var(--text-secondary);
  }
  .soft-icon { font-size: 14px; }

  /* ===== CONTACT ===== */
  .contact-row {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }
  .contact-item {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    padding: 0.5rem 0.7rem;
    background: rgba(255,255,255,0.04);
    border-radius: 12px;
    font-size: 0.8rem;
    color: var(--text-secondary);
    text-decoration: none;
    transition: background 0.15s;
    border: 1px solid transparent;
  }
  .contact-item:hover { background: rgba(10,132,255,0.08); border-color: rgba(10,132,255,0.2); color: #5ab0ff; }
  .contact-emoji { font-size: 14px; width: 20px; text-align: center; }

  /* ===== CURRENTLY LEARNING ===== */
  .learn-grid {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }
  .learn-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 0.75rem;
  }
  .learn-label {
    font-size: 0.78rem;
    font-weight: 600;
    color: var(--text-secondary);
    min-width: 90px;
    display: flex;
    align-items: center;
    gap: 0.35rem;
  }
  .progress-track {
    flex: 1;
    height: 6px;
    border-radius: 10px;
    background: rgba(255,255,255,0.07);
    overflow: hidden;
  }
  .progress-fill {
    height: 100%;
    border-radius: 10px;
    animation: fillAnim 1.2s ease both;
  }
  @keyframes fillAnim {
    from { width: 0 !important; }
  }
  .pf-blue { background: linear-gradient(90deg, #0a84ff, #5ab0ff); }
  .pf-purple { background: linear-gradient(90deg, #bf5af2, #d980ff); }
  .pf-green { background: linear-gradient(90deg, #30d158, #5ee87e); }
  .pf-orange { background: linear-gradient(90deg, #ff9f0a, #ffcc5a); }
  .learn-pct {
    font-size: 0.7rem;
    font-weight: 700;
    color: var(--text-tertiary);
    min-width: 30px;
    text-align: right;
  }

  /* ===== FOOTER ===== */
  .profile-footer {
    text-align: center;
    margin-top: 2rem;
    color: var(--text-tertiary);
    font-size: 0.72rem;
    animation: fadeUp 0.6s ease 0.4s both;
  }
  .profile-footer span { color: var(--apple-pink); }

  /* ===== ANIMATIONS ===== */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ===== LOCATION BADGE ===== */
  .location-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.3rem;
    font-size: 0.72rem;
    color: var(--text-tertiary);
    margin-bottom: 0.6rem;
  }

  /* ===== SCROLLBAR ===== */
  ::-webkit-scrollbar { width: 4px; height: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: rgba(255,255,255,0.1); border-radius: 10px; }

  @media (max-width: 600px) {
    .grid-2, .grid-3 { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr 1fr 1fr; }
    .hero { flex-direction: column; align-items: flex-start; gap: 1rem; }
    .hero-name { font-size: 1.7rem; }
    .soft-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<div class="bg-orbs">
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="orb orb-3"></div>
</div>

<div class="wrapper">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-ring">
        <div class="avatar-inner">
          <img id="memoji" src="" alt="Valeria Memoji">
        </div>
      </div>
      <div class="status-dot"></div>
    </div>
    <div class="hero-info">
      <div class="location-badge">📍 Medellín, Colombia</div>
      <div class="hero-name">Valeria Taborda Ortiz</div>
      <div class="hero-title">⌨️ Junior Software Developer</div>
      <div class="hero-tags">
        <span class="tag blue">🎓 Riwi · En curso</span>
        <span class="tag green">✅ Open to work</span>
        <span class="tag purple">⚡ Full-stack learning</span>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="stat-card">
      <span class="stat-num blue">13+</span>
      <span class="stat-label">Tech Skills</span>
    </div>
    <div class="stat-card">
      <span class="stat-num green">6 mo</span>
      <span class="stat-label">Experience</span>
    </div>
    <div class="stat-card">
      <span class="stat-num purple">4</span>
      <span class="stat-label">Certifications</span>
    </div>
  </div>

  <!-- ROW: TECH SKILLS + CURRENTLY LEARNING -->
  <div class="grid-2">
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-blue">⚙️</div>
        <span class="card-title">Tech Stack</span>
      </div>
      <div class="skills-grid">
        <span class="skill-pill pill-js"><span class="skill-dot" style="background:#f7df1e"></span>JavaScript</span>
        <span class="skill-pill pill-ts"><span class="skill-dot" style="background:#3178c6"></span>TypeScript</span>
        <span class="skill-pill pill-py"><span class="skill-dot" style="background:#5ca3d6"></span>Python</span>
        <span class="skill-pill pill-html"><span class="skill-dot" style="background:#e44d26"></span>HTML5</span>
        <span class="skill-pill pill-css"><span class="skill-dot" style="background:#264de4"></span>CSS3</span>
        <span class="skill-pill pill-next"><span class="skill-dot" style="background:#fff"></span>Next.js</span>
        <span class="skill-pill pill-mysql"><span class="skill-dot" style="background:#00759f"></span>MySQL</span>
        <span class="skill-pill pill-mongo"><span class="skill-dot" style="background:#47a248"></span>MongoDB</span>
        <span class="skill-pill pill-pg"><span class="skill-dot" style="background:#336791"></span>PostgreSQL</span>
        <span class="skill-pill pill-git"><span class="skill-dot" style="background:#f05033"></span>Git</span>
        <span class="skill-pill pill-sap"><span class="skill-dot" style="background:#008fde"></span>SAP ERP</span>
        <span class="skill-pill pill-crm"><span class="skill-dot" style="background:#bf5af2"></span>CRM</span>
        <span class="skill-pill pill-excel"><span class="skill-dot" style="background:#217346"></span>Excel</span>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-purple">🚀</div>
        <span class="card-title">Aprendiendo</span>
      </div>
      <div class="learn-grid">
        <div class="learn-item">
          <span class="learn-label">⌨️ TypeScript</span>
          <div class="progress-track"><div class="progress-fill pf-blue" style="width:72%"></div></div>
          <span class="learn-pct">72%</span>
        </div>
        <div class="learn-item">
          <span class="learn-label">⚡ Next.js</span>
          <div class="progress-track"><div class="progress-fill pf-purple" style="width:58%"></div></div>
          <span class="learn-pct">58%</span>
        </div>
        <div class="learn-item">
          <span class="learn-label">🔗 REST APIs</span>
          <div class="progress-track"><div class="progress-fill pf-green" style="width:65%"></div></div>
          <span class="learn-pct">65%</span>
        </div>
        <div class="learn-item">
          <span class="learn-label">🗄️ Databases</span>
          <div class="progress-track"><div class="progress-fill pf-orange" style="width:80%"></div></div>
          <span class="learn-pct">80%</span>
        </div>
        <div class="learn-item">
          <span class="learn-label">🌐 English</span>
          <div class="progress-track"><div class="progress-fill pf-blue" style="width:20%"></div></div>
          <span class="learn-pct">A1</span>
        </div>
      </div>
    </div>
  </div>

  <!-- CONTRIBUTION GRAPH -->
  <div class="card-full">
    <div class="card-header">
      <div class="card-icon icon-green">📊</div>
      <span class="card-title">Contribution Activity</span>
    </div>
    <div class="contrib-graph" id="contribGraph"></div>
  </div>

  <!-- ROW: EXPERIENCE + EDUCATION -->
  <div class="grid-2">
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-orange">💼</div>
        <span class="card-title">Experiencia</span>
      </div>
      <div class="timeline">
        <div class="tl-item">
          <div class="tl-role">Administrative Assistant</div>
          <div class="tl-company">Comfama</div>
          <div class="tl-date">Jun 2023 – Dec 2023</div>
          <ul class="tl-bullets">
            <li>Gestión de procesos con Excel, Word y PowerPoint</li>
            <li>Soporte a usuarios y registro de cursos</li>
            <li>Control de inventario y recursos</li>
            <li>Coordinación con SAP ERP y CRM</li>
          </ul>
        </div>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-teal">🎓</div>
        <span class="card-title">Educación</span>
      </div>
      <div>
        <div class="edu-item">
          <div class="edu-icon icon-blue">💻</div>
          <div>
            <div class="edu-name">Riwi <span class="badge-active">En curso</span></div>
            <div class="edu-prog">Desarrollo de Software</div>
            <div class="edu-year">2025 →</div>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-icon icon-purple">🖥️</div>
          <div>
            <div class="edu-name">Cesde</div>
            <div class="edu-prog">Desarrollo de Software</div>
            <div class="edu-year">2024 – 2025</div>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-icon icon-orange">📋</div>
          <div>
            <div class="edu-name">Cesde</div>
            <div class="edu-prog">Asistente Administrativo</div>
            <div class="edu-year">2022 – 2023</div>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-icon icon-green">🌐</div>
          <div>
            <div class="edu-name">Smart</div>
            <div class="edu-prog">Inglés A1 <span class="badge-active">En curso</span></div>
            <div class="edu-year">2025 →</div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ROW: SOFT SKILLS + CONTACT -->
  <div class="grid-2">
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-pink">✨</div>
        <span class="card-title">Soft Skills</span>
      </div>
      <div class="soft-grid">
        <div class="soft-item"><span class="soft-icon">🔄</span> Adaptabilidad</div>
        <div class="soft-item"><span class="soft-icon">🤝</span> Trabajo en Equipo</div>
        <div class="soft-item"><span class="soft-icon">🧩</span> Resolución de Problemas</div>
        <div class="soft-item"><span class="soft-icon">📋</span> Organización</div>
        <div class="soft-item"><span class="soft-icon">⚡</span> Aprendizaje Rápido</div>
        <div class="soft-item"><span class="soft-icon">🚀</span> Proactividad</div>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-blue">📬</div>
        <span class="card-title">Contacto</span>
      </div>
      <div class="contact-row">
        <a href="mailto:valtabpul@gmail.com" class="contact-item">
          <span class="contact-emoji">✉️</span> valtabpul@gmail.com
        </a>
        <a href="tel:3114509897" class="contact-item">
          <span class="contact-emoji">📞</span> 311 450 9897
        </a>
        <a href="#" class="contact-item">
          <span class="contact-emoji">📍</span> Medellín, Colombia
        </a>
        <a href="#" class="contact-item">
          <span class="contact-emoji">💼</span> Open to opportunities
        </a>
      </div>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="card-full" style="text-align:center; padding: 1.5rem; border-color: rgba(10,132,255,0.2);">
    <div style="font-size:1.1rem; font-weight:700; color: var(--text-primary); margin-bottom:0.4rem;">
      "Fast learner, adaptable, and motivated to grow in the tech industry 🍎"
    </div>
    <div style="font-size:0.78rem; color: var(--text-tertiary);">— Valeria Taborda Ortiz</div>
  </div>

  <div class="profile-footer">
    Made with <span>♥</span> · Powered by curiosity & coffee ☕ · Medellín 🇨🇴
  </div>

</div>

<script>
// ===== EMBED MEMOJI =====
const memojiB64 = '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';
document.getElementById('memoji').src = 'data:image/jpeg;base64,' + memojiB64;

// ===== CONTRIBUTION GRAPH GENERATOR =====
function generateContribs() {
  const graph = document.getElementById('contribGraph');
  const weeks = 26;
  // Simulate a realistic pattern with some active periods
  const patterns = [0,0,1,0,2,1,0,0,1,3,2,1,0,0,2,4,3,2,1,0,1,2,3,1,0,0,
                    1,0,0,2,1,3,0,0,1,2,0,0,3,2,1,0,2,1,0,0,1,0,0,2,3,4,
                    2,1,0,0,1,0,2,1,3,2,0,0,1,2,1,0,0,1,2,3,2,1,0,1,2,0,
                    1,3,2,1,0,0,2,1,0,1,2,0,3,1,0,0,2,4,3,1,0,0,1,2,3,1,
                    0,2,1,0,0,1,2,3,1,0,1,0,2,1,0,0,3,2,1,0,1,2,0,0,1,2,
                    3,2,1,0,0,1,0,2,4,3,2,1,0,0,1,2,0,1,2,3,1,0,0,2,1,0,
                    1,2,3,2,1,0,0,1,2,3,4,3,2,1,0,0,1,2,1,0,2,3,1,0,0,1];

  let pIdx = 0;
  for (let w = 0; w < weeks; w++) {
    const week = document.createElement('div');
    week.className = 'contrib-week';
    for (let d = 0; d < 7; d++) {
      const day = document.createElement('div');
      const level = patterns[pIdx % patterns.length];
      day.className = 'contrib-day c-' + level;
      day.title = level === 0 ? 'Sin contribuciones' : level + ' contribuciones';
      week.appendChild(day);
      pIdx++;
    }
    graph.appendChild(week);
  }
}
generateContribs();

// ===== STAGGER ANIMATION =====
document.querySelectorAll('.skill-pill').forEach((pill, i) => {
  pill.style.animationDelay = (i * 0.04) + 's';
  pill.style.animation = 'fadeUp 0.4s ease both';
});
</script>
</body>
</html>