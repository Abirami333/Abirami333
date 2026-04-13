<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abirami S – GitHub Profile README Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0c10;
    --surface: #10141c;
    --card: #141820;
    --border: #1e2530;
    --accent: #00e5ff;
    --accent2: #7c5cfc;
    --accent3: #ff6b6b;
    --green: #39d353;
    --text: #e6edf3;
    --muted: #7d8590;
    --font-display: 'Syne', sans-serif;
    --font-mono: 'Space Mono', monospace;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-display);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .page {
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
    margin-bottom: 36px;
    animation: fadeDown 0.7s ease both;
  }

  .badge-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 8px;
  }

  .badge {
    font-family: var(--font-mono);
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 4px;
    border: 1px solid;
    letter-spacing: 0.08em;
    animation: fadeIn 1s ease both;
  }

  .badge-cyan { color: var(--accent); border-color: var(--accent); background: rgba(0,229,255,0.07); }
  .badge-purple { color: var(--accent2); border-color: var(--accent2); background: rgba(124,92,252,0.1); }
  .badge-red { color: var(--accent3); border-color: var(--accent3); background: rgba(255,107,107,0.08); }
  .badge-green { color: var(--green); border-color: var(--green); background: rgba(57,211,83,0.08); }

  .name {
    font-family: var(--font-display);
    font-size: clamp(2.4rem, 7vw, 3.8rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    background: linear-gradient(135deg, #fff 30%, var(--accent) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .tagline {
    font-family: var(--font-mono);
    font-size: 13px;
    color: var(--muted);
    letter-spacing: 0.04em;
  }

  .tagline span { color: var(--accent); }

  /* Typing cursor */
  .cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--accent);
    margin-left: 2px;
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ── ABOUT ── */
  .section { margin-bottom: 32px; animation: fadeUp 0.8s ease both; }
  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }
  .section:nth-child(6) { animation-delay: 0.5s; }

  .section-label {
    font-family: var(--font-mono);
    font-size: 10px;
    color: var(--accent);
    letter-spacing: 0.18em;
    text-transform: uppercase;
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  .about-text {
    font-size: 14.5px;
    line-height: 1.75;
    color: #b0bec5;
    max-width: 680px;
  }

  .about-text strong { color: var(--text); font-weight: 600; }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
    gap: 12px;
    margin-bottom: 32px;
    animation: fadeUp 0.8s 0.15s ease both;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent2), var(--accent));
    opacity: 0;
    transition: opacity 0.3s;
  }

  .stat-card:hover { border-color: var(--accent); transform: translateY(-3px); }
  .stat-card:hover::before { opacity: 1; }

  .stat-val {
    font-size: 26px;
    font-weight: 800;
    color: var(--accent);
    display: block;
    line-height: 1.1;
    font-family: var(--font-mono);
  }

  .stat-label {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-top: 4px;
  }

  /* ── SKILL GRID ── */
  .skill-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 14px;
  }

  .skill-group {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 18px;
    transition: border-color 0.3s, transform 0.3s;
  }

  .skill-group:hover { border-color: rgba(0,229,255,0.3); transform: translateY(-2px); }

  .skill-group-title {
    font-family: var(--font-mono);
    font-size: 10px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 10px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }

  .sg-frontend .skill-group-title { color: var(--accent); }
  .sg-backend .skill-group-title { color: var(--accent2); }
  .sg-db .skill-group-title { color: var(--accent3); }
  .sg-tools .skill-group-title { color: var(--green); }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .skill-tag {
    font-family: var(--font-mono);
    font-size: 10.5px;
    padding: 3px 8px;
    border-radius: 4px;
    background: rgba(255,255,255,0.04);
    color: #c9d1d9;
    border: 1px solid var(--border);
    transition: background 0.2s, color 0.2s;
  }

  .sg-frontend .skill-tag:hover { background: rgba(0,229,255,0.1); color: var(--accent); }
  .sg-backend .skill-tag:hover { background: rgba(124,92,252,0.1); color: var(--accent2); }
  .sg-db .skill-tag:hover { background: rgba(255,107,107,0.1); color: var(--accent3); }
  .sg-tools .skill-tag:hover { background: rgba(57,211,83,0.1); color: var(--green); }

  /* ── PROJECTS ── */
  .project-list { display: flex; flex-direction: column; gap: 14px; }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 22px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
  }

  .project-card::after {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 3px;
    background: var(--stripe);
    opacity: 0.8;
  }

  .project-card:hover { border-color: var(--stripe); transform: translateX(4px); }

  .project-card.p1 { --stripe: var(--accent); }
  .project-card.p2 { --stripe: var(--accent2); }
  .project-card.p3 { --stripe: var(--accent3); }

  .project-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 12px;
    flex-wrap: wrap;
    margin-bottom: 8px;
  }

  .project-title {
    font-size: 15px;
    font-weight: 700;
    color: var(--text);
  }

  .project-stack {
    font-family: var(--font-mono);
    font-size: 10px;
    color: var(--muted);
    padding: 2px 8px;
    border: 1px solid var(--border);
    border-radius: 3px;
    white-space: nowrap;
  }

  .project-desc {
    font-size: 13px;
    line-height: 1.65;
    color: #7d8590;
  }

  .project-points {
    margin-top: 10px;
    display: flex;
    flex-direction: column;
    gap: 5px;
  }

  .point {
    font-size: 12.5px;
    color: #8b949e;
    padding-left: 14px;
    position: relative;
    line-height: 1.5;
  }

  .point::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: var(--stripe);
    font-size: 10px;
    top: 2px;
  }

  /* ── EXPERIENCE ── */
  .exp-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 22px;
    border-left: 3px solid var(--accent2);
  }

  .exp-header { display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 8px; margin-bottom: 10px; }
  .exp-title { font-size: 15px; font-weight: 700; }
  .exp-company { font-size: 12px; color: var(--accent2); font-family: var(--font-mono); }
  .exp-date { font-family: var(--font-mono); font-size: 10px; color: var(--muted); padding: 3px 8px; border: 1px solid var(--border); border-radius: 3px; }

  /* ── CONNECT ── */
  .connect-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin-top: 8px;
  }

  .connect-btn {
    display: flex;
    align-items: center;
    gap: 7px;
    padding: 9px 16px;
    border-radius: 7px;
    font-family: var(--font-mono);
    font-size: 11px;
    letter-spacing: 0.06em;
    text-decoration: none;
    border: 1px solid;
    transition: background 0.2s, transform 0.2s;
    cursor: pointer;
  }

  .connect-btn:hover { transform: translateY(-2px); }
  .btn-email { color: var(--accent); border-color: var(--accent); background: rgba(0,229,255,0.05); }
  .btn-email:hover { background: rgba(0,229,255,0.15); }
  .btn-gh { color: var(--text); border-color: var(--border); background: rgba(255,255,255,0.04); }
  .btn-gh:hover { background: rgba(255,255,255,0.1); border-color: #fff3; }
  .btn-li { color: #0a66c2; border-color: #0a66c2; background: rgba(10,102,194,0.07); }
  .btn-li:hover { background: rgba(10,102,194,0.15); }

  /* ── CONTRIBUTION SNAKE ── */
  .snake-section {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 22px;
    margin-bottom: 32px;
    animation: fadeUp 0.8s 0.55s ease both;
  }

  .contribution-grid {
    display: grid;
    grid-template-columns: repeat(53, 1fr);
    gap: 2px;
    margin-top: 12px;
  }

  .contrib-cell {
    aspect-ratio: 1;
    border-radius: 2px;
    transition: transform 0.15s;
  }

  .contrib-cell:hover { transform: scale(1.6); z-index: 2; position: relative; }

  /* ── CERT ── */
  .cert-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 20px;
    display: flex;
    align-items: center;
    gap: 14px;
  }

  .cert-icon {
    font-size: 24px;
    flex-shrink: 0;
  }

  .cert-name { font-size: 14px; font-weight: 600; }
  .cert-issuer { font-family: var(--font-mono); font-size: 11px; color: var(--muted); margin-top: 2px; }

  /* ── FOOTER ── */
  .footer {
    margin-top: 48px;
    padding-top: 20px;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 10px;
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--muted);
    animation: fadeUp 0.8s 0.6s ease both;
  }

  .footer .dot {
    display: inline-block;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--green);
    margin-right: 6px;
    box-shadow: 0 0 6px var(--green);
    animation: pulse 2s infinite;
  }

  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.6;transform:scale(0.85)} }

  /* ── COPY BUTTON ── */
  .copy-section {
    margin-top: 40px;
    background: linear-gradient(135deg, rgba(0,229,255,0.05), rgba(124,92,252,0.05));
    border: 1px dashed rgba(0,229,255,0.25);
    border-radius: 12px;
    padding: 20px 24px;
    text-align: center;
  }

  .copy-section p {
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 14px;
    line-height: 1.6;
  }

  .copy-section strong { color: var(--accent); }

  .btn-copy {
    background: linear-gradient(135deg, var(--accent2), var(--accent));
    color: #000;
    border: none;
    padding: 11px 24px;
    border-radius: 7px;
    font-family: var(--font-mono);
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.06em;
    cursor: pointer;
    transition: opacity 0.2s, transform 0.2s;
  }

  .btn-copy:hover { opacity: 0.9; transform: translateY(-2px); }
  .btn-copy:active { transform: scale(0.97); }

  /* ── ANIMATIONS ── */
  @keyframes fadeDown { from{opacity:0;transform:translateY(-20px)} to{opacity:1;transform:translateY(0)} }
  @keyframes fadeUp { from{opacity:0;transform:translateY(20px)} to{opacity:1;transform:translateY(0)} }
  @keyframes fadeIn { from{opacity:0} to{opacity:1} }

  /* scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }
</style>
</head>
<body>
<div class="page">

  <!-- HEADER -->
  <div class="header">
    <div class="badge-row">
      <span class="badge badge-cyan">☕ Java Full Stack Developer</span>
      <span class="badge badge-purple">⚛️ React.js</span>
      <span class="badge badge-red">🌱 Spring Boot</span>
      <span class="badge badge-green">📍 Chennai, India</span>
    </div>
    <h1 class="name">Abirami S</h1>
    <p class="tagline">&gt; Building scalable systems, one commit at a time<span class="cursor"></span></p>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="stat-card">
      <span class="stat-val">3+</span>
      <div class="stat-label">Projects Built</div>
    </div>
    <div class="stat-card">
      <span class="stat-val">8.09</span>
      <div class="stat-label">CGPA</div>
    </div>
    <div class="stat-card">
      <span class="stat-val">2025</span>
      <div class="stat-label">CSE Graduate</div>
    </div>
    <div class="stat-card">
      <span class="stat-val">FS</span>
      <div class="stat-label">Certified Dev</div>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-label">// about me</div>
    <p class="about-text">
      Hey there! 👋 I'm a <strong>Computer Science Engineering graduate (2025)</strong> from UCE Kanchipuram with a passion for
      building production-ready full-stack applications. I thrive at the intersection of <strong>clean backend APIs</strong>
      and <strong>intuitive frontend experiences</strong>. Deeply interested in <strong>cloud-native fintech</strong>,
      <strong>payment systems</strong>, and writing code that actually solves real-world problems — not just passes test cases.
    </p>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-label">// tech stack</div>
    <div class="skill-grid">
      <div class="skill-group sg-frontend">
        <div class="skill-group-title">⚡ Frontend</div>
        <div class="skill-tags">
          <span class="skill-tag">React.js</span>
          <span class="skill-tag">JavaScript ES6+</span>
          <span class="skill-tag">HTML5</span>
          <span class="skill-tag">CSS3</span>
          <span class="skill-tag">Bootstrap</span>
          <span class="skill-tag">React Hooks</span>
          <span class="skill-tag">SPA</span>
          <span class="skill-tag">Responsive Design</span>
        </div>
      </div>
      <div class="skill-group sg-backend">
        <div class="skill-group-title">🔧 Backend</div>
        <div class="skill-tags">
          <span class="skill-tag">Java (Core)</span>
          <span class="skill-tag">Spring Boot</span>
          <span class="skill-tag">REST APIs</span>
          <span class="skill-tag">MVC</span>
          <span class="skill-tag">Hibernate / JPA</span>
          <span class="skill-tag">Spring Security</span>
          <span class="skill-tag">JWT Auth</span>
          <span class="skill-tag">Dependency Injection</span>
        </div>
      </div>
      <div class="skill-group sg-db">
        <div class="skill-group-title">🗃️ Database</div>
        <div class="skill-tags">
          <span class="skill-tag">MySQL</span>
          <span class="skill-tag">SQL Queries</span>
          <span class="skill-tag">CRUD Ops</span>
          <span class="skill-tag">Normalization</span>
          <span class="skill-tag">Query Optimization</span>
        </div>
      </div>
      <div class="skill-group sg-tools">
        <div class="skill-group-title">🛠️ Tools & Practices</div>
        <div class="skill-tags">
          <span class="skill-tag">Postman</span>
          <span class="skill-tag">Git / GitHub</span>
          <span class="skill-tag">SDLC</span>
          <span class="skill-tag">Debugging</span>
          <span class="skill-tag">Clean Code</span>
          <span class="skill-tag">OOP</span>
        </div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-label">// featured projects</div>
    <div class="project-list">

      <div class="project-card p1">
        <div class="project-header">
          <span class="project-title">🧑‍🏭 Smart Migrant Labour Management System</span>
          <span class="project-stack">React + JavaScript</span>
        </div>
        <div class="project-points">
          <div class="point">Full-stack web app for registration, job mapping & welfare tracking of migrant workers in Tamil Nadu.</div>
          <div class="point">Implemented secure labour onboarding, job allocation workflows & real-time monitoring modules.</div>
          <div class="point">Enhanced UX with intuitive UI and optimized database queries for performance.</div>
        </div>
      </div>

      <div class="project-card p2">
        <div class="project-header">
          <span class="project-title">🏥 Medical Appointment System</span>
          <span class="project-stack">Spring Boot + MySQL</span>
        </div>
        <div class="project-points">
          <div class="point">Clinic appointment system with RESTful APIs managing patients, doctors & appointments.</div>
          <div class="point">CRUD operations using MySQL; tested all REST endpoints via Postman for reliability.</div>
        </div>
      </div>

      <div class="project-card p3">
        <div class="project-header">
          <span class="project-title">💼 Job Portal System</span>
          <span class="project-stack">Spring Boot + MySQL</span>
        </div>
        <div class="project-points">
          <div class="point">Scalable RESTful job portal backend with JWT-based auth & role-based authorization via Spring Security.</div>
          <div class="point">Efficient DB operations with Spring Data JPA + MySQL; modular architecture for scalability.</div>
        </div>
      </div>

    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="section">
    <div class="section-label">// experience</div>
    <div class="exp-card">
      <div class="exp-header">
        <div>
          <div class="exp-title">Frontend Developer Intern</div>
          <div class="exp-company">Tripmilestone Tours Pvt. Ltd. (TripXplo)</div>
        </div>
        <div class="exp-date">Jul 2024 – Sep 2025</div>
      </div>
      <div class="project-points">
        <div class="point" style="--stripe:var(--accent2)">Developed & optimized data retrieval modules for the TripXplo Admin Dashboard using React.js.</div>
        <div class="point" style="--stripe:var(--accent2)">Collaborated with the engineering team to improve UI components and dashboard performance.</div>
        <div class="point" style="--stripe:var(--accent2)">Integrated frontend components with backend APIs; debugged UI issues using component-based development.</div>
      </div>
    </div>
  </div>

  <!-- CONTRIBUTION GRID -->
  <div class="snake-section">
    <div class="section-label" style="margin-bottom:0">// contribution activity</div>
    <div class="contribution-grid" id="contribGrid"></div>
  </div>

  <!-- CERTIFICATION -->
  <div class="section">
    <div class="section-label">// certifications</div>
    <div class="cert-card">
      <div class="cert-icon">🏆</div>
      <div>
        <div class="cert-name">Full Stack Development Certification</div>
        <div class="cert-issuer">Besant Technologies, Velachery</div>
      </div>
    </div>
  </div>

  <!-- EDUCATION -->
  <div class="section">
    <div class="section-label">// education</div>
    <div class="project-list">
      <div class="project-card p1" style="padding:16px 22px">
        <div class="project-header">
          <span class="project-title">B.E. Computer Science & Engineering</span>
          <span class="project-stack">CGPA 8.09</span>
        </div>
        <div style="font-size:12px;color:var(--muted);margin-top:4px;font-family:var(--font-mono)">University College of Engineering Kanchipuram · 2021–2025</div>
      </div>
      <div class="project-card p2" style="padding:14px 22px">
        <div class="project-header">
          <span class="project-title" style="font-size:13.5px">HSC 93.7% &nbsp;|&nbsp; SSC 92.6%</span>
        </div>
        <div style="font-size:12px;color:var(--muted);margin-top:2px;font-family:var(--font-mono)">SSKV Girls Hr Sec School, Kanchipuram</div>
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section">
    <div class="section-label">// let's connect</div>
    <div class="connect-row">
      <a class="connect-btn btn-email" href="mailto:abiramisrinivasan2004@gmail.com">
        ✉️ abiramisrinivasan2004@gmail.com
      </a>
      <a class="connect-btn btn-gh" href="#">
        🐙 GitHub
      </a>
      <a class="connect-btn btn-li" href="#">
        💼 LinkedIn
      </a>
    </div>
  </div>

  <!-- COPY INSTRUCTIONS -->
  <div class="copy-section">
    <p>
      📋 <strong>GitHub-ல use பண்ண:</strong> உன் GitHub username-ஓட same name-ல ஒரு repository create பண்ணு
      (e.g., <strong>Abirami-S/Abirami-S</strong>), அதுல <strong>README.md</strong> file create பண்ணி
      கீழே உள்ள markdown content paste பண்ணு. இந்த HTML file preview மட்டும் — actual README markdown தனியா copy பண்ணணும்.
    </p>
    <button class="btn-copy" onclick="copyMarkdown()">📋 Copy README.md Markdown</button>
    <div id="copyMsg" style="margin-top:10px;font-family:var(--font-mono);font-size:12px;color:var(--green);display:none">✅ Copied! GitHub README.md-ல paste பண்ணு.</div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <span><span class="dot"></span>Open to opportunities · Chennai, India</span>
    <span>Built with ❤️ by Abirami S</span>
  </div>

</div>

<!-- Hidden markdown for copy -->
<textarea id="mdContent" style="position:absolute;left:-9999px">
<div align="center">

```
 █████╗ ██████╗ ██╗██████╗  █████╗ ███╗   ███╗██╗    ███████╗
██╔══██╗██╔══██╗██║██╔══██╗██╔══██╗████╗ ████║██║    ██╔════╝
███████║██████╔╝██║██████╔╝███████║██╔████╔██║██║    ███████╗
██╔══██║██╔══██╗██║██╔══██╗██╔══██║██║╚██╔╝██║██║    ╚════██║
██║  ██║██████╔╝██║██║  ██║██║  ██║██║ ╚═╝ ██║██║    ███████║
╚═╝  ╚═╝╚═════╝ ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝╚═╝    ╚══════╝
```

# Hey there! 👋 I'm Abirami S

### ☕ Java Full Stack Developer · ⚛️ React.js · 🌱 Spring Boot · 📍 Chennai

![Profile Views](https://komarev.com/ghpvc/?username=YOUR_USERNAME&color=00e5ff&style=flat-square)
![Open to Work](https://img.shields.io/badge/Open%20to%20Work-00e5ff?style=flat-square&logoColor=black)
![CSE Graduate](https://img.shields.io/badge/CSE%20Graduate-2025-7c5cfc?style=flat-square)

</div>

---

## 🧠 About Me

> *"Building scalable systems, one commit at a time."*

- 🎓 **B.E. CSE** graduate (2025) from University College of Engineering, Kanchipuram · **CGPA: 8.09**
- 💻 Passionate about **clean backend APIs** and **intuitive frontend experiences**
- 🔐 Experienced in **SDLC, API testing, debugging, SQL validation & application support**
- 🚀 Strong interest in **cloud-native fintech** and **payment systems**
- 📬 Reach me: **abiramisrinivasan2004@gmail.com** · 📞 9344090446

---

## 🛠️ Tech Stack

**Frontend**
![React](https://img.shields.io/badge/React.js-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=flat-square&logo=bootstrap&logoColor=white)

**Backend**
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white)
![Hibernate](https://img.shields.io/badge/Hibernate-59666C?style=flat-square&logo=hibernate&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=json-web-tokens&logoColor=white)

**Database & Tools**
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)

---

## 🚀 Featured Projects

### 🧑‍🏭 Smart Migrant Labour Management System
> `React.js` · `JavaScript` · `Full Stack`

- Full-stack web app for **registration, job mapping & welfare tracking** of migrant workers in Tamil Nadu
- Implemented **secure labour onboarding**, job allocation workflows & real-time monitoring modules
- Enhanced UX with intuitive UI and optimized database queries for performance

---

### 🏥 Medical Appointment System
> `Spring Boot` · `MySQL` · `REST API`

- Clinic appointment system with **RESTful APIs** managing patients, doctors & appointments
- CRUD operations using MySQL; tested all REST endpoints via **Postman** for reliability

---

### 💼 Job Portal System
> `Spring Boot` · `Spring Security` · `JWT` · `MySQL`

- Scalable RESTful job portal backend with **JWT-based authentication** & role-based authorization
- Efficient DB operations with **Spring Data JPA + MySQL**; modular architecture for scalability

---

## 💼 Experience

**Frontend Developer Intern** @ Tripmilestone Tours Pvt. Ltd. (TripXplo) *(Jul 2024 – Sep 2025)*

- Developed & optimized data retrieval modules for **TripXplo Admin Dashboard** using React.js
- Collaborated with engineering team to improve UI components and dashboard performance
- Integrated frontend components with backend APIs; debugged UI issues via component-based development

---

## 🎓 Education

| Degree | Institution | Score | Year |
|--------|------------|-------|------|
| B.E. Computer Science & Engineering | UCE Kanchipuram | CGPA 8.09 | 2021–2025 |
| HSC | SSKV Girls Hr Sec School, Kanchipuram | 93.7% | — |
| SSC | SSKV Girls Hr Sec School, Kanchipuram | 92.6% | — |

---

## 🏆 Certification

- 📜 **Full Stack Development Certification** — Besant Technologies, Velachery

---

## 📊 GitHub Stats

<div align="center">

![Abirami's GitHub Stats](https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0a0c10&title_color=00e5ff&icon_color=7c5cfc&text_color=e6edf3)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=tokyonight&hide_border=true&bg_color=0a0c10&title_color=00e5ff&text_color=e6edf3)

![GitHub Streak](https://streak-stats.demolab.com/?user=YOUR_USERNAME&theme=tokyonight&hide_border=true&background=0a0c10&ring=00e5ff&fire=7c5cfc&currStreakLabel=00e5ff)

</div>

---

## 📬 Let's Connect

[![Email](https://img.shields.io/badge/Email-abiramisrinivasan2004@gmail.com-00e5ff?style=flat-square&logo=gmail)](mailto:abiramisrinivasan2004@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?style=flat-square&logo=github)](https://github.com/YOUR_USERNAME)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/YOUR_LINKEDIN)

---

<div align="center">
  <i>⚡ "Detail-oriented developer who turns coffee into clean code."</i><br><br>
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,30&height=80&section=footer" width="100%"/>
</div>
</textarea>

<script>
  // Generate contribution grid
  const grid = document.getElementById('contribGrid');
  const levels = [0,0,0,1,1,2,2,3,4];
  const colors = ['#161b22','#0e4429','#006d32','#26a641','#39d353'];

  for(let i = 0; i < 53*7; i++) {
    const cell = document.createElement('div');
    cell.className = 'contrib-cell';
    // Simulate realistic contribution pattern
    const rand = Math.random();
    let level = 0;
    if(rand > 0.55) level = 1;
    if(rand > 0.72) level = 2;
    if(rand > 0.85) level = 3;
    if(rand > 0.93) level = 4;
    cell.style.background = colors[level];
    cell.title = `${level > 0 ? level * 2 : 0} contributions`;
    grid.appendChild(cell);
  }

  function copyMarkdown() {
    const text = document.getElementById('mdContent').value.trim();
    navigator.clipboard.writeText(text).then(() => {
      document.getElementById('copyMsg').style.display = 'block';
      setTimeout(()=>{ document.getElementById('copyMsg').style.display='none'; }, 4000);
    });
  }
</script>

</body>
</html>
