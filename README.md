<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>M.N Abdul Rahman — Portfolio CV</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #060810;
    --surface: #0d1120;
    --surface2: #141828;
    --border: rgba(99,130,255,0.15);
    --accent: #4f7cff;
    --accent2: #a78bfa;
    --accent3: #38bdf8;
    --text: #e8ecf8;
    --muted: #8893b0;
    --glow: rgba(79,124,255,0.3);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 15px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* Animated background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 50% at 20% 10%, rgba(79,124,255,0.08) 0%, transparent 60%),
      radial-gradient(ellipse 60% 40% at 80% 80%, rgba(167,139,250,0.06) 0%, transparent 60%),
      radial-gradient(ellipse 40% 60% at 50% 50%, rgba(56,189,248,0.04) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  /* Floating particles */
  .particles {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }
  .particle {
    position: absolute;
    width: 2px;
    height: 2px;
    border-radius: 50%;
    background: var(--accent);
    opacity: 0;
    animation: float-up linear infinite;
  }
  @keyframes float-up {
    0% { opacity: 0; transform: translateY(0) scale(0); }
    10% { opacity: 0.6; }
    90% { opacity: 0.2; }
    100% { opacity: 0; transform: translateY(-100vh) scale(1.5); }
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ---- HEADER ---- */
  header {
    padding: 72px 0 48px;
    position: relative;
  }

  .header-inner {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: start;
  }

  .tag-line {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.2em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 16px;
    opacity: 0;
    animation: fade-in 0.6s ease forwards 0.2s;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .tag-line::before {
    content: '';
    width: 28px;
    height: 1px;
    background: var(--accent);
    display: block;
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(36px, 6vw, 56px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.02em;
    opacity: 0;
    animation: slide-up 0.7s ease forwards 0.3s;
  }
  h1 span {
    display: block;
    background: linear-gradient(135deg, #fff 0%, var(--accent) 50%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .headline {
    margin-top: 14px;
    color: var(--muted);
    font-size: 15px;
    font-weight: 300;
    max-width: 520px;
    opacity: 0;
    animation: fade-in 0.7s ease forwards 0.5s;
  }

  .contact-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 24px;
    opacity: 0;
    animation: fade-in 0.7s ease forwards 0.7s;
  }
  .pill {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 6px 14px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 100px;
    font-size: 12px;
    color: var(--muted);
    text-decoration: none;
    transition: all 0.25s ease;
    white-space: nowrap;
  }
  .pill:hover {
    border-color: var(--accent);
    color: var(--text);
    box-shadow: 0 0 16px var(--glow);
    transform: translateY(-1px);
  }
  .pill svg { width: 13px; height: 13px; flex-shrink: 0; }

  /* GitHub preview card */
  .github-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 20px;
    width: 220px;
    flex-shrink: 0;
    opacity: 0;
    animation: slide-left 0.7s ease forwards 0.6s;
    position: relative;
    overflow: hidden;
  }
  .github-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
  }
  .github-card-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 14px;
  }
  .gh-avatar {
    width: 38px; height: 38px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 14px;
    color: #fff;
    flex-shrink: 0;
  }
  .gh-name { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 13px; }
  .gh-handle { font-size: 11px; color: var(--muted); font-family: 'DM Mono', monospace; }
  .gh-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
  .gh-stat {
    background: var(--surface2);
    border-radius: 8px;
    padding: 8px 10px;
    text-align: center;
  }
  .gh-stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 18px;
    font-weight: 700;
    color: var(--accent);
    display: block;
    line-height: 1;
  }
  .gh-stat-label { font-size: 10px; color: var(--muted); margin-top: 2px; display: block; }
  .gh-langs { margin-top: 10px; }
  .gh-lang-bar {
    height: 5px;
    border-radius: 3px;
    background: linear-gradient(90deg, #f0db4f 28%, #b07219 28% 45%, #e34c26 45% 58%, #4f7cff 58% 72%, #cc342d 72%);
    margin-bottom: 6px;
  }
  .gh-lang-labels { display: flex; flex-wrap: wrap; gap: 6px; }
  .gh-lang-dot {
    display: inline-flex; align-items: center; gap: 4px;
    font-size: 10px; color: var(--muted);
  }
  .dot { width: 7px; height: 7px; border-radius: 50%; }

  /* divider */
  .divider {
    width: 100%;
    height: 1px;
    background: var(--border);
    margin: 40px 0;
    position: relative;
  }
  .divider::before {
    content: '';
    position: absolute;
    left: 0; top: 0;
    width: 60px; height: 1px;
    background: var(--accent);
  }

  /* ---- SECTIONS ---- */
  section { margin-bottom: 56px; opacity: 0; transform: translateY(20px); transition: opacity 0.6s ease, transform 0.6s ease; }
  section.visible { opacity: 1; transform: none; }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.25em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* Summary */
  .summary-text {
    font-size: 16px;
    line-height: 1.8;
    color: var(--text);
    font-weight: 300;
    border-left: 2px solid var(--accent);
    padding-left: 20px;
  }

  /* Experience */
  .exp-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px 28px;
    margin-bottom: 16px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.25s, box-shadow 0.25s, transform 0.25s;
    cursor: default;
  }
  .exp-item:hover {
    border-color: rgba(79,124,255,0.4);
    box-shadow: 0 8px 40px rgba(79,124,255,0.1);
    transform: translateY(-2px);
  }
  .exp-item::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), transparent);
    opacity: 0;
    transition: opacity 0.25s;
  }
  .exp-item:hover::before { opacity: 1; }

  .exp-header { display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; margin-bottom: 4px; flex-wrap: wrap; }
  .exp-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 16px; }
  .exp-date {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    background: rgba(79,124,255,0.1);
    padding: 3px 10px;
    border-radius: 100px;
    white-space: nowrap;
    border: 1px solid rgba(79,124,255,0.2);
  }
  .exp-date.current {
    background: rgba(56,189,248,0.1);
    color: var(--accent3);
    border-color: rgba(56,189,248,0.25);
    animation: pulse-badge 2s ease infinite;
  }
  @keyframes pulse-badge {
    0%, 100% { box-shadow: 0 0 0 0 rgba(56,189,248,0.2); }
    50% { box-shadow: 0 0 0 4px rgba(56,189,248,0); }
  }
  .exp-company {
    font-size: 13px;
    color: var(--accent2);
    margin-bottom: 14px;
    font-weight: 500;
  }
  .exp-bullets { list-style: none; }
  .exp-bullets li {
    font-size: 13.5px;
    color: var(--muted);
    padding: 4px 0 4px 18px;
    position: relative;
    line-height: 1.6;
  }
  .exp-bullets li::before {
    content: '→';
    position: absolute;
    left: 0;
    color: var(--accent);
    font-size: 11px;
    top: 5px;
  }

  /* Current badge */
  .current-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 11px;
    color: var(--accent3);
    font-family: 'DM Mono', monospace;
    letter-spacing: 0.05em;
  }
  .live-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--accent3);
    animation: blink 1.5s ease infinite;
  }
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.2; }
  }

  /* Projects grid */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }
  @media (max-width: 600px) { .projects-grid { grid-template-columns: 1fr; } }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }
  .project-card:hover {
    border-color: rgba(79,124,255,0.4);
    box-shadow: 0 6px 30px rgba(79,124,255,0.12);
    transform: translateY(-3px);
  }
  .project-icon { font-size: 22px; margin-bottom: 10px; }
  .project-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 14px; margin-bottom: 6px; }
  .project-desc { font-size: 12.5px; color: var(--muted); line-height: 1.6; margin-bottom: 12px; }
  .project-stack { display: flex; flex-wrap: wrap; gap: 5px; }
  .tech-tag {
    font-size: 10px;
    font-family: 'DM Mono', monospace;
    padding: 2px 8px;
    border-radius: 4px;
    background: rgba(79,124,255,0.1);
    color: var(--accent);
    border: 1px solid rgba(79,124,255,0.2);
  }

  /* Skills */
  .skills-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; }
  @media (max-width: 600px) { .skills-grid { grid-template-columns: repeat(2, 1fr); } }

  .skill-group {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px;
  }
  .skill-group-title {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--accent2);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .skill-list { display: flex; flex-direction: column; gap: 6px; }
  .skill-item { font-size: 12px; color: var(--muted); display: flex; align-items: center; gap: 6px; }
  .skill-item::before { content: ''; width: 4px; height: 4px; border-radius: 50%; background: var(--accent); flex-shrink: 0; }

  /* Achievements */
  .achieve-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; }
  @media (max-width: 600px) { .achieve-grid { grid-template-columns: 1fr; } }

  .achieve-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px;
    text-align: center;
    transition: all 0.25s;
  }
  .achieve-card:hover { border-color: rgba(79,124,255,0.4); transform: translateY(-2px); }
  .achieve-num {
    font-family: 'Syne', sans-serif;
    font-size: 32px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
  }
  .achieve-label { font-size: 11px; color: var(--muted); margin-top: 6px; }

  /* Education */
  .edu-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px 24px;
    margin-bottom: 12px;
    display: flex;
    gap: 18px;
    align-items: flex-start;
    transition: all 0.25s;
  }
  .edu-item:hover { border-color: rgba(79,124,255,0.4); transform: translateX(4px); }
  .edu-icon {
    width: 40px; height: 40px; border-radius: 10px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    display: flex; align-items: center; justify-content: center;
    font-size: 18px; flex-shrink: 0;
  }
  .edu-degree { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 14px; }
  .edu-school { font-size: 12px; color: var(--accent2); margin: 3px 0; }
  .edu-date { font-size: 11px; color: var(--muted); font-family: 'DM Mono', monospace; }

  /* Certs */
  .cert-row { display: flex; flex-direction: column; gap: 10px; }
  .cert-item {
    display: flex;
    align-items: center;
    gap: 14px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 12px 18px;
    transition: all 0.25s;
  }
  .cert-item:hover { border-color: rgba(79,124,255,0.4); transform: translateX(4px); }
  .cert-logo {
    width: 32px; height: 32px; border-radius: 6px;
    background: linear-gradient(135deg, #0078d4, #005a9e);
    display: flex; align-items: center; justify-content: center;
    font-size: 14px; flex-shrink: 0;
  }
  .cert-name { font-weight: 500; font-size: 13px; }
  .cert-issuer { font-size: 11px; color: var(--muted); }

  /* Social links */
  .social-grid { display: flex; flex-wrap: wrap; gap: 10px; }
  .social-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 18px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    text-decoration: none;
    color: var(--muted);
    font-size: 13px;
    font-weight: 500;
    transition: all 0.25s;
  }
  .social-link:hover {
    color: var(--text);
    border-color: var(--accent);
    box-shadow: 0 4px 20px var(--glow);
    transform: translateY(-2px);
  }
  .social-link svg { width: 16px; height: 16px; }

  /* Animations */
  @keyframes fade-in { from { opacity: 0; } to { opacity: 1; } }
  @keyframes slide-up { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: none; } }
  @keyframes slide-left { from { opacity: 0; transform: translateX(20px); } to { opacity: 1; transform: none; } }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }
  ::-webkit-scrollbar-thumb:hover { background: var(--accent); }

  @media (max-width: 680px) {
    .header-inner { grid-template-columns: 1fr; }
    .github-card { width: 100%; }
    .skills-grid { grid-template-columns: 1fr 1fr; }
    .achieve-grid { grid-template-columns: repeat(3, 1fr); }
  }
</style>
</head>
<body>

<!-- Particles -->
<div class="particles" id="particles"></div>

<div class="container">
  <!-- HEADER -->
  <header>
    <div class="header-inner">
      <div>
        <div class="tag-line">Available for opportunities</div>
        <h1>
          <span>M.N Abdul</span>
          <span>Rahman</span>
        </h1>
        <p class="headline">Creative Content Specialist & Full Stack Developer combining software engineering with digital storytelling to build data-driven experiences.</p>
        <div class="contact-pills">
          <a href="mailto:nazeemrahman434@gmail.com" class="pill">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
            nazeemrahman434@gmail.com
          </a>
          <a href="https://linkedin.com/in/abdul-rahman-a58399259" target="_blank" class="pill">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
            LinkedIn
          </a>
          <a href="https://github.com/Abdul-Rahman127" target="_blank" class="pill">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
            GitHub
          </a>
        </div>
      </div>

      <!-- GitHub Preview Card -->
      <div class="github-card">
        <div class="github-card-header">
          <div class="gh-avatar">AR</div>
          <div>
            <div class="gh-name">Abdul Rahman</div>
            <div class="gh-handle">@Abdul-Rahman127</div>
          </div>
        </div>
        <div class="gh-stats">
          <div class="gh-stat">
            <span class="gh-stat-num">12+</span>
            <span class="gh-stat-label">Repos</span>
          </div>
          <div class="gh-stat">
            <span class="gh-stat-num">5+</span>
            <span class="gh-stat-label">Projects</span>
          </div>
          <div class="gh-stat" style="grid-column: span 2;">
            <span class="gh-stat-num" style="font-size:14px">Full Stack Dev</span>
            <span class="gh-stat-label">JavaScript · Python · C#</span>
          </div>
        </div>
        <div class="gh-langs" style="margin-top:12px">
          <div class="gh-lang-bar"></div>
          <div class="gh-lang-labels">
            <span class="gh-lang-dot"><span class="dot" style="background:#f0db4f"></span>JS</span>
            <span class="gh-lang-dot"><span class="dot" style="background:#b07219"></span>Java</span>
            <span class="gh-lang-dot"><span class="dot" style="background:#e34c26"></span>HTML</span>
            <span class="gh-lang-dot"><span class="dot" style="background:#4f7cff"></span>C#</span>
            <span class="gh-lang-dot"><span class="dot" style="background:#cc342d"></span>PHP</span>
          </div>
        </div>
      </div>
    </div>
  </header>

  <div class="divider"></div>

  <!-- SUMMARY -->
  <section>
    <div class="section-label">Professional Summary</div>
    <p class="summary-text">
      Creative digital marketing professional with proven expertise in social media management, content strategy, and brand growth. Combines software engineering background with creative storytelling to deliver data-driven marketing campaigns that drive measurable results. Experienced in video production, campaign execution, and leveraging generative AI for marketing optimization.
    </p>
  </section>

  <!-- ACHIEVEMENTS -->
  <section>
    <div class="section-label">By the Numbers</div>
    <div class="achieve-grid">
      <div class="achieve-card">
        <div class="achieve-num">40%</div>
        <div class="achieve-label">Operational efficiency improvement via POS system</div>
      </div>
      <div class="achieve-card">
        <div class="achieve-num">4+</div>
        <div class="achieve-label">Social platforms managed (YT, IG, TikTok, FB)</div>
      </div>
      <div class="achieve-card">
        <div class="achieve-num">7+</div>
        <div class="achieve-label">Languages & frameworks in technical stack</div>
      </div>
    </div>
  </section>

  <!-- EXPERIENCE -->
  <section>
    <div class="section-label">Experience</div>

    <!-- Current role -->
    <div class="exp-item">
      <div class="exp-header">
        <div>
          <div style="display:flex;align-items:center;gap:12px;flex-wrap:wrap;margin-bottom:4px;">
            <div class="exp-title">Project Management Intern</div>
            <span class="current-badge"><span class="live-dot"></span> Current Role</span>
          </div>
        </div>
        <div class="exp-date current">2025 – Present</div>
      </div>
      <div class="exp-company">Active Position</div>
      <ul class="exp-bullets">
        <li>Supporting project planning, scheduling, and coordination across cross-functional teams to ensure timely delivery of milestones</li>
        <li>Assisting in risk assessment, stakeholder communication, and resource allocation for ongoing digital and software projects</li>
        <li>Documenting project progress, preparing status reports, and maintaining task management systems for team visibility</li>
        <li>Applying agile and iterative methodologies to streamline workflows and improve team productivity</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-header">
        <div class="exp-title">Creative Content Specialist</div>
        <div class="exp-date">June – Dec 2025</div>
      </div>
      <div class="exp-company">Catchup Digital Marketing & Technologies</div>
      <ul class="exp-bullets">
        <li>Spearheaded creative content strategies for multiple brand clients, developing integrated campaigns combining video production, social media management, and brand positioning</li>
        <li>Led video content production from concept to completion, optimizing for platform-specific requirements and audience preferences to maximize reach and retention</li>
        <li>Leveraged data analytics and performance metrics to continuously optimize content strategy, analyzing engagement rates, conversions, and ROI</li>
        <li>Managed client relationships and provided strategic consultation on digital marketing initiatives and emerging trends</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-header">
        <div class="exp-title">Digital Marketer</div>
        <div class="exp-date">July 2024 – Jan 2025</div>
      </div>
      <div class="exp-company">Freelance — Self-Employed</div>
      <ul class="exp-bullets">
        <li>Executed end-to-end digital marketing campaigns for diverse clients, implementing social media strategies that enhanced brand visibility and audience engagement</li>
        <li>Created compelling visual content including promotional videos, graphics, and multimedia assets tailored to target demographics</li>
        <li>Utilized generative AI tools to enhance content creation efficiency and explore innovative marketing approaches</li>
      </ul>
    </div>
  </section>

  <!-- PROJECTS -->
  <section>
    <div class="section-label">Signature Projects</div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-icon">🛍️</div>
        <div class="project-title">Enterprise POS System</div>
        <div class="project-desc">Streamlined inventory management and integrated business operations for a toy company, boosting efficiency by 40%.</div>
        <div class="project-stack">
          <span class="tech-tag">C#</span>
          <span class="tech-tag">Visual Studio</span>
          <span class="tech-tag">MS SQL Server</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon">📸</div>
        <div class="project-title">Photography Portfolio Platform</div>
        <div class="project-desc">Responsive gallery system with client booking management and SEO-optimized architecture.</div>
        <div class="project-stack">
          <span class="tech-tag">HTML</span>
          <span class="tech-tag">JavaScript</span>
          <span class="tech-tag">PHP</span>
          <span class="tech-tag">XAMPP</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon">🎥</div>
        <div class="project-title">Cloud Video Platform</div>
        <div class="project-desc">Intuitive cloud-based video platform with advanced library management and responsive cross-device design.</div>
        <div class="project-stack">
          <span class="tech-tag">Figma</span>
          <span class="tech-tag">Draw.io</span>
          <span class="tech-tag">Canva</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon">🚌</div>
        <div class="project-title">Transport Reservation System</div>
        <div class="project-desc">Real-time booking system with dynamic schedule management and automated seat allocation.</div>
        <div class="project-stack">
          <span class="tech-tag">Java</span>
          <span class="tech-tag">Visual Studio</span>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section>
    <div class="section-label">Technical Arsenal</div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-title">Languages</div>
        <div class="skill-list">
          <span class="skill-item">JavaScript</span>
          <span class="skill-item">Python</span>
          <span class="skill-item">Java</span>
          <span class="skill-item">C# / C++</span>
          <span class="skill-item">PHP</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Frontend</div>
        <div class="skill-list">
          <span class="skill-item">HTML5 / CSS3</span>
          <span class="skill-item">Responsive Design</span>
          <span class="skill-item">Figma</span>
          <span class="skill-item">UI/UX Principles</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Tools</div>
        <div class="skill-list">
          <span class="skill-item">VS Code / GitHub</span>
          <span class="skill-item">MySQL</span>
          <span class="skill-item">Power BI</span>
          <span class="skill-item">XAMPP</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Marketing</div>
        <div class="skill-list">
          <span class="skill-item">Social Media Strategy</span>
          <span class="skill-item">SEO / SEM</span>
          <span class="skill-item">Email Marketing</span>
          <span class="skill-item">Campaign Analytics</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Creative</div>
        <div class="skill-list">
          <span class="skill-item">Video Production</span>
          <span class="skill-item">Brand Design</span>
          <span class="skill-item">Content Strategy</span>
          <span class="skill-item">Storytelling</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">AI & Data</div>
        <div class="skill-list">
          <span class="skill-item">Generative AI Tools</span>
          <span class="skill-item">Data Analysis</span>
          <span class="skill-item">A/B Testing</span>
          <span class="skill-item">Performance Analytics</span>
        </div>
      </div>
    </div>
  </section>

  <!-- EDUCATION -->
  <section>
    <div class="section-label">Education</div>
    <div class="edu-item">
      <div class="edu-icon">🎓</div>
      <div>
        <div class="edu-degree">BSc (Hons) Computer Science in Software Engineering</div>
        <div class="edu-school">Kingston University, UK</div>
        <div class="edu-date">Sept 2024 – Sept 2025</div>
      </div>
    </div>
    <div class="edu-item">
      <div class="edu-icon">📚</div>
      <div>
        <div class="edu-degree">Pearson BTEC Level 5 HND in Computing Software Engineering</div>
        <div class="edu-school">London Metropolitan University, UK</div>
        <div class="edu-date">Sept 2021 – Sept 2024</div>
      </div>
    </div>
  </section>

  <!-- CERTIFICATIONS -->
  <section>
    <div class="section-label">Certifications</div>
    <div class="cert-row">
      <div class="cert-item">
        <div class="cert-logo">M</div>
        <div>
          <div class="cert-name">Career Essentials in Data Analysis</div>
          <div class="cert-issuer">Microsoft & LinkedIn Learning</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-logo">🤖</div>
        <div>
          <div class="cert-name">Career Essentials in Generative AI</div>
          <div class="cert-issuer">Microsoft & LinkedIn Learning</div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONNECT -->
  <section>
    <div class="section-label">Connect</div>
    <div class="social-grid">
      <a href="mailto:nazeemrahman434@gmail.com" class="social-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
        Email
      </a>
      <a href="https://linkedin.com/in/abdul-rahman-a58399259" target="_blank" class="social-link">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a href="https://github.com/Abdul-Rahman127" target="_blank" class="social-link">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
        GitHub
      </a>
      <a href="https://www.instagram.com/abd.rahman.07/" target="_blank" class="social-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
        Instagram
      </a>
      <a href="https://www.tiktok.com/@abd.rahman.07" target="_blank" class="social-link">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-2.88 2.5 2.89 2.89 0 0 1-2.89-2.89 2.89 2.89 0 0 1 2.89-2.89c.28 0 .54.04.79.1V9.01a6.33 6.33 0 0 0-.79-.05 6.34 6.34 0 0 0-6.34 6.34 6.34 6.34 0 0 0 6.34 6.34 6.34 6.34 0 0 0 6.33-6.34l-.01-8.83a8.18 8.18 0 0 0 4.78 1.52V4.56a4.85 4.85 0 0 1-1-.13z"/></svg>
        TikTok
      </a>
      <a href="https://web.facebook.com/abdul.rhman.186590" target="_blank" class="social-link">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/></svg>
        Facebook
      </a>
    </div>
  </section>

</div>

<script>
  // Generate floating particles
  const container = document.getElementById('particles');
  for (let i = 0; i < 30; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.cssText = `
      left: ${Math.random() * 100}%;
      animation-duration: ${6 + Math.random() * 10}s;
      animation-delay: ${Math.random() * 10}s;
      width: ${1 + Math.random() * 2}px;
      height: ${1 + Math.random() * 2}px;
      opacity: ${0.2 + Math.random() * 0.4};
      background: ${['#4f7cff','#a78bfa','#38bdf8'][Math.floor(Math.random()*3)]};
    `;
    container.appendChild(p);
  }

  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('section').forEach(s => observer.observe(s));

  // Counter animation for achieve numbers
  function animateCounters() {
    document.querySelectorAll('.achieve-num').forEach(el => {
      const text = el.textContent;
      const num = parseFloat(text);
      if (isNaN(num)) return;
      const suffix = text.replace(num.toString(), '');
      let start = 0;
      const step = num / 40;
      const timer = setInterval(() => {
        start = Math.min(start + step, num);
        el.textContent = (Number.isInteger(num) ? Math.round(start) : start.toFixed(0)) + suffix;
        if (start >= num) clearInterval(timer);
      }, 30);
    });
  }

  const counterObserver = new IntersectionObserver((entries) => {
    if (entries[0].isIntersecting) { animateCounters(); counterObserver.disconnect(); }
  }, { threshold: 0.5 });

  const achieveSection = document.querySelector('.achieve-grid');
  if (achieveSection) counterObserver.observe(achieveSection);
</script>
</body>
</html>
