<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Yash Patel — DevOps Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080c10;
    --surface: #0d1117;
    --card: #111820;
    --border: #1e2d3d;
    --green: #39d353;
    --green-dim: #196127;
    --cyan: #58d9f9;
    --orange: #ff8c42;
    --text: #e6edf3;
    --muted: #7d8590;
    --accent: #39d353;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(57,211,83,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(57,211,83,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 60px 0 40px;
    animation: fadeUp 0.8s ease both;
  }

  .hero-tag {
    display: inline-block;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--green);
    border: 1px solid var(--green-dim);
    padding: 4px 14px;
    border-radius: 2px;
    margin-bottom: 20px;
  }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(48px, 9vw, 84px);
    font-weight: 800;
    letter-spacing: -2px;
    line-height: 1;
    background: linear-gradient(135deg, #ffffff 0%, #39d353 50%, #58d9f9 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
  }

  .hero-sub {
    font-size: 13px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 32px;
  }

  .hero-badges {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 3px;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.5px;
    text-decoration: none;
    transition: all 0.2s;
  }
  .badge:hover { transform: translateY(-2px); filter: brightness(1.2); }
  .badge-linkedin { background: #0A66C2; color: #fff; }
  .badge-email { background: #EA4335; color: #fff; }
  .badge-github { background: #21262d; color: #fff; border: 1px solid var(--border); }

  /* ── SECTION HEADERS ── */
  .section {
    margin: 56px 0 0;
    animation: fadeUp 0.6s ease both;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }

  .section-label {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--green);
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, var(--border), transparent);
  }

  /* ── TERMINAL BLOCK ── */
  .terminal {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
  }

  .terminal-bar {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 10px 16px;
    background: #161b22;
    border-bottom: 1px solid var(--border);
  }

  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #ffbd2e; }
  .dot-g { background: #28c840; }

  .terminal-title {
    margin-left: auto;
    font-size: 11px;
    color: var(--muted);
  }

  .terminal-body {
    padding: 20px 24px;
    font-size: 13px;
    line-height: 1.8;
  }

  .prompt { color: var(--green); }
  .cmd { color: var(--cyan); }
  .comment { color: var(--muted); }
  .val { color: var(--orange); }
  .str { color: #a5d6ff; }
  .key { color: var(--green); }

  /* ── SKILLS GRID ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 16px 18px;
    display: flex;
    align-items: center;
    gap: 12px;
    transition: all 0.25s;
    cursor: default;
  }

  .skill-card:hover {
    border-color: var(--green);
    background: #0f1d12;
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(57,211,83,0.1);
  }

  .skill-icon {
    width: 36px;
    height: 36px;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
  }

  .skill-name { font-size: 13px; font-weight: 500; color: var(--text); }
  .skill-sub { font-size: 10px; color: var(--muted); margin-top: 2px; }

  /* ── PROJECT CARDS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media (max-width: 600px) {
    .projects-grid { grid-template-columns: 1fr; }
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 24px;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(to right, var(--green), var(--cyan));
    opacity: 0;
    transition: opacity 0.25s;
  }

  .project-card:hover {
    border-color: var(--green);
    transform: translateY(-3px);
    box-shadow: 0 12px 32px rgba(57,211,83,0.08);
  }
  .project-card:hover::before { opacity: 1; }

  .project-icon { font-size: 28px; margin-bottom: 12px; }
  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 8px;
  }
  .project-desc { font-size: 11px; color: var(--muted); line-height: 1.7; }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 14px;
  }

  .tag {
    font-size: 10px;
    padding: 3px 8px;
    border-radius: 2px;
    background: rgba(57,211,83,0.08);
    color: var(--green);
    border: 1px solid rgba(57,211,83,0.2);
  }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media (max-width: 600px) {
    .stats-row { grid-template-columns: 1fr; }
  }

  .stat-img {
    width: 100%;
    border-radius: 8px;
    border: 1px solid var(--border);
    display: block;
  }

  .streak-wrap {
    margin-top: 16px;
    text-align: center;
  }

  /* ── CONTRIBUTION CHART ── */
  .contrib-wrap {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    overflow: hidden;
  }

  .contrib-wrap img { width: 100%; border-radius: 4px; }

  /* ── LEARNING ── */
  .learning-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 10px;
  }

  .learn-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 14px 16px;
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 12px;
    color: var(--text);
    transition: all 0.2s;
  }

  .learn-item:hover {
    border-color: var(--cyan);
    background: #0a1520;
  }

  .learn-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--green);
    flex-shrink: 0;
    box-shadow: 0 0 6px var(--green);
    animation: pulse 2s ease infinite;
  }

  /* ── PRINCIPLES ── */
  .principles-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 10px;
  }

  .principle {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 18px 16px;
    text-align: center;
    transition: all 0.2s;
  }

  .principle:hover {
    border-color: var(--green-dim);
    background: #0f1d12;
  }

  .principle-icon { font-size: 24px; margin-bottom: 8px; }
  .principle-text { font-size: 11px; color: var(--muted); line-height: 1.5; }

  /* ── FOOTER ── */
  .footer {
    margin-top: 72px;
    text-align: center;
    padding: 32px 0;
    border-top: 1px solid var(--border);
  }

  .footer-text {
    font-family: 'Syne', sans-serif;
    font-size: 18px;
    font-weight: 700;
    background: linear-gradient(90deg, var(--green), var(--cyan));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
  }

  .footer-sub { font-size: 11px; color: var(--muted); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  .section:nth-child(1) { animation-delay: 0.0s; }
  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }
  .section:nth-child(6) { animation-delay: 0.5s; }
  .section:nth-child(7) { animation-delay: 0.6s; }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-tag">Open to Opportunities</div>
    <h1>Yash Patel</h1>
    <div class="hero-sub">DevOps Engineer &nbsp;·&nbsp; Cloud Infrastructure &nbsp;·&nbsp; Automation</div>
    <div class="hero-badges">
      <a class="badge badge-linkedin" href="https://linkedin.com/in/yash-patel-b58626226" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="badge badge-email" href="mailto:yashpatel22150@gmail.com">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Email
      </a>
      <a class="badge badge-github" href="https://github.com/YashPatel0" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
        GitHub
      </a>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">about</span>
      <div class="section-line"></div>
    </div>
    <div class="terminal">
      <div class="terminal-bar">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="terminal-title">yash@devops ~ zsh</span>
      </div>
      <div class="terminal-body">
        <div><span class="prompt">❯</span> <span class="cmd">cat</span> about.yaml</div>
        <br>
        <div><span class="key">name</span>: <span class="str">Yash Patel</span></div>
        <div><span class="key">role</span>: <span class="str">DevOps & Cloud Engineer</span></div>
        <div><span class="key">location</span>: <span class="str">India 🇮🇳</span></div>
        <div><span class="key">status</span>: <span class="val">Actively Building & Learning</span></div>
        <div><span class="key">focus</span>:</div>
        <div>&nbsp; - <span class="str">Designing scalable cloud infrastructure on AWS</span></div>
        <div>&nbsp; - <span class="str">Containerising apps with Docker & Kubernetes</span></div>
        <div>&nbsp; - <span class="str">Infrastructure as Code with Terraform</span></div>
        <div>&nbsp; - <span class="str">Automating CI/CD pipelines end-to-end</span></div>
        <div>&nbsp; - <span class="str">Linux server administration & Bash scripting</span></div>
        <br>
        <div><span class="prompt">❯</span> <span class="comment"># Building reliable, production-ready systems.</span></div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">tech stack</span>
      <div class="section-line"></div>
    </div>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-icon" style="background:#1a2535">🐧</div>
        <div><div class="skill-name">Linux</div><div class="skill-sub">Server Admin · Bash</div></div>
      </div>
      <div class="skill-card">
        <div class="skill-icon" style="background:#1f2010">
          <img src="https://cdn.simpleicons.org/amazonaws/FF9900" width="22"/>
        </div>
        <div><div class="skill-name">AWS</div><div class="skill-sub">EC2 · VPC · S3 · IAM</div></div>
      </div>
      <div class="skill-card">
        <div class="skill-icon" style="background:#1a1030">
          <img src="https://cdn.simpleicons.org/amazonaws/527FFF" width="22"/>
        </div>
        <div><div class="skill-name">RDS · EKS</div><div class="skill-sub">Managed DB & K8s</div></div>
      </div>
      <div class="skill-card">
        <div class="skill-icon" style="background:#0f1e2a">
          <img src="https://cdn.simpleicons.org/docker/2496ED" width="22"/>
        </div>
        <div><div class="skill-name">Docker</div><div class="skill-sub">Images · Containers</div></div>
      </div>
      <div class="skill-card">
        <div class="skill-icon" style="background:#0f1826">
          <img src="https://cdn.simpleicons.org/kubernetes/326CE5" width="22"/>
        </div>
        <div><div class="skill-name">Kubernetes</div><div class="skill-sub">Deploy · Svc · Ingress</div></div>
      </div>
      <div class="skill-card">
        <div class="skill-icon" style="background:#1a1230">
          <img src="https://cdn.simpleicons.org/terraform/7B42BC" width="22"/>
        </div>
        <div><div class="skill-name">Terraform</div><div class="skill-sub">Modular IaC</div></div>
      </div>
      <div class="skill-card">
        <div class="skill-icon" style="background:#1a1410">
          <img src="https://cdn.simpleicons.org/git/F05032" width="22"/>
        </div>
        <div><div class="skill-name">Git & GitHub</div><div class="skill-sub">Version Control</div></div>
      </div>
      <div class="skill-card">
        <div class="skill-icon" style="background:#0f1822">
          <img src="https://cdn.simpleicons.org/githubactions/2088FF" width="22"/>
        </div>
        <div><div class="skill-name">GitHub Actions</div><div class="skill-sub">CI/CD Pipelines</div></div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">projects</span>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-icon">⚓</div>
        <div class="project-name">Kubernetes Deployment</div>
        <div class="project-desc">Dockerized full-stack app deployed on Kubernetes with Services, Ingress, and production-ready manifests.</div>
        <div class="project-tags">
          <span class="tag">Docker</span>
          <span class="tag">Kubernetes</span>
          <span class="tag">NGINX Ingress</span>
          <span class="tag">EKS</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon">🏗️</div>
        <div class="project-name">AWS Infra Automation</div>
        <div class="project-desc">Modular Terraform architecture — Multi-AZ VPC, private/public subnets, NAT Gateway, and EKS cluster provisioning.</div>
        <div class="project-tags">
          <span class="tag">Terraform</span>
          <span class="tag">AWS VPC</span>
          <span class="tag">EKS</span>
          <span class="tag">NAT GW</span>
        </div>
      </div>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">github stats</span>
      <div class="section-line"></div>
    </div>
    <div class="stats-row">
      <img class="stat-img" src="https://github-readme-stats.vercel.app/api?username=YashPatel0&show_icons=true&theme=github_dark&hide_border=true&title_color=39d353&icon_color=39d353&text_color=c9d1d9&bg_color=0d1117&rank_icon=github" alt="Stats" />
      <img class="stat-img" src="https://github-readme-stats.vercel.app/api/top-langs/?username=YashPatel0&layout=compact&theme=github_dark&hide_border=true&title_color=39d353&text_color=c9d1d9&bg_color=0d1117" alt="Languages" />
    </div>
    <div class="streak-wrap">
      <img class="stat-img" src="https://streak-stats.demolab.com?user=YashPatel0&theme=github-dark-blue&hide_border=true&ring=39d353&fire=39d353&currStreakLabel=39d353&sideLabels=7d8590&dates=7d8590&background=0d1117" alt="Streak" style="max-width:560px;margin:16px auto;" />
    </div>
  </div>

  <!-- CONTRIBUTION CHART -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">contribution activity</span>
      <div class="section-line"></div>
    </div>
    <div class="contrib-wrap">
      <img src="https://ghchart.rshah.org/39d353/YashPatel0" alt="Contribution Chart" style="width:100%;border-radius:4px;"/>
    </div>
    <div style="margin-top:16px;">
      <img class="stat-img" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=YashPatel0&theme=github_dark" alt="Summary" style="border-radius:8px;"/>
    </div>
  </div>

  <!-- LEARNING -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">currently learning</span>
      <div class="section-line"></div>
    </div>
    <div class="learning-grid">
      <div class="learn-item"><div class="learn-dot"></div>Helm Charts & HPA</div>
      <div class="learn-item"><div class="learn-dot"></div>Prometheus & Grafana</div>
      <div class="learn-item"><div class="learn-dot"></div>Production EKS Patterns</div>
      <div class="learn-item"><div class="learn-dot"></div>GitOps — ArgoCD</div>
      <div class="learn-item"><div class="learn-dot"></div>Advanced CI/CD</div>
      <div class="learn-item"><div class="learn-dot"></div>AWS Networking Deep Dive</div>
    </div>
  </div>

  <!-- PRINCIPLES -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">principles</span>
      <div class="section-line"></div>
    </div>
    <div class="principles-grid">
      <div class="principle"><div class="principle-icon">🤖</div><div class="principle-text">Automate everything repetitive</div></div>
      <div class="principle"><div class="principle-icon">📜</div><div class="principle-text">Infrastructure as Code, always</div></div>
      <div class="principle"><div class="principle-icon">📈</div><div class="principle-text">Design for scale & fault tolerance</div></div>
      <div class="principle"><div class="principle-icon">👁️</div><div class="principle-text">Monitor apps & infra continuously</div></div>
      <div class="principle"><div class="principle-icon">🔄</div><div class="principle-text">Improve deployment reliability</div></div>
      <div class="principle"><div class="principle-icon">🔐</div><div class="principle-text">Security built in, not bolted on</div></div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-text">Building Infrastructure. Automating Deployments. Improving Reliability.</div>
    <div class="footer-sub">
      <img src="https://komarev.com/ghpvc/?username=YashPatel0&style=flat-square&color=39d353&label=profile+views" alt="views" style="vertical-align:middle;margin-top:12px;"/>
    </div>
  </div>

</div>
</body>
</html>
