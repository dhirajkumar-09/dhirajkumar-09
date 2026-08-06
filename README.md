<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dhiraj Kumar — Full Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#09090b;
    --surface:#121214;
    --border:#26262a;
    --text:#f2efe9;
    --muted:#8b8b92;
    --gold:#d9b45c;
    --gold-soft:rgba(217,180,92,0.13);
    --violet:#8b7cf6;
    --violet-soft:rgba(139,124,246,0.13);
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:'Inter',sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  .mono{font-family:'JetBrains Mono',monospace;}
  .display{font-family:'Space Grotesk',sans-serif;}
  a{text-decoration:none;color:inherit;}
  .wrap{max-width:1152px;margin:0 auto;padding:0 24px;}

  /* Hero */
  .hero-section{position:relative;overflow:hidden;}
  .glow{position:absolute;filter:blur(40px);pointer-events:none;border-radius:50%;}
  .glow-gold{top:-120px;left:8%;width:480px;height:480px;background:radial-gradient(circle,rgba(217,180,92,0.14) 0%, transparent 70%);}
  .glow-violet{top:80px;right:4%;width:420px;height:420px;background:radial-gradient(circle,rgba(139,124,246,0.11) 0%, transparent 70%);}

  .nav{position:relative;z-index:2;display:flex;align-items:center;justify-content:space-between;padding-top:32px;}
  .logo-badge{width:40px;height:40px;border-radius:999px;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:600;color:var(--gold);}
  .nav-links{display:flex;gap:32px;font-size:14px;color:var(--muted);}
  .status-pill{font-size:12px;padding:6px 14px;border-radius:999px;border:1px solid var(--border);display:flex;align-items:center;gap:8px;color:var(--muted);}
  .dot{width:6px;height:6px;border-radius:999px;background:#5fd97a;display:inline-block;}

  .hero{position:relative;z-index:2;padding:64px 0 80px;}
  .eyebrow{font-size:12px;letter-spacing:0.3em;text-transform:uppercase;color:var(--gold);margin-bottom:24px;}
  .name{
    font-weight:600;
    font-size:clamp(3rem,10vw,8rem);
    line-height:0.95;
    letter-spacing:-0.02em;
    margin:0;
  }
  .name .gold-text{
    background:linear-gradient(90deg,#d9b45c,#f3e0ad,#d9b45c);
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
  }
  .tagline{font-size:clamp(1rem,2vw,1.15rem);max-width:560px;color:var(--muted);margin-top:32px;line-height:1.6;}
  .hero-actions{margin-top:32px;display:flex;flex-wrap:wrap;gap:12px;align-items:center;}
  .badge-loc{font-size:12px;padding:8px 14px;border-radius:999px;border:1px solid var(--border);color:var(--muted);display:flex;align-items:center;gap:6px;}
  .btn-primary{font-size:12px;font-weight:600;padding:8px 16px;border-radius:999px;background:var(--text);color:var(--bg);display:flex;align-items:center;gap:6px;}
  .btn-outline{font-size:12px;padding:8px 16px;border-radius:999px;border:1px solid var(--border);color:var(--text);display:flex;align-items:center;gap:6px;}

  /* Content sections */
  .content{padding-bottom:96px;display:flex;flex-direction:column;gap:64px;}
  .section-label{font-size:12px;text-transform:uppercase;letter-spacing:0.1em;color:var(--muted);margin-bottom:20px;}

  .stats-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:16px;}
  @media(min-width:768px){.stats-grid{grid-template-columns:repeat(4,1fr);}}
  .stat-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:16px;display:flex;align-items:center;gap:12px;}
  .stat-icon{background:var(--gold-soft);border-radius:8px;padding:8px;display:flex;align-items:center;justify-content:center;}
  .stat-value{font-size:20px;font-weight:600;}
  .stat-label{font-size:12px;color:var(--muted);}

  .two-col{display:grid;grid-template-columns:1fr;gap:24px;}
  @media(min-width:1024px){.two-col{grid-template-columns:1.4fr 1fr;}}
  .card{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:24px;}
  .card-head{display:flex;align-items:center;justify-content:space-between;margin-bottom:24px;}

  .contrib-grid{display:flex;flex-direction:column;gap:3px;overflow-x:auto;}
  .contrib-row{display:flex;gap:3px;}
  .contrib-cell{width:8px;height:8px;border-radius:2px;}

  .lang-row{display:flex;align-items:center;gap:20px;}
  .lang-legend{flex:1;display:flex;flex-direction:column;gap:8px;}
  .lang-item{display:flex;align-items:center;justify-content:space-between;font-size:12px;}
  .lang-dot{width:7px;height:7px;border-radius:999px;display:inline-block;margin-right:8px;}

  .chip-row{display:flex;flex-wrap:wrap;gap:10px;}
  .chip{font-size:14px;padding:8px 16px;border-radius:999px;border:1px solid var(--border);background:var(--surface);}

  .projects-grid{display:grid;grid-template-columns:1fr;gap:16px;}
  @media(min-width:768px){.projects-grid{grid-template-columns:1fr 1fr;}}
  .project-card{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:24px;display:block;transition:border-color 0.2s;}
  .project-card:hover{border-color:#39393f;}
  .project-top{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:16px;}
  .project-icon{width:40px;height:40px;border-radius:10px;background:var(--violet-soft);display:flex;align-items:center;justify-content:center;}
  .project-title{font-family:'Space Grotesk',sans-serif;font-size:18px;font-weight:600;margin:0 0 8px;}
  .project-desc{font-size:14px;color:var(--muted);line-height:1.55;margin:0 0 16px;}
  .tag{font-size:11px;padding:4px 8px;border-radius:6px;background:var(--gold-soft);color:var(--gold);margin-right:6px;display:inline-block;margin-bottom:6px;}

  .contact-card{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:56px 24px;text-align:center;}
  .contact-eyebrow{font-size:12px;letter-spacing:0.3em;text-transform:uppercase;color:var(--gold);margin-bottom:16px;}
  .contact-title{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:clamp(1.75rem,5vw,3.25rem);line-height:1.15;margin:0;}
  .contact-actions{margin-top:32px;display:flex;flex-wrap:wrap;justify-content:center;gap:12px;}
  .btn-lg{font-size:14px;padding:10px 20px;border-radius:999px;display:flex;align-items:center;gap:8px;font-weight:600;}
  .btn-lg.primary{background:var(--text);color:var(--bg);}
  .btn-lg.outline{border:1px solid var(--border);color:var(--text);font-weight:500;}

  .footer{display:flex;align-items:center;justify-content:space-between;font-size:12px;color:var(--muted);padding-top:16px;border-top:1px solid var(--border);}

  svg.icon{display:block;}
</style>
</head>
<body>

<div class="hero-section">
  <div class="glow glow-gold"></div>
  <div class="glow glow-violet"></div>

  <div class="wrap">
    <div class="nav">
      <div class="logo-badge display">DK</div>
      <div class="nav-links mono" style="display:none;" id="navLinksDesktop">
        <span>Work</span><span>Stack</span><span>Contact</span>
      </div>
      <div class="status-pill mono"><span class="dot"></span>open to work</div>
    </div>

    <div class="hero">
      <p class="eyebrow mono">// Full Stack Developer — AI Enthusiast</p>
      <h1 class="name display">
        <span>Dhiraj</span><br>
        <span class="gold-text">Kumar</span>
      </h1>
      <p class="tagline">CSE (IoT) student building full-stack &amp; AI-driven products — from idea to production. Currently sharpening DSA and shipping side projects.</p>

      <div class="hero-actions">
        <span class="badge-loc mono">
          <svg class="icon" width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0Z"/><circle cx="12" cy="10" r="3"/></svg>
          Patna, Bihar, India
        </span>
        <a href="#" class="btn-primary mono">
          View Resume
          <svg class="icon" width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17 17 7M7 7h10v10"/></svg>
        </a>
        <a href="#" class="btn-outline mono">
          <svg class="icon" width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 .5C5.65.5.5 5.65.5 12c0 5.08 3.29 9.39 7.86 10.91.57.1.78-.25.78-.55v-1.94c-3.2.7-3.87-1.54-3.87-1.54-.53-1.34-1.28-1.7-1.28-1.7-1.05-.72.08-.7.08-.7 1.16.08 1.77 1.19 1.77 1.19 1.03 1.76 2.7 1.25 3.36.96.1-.75.4-1.25.73-1.54-2.55-.29-5.23-1.28-5.23-5.68 0-1.26.45-2.29 1.19-3.1-.12-.29-.52-1.46.11-3.05 0 0 .97-.31 3.18 1.18a11.06 11.06 0 0 1 5.79 0c2.2-1.49 3.17-1.18 3.17-1.18.64 1.59.24 2.76.12 3.05.74.81 1.19 1.84 1.19 3.1 0 4.41-2.69 5.38-5.25 5.67.41.36.78 1.06.78 2.14v3.17c0 .3.21.66.79.55A10.52 10.52 0 0 0 23.5 12C23.5 5.65 18.35.5 12 .5Z"/></svg>
          GitHub
        </a>
      </div>
    </div>
  </div>
</div>

<div class="wrap content">

  <div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-icon"><svg class="icon" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#d9b45c" stroke-width="2"><polyline points="23 6 13.5 15.5 8.5 10.5 1 18"/><polyline points="17 6 23 6 23 12"/></svg></div>
        <div><div class="stat-value display">204</div><div class="stat-label">Contributions</div></div>
      </div>
      <div class="stat-card">
        <div class="stat-icon"><svg class="icon" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#d9b45c" stroke-width="2"><path d="M8.5 14.5A2.5 2.5 0 0 0 11 12c0-1.38-.5-2-1-3-1.072-2.143-.224-4.054 2-6 .5 2.5 2 4.9 4 6.5 2 1.6 3 3.5 3 5.5a7 7 0 1 1-14 0c0-1.153.433-2.294 1-3a2.5 2.5 0 0 0 2.5 2.5z"/></svg></div>
        <div><div class="stat-value display">26</div><div class="stat-label">Current Streak</div></div>
      </div>
      <div class="stat-card">
        <div class="stat-icon"><svg class="icon" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#d9b45c" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg></div>
        <div><div class="stat-value display">132</div><div class="stat-label">Stars Earned</div></div>
      </div>
      <div class="stat-card">
        <div class="stat-icon"><svg class="icon" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#d9b45c" stroke-width="2"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"/><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"/></svg></div>
        <div><div class="stat-value display">18</div><div class="stat-label">Repositories</div></div>
      </div>
    </div>
  </div>

  <div class="two-col">
    <div class="card">
      <div class="card-head">
        <span class="section-label mono" style="margin:0;">Contribution activity</span>
        <svg class="icon" width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="#d9b45c" stroke-width="2"><path d="M12 3v18M3 12h18"/></svg>
      </div>
      <div id="contribGrid" class="contrib-grid"></div>
    </div>

    <div class="card">
      <span class="section-label mono">Language mix</span>
      <div class="lang-row">
        <svg id="donutChart" width="120" height="120" viewBox="0 0 120 120"></svg>
        <div class="lang-legend" id="langLegend"></div>
      </div>
    </div>
  </div>

  <div>
    <span class="section-label mono">Toolkit</span>
    <div class="chip-row">
      <span class="chip">Python</span>
      <span class="chip">JavaScript</span>
      <span class="chip">React</span>
      <span class="chip">Node.js</span>
      <span class="chip">HTML5</span>
      <span class="chip">CSS3</span>
      <span class="chip">Firebase</span>
      <span class="chip">Git</span>
      <span class="chip">C++</span>
      <span class="chip">VS Code</span>
    </div>
  </div>

  <div>
    <div style="display:flex;align-items:baseline;justify-content:space-between;margin-bottom:20px;">
      <span class="section-label mono" style="margin:0;">Selected work</span>
      <span class="mono" style="font-size:12px;color:var(--muted);">4 projects</span>
    </div>
    <div class="projects-grid">

      <a href="#" class="project-card">
        <div class="project-top">
          <div class="project-icon"><svg class="icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#8b7cf6" stroke-width="2"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg></div>
          <svg class="icon" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="var(--muted)" stroke-width="2"><path d="M7 17 17 7M7 7h10v10"/></svg>
        </div>
        <h4 class="project-title">EduForge</h4>
        <p class="project-desc">AI-powered learning platform with smart roadmaps, mock tests and progress analytics.</p>
        <div><span class="tag mono">React</span><span class="tag mono">Firebase</span><span class="tag mono">AI</span></div>
      </a>

      <a href="#" class="project-card">
        <div class="project-top">
          <div class="project-icon"><svg class="icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#8b7cf6" stroke-width="2"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg></div>
          <svg class="icon" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="var(--muted)" stroke-width="2"><path d="M7 17 17 7M7 7h10v10"/></svg>
        </div>
        <h4 class="project-title">My Portfolio</h4>
        <p class="project-desc">A responsive developer portfolio site showcasing my projects, skills and achievements.</p>
        <div><span class="tag mono">HTML</span><span class="tag mono">CSS</span><span class="tag mono">JavaScript</span></div>
      </a>

      <a href="#" class="project-card">
        <div class="project-top">
          <div class="project-icon"><svg class="icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#8b7cf6" stroke-width="2"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg></div>
          <svg class="icon" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="var(--muted)" stroke-width="2"><path d="M7 17 17 7M7 7h10v10"/></svg>
        </div>
        <h4 class="project-title">Stadium Command Centre</h4>
        <p class="project-desc">Real-time stadium monitoring dashboard built for smart, large-scale event management.</p>
        <div><span class="tag mono">React</span><span class="tag mono">Tailwind</span><span class="tag mono">Firebase</span></div>
      </a>

      <a href="#" class="project-card">
        <div class="project-top">
          <div class="project-icon"><svg class="icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#8b7cf6" stroke-width="2"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg></div>
          <svg class="icon" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="var(--muted)" stroke-width="2"><path d="M7 17 17 7M7 7h10v10"/></svg>
        </div>
        <h4 class="project-title">LeetCode Solutions</h4>
        <p class="project-desc">A growing archive of 250+ DSA problems solved with clean, explained Python code.</p>
        <div><span class="tag mono">Python</span><span class="tag mono">DSA</span></div>
      </a>

    </div>
  </div>

  <div class="contact-card">
    <p class="contact-eyebrow mono">Let's build something</p>
    <h3 class="contact-title">Open to internships, collabs<br>&amp; interesting problems.</h3>
    <div class="contact-actions">
      <a href="mailto:dhirajkumar09.business@gmail.com" class="btn-lg primary">
        <svg class="icon" width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 6-10 7L2 6"/></svg>
        Say hello
      </a>
      <a href="#" class="btn-lg outline">
        <svg class="icon" width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M20.45 20.45h-3.55v-5.57c0-1.33-.03-3.04-1.85-3.04-1.85 0-2.14 1.45-2.14 2.94v5.67H9.36V9h3.41v1.56h.05c.48-.9 1.64-1.85 3.38-1.85 3.6 0 4.27 2.37 4.27 5.46v6.28zM5.34 7.43a2.06 2.06 0 1 1 0-4.12 2.06 2.06 0 0 1 0 4.12zM7.12 20.45H3.56V9h3.56v11.45z"/></svg>
        LinkedIn
      </a>
      <a href="#" class="btn-lg outline">
        <svg class="icon" width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M12 .5C5.65.5.5 5.65.5 12c0 5.08 3.29 9.39 7.86 10.91.57.1.78-.25.78-.55v-1.94c-3.2.7-3.87-1.54-3.87-1.54-.53-1.34-1.28-1.7-1.28-1.7-1.05-.72.08-.7.08-.7 1.16.08 1.77 1.19 1.77 1.19 1.03 1.76 2.7 1.25 3.36.96.1-.75.4-1.25.73-1.54-2.55-.29-5.23-1.28-5.23-5.68 0-1.26.45-2.29 1.19-3.1-.12-.29-.52-1.46.11-3.05 0 0 .97-.31 3.18 1.18a11.06 11.06 0 0 1 5.79 0c2.2-1.49 3.17-1.18 3.17-1.18.64 1.59.24 2.76.12 3.05.74.81 1.19 1.84 1.19 3.1 0 4.41-2.69 5.38-5.25 5.67.41.36.78 1.06.78 2.14v3.17c0 .3.21.66.79.55A10.52 10.52 0 0 0 23.5 12C23.5 5.65 18.35.5 12 .5Z"/></svg>
        GitHub
      </a>
    </div>
  </div>

  <div class="footer mono">
    <span>© 2026 Dhiraj Kumar</span>
    <span>Made with care</span>
  </div>

</div>

<script>
  // Contribution grid
  (function(){
    let s = 42;
    function rand(){ s = (s * 9301 + 49297) % 233280; return s / 233280; }
    const levels = ["#1a1a1d", "#4a3a1c", "#8a6a24", "#c99a30", "#d9b45c"];
    const rows = 7, cols = 30;
    const container = document.getElementById('contribGrid');
    for(let i=0;i<rows;i++){
      const row = document.createElement('div');
      row.className = 'contrib-row';
      for(let j=0;j<cols;j++){
        const cell = document.createElement('div');
        cell.className = 'contrib-cell';
        cell.style.backgroundColor = levels[Math.floor(rand()*5)];
        row.appendChild(cell);
      }
      container.appendChild(row);
    }
  })();

  // Donut chart
  (function(){
    const data = [
      { name: "Python", value: 56.1, color: "#d9b45c" },
      { name: "JavaScript", value: 18.7, color: "#8b7cf6" },
      { name: "Java", value: 10.5, color: "#5fb3a3" },
      { name: "C++", value: 7.3, color: "#e0745c" },
      { name: "Other", value: 7.4, color: "#4a4a50" },
    ];
    const svg = document.getElementById('donutChart');
    const cx = 60, cy = 60, rOuter = 52, rInner = 32;
    let startAngle = -90;
    const ns = "http://www.w3.org/2000/svg";

    function polarToCartesian(cx, cy, r, angleDeg){
      const a = (angleDeg - 90) * Math.PI / 180;
      return { x: cx + r * Math.cos(a), y: cy + r * Math.sin(a) };
    }
    function arcPath(cx, cy, rOuter, rInner, startAngle, endAngle){
      const startOuter = polarToCartesian(cx, cy, rOuter, endAngle);
      const endOuter = polarToCartesian(cx, cy, rOuter, startAngle);
      const startInner = polarToCartesian(cx, cy, rInner, endAngle);
      const endInner = polarToCartesian(cx, cy, rInner, startAngle);
      const largeArc = endAngle - startAngle <= 180 ? "0" : "1";
      return [
        "M", startOuter.x, startOuter.y,
        "A", rOuter, rOuter, 0, largeArc, 0, endOuter.x, endOuter.y,
        "L", endInner.x, endInner.y,
        "A", rInner, rInner, 0, largeArc, 1, startInner.x, startInner.y,
        "Z"
      ].join(" ");
    }

    let angle = 0;
    data.forEach(d => {
      const sweep = d.value / 100 * 360;
      const path = document.createElementNS(ns, "path");
      path.setAttribute("d", arcPath(cx, cy, rOuter, rInner, angle, angle + sweep - 2));
      path.setAttribute("fill", d.color);
      svg.appendChild(path);
      angle += sweep;
    });

    const legend = document.getElementById('langLegend');
    data.forEach(d => {
      const item = document.createElement('div');
      item.className = 'lang-item';
      item.innerHTML = '<span style="display:flex;align-items:center;"><span class="lang-dot" style="background:' + d.color + '"></span>' + d.name + '</span><span class="mono" style="color:var(--muted)">' + d.value + '%</span>';
      legend.appendChild(item);
    });
  })();

  // responsive nav links
  function updateNav(){
    document.getElementById('navLinksDesktop').style.display = window.innerWidth >= 640 ? 'flex' : 'none';
  }
  updateNav();
  window.addEventListener('resize', updateNav);
</script>

</body>
</html>
