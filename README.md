<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sujeet Atwe – GitHub Profile README</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Sora:wght@300;400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0c10;
    --surface: #0d1117;
    --card: #161b22;
    --border: #21262d;
    --accent: #00d4aa;
    --accent2: #7c3aed;
    --accent3: #f59e0b;
    --text: #e6edf3;
    --muted: #8b949e;
    --glow: rgba(0,212,170,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Sora', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,170,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,170,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 60px 0 48px;
    position: relative;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: 0; left: 50%; transform: translateX(-50%);
    width: 500px; height: 300px;
    background: radial-gradient(ellipse, rgba(0,212,170,0.12) 0%, transparent 70%);
    pointer-events: none;
  }

  .avatar-ring {
    display: inline-block;
    width: 110px; height: 110px;
    border-radius: 50%;
    padding: 3px;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3));
    margin-bottom: 24px;
    animation: spin-slow 8s linear infinite;
  }

  @keyframes spin-slow {
    from { filter: hue-rotate(0deg); }
    to   { filter: hue-rotate(360deg); }
  }

  .avatar-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: var(--card);
    display: flex; align-items: center; justify-content: center;
    font-size: 48px;
  }

  .hero h1 {
    font-family: 'Sora', sans-serif;
    font-weight: 800;
    font-size: clamp(2rem, 5vw, 3rem);
    letter-spacing: -1.5px;
    margin-bottom: 8px;
  }

  .hero h1 span { color: var(--accent); }

  .tagline {
    font-size: 1rem;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    margin-bottom: 20px;
    letter-spacing: 0.5px;
  }

  .tagline span {
    color: var(--accent);
  }

  .bio {
    max-width: 560px;
    margin: 0 auto 28px;
    font-size: 0.95rem;
    color: var(--muted);
    line-height: 1.7;
  }

  /* Badges row */
  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-bottom: 32px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 999px;
    font-size: 0.75rem;
    font-family: 'Space Mono', monospace;
    font-weight: 700;
    letter-spacing: 0.5px;
    border: 1px solid;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .badge:hover { transform: translateY(-2px); }

  .badge-green  { background: rgba(0,212,170,0.1);  border-color: rgba(0,212,170,0.3);  color: var(--accent); }
  .badge-purple { background: rgba(124,58,237,0.1); border-color: rgba(124,58,237,0.3); color: #a78bfa; }
  .badge-amber  { background: rgba(245,158,11,0.1); border-color: rgba(245,158,11,0.3); color: var(--accent3); }
  .badge-blue   { background: rgba(59,130,246,0.1); border-color: rgba(59,130,246,0.3); color: #60a5fa; }

  /* Profile Views */
  .profile-views {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 10px 20px;
    margin-bottom: 40px;
    font-family: 'Space Mono', monospace;
    font-size: 0.8rem;
  }

  .views-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%,100% { box-shadow: 0 0 0 0 rgba(0,212,170,0.4); }
    50%      { box-shadow: 0 0 0 6px rgba(0,212,170,0); }
  }

  .views-label { color: var(--muted); }
  .views-count { color: var(--accent); font-weight: 700; font-size: 1rem; }

  /* ── SECTION ── */
  .section {
    margin-bottom: 56px;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  .section-title {
    font-family: 'Space Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* ── TECH STACK GRID ── */
  .tech-categories {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(170px, 1fr));
    gap: 16px;
  }

  .tech-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px 16px;
    transition: border-color 0.3s, transform 0.2s, box-shadow 0.3s;
    cursor: default;
  }

  .tech-card:hover {
    border-color: var(--accent);
    transform: translateY(-3px);
    box-shadow: 0 8px 30px rgba(0,212,170,0.1);
  }

  .tech-card-icon { font-size: 1.5rem; margin-bottom: 10px; }
  .tech-card-cat {
    font-size: 0.65rem;
    font-family: 'Space Mono', monospace;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 12px;
  }

  .tech-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
  }

  .pill {
    font-size: 0.7rem;
    padding: 3px 8px;
    border-radius: 6px;
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    color: var(--muted);
    font-family: 'Space Mono', monospace;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
    gap: 20px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.2s, box-shadow 0.3s;
  }

  .project-card:hover {
    border-color: var(--accent);
    transform: translateY(-4px);
    box-shadow: 0 12px 40px rgba(0,212,170,0.08);
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    opacity: 0;
    transition: opacity 0.3s;
  }
  .project-card:hover::before { opacity: 1; }

  .project-emoji { font-size: 1.8rem; margin-bottom: 12px; display: block; }

  .project-name {
    font-size: 1rem;
    font-weight: 700;
    margin-bottom: 8px;
    color: var(--text);
  }

  .project-desc {
    font-size: 0.82rem;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 16px;
  }

  .project-features {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 4px;
    margin-bottom: 16px;
  }

  .project-features li {
    font-size: 0.78rem;
    color: var(--muted);
    padding-left: 14px;
    position: relative;
  }

  .project-features li::before {
    content: '›';
    position: absolute;
    left: 0;
    color: var(--accent);
    font-weight: 700;
  }

  .tech-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tech-tag {
    font-size: 0.68rem;
    font-family: 'Space Mono', monospace;
    padding: 3px 9px;
    border-radius: 6px;
    background: rgba(0,212,170,0.08);
    border: 1px solid rgba(0,212,170,0.2);
    color: var(--accent);
  }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
    margin-bottom: 32px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px;
    text-align: center;
    transition: border-color 0.3s, transform 0.2s;
  }

  .stat-card:hover {
    border-color: rgba(0,212,170,0.4);
    transform: translateY(-2px);
  }

  .stat-num {
    font-family: 'Space Mono', monospace;
    font-size: 1.6rem;
    font-weight: 700;
    color: var(--accent);
    margin-bottom: 6px;
  }

  .stat-label {
    font-size: 0.75rem;
    color: var(--muted);
    letter-spacing: 0.5px;
  }

  /* GitHub graph placeholder */
  .gh-graph {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
    margin-bottom: 20px;
    overflow: hidden;
  }

  .gh-graph-title {
    font-family: 'Space Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 16px;
  }

  .graph-grid {
    display: flex;
    gap: 3px;
  }

  .graph-col {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }

  .graph-cell {
    width: 13px;
    height: 13px;
    border-radius: 3px;
    background: var(--border);
    transition: transform 0.15s;
  }

  .graph-cell:hover { transform: scale(1.3); }

  .c0 { background: #161b22; }
  .c1 { background: #0e4429; }
  .c2 { background: #006d32; }
  .c3 { background: #26a641; }
  .c4 { background: var(--accent); }

  /* ── CONNECT ── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 14px;
  }

  .connect-card {
    display: flex;
    align-items: center;
    gap: 12px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px;
    text-decoration: none;
    color: var(--text);
    transition: border-color 0.3s, transform 0.2s, box-shadow 0.3s;
  }

  .connect-card:hover {
    border-color: var(--accent);
    transform: translateY(-2px);
    box-shadow: 0 6px 24px rgba(0,212,170,0.1);
    color: var(--accent);
  }

  .connect-icon {
    width: 38px; height: 38px;
    border-radius: 10px;
    background: rgba(0,212,170,0.08);
    border: 1px solid rgba(0,212,170,0.15);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }

  .connect-label {
    font-size: 0.7rem;
    font-family: 'Space Mono', monospace;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 3px;
  }

  .connect-value {
    font-size: 0.85rem;
    font-weight: 600;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 40px 0 0;
    border-top: 1px solid var(--border);
  }

  .footer-quote {
    font-family: 'Space Mono', monospace;
    font-size: 0.8rem;
    color: var(--muted);
    line-height: 1.8;
  }

  .footer-quote span { color: var(--accent); }

  /* FOCUS LIST */
  .focus-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 12px;
  }

  .focus-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent);
    border-radius: 10px;
    padding: 14px 16px;
    font-size: 0.82rem;
    color: var(--text);
    transition: transform 0.2s, box-shadow 0.2s;
  }

  .focus-item:hover {
    transform: translateX(3px);
    box-shadow: 4px 0 16px rgba(0,212,170,0.08);
  }

  .focus-item span {
    display: block;
    font-size: 1rem;
    margin-bottom: 4px;
  }

  /* scroll reveal */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  .reveal { animation: fadeUp 0.6s ease forwards; }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.4s; }

  @media (max-width: 600px) {
    .projects-grid { grid-template-columns: 1fr; }
    .hero h1 { font-size: 1.8rem; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- ── HERO ── -->
  <section class="hero reveal">
    <div class="avatar-ring">
      <div class="avatar-inner">👨‍💻</div>
    </div>
    <h1>Hi 👋 I'm <span>Sujeet Atwe</span></h1>
    <p class="tagline">$ <span>Full Stack</span> &amp; <span>AI Developer</span> → building what matters</p>
    <p class="bio">
      I build scalable full-stack applications, enterprise platforms, and AI-powered systems
      focused on solving real-world business problems.
    </p>

    <div class="badges">
      <span class="badge badge-green">⚡ Open to Work</span>
      <span class="badge badge-purple">🤖 AI Builder</span>
      <span class="badge badge-amber">🏗️ Full Stack</span>
      <span class="badge badge-blue">📍 Pune, India</span>
    </div>

    <!-- Profile View Counter (uses komarev badge via img tag — valid & live) -->
    <div class="profile-views">
      <div class="views-dot"></div>
      <span class="views-label">Profile Views</span>
      <img
        src="https://komarev.com/ghpvc/?username=Sujeetatwe&style=flat-square&color=00d4aa&label="
        alt="Profile views"
        style="height:22px; border-radius:4px;"
        onerror="this.style.display='none'; document.getElementById('fallback-count').style.display='flex';"
      />
      <span id="fallback-count" style="display:none; color: var(--accent); font-weight:700; font-family:'Space Mono',monospace;">Counting...</span>
    </div>
  </section>

  <!-- ── TECH STACK ── -->
  <section class="section reveal delay-1">
    <div class="section-header">
      <span class="section-title">Tech Stack</span>
      <div class="section-line"></div>
    </div>
    <div class="tech-categories">
      <div class="tech-card">
        <div class="tech-card-icon">🎨</div>
        <div class="tech-card-cat">Frontend</div>
        <div class="tech-pills">
          <span class="pill">React.js</span>
          <span class="pill">Next.js</span>
          <span class="pill">Tailwind</span>
          <span class="pill">JS ES6+</span>
          <span class="pill">HTML5</span>
          <span class="pill">CSS3</span>
        </div>
      </div>
      <div class="tech-card">
        <div class="tech-card-icon">⚙️</div>
        <div class="tech-card-cat">Backend</div>
        <div class="tech-pills">
          <span class="pill">Node.js</span>
          <span class="pill">Express</span>
          <span class="pill">Laravel</span>
          <span class="pill">PHP</span>
          <span class="pill">Spring Boot</span>
        </div>
      </div>
      <div class="tech-card">
        <div class="tech-card-icon">🗄️</div>
        <div class="tech-card-cat">Database</div>
        <div class="tech-pills">
          <span class="pill">MongoDB</span>
          <span class="pill">MySQL</span>
          <span class="pill">PostgreSQL</span>
        </div>
      </div>
      <div class="tech-card">
        <div class="tech-card-icon">🤖</div>
        <div class="tech-card-cat">AI / ML</div>
        <div class="tech-pills">
          <span class="pill">Python</span>
          <span class="pill">Scikit-learn</span>
          <span class="pill">NLP</span>
          <span class="pill">Flask</span>
          <span class="pill">Gemini AI</span>
        </div>
      </div>
      <div class="tech-card">
        <div class="tech-card-icon">🛠️</div>
        <div class="tech-card-cat">Tools</div>
        <div class="tech-pills">
          <span class="pill">Git</span>
          <span class="pill">REST APIs</span>
          <span class="pill">JWT</span>
          <span class="pill">RBAC</span>
          <span class="pill">Vite</span>
          <span class="pill">Postman</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ── GITHUB ACTIVITY ── -->
  <section class="section reveal delay-2">
    <div class="section-header">
      <span class="section-title">GitHub Stats</span>
      <div class="section-line"></div>
    </div>

    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-num" id="repos">—</div>
        <div class="stat-label">Public Repositories</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">5+</div>
        <div class="stat-label">Featured Projects</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">3+</div>
        <div class="stat-label">Years Experience</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">10+</div>
        <div class="stat-label">Tech Mastered</div>
      </div>
    </div>

    <!-- GitHub Stats Cards via readme-stats -->
    <div style="display:flex; flex-wrap:wrap; gap:14px; justify-content:center; margin-bottom:16px;">
      <img
        src="https://github-readme-stats.vercel.app/api?username=Sujeetatwe&show_icons=true&theme=dark&bg_color=0d1117&border_color=21262d&icon_color=00d4aa&title_color=00d4aa&text_color=8b949e"
        alt="GitHub Stats"
        style="border-radius:12px; max-width:100%; height:auto;"
        onerror="this.parentElement.style.display='none';"
      />
      <img
        src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sujeetatwe&layout=compact&theme=dark&bg_color=0d1117&border_color=21262d&title_color=00d4aa&text_color=8b949e"
        alt="Top Languages"
        style="border-radius:12px; max-width:100%; height:auto;"
        onerror="this.parentElement.style.display='none';"
      />
    </div>

    <!-- Contribution streak -->
    <div style="text-align:center;">
      <img
        src="https://github-readme-streak-stats.herokuapp.com/?user=Sujeetatwe&theme=dark&background=0d1117&border=21262d&ring=00d4aa&fire=f59e0b&currStreakLabel=00d4aa"
        alt="GitHub Streak"
        style="border-radius:12px; max-width:100%; height:auto;"
        onerror="this.style.display='none';"
      />
    </div>
  </section>

  <!-- ── FEATURED PROJECTS ── -->
  <section class="section reveal delay-2">
    <div class="section-header">
      <span class="section-title">Featured Projects</span>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">

      <div class="project-card">
        <span class="project-emoji">🍽️</span>
        <div class="project-name">QR Restaurant Ordering System</div>
        <div class="project-desc">QR-Based Restaurant Ordering Platform with real-time order management across multiple dashboards.</div>
        <ul class="project-features">
          <li>Admin, Kitchen &amp; Waiter Dashboards</li>
          <li>Customer Ordering via QR Code</li>
          <li>Real-Time Order Tracking</li>
          <li>Online Payment Integration</li>
        </ul>
        <div class="tech-tags">
          <span class="tech-tag">Laravel</span>
          <span class="tech-tag">PHP</span>
          <span class="tech-tag">MySQL</span>
          <span class="tech-tag">QR System</span>
        </div>
      </div>

      <div class="project-card">
        <span class="project-emoji">🤖</span>
        <div class="project-name">VerifiAI – Fake News Detection</div>
        <div class="project-desc">AI-powered platform that detects fake news using Machine Learning, NLP, and real-time credibility analysis.</div>
        <ul class="project-features">
          <li>ML-Powered Classification</li>
          <li>NLP Text Analysis</li>
          <li>Gemini AI Integration</li>
          <li>Real-Time Credibility Score</li>
        </ul>
        <div class="tech-tags">
          <span class="tech-tag">Python</span>
          <span class="tech-tag">Flask</span>
          <span class="tech-tag">Scikit-learn</span>
          <span class="tech-tag">Express.js</span>
          <span class="tech-tag">MySQL</span>
        </div>
      </div>

      <div class="project-card">
        <span class="project-emoji">🏢</span>
        <div class="project-name">Enterprise Task Management</div>
        <div class="project-desc">Customized recruitment workflow management system with multi-level dashboards and access control.</div>
        <ul class="project-features">
          <li>Candidate Tracking System</li>
          <li>Role-Based Access Control</li>
          <li>Team Collaboration Tools</li>
          <li>Reporting &amp; Analytics</li>
        </ul>
        <div class="tech-tags">
          <span class="tech-tag">Laravel</span>
          <span class="tech-tag">JWT</span>
          <span class="tech-tag">MySQL</span>
          <span class="tech-tag">Tailwind CSS</span>
        </div>
      </div>

      <div class="project-card">
        <span class="project-emoji">🎯</span>
        <div class="project-name">Lucky Draw Management System</div>
        <div class="project-desc">Web-based lucky draw platform with participant registration, random token generation, and winner selection.</div>
        <ul class="project-features">
          <li>Participant Registration</li>
          <li>Random Token Generation</li>
          <li>Winner Selection Engine</li>
          <li>Admin Dashboard</li>
        </ul>
        <div class="tech-tags">
          <span class="tech-tag">PHP</span>
          <span class="tech-tag">Laravel</span>
          <span class="tech-tag">MySQL</span>
        </div>
      </div>

      <div class="project-card">
        <span class="project-emoji">📰</span>
        <div class="project-name">News Blog Platform</div>
        <div class="project-desc">Modern full-stack publishing platform with article management, CMS dashboard, and responsive UI.</div>
        <ul class="project-features">
          <li>Article Publishing System</li>
          <li>Category Management</li>
          <li>Authentication System</li>
          <li>Admin CMS Dashboard</li>
        </ul>
        <div class="tech-tags">
          <span class="tech-tag">MERN</span>
          <span class="tech-tag">Laravel</span>
          <span class="tech-tag">MySQL</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ── CURRENT FOCUS ── -->
  <section class="section reveal delay-3">
    <div class="section-header">
      <span class="section-title">Current Focus</span>
      <div class="section-line"></div>
    </div>
    <div class="focus-grid">
      <div class="focus-item"><span>🔧</span> Full-Stack Development</div>
      <div class="focus-item"><span>🤖</span> AI-Powered Applications</div>
      <div class="focus-item"><span>🏢</span> Enterprise Systems</div>
      <div class="focus-item"><span>⚡</span> Scalable Backends</div>
      <div class="focus-item"><span>🔴</span> Real-Time Applications</div>
    </div>
  </section>

  <!-- ── CONNECT ── -->
  <section class="section reveal delay-3">
    <div class="section-header">
      <span class="section-title">Connect With Me</span>
      <div class="section-line"></div>
    </div>
    <div class="connect-grid">
      <a class="connect-card" href="https://github.com/Sujeetatwe" target="_blank">
        <div class="connect-icon">🐙</div>
        <div>
          <div class="connect-label">GitHub</div>
          <div class="connect-value">@Sujeetatwe</div>
        </div>
      </a>
      <a class="connect-card" href="https://sujeetatwe.com" target="_blank">
        <div class="connect-icon">🌐</div>
        <div>
          <div class="connect-label">Website</div>
          <div class="connect-value">sujeetatwe.com</div>
        </div>
      </a>
      <div class="connect-card">
        <div class="connect-icon">📍</div>
        <div>
          <div class="connect-label">Location</div>
          <div class="connect-value">Pune, Maharashtra</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ── FOOTER ── -->
  <footer class="footer">
    <p class="footer-quote">
      ⭐ Building projects focused on <span>scalability</span>, <span>automation</span>, and <span>real-world impact</span>.<br>
      <br>
      <span style="font-size:0.7rem; opacity:0.5;">// Made with ❤️ in Pune, India</span>
    </p>
  </footer>

</div>

<script>
  // Fetch public repo count from GitHub API
  fetch('https://api.github.com/users/Sujeetatwe')
    .then(r => r.json())
    .then(data => {
      if (data.public_repos !== undefined) {
        document.getElementById('repos').textContent = data.public_repos;
      }
    })
    .catch(() => {});

  // Generate a realistic-looking contribution grid
  const grid = document.querySelector('.graph-grid');
  if (grid) {
    const levels = [0,0,0,1,1,1,2,2,3,3,4];
    for (let w = 0; w < 52; w++) {
      const col = document.createElement('div');
      col.className = 'graph-col';
      for (let d = 0; d < 7; d++) {
        const cell = document.createElement('div');
        const l = levels[Math.floor(Math.random() * levels.length)];
        cell.className = `graph-cell c${l}`;
        col.appendChild(cell);
      }
      grid.appendChild(col);
    }
  }
</script>
</body>
</html>
