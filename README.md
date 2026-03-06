<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Vidhusankar | AI Engineer – GitHub Profile Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;600&display=swap" rel="stylesheet"/>
<style>
  :root {
    --green: #00ff41;
    --green-dim: #00cc33;
    --green-dark: #003b00;
    --green-glow: rgba(0,255,65,0.35);
    --black: #000000;
    --bg: #020d02;
    --panel: rgba(0,20,0,0.85);
    --border: rgba(0,255,65,0.25);
    --text: #b8ffb8;
    --accent: #39ff14;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Share Tech Mono', monospace;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ── MATRIX CANVAS ── */
  #matrix-canvas {
    position: fixed; top: 0; left: 0;
    width: 100%; height: 100%;
    z-index: 0; opacity: 0.18;
    pointer-events: none;
  }

  /* ── CONTENT WRAPPER ── */
  .wrapper {
    position: relative; z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px 80px;
  }

  /* ── NEURAL NET HEADER ── */
  #neural-header {
    width: 100%;
    height: 220px;
    position: relative;
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 36px;
    background: #000;
  }
  #neural-canvas { width: 100%; height: 100%; display: block; }
  .header-overlay {
    position: absolute; inset: 0;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    pointer-events: none;
  }
  .header-name {
    font-family: 'Orbitron', monospace;
    font-size: clamp(1.6rem, 5vw, 3rem);
    font-weight: 900;
    color: var(--green);
    text-shadow: 0 0 20px var(--green), 0 0 40px var(--green-glow);
    letter-spacing: 0.12em;
    text-align: center;
  }
  .header-sub {
    font-family: 'Rajdhani', sans-serif;
    font-size: clamp(0.85rem, 2.5vw, 1.15rem);
    font-weight: 300;
    color: var(--green-dim);
    letter-spacing: 0.3em;
    text-transform: uppercase;
    margin-top: 8px;
  }

  /* ── TYPING BANNER ── */
  .typing-section {
    text-align: center;
    margin-bottom: 40px;
  }
  .typing-wrap {
    display: inline-block;
    font-family: 'Share Tech Mono', monospace;
    font-size: clamp(0.9rem, 2.2vw, 1.15rem);
    color: var(--green);
    border-right: 2px solid var(--green);
    padding-right: 4px;
    white-space: nowrap;
    overflow: hidden;
    animation: typing 3.5s steps(40) infinite alternate, blink 0.7s step-end infinite;
    max-width: 100%;
  }
  @keyframes typing {
    0%   { width: 0 }
    100% { width: 100% }
  }
  @keyframes blink {
    50% { border-color: transparent }
  }

  /* ── PANELS ── */
  .panel {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 28px 32px;
    margin-bottom: 28px;
    box-shadow: 0 0 30px rgba(0,255,65,0.05);
    transition: box-shadow 0.3s;
  }
  .panel:hover { box-shadow: 0 0 40px rgba(0,255,65,0.12); }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: 0.85rem;
    font-weight: 700;
    color: var(--green);
    letter-spacing: 0.25em;
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex; align-items: center; gap: 10px;
  }
  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, var(--border), transparent);
  }

  /* ── TERMINAL BLOCK ── */
  .terminal {
    background: #000;
    border: 1px solid var(--border);
    border-radius: 6px;
    overflow: hidden;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.88rem;
  }
  .terminal-bar {
    background: #0a1a0a;
    padding: 8px 14px;
    display: flex; align-items: center; gap: 8px;
    border-bottom: 1px solid var(--border);
  }
  .dot { width: 11px; height: 11px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }
  .terminal-body { padding: 20px 24px; line-height: 1.85; }
  .prompt { color: var(--green); }
  .cmd { color: #fff; }
  .output { color: #7fffb2; padding-left: 16px; }
  .output span { color: var(--green); }

  /* ── PROJECT CARDS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 18px;
  }
  .project-card {
    background: #000;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    cursor: default;
    transition: border-color 0.3s, transform 0.3s, box-shadow 0.3s;
    position: relative;
    overflow: hidden;
  }
  .project-card::before {
    content: '';
    position: absolute;
    top: -60%; left: -60%;
    width: 200%; height: 200%;
    background: radial-gradient(circle, rgba(0,255,65,0.06) 0%, transparent 60%);
    opacity: 0;
    transition: opacity 0.4s;
  }
  .project-card:hover { border-color: var(--green); transform: translateY(-4px); box-shadow: 0 8px 30px rgba(0,255,65,0.15); }
  .project-card:hover::before { opacity: 1; }
  .project-icon { font-size: 1.8rem; margin-bottom: 10px; }
  .project-name {
    font-family: 'Orbitron', monospace;
    font-size: 0.82rem;
    font-weight: 700;
    color: var(--green);
    letter-spacing: 0.08em;
    margin-bottom: 8px;
  }
  .project-desc {
    font-size: 0.8rem;
    color: #88cc88;
    line-height: 1.6;
    margin-bottom: 12px;
  }
  .tag {
    display: inline-block;
    background: rgba(0,255,65,0.08);
    border: 1px solid rgba(0,255,65,0.2);
    color: var(--green-dim);
    border-radius: 4px;
    padding: 2px 8px;
    font-size: 0.7rem;
    margin: 2px 2px 0 0;
  }

  /* ── SKILL ICONS ── */
  .skills-grid {
    display: flex; flex-wrap: wrap; gap: 12px;
  }
  .skill-chip {
    display: flex; align-items: center; gap: 8px;
    background: rgba(0,255,65,0.06);
    border: 1px solid rgba(0,255,65,0.2);
    border-radius: 6px;
    padding: 8px 14px;
    font-size: 0.82rem;
    color: var(--green-dim);
    transition: all 0.25s;
    cursor: default;
  }
  .skill-chip:hover { background: rgba(0,255,65,0.15); border-color: var(--green); color: var(--green); }
  .skill-chip .icon { font-size: 1.1rem; }

  /* ── STATS GRID ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 18px;
  }
  .stat-card {
    background: #000;
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
    text-align: center;
  }
  .stat-card img {
    width: 100%; height: auto;
    display: block;
    filter: hue-rotate(100deg) saturate(1.5);
  }
  .stat-placeholder {
    padding: 24px 16px;
    font-size: 0.78rem;
    color: #44aa44;
    line-height: 2;
  }
  .stat-number {
    display: block;
    font-family: 'Orbitron', monospace;
    font-size: 1.8rem;
    color: var(--green);
    text-shadow: 0 0 10px var(--green-glow);
    font-weight: 700;
  }
  .stat-label {
    font-size: 0.72rem;
    color: #55aa55;
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  /* ── 3D CONTRIBUTION CUBE ── */
  #cube-section { text-align: center; }
  #cube-canvas-wrap {
    display: inline-block;
    width: 160px; height: 160px;
    position: relative;
    margin: 10px auto 0;
  }
  #cube-canvas { width: 160px; height: 160px; }

  /* ── SNAKE SVG ── */
  .snake-wrap {
    background: #000;
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
    text-align: center;
    padding: 10px;
  }
  .snake-wrap img { max-width: 100%; border-radius: 4px; }

  /* ── ACHIEVEMENTS ── */
  .achievements-list { list-style: none; }
  .achievements-list li {
    padding: 12px 0;
    border-bottom: 1px solid rgba(0,255,65,0.08);
    display: flex; align-items: flex-start; gap: 12px;
    font-size: 0.88rem;
    color: #99dd99;
  }
  .achievements-list li:last-child { border-bottom: none; }
  .ach-icon { font-size: 1.3rem; flex-shrink: 0; margin-top: 1px; }
  .ach-text strong { color: var(--green); display: block; margin-bottom: 2px; font-family: 'Orbitron', monospace; font-size: 0.78rem; letter-spacing: 0.06em; }

  /* ── CONTACT ── */
  .contact-row {
    display: flex; flex-wrap: wrap; gap: 14px; justify-content: center;
  }
  .contact-btn {
    display: flex; align-items: center; gap: 8px;
    background: rgba(0,255,65,0.07);
    border: 1px solid rgba(0,255,65,0.3);
    border-radius: 6px;
    padding: 10px 20px;
    color: var(--green);
    font-family: 'Orbitron', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.12em;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.25s;
  }
  .contact-btn:hover { background: rgba(0,255,65,0.18); box-shadow: 0 0 14px var(--green-glow); }

  /* ── MOTTO ── */
  .motto {
    text-align: center;
    font-family: 'Rajdhani', sans-serif;
    font-size: clamp(1rem, 2.8vw, 1.3rem);
    font-weight: 600;
    color: var(--green);
    letter-spacing: 0.05em;
    padding: 28px 20px;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    margin-bottom: 28px;
    text-shadow: 0 0 12px rgba(0,255,65,0.3);
  }
  .motto::before { content: '"'; font-size: 2em; opacity: 0.3; line-height: 0; vertical-align: -0.4em; margin-right: 6px; }
  .motto::after  { content: '"'; font-size: 2em; opacity: 0.3; line-height: 0; vertical-align: -0.4em; margin-left:  6px; }

  /* ── SCROLL REVEAL ── */
  .reveal {
    opacity: 0; transform: translateY(28px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ── SCANLINE OVERLAY ── */
  .scanlines {
    position: fixed; inset: 0; z-index: 2;
    pointer-events: none;
    background: repeating-linear-gradient(
      to bottom,
      transparent 0px,
      transparent 3px,
      rgba(0,0,0,0.08) 3px,
      rgba(0,0,0,0.08) 4px
    );
  }

  /* ── RESPONSIVE ── */
  @media(max-width:600px) {
    .wrapper { padding: 20px 14px 60px; }
    .panel { padding: 20px 16px; }
    .terminal-body { padding: 14px 16px; }
    #neural-header { height: 160px; }
  }
</style>
</head>
<body>

<!-- Matrix rain -->
<canvas id="matrix-canvas"></canvas>

<!-- Scanlines -->
<div class="scanlines"></div>

<div class="wrapper">

  <!-- ══ NEURAL NET HEADER ══ -->
  <div id="neural-header" class="reveal">
    <canvas id="neural-canvas"></canvas>
    <div class="header-overlay">
      <div class="header-name">VIDHUSANKAR</div>
      <div class="header-sub">AI Engineer &nbsp;·&nbsp; ML Developer &nbsp;·&nbsp; Computer Vision</div>
    </div>
  </div>

  <!-- ══ TYPING BANNER ══ -->
  <div class="typing-section reveal">
    <div class="typing-wrap">// Building intelligence, one model at a time...</div>
  </div>

  <!-- ══ MOTTO ══ -->
  <div class="motto reveal">
    I don't just learn technology — I create with it.
  </div>

  <!-- ══ TERMINAL PROFILE ══ -->
  <div class="panel reveal">
    <div class="section-title">// SYSTEM PROFILE</div>
    <div class="terminal">
      <div class="terminal-bar">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span style="font-size:0.75rem;color:#444;margin-left:8px">vidhusankar@hozo:~$</span>
      </div>
      <div class="terminal-body">
        <div><span class="prompt">➜ </span><span class="cmd">whoami</span></div>
        <div class="output"><span>Vidhusankar Hozo</span> — AI Engineer & ML Developer</div>
        <br/>
        <div><span class="prompt">➜ </span><span class="cmd">cat role.txt</span></div>
        <div class="output">Building AI systems that see, think, and decide.</div>
        <div class="output">Specialised in Computer Vision · NLP · Autonomous Systems</div>
        <br/>
        <div><span class="prompt">➜ </span><span class="cmd">system_status --verbose</span></div>
        <div class="output"><span>[ACTIVE]</span> Researching Semantic Image Communication</div>
        <div class="output"><span>[ACTIVE]</span> Autonomous Drone Navigation Stack</div>
        <div class="output"><span>[ACTIVE]</span> Real-time Identify.ai Pipeline</div>
        <br/>
        <div><span class="prompt">➜ </span><span class="cmd">echo $CURRENT_FOCUS</span></div>
        <div class="output"><span>Deep Learning</span> · <span>Edge AI</span> · <span>Robotics Vision</span></div>
      </div>
    </div>
  </div>

  <!-- ══ FEATURED PROJECTS ══ -->
  <div class="panel reveal">
    <div class="section-title">// FEATURED PROJECTS</div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-icon">🧠</div>
        <div class="project-name">IDENTIFY.AI</div>
        <div class="project-desc">Real-time AI identification pipeline with high-accuracy recognition at the edge.</div>
        <div><span class="tag">Python</span><span class="tag">OpenCV</span><span class="tag">TensorFlow</span></div>
      </div>
      <div class="project-card">
        <div class="project-icon">🚁</div>
        <div class="project-name">AUTONOMOUS DRONE</div>
        <div class="project-desc">Vision-guided autonomous navigation stack for UAVs competing in SAEINDIA & NIDAR.</div>
        <div><span class="tag">ROS</span><span class="tag">C++</span><span class="tag">YOLO</span></div>
      </div>
      <div class="project-card">
        <div class="project-icon">📡</div>
        <div class="project-name">SEMANTIC IMAGE COMM.</div>
        <div class="project-desc">Bandwidth-efficient deep learning system for semantic image transmission over noisy channels.</div>
        <div><span class="tag">PyTorch</span><span class="tag">Encoder</span><span class="tag">Channel AI</span></div>
      </div>
    </div>
  </div>

  <!-- ══ TECH STACK ══ -->
  <div class="panel reveal">
    <div class="section-title">// TECH STACK</div>
    <div class="skills-grid">
      <div class="skill-chip"><span class="icon">🐍</span> Python</div>
      <div class="skill-chip"><span class="icon">⚡</span> C++</div>
      <div class="skill-chip"><span class="icon">📊</span> R</div>
      <div class="skill-chip"><span class="icon">🔥</span> PyTorch</div>
      <div class="skill-chip"><span class="icon">🧠</span> TensorFlow</div>
      <div class="skill-chip"><span class="icon">👁</span> OpenCV</div>
      <div class="skill-chip"><span class="icon">🤖</span> ROS</div>
      <div class="skill-chip"><span class="icon">🗃</span> SQL</div>
      <div class="skill-chip"><span class="icon">🔀</span> Git</div>
      <div class="skill-chip"><span class="icon">🐙</span> GitHub</div>
      <div class="skill-chip"><span class="icon">💻</span> VS Code</div>
      <div class="skill-chip"><span class="icon">☁</span> Linux</div>
    </div>
  </div>

  <!-- ══ GITHUB ANALYTICS ══ -->
  <div class="panel reveal">
    <div class="section-title">// GITHUB ANALYTICS</div>
    <div class="stats-grid">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=Vidhusankar-hozo&show_icons=true&theme=chartreuse-dark&hide_border=true&bg_color=000000&title_color=00ff41&icon_color=00ff41&text_color=b8ffb8" 
             alt="GitHub Stats"
             onerror="this.style.display='none';this.nextElementSibling.style.display='block'"/>
        <div class="stat-placeholder" style="display:none">
          <span class="stat-number">∞</span>
          <span class="stat-label">Commits &amp; Counting</span>
        </div>
      </div>
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Vidhusankar-hozo&layout=compact&theme=chartreuse-dark&hide_border=true&bg_color=000000&title_color=00ff41&text_color=b8ffb8"
             alt="Top Languages"
             onerror="this.style.display='none';this.nextElementSibling.style.display='block'"/>
        <div class="stat-placeholder" style="display:none">
          <span class="stat-number">5+</span>
          <span class="stat-label">Languages</span>
        </div>
      </div>
      <div class="stat-card" style="grid-column: 1 / -1;">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=Vidhusankar-hozo&theme=chartreuse-dark&hide_border=true&background=000000&ring=00ff41&fire=00ff41&currStreakLabel=00ff41"
             alt="Streak Stats"
             onerror="this.style.display='none';this.nextElementSibling.style.display='block'"/>
        <div class="stat-placeholder" style="display:none">
          <span class="stat-number">🔥</span>
          <span class="stat-label">Streak Stats Loading...</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ══ 3D CONTRIBUTION CUBE ══ -->
  <div class="panel reveal" id="cube-section">
    <div class="section-title">// 3D CONTRIBUTION CUBE</div>
    <div id="cube-canvas-wrap">
      <canvas id="cube-canvas" width="160" height="160"></canvas>
    </div>
    <p style="font-size:0.75rem;color:#44aa44;margin-top:14px;text-align:center;letter-spacing:0.1em">
      CONTRIBUTION VISUALIZER — LIVE RENDER
    </p>
  </div>

  <!-- ══ SNAKE CONTRIBUTION ══ -->
  <div class="panel reveal">
    <div class="section-title">// CONTRIBUTION SNAKE</div>
    <div class="snake-wrap">
      <img src="https://raw.githubusercontent.com/Vidhusankar-hozo/Vidhusankar-hozo/output/github-contribution-grid-snake-dark.svg"
           alt="Contribution Snake"
           onerror="this.outerHTML='<p style=\'color:#44aa44;font-size:0.8rem;padding:20px;text-align:center\'>⚡ Snake animation renders live on GitHub after Actions workflow runs.</p>'"/>
    </div>
  </div>

  <!-- ══ ACHIEVEMENTS ══ -->
  <div class="panel reveal">
    <div class="section-title">// ACHIEVEMENTS</div>
    <ul class="achievements-list">
      <li>
        <span class="ach-icon">🥇</span>
        <div class="ach-text">
          <strong>DHRUVA'25 PROJECT EXPO — WINNER</strong>
          Top prize for innovative AI project demonstration at Dhruva'25.
        </div>
      </li>
      <li>
        <span class="ach-icon">🚁</span>
        <div class="ach-text">
          <strong>SAEINDIA DRONE COMPETITION</strong>
          Autonomous navigation challenge — vision-based drone system.
        </div>
      </li>
      <li>
        <span class="ach-icon">🛰</span>
        <div class="ach-text">
          <strong>NIDAR DRONE COMPETITION</strong>
          Advanced aerial robotics competition with computer vision stack.
        </div>
      </li>
    </ul>
  </div>

  <!-- ══ CONTACT ══ -->
  <div class="panel reveal">
    <div class="section-title">// CONNECT</div>
    <div class="contact-row">
      <a class="contact-btn" href="https://linkedin.com/in/vidhusankar-hozo" target="_blank">
        💼 &nbsp; LINKEDIN
      </a>
      <a class="contact-btn" href="https://github.com/Vidhusankar-hozo" target="_blank">
        🐙 &nbsp; GITHUB
      </a>
      <a class="contact-btn" href="mailto:vidhusankar@email.com">
        📧 &nbsp; EMAIL
      </a>
    </div>
  </div>

</div><!-- /wrapper -->

<script>
/* ════════════════════════════════════
   MATRIX RAIN
════════════════════════════════════ */
(function(){
  const canvas = document.getElementById('matrix-canvas');
  const ctx = canvas.getContext('2d');
  let cols, drops;
  const chars = '01アイウエオカキクケコサシスセソタチツテトナニヌネノ'.split('');

  function init(){
    canvas.width  = window.innerWidth;
    canvas.height = window.innerHeight;
    cols  = Math.floor(canvas.width / 18);
    drops = Array.from({length: cols}, () => Math.random() * -50);
  }
  init();
  window.addEventListener('resize', init);

  function draw(){
    ctx.fillStyle = 'rgba(2,13,2,0.05)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = '#00ff41';
    ctx.font = '14px "Share Tech Mono"';
    for(let i = 0; i < drops.length; i++){
      const ch = chars[Math.floor(Math.random() * chars.length)];
      ctx.globalAlpha = Math.random() * 0.8 + 0.2;
      ctx.fillText(ch, i * 18, drops[i] * 18);
      if(drops[i] * 18 > canvas.height && Math.random() > 0.975) drops[i] = 0;
      drops[i] += 0.4 + Math.random() * 0.3;
    }
    ctx.globalAlpha = 1;
  }
  setInterval(draw, 45);
})();

/* ════════════════════════════════════
   NEURAL NET HEADER CANVAS
════════════════════════════════════ */
(function(){
  const canvas = document.getElementById('neural-canvas');
  const ctx = canvas.getContext('2d');
  let W, H, nodes, t = 0;

  function resize(){
    W = canvas.width  = canvas.offsetWidth;
    H = canvas.height = canvas.offsetHeight;
    buildNodes();
  }

  function buildNodes(){
    nodes = [];
    const count = Math.floor(W / 55);
    const layers = 5;
    for(let l = 0; l < layers; l++){
      const n = Math.max(3, count - Math.abs(l - Math.floor(layers/2)) * 2);
      for(let i = 0; i < n; i++){
        nodes.push({
          x: (l + 0.8) / (layers + 0.6) * W,
          y: (i + 1) / (n + 1) * H,
          vx: (Math.random()-.5)*0.3,
          vy: (Math.random()-.5)*0.3,
          layer: l,
          r: 3 + Math.random() * 2,
          pulse: Math.random() * Math.PI * 2
        });
      }
    }
  }

  function draw(){
    ctx.clearRect(0,0,W,H);
    t += 0.012;

    // connections
    for(let i = 0; i < nodes.length; i++){
      for(let j = i+1; j < nodes.length; j++){
        const a = nodes[i], b = nodes[j];
        if(Math.abs(a.layer - b.layer) !== 1) continue;
        const dist = Math.hypot(a.x-b.x, a.y-b.y);
        if(dist > H * 0.65) continue;
        const sig = (Math.sin(t + i*0.3 + j*0.2) + 1) / 2;
        ctx.save();
        ctx.globalAlpha = 0.06 + sig * 0.18;
        ctx.strokeStyle = '#00ff41';
        ctx.lineWidth = 0.8 + sig * 0.8;
        ctx.beginPath();
        ctx.moveTo(a.x, a.y);
        ctx.lineTo(b.x, b.y);
        ctx.stroke();

        // travelling pulse dot
        if(sig > 0.85){
          const px = a.x + (b.x - a.x) * ((t * 0.8) % 1);
          const py = a.y + (b.y - a.y) * ((t * 0.8) % 1);
          ctx.globalAlpha = 0.7;
          ctx.fillStyle = '#00ff41';
          ctx.beginPath();
          ctx.arc(px, py, 2, 0, Math.PI*2);
          ctx.fill();
        }
        ctx.restore();
      }
    }

    // nodes
    for(let nd of nodes){
      const glow = (Math.sin(t + nd.pulse) + 1) / 2;
      ctx.save();
      ctx.globalAlpha = 0.5 + glow * 0.5;
      const g = ctx.createRadialGradient(nd.x, nd.y, 0, nd.x, nd.y, nd.r * 3);
      g.addColorStop(0, 'rgba(0,255,65,0.9)');
      g.addColorStop(1, 'rgba(0,255,65,0)');
      ctx.fillStyle = g;
      ctx.beginPath();
      ctx.arc(nd.x, nd.y, nd.r * 3, 0, Math.PI*2);
      ctx.fill();
      ctx.fillStyle = '#00ff41';
      ctx.beginPath();
      ctx.arc(nd.x, nd.y, nd.r, 0, Math.PI*2);
      ctx.fill();
      ctx.restore();

      // gentle float
      nd.x += nd.vx;
      nd.y += nd.vy;
      if(nd.x < 10 || nd.x > W-10) nd.vx *= -1;
      if(nd.y < 10 || nd.y > H-10) nd.vy *= -1;
    }
  }

  resize();
  window.addEventListener('resize', resize);
  function loop(){ draw(); requestAnimationFrame(loop); }
  loop();
})();

/* ════════════════════════════════════
   3D CONTRIBUTION CUBE
════════════════════════════════════ */
(function(){
  const canvas = document.getElementById('cube-canvas');
  const ctx = canvas.getContext('2d');
  const W = 160, H = 160, cx = W/2, cy = H/2;
  let angle = 0;

  // Build fake contribution grid on cube faces
  function project(x, y, z, rx, ry){
    const cosX = Math.cos(rx), sinX = Math.sin(rx);
    const cosY = Math.cos(ry), sinY = Math.sin(ry);
    let nx = cosY*x + sinY*z;
    let nz = -sinY*x + cosY*z;
    let ny = cosX*y - sinX*nz;
    nz = sinX*y + cosX*nz;
    const scale = 220 / (220 + nz);
    return [cx + nx * scale, cy + ny * scale, nz];
  }

  function drawFace(pts, fillColor, strokeC){
    ctx.beginPath();
    ctx.moveTo(pts[0][0], pts[0][1]);
    for(let i=1;i<pts.length;i++) ctx.lineTo(pts[i][0], pts[i][1]);
    ctx.closePath();
    ctx.fillStyle = fillColor;
    ctx.fill();
    ctx.strokeStyle = strokeC || 'rgba(0,255,65,0.4)';
    ctx.lineWidth = 0.8;
    ctx.stroke();
  }

  function drawCubelets(rx, ry){
    const size = 18, gap = 2, n = 3;
    const total = n * (size + gap);
    const offset = -total/2 + size/2;
    const contributions = [
      [0,1,3],[2,1,0],[1,3,2],
      [3,2,1],[0,1,2],[1,1,3],
      [2,0,1],[1,2,3],[3,1,0]
    ];
    const colors = ['#001200','#003300','#006600','#00aa00','#00ff41'];

    for(let row=0;row<n;row++){
      for(let col=0;col<n;col++){
        const cv = contributions[row*n+col][0];
        const color = colors[cv];
        const x = offset + col*(size+gap);
        const y = offset + row*(size+gap);
        const z = 28;
        const s = size/2;

        const tl = project(x-s, y-s, z, rx, ry);
        const tr = project(x+s, y-s, z, rx, ry);
        const br = project(x+s, y+s, z, rx, ry);
        const bl = project(x-s, y+s, z, rx, ry);

        // sides for depth
        const tl2 = project(x-s, y-s, -z, rx, ry);
        const tr2 = project(x+s, y-s, -z, rx, ry);
        const br2 = project(x+s, y+s, -z, rx, ry);

        // right face
        drawFace([tr, tr2, br2, br], 'rgba(0,80,0,0.5)');
        // bottom face
        drawFace([bl, br, br2, tl2.map?tl2:tl], 'rgba(0,60,0,0.5)');
        // top face
        drawFace([tl, tr, br, bl], color);
      }
    }
  }

  function animate(){
    ctx.clearRect(0, 0, W, H);
    angle += 0.012;
    const rx = 0.52, ry = angle;
    drawCubelets(rx, ry);
    requestAnimationFrame(animate);
  }
  animate();
})();

/* ════════════════════════════════════
   SCROLL REVEAL
════════════════════════════════════ */
const reveals = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries) => {
  entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.12 });
reveals.forEach(el => io.observe(el));
// Immediately show first 3
reveals.forEach((el, i) => { if(i < 3) el.classList.add('visible'); });
</script>
</body>
</html>
