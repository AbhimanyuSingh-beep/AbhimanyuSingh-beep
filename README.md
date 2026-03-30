<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Abhimanyu Singh – Digital Literacy Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #0a0a0f;
      --surface: #12121a;
      --card: #1a1a26;
      --accent: #7c3aed;
      --accent2: #06b6d4;
      --accent3: #f59e0b;
      --text: #e8e8f0;
      --muted: #888899;
      --border: #2a2a3a;
      --glow: rgba(124,58,237,0.3);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Syne', sans-serif;
      overflow-x: hidden;
      cursor: none;
    }

    /* Custom cursor */
    .cursor {
      position: fixed; width: 10px; height: 10px;
      background: var(--accent); border-radius: 50%;
      pointer-events: none; z-index: 9999;
      transform: translate(-50%, -50%);
      transition: transform 0.1s ease;
      mix-blend-mode: screen;
    }
    .cursor-ring {
      position: fixed; width: 36px; height: 36px;
      border: 1.5px solid var(--accent2); border-radius: 50%;
      pointer-events: none; z-index: 9998;
      transform: translate(-50%, -50%);
      transition: transform 0.15s ease, width 0.2s, height 0.2s;
    }

    /* Grid background */
    body::before {
      content: '';
      position: fixed; inset: 0;
      background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 60px 60px;
      opacity: 0.3;
      pointer-events: none;
      z-index: 0;
    }

    /* Glowing orbs */
    .orb {
      position: fixed; border-radius: 50%;
      filter: blur(80px); pointer-events: none; z-index: 0;
    }
    .orb-1 { width: 400px; height: 400px; background: rgba(124,58,237,0.15); top: -100px; left: -100px; }
    .orb-2 { width: 300px; height: 300px; background: rgba(6,182,212,0.1); bottom: 100px; right: -50px; }
    .orb-3 { width: 250px; height: 250px; background: rgba(245,158,11,0.08); top: 50%; left: 40%; }

    /* ── HEADER ── */
    header {
      position: relative; z-index: 10;
      padding: 80px 40px 60px;
      max-width: 1000px; margin: 0 auto;
      display: grid; grid-template-columns: 1fr auto;
      align-items: start; gap: 40px;
      border-bottom: 1px solid var(--border);
    }

    .badge {
      display: inline-block;
      padding: 6px 14px;
      background: rgba(124,58,237,0.15);
      border: 1px solid rgba(124,58,237,0.4);
      border-radius: 100px;
      font-family: 'Space Mono', monospace;
      font-size: 11px; color: var(--accent2);
      letter-spacing: 1px; text-transform: uppercase;
      margin-bottom: 20px;
      animation: fadeUp 0.6s ease both;
    }

    h1 {
      font-size: clamp(2.5rem, 6vw, 4.5rem);
      font-weight: 800; line-height: 1.05;
      letter-spacing: -2px;
      animation: fadeUp 0.7s ease 0.1s both;
    }

    h1 span {
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    }

    .subtitle {
      margin-top: 16px;
      font-size: 1.05rem; color: var(--muted);
      font-weight: 400; line-height: 1.6;
      animation: fadeUp 0.7s ease 0.2s both;
    }

    .meta-tags {
      display: flex; flex-wrap: wrap; gap: 10px;
      margin-top: 28px;
      animation: fadeUp 0.7s ease 0.3s both;
    }

    .tag {
      padding: 6px 14px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 6px;
      font-family: 'Space Mono', monospace;
      font-size: 11px; color: var(--muted);
    }

    .reg-block {
      text-align: right;
      animation: fadeUp 0.7s ease 0.2s both;
    }
    .reg-block .reg-label {
      font-family: 'Space Mono', monospace;
      font-size: 10px; color: var(--muted);
      text-transform: uppercase; letter-spacing: 2px;
    }
    .reg-block .reg-value {
      font-family: 'Space Mono', monospace;
      font-size: 1.4rem; font-weight: 700;
      color: var(--accent3);
      margin-top: 4px;
    }

    /* ── NAV ── */
    nav {
      position: sticky; top: 0; z-index: 100;
      background: rgba(10,10,15,0.85);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
      padding: 0 40px;
    }
    nav ul {
      max-width: 1000px; margin: 0 auto;
      display: flex; gap: 0;
      list-style: none;
    }
    nav a {
      display: block; padding: 18px 20px;
      font-size: 12px; font-weight: 600;
      text-transform: uppercase; letter-spacing: 1.5px;
      color: var(--muted); text-decoration: none;
      border-bottom: 2px solid transparent;
      transition: color 0.2s, border-color 0.2s;
    }
    nav a:hover { color: var(--text); border-color: var(--accent); }

    /* ── MAIN ── */
    main { max-width: 1000px; margin: 0 auto; padding: 0 40px 80px; position: relative; z-index: 10; }

    section { padding: 70px 0 0; }

    .section-label {
      font-family: 'Space Mono', monospace;
      font-size: 10px; color: var(--accent2);
      text-transform: uppercase; letter-spacing: 3px;
      margin-bottom: 12px;
    }

    h2 {
      font-size: 2rem; font-weight: 800;
      letter-spacing: -1px; margin-bottom: 32px;
    }

    /* ── TASKS GRID ── */
    .tasks-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 20px;
    }

    .task-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 28px;
      position: relative; overflow: hidden;
      transition: transform 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
      animation: fadeUp 0.6s ease both;
    }
    .task-card:hover {
      transform: translateY(-4px);
      border-color: var(--accent);
      box-shadow: 0 0 30px var(--glow);
    }
    .task-card::before {
      content: '';
      position: absolute; top: 0; left: 0; right: 0; height: 2px;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      opacity: 0; transition: opacity 0.3s;
    }
    .task-card:hover::before { opacity: 1; }

    .task-num {
      font-family: 'Space Mono', monospace;
      font-size: 10px; color: var(--accent);
      text-transform: uppercase; letter-spacing: 2px;
      margin-bottom: 10px;
    }
    .task-card h3 {
      font-size: 1rem; font-weight: 700;
      margin-bottom: 10px; line-height: 1.3;
    }
    .task-card p {
      font-size: 0.85rem; color: var(--muted);
      line-height: 1.6;
    }
    .task-mark {
      position: absolute; top: 24px; right: 24px;
      font-family: 'Space Mono', monospace;
      font-size: 11px; color: var(--accent3);
      background: rgba(245,158,11,0.1);
      border: 1px solid rgba(245,158,11,0.3);
      padding: 3px 10px; border-radius: 100px;
    }

    /* ── LINKS ── */
    .links-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 16px;
    }

    .link-card {
      display: flex; align-items: center; gap: 14px;
      padding: 18px 20px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      text-decoration: none; color: var(--text);
      transition: border-color 0.2s, transform 0.2s, box-shadow 0.2s;
    }
    .link-card:hover {
      border-color: var(--accent2);
      transform: translateY(-2px);
      box-shadow: 0 0 20px rgba(6,182,212,0.15);
    }
    .link-icon {
      width: 38px; height: 38px; border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
      font-size: 18px; flex-shrink: 0;
    }
    .link-info { min-width: 0; }
    .link-name { font-size: 0.85rem; font-weight: 700; }
    .link-handle { font-family: 'Space Mono', monospace; font-size: 10px; color: var(--muted); margin-top: 2px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }

    /* ── STRUCTURE ── */
    .tree {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 32px;
      font-family: 'Space Mono', monospace;
      font-size: 13px; line-height: 2;
    }
    .tree .folder { color: var(--accent3); }
    .tree .file { color: var(--accent2); }
    .tree .muted { color: var(--muted); }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--border);
      padding: 40px;
      max-width: 1000px; margin: 60px auto 0;
      display: flex; justify-content: space-between; align-items: center;
      flex-wrap: wrap; gap: 16px;
      position: relative; z-index: 10;
    }
    footer p { font-family: 'Space Mono', monospace; font-size: 11px; color: var(--muted); }
    .pass-badge {
      padding: 6px 16px;
      background: rgba(6,182,212,0.1);
      border: 1px solid rgba(6,182,212,0.3);
      border-radius: 100px;
      font-family: 'Space Mono', monospace;
      font-size: 11px; color: var(--accent2);
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* stagger task cards */
    .task-card:nth-child(1) { animation-delay: 0.1s; }
    .task-card:nth-child(2) { animation-delay: 0.2s; }
    .task-card:nth-child(3) { animation-delay: 0.3s; }
    .task-card:nth-child(4) { animation-delay: 0.4s; }
    .task-card:nth-child(5) { animation-delay: 0.5s; }

    @media (max-width: 600px) {
      header { grid-template-columns: 1fr; padding: 50px 24px 40px; }
      nav { padding: 0 16px; }
      nav a { padding: 16px 12px; font-size: 10px; }
      main { padding: 0 24px 60px; }
      footer { padding: 32px 24px; flex-direction: column; align-items: flex-start; }
    }
  </style>
</head>
<body>

  <div class="cursor" id="cursor"></div>
  <div class="cursor-ring" id="cursorRing"></div>
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="orb orb-3"></div>

  <!-- HEADER -->
  <header>
    <div>
      <div class="badge">CSE0001 · Digital Literacy · VIT Bhopal</div>
      <h1>Abhimanyu<br/><span>Singh</span></h1>
      <p class="subtitle">Student Digital Ambassador &nbsp;·&nbsp; B.Tech CSE, First Year<br/>VIT Bhopal University</p>
      <div class="meta-tags">
        <span class="tag">DSA</span>
        <span class="tag">C++</span>
        <span class="tag">AI</span>
        <span class="tag">Web Dev</span>
        <span class="tag">Competitive Programming</span>
      </div>
    </div>
    <div class="reg-block">
      <div class="reg-label">Reg. No.</div>
      <div class="reg-value">25BCE10956</div>
    </div>
  </header>

  <!-- NAV -->
  <nav>
    <ul>
      <li><a href="#tasks">Tasks</a></li>
      <li><a href="#links">Links</a></li>
      <li><a href="#structure">Structure</a></li>
    </ul>
  </nav>

  <main>

    <!-- TASKS -->
    <section id="tasks">
      <div class="section-label">Project Modules</div>
      <h2>Five Tasks Completed</h2>
      <div class="tasks-grid">

        <div class="task-card">
          <div class="task-num">Task 01 · Module 1</div>
          <span class="task-mark">20 marks</span>
          <h3>Digital Literacy Awareness Infographic</h3>
          <p>Designed a one-page infographic using Canva covering digital literacy, useful student tools, and safe internet practices.</p>
        </div>

        <div class="task-card">
          <div class="task-num">Task 02 · Module 2</div>
          <span class="task-mark">20 marks</span>
          <h3>Student Digital Portfolio</h3>
          <p>Set up professional profiles on GitHub, LinkedIn, and Kaggle with a complete profile README and education details.</p>
        </div>

        <div class="task-card">
          <div class="task-num">Task 03 · Module 3</div>
          <span class="task-mark">20 marks</span>
          <h3>Coding & Collaboration Platforms</h3>
          <p>Completed a beginner challenge on HackerRank. Built a 5-question Digital Literacy Quiz using Google Forms for batchmates.</p>
        </div>

        <div class="task-card">
          <div class="task-num">Task 04 · Module 4</div>
          <span class="task-mark">20 marks</span>
          <h3>Professional Email & Etiquette Guide</h3>
          <p>Drafted two professional emails — deadline extension and internship application. Created a Social Media Do's & Don'ts checklist.</p>
        </div>

        <div class="task-card">
          <div class="task-num">Task 05 · Module 5</div>
          <span class="task-mark">20 marks</span>
          <h3>Cybercrime Awareness – Phishing</h3>
          <p>Wrote a phishing case study and an 8-tip prevention checklist including UPI safety and reporting via cybercrime.gov.in / 1930.</p>
        </div>

      </div>
    </section>

    <!-- LINKS -->
    <section id="links">
      <div class="section-label">Profiles & Resources</div>
      <h2>Key Links</h2>
      <div class="links-grid">

        <a class="link-card" href="https://github.com/AbhimanyuSingh-beep" target="_blank">
          <div class="link-icon" style="background:rgba(124,58,237,0.15)">🐙</div>
          <div class="link-info">
            <div class="link-name">GitHub</div>
            <div class="link-handle">AbhimanyuSingh-beep</div>
          </div>
        </a>

        <a class="link-card" href="https://www.linkedin.com/in/abhimanyu-singh-699187364/" target="_blank">
          <div class="link-icon" style="background:rgba(6,182,212,0.15)">💼</div>
          <div class="link-info">
            <div class="link-name">LinkedIn</div>
            <div class="link-handle">Abhimanyu Singh</div>
          </div>
        </a>

        <a class="link-card" href="https://docs.google.com/forms/d/e/1FAIpQLSf8y8AUxEfy7irYYOJfyBRVIL5O6Z2XXPrRBaEBmxmurdyFFQ/viewform?usp=dialog" target="_blank">
          <div class="link-icon" style="background:rgba(245,158,11,0.15)">📋</div>
          <div class="link-info">
            <div class="link-name">Digital Literacy Quiz</div>
            <div class="link-handle">Google Form · Task 3</div>
          </div>
        </a>

        <a class="link-card" href="https://cybercrime.gov.in" target="_blank">
          <div class="link-icon" style="background:rgba(239,68,68,0.15)">🛡️</div>
          <div class="link-info">
            <div class="link-name">Cyber Crime Portal</div>
            <div class="link-handle">cybercrime.gov.in · 1930</div>
          </div>
        </a>

      </div>
    </section>

    <!-- STRUCTURE -->
    <section id="structure">
      <div class="section-label">Repository</div>
      <h2>Folder Structure</h2>
      <div class="tree">
        <div><span class="folder">📁 digital-literacy-project/</span></div>
        <div>&nbsp;&nbsp;├── <span class="file">README.md</span></div>
        <div>&nbsp;&nbsp;├── <span class="file">index.html</span> &nbsp;<span class="muted">← this page</span></div>
        <div>&nbsp;&nbsp;├── <span class="folder">📁 report/</span></div>
        <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;└── <span class="file">Project_Report_Abhimanyu_Singh.pdf</span></div>
        <div>&nbsp;&nbsp;├── <span class="folder">📁 task-1-presentation/</span></div>
        <div>&nbsp;&nbsp;├── <span class="folder">📁 task-2-portfolio/</span></div>
        <div>&nbsp;&nbsp;├── <span class="folder">📁 task-3-platforms/</span></div>
        <div>&nbsp;&nbsp;├── <span class="folder">📁 task-4-email-etiquette/</span></div>
        <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="file">Emails_Abhimanyu_Singh.pdf</span></div>
        <div>&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;└── <span class="file">social-media-checklist.md</span></div>
        <div>&nbsp;&nbsp;└── <span class="folder">📁 task-5-cybercrime/</span></div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── <span class="file">casestudy.md</span></div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── <span class="file">prevention-checklist.md</span></div>
      </div>
    </section>

  </main>

  <footer>
    <p>© 2025 Abhimanyu Singh · 25BCE10956 · VIT Bhopal University</p>
    <div class="pass-badge">Pass / Fail · 1 Credit · Non-CGPA</div>
  </footer>

  <script>
    const cursor = document.getElementById('cursor');
    const ring = document.getElementById('cursorRing');
    let mx = 0, my = 0, rx = 0, ry = 0;

    document.addEventListener('mousemove', e => {
      mx = e.clientX; my = e.clientY;
      cursor.style.left = mx + 'px';
      cursor.style.top  = my + 'px';
    });

    function animateRing() {
      rx += (mx - rx) * 0.12;
      ry += (my - ry) * 0.12;
      ring.style.left = rx + 'px';
      ring.style.top  = ry + 'px';
      requestAnimationFrame(animateRing);
    }
    animateRing();

    document.querySelectorAll('a, .task-card').forEach(el => {
      el.addEventListener('mouseenter', () => {
        ring.style.width = '56px'; ring.style.height = '56px';
        ring.style.borderColor = 'var(--accent3)';
      });
      el.addEventListener('mouseleave', () => {
        ring.style.width = '36px'; ring.style.height = '36px';
        ring.style.borderColor = 'var(--accent2)';
      });
    });
  </script>
</body>
</html>
