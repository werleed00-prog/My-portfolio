<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mustapha Mutawakkil · Portfolio</title>
  <!-- Font Awesome 6 -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    }

    body {
      background: #f4f6fa;
      color: #0b1a2e;
      padding: 1.8rem 1.2rem;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      background: white;
      border-radius: 2.8rem;
      box-shadow: 0 30px 60px -20px rgba(0, 20, 40, 0.2);
      padding: 2rem 2rem 1.5rem;
      transition: 0.2s;
    }

    /* ----- navigation (10 clickable pages) ----- */
    .top-nav {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      gap: 0.5rem 0.9rem;
      padding-bottom: 1.5rem;
      border-bottom: 2px solid #eef2f8;
      margin-bottom: 2.2rem;
    }

    .nav-btn {
      background: transparent;
      border: 1px solid #dce2ec;
      padding: 0.4rem 1rem;
      border-radius: 60px;
      font-size: 0.8rem;
      font-weight: 500;
      color: #1f2a44;
      transition: 0.2s;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      text-decoration: none;
      background: white;
    }

    .nav-btn i { color: #3b4b7a; font-size: 0.8rem; }
    .nav-btn:hover {
      background: #e7edf9;
      border-color: #6a7fb0;
      transform: translateY(-2px);
      box-shadow: 0 4px 8px rgba(0,0,0,0.02);
    }
    .nav-btn.active {
      background: #1f2a44;
      border-color: #1f2a44;
      color: white;
    }
    .nav-btn.active i { color: white; }

    /* ----- page sections (only active page is shown) ----- */
    .page {
      display: none;
      animation: fade 0.2s ease;
    }
    .page.active-page {
      display: block;
    }

    @keyframes fade {
      0% { opacity: 0.3; transform: translateY(6px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    /* ----- header / intro (page 1) ----- */
    .intro {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 2.5rem;
      margin-bottom: 2.5rem;
      padding-bottom: 1.8rem;
      border-bottom: 1px solid #eaf0f6;
    }

    .avatar {
      width: 140px;
      height: 140px;
      background: linear-gradient(145deg, #1f2a44, #2d3d66);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3.6rem;
      font-weight: 600;
      color: white;
      box-shadow: 0 14px 28px -10px rgba(26, 42, 80, 0.3);
      flex-shrink: 0;
    }

    .intro-text h1 {
      font-size: 3rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      color: #0b1a2e;
    }
    .intro-text h1 span {
      background: linear-gradient(135deg, #1f2a44, #47648f);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .tagline {
      font-size: 1.25rem;
      color: #2d405b;
      margin-top: 0.2rem;
    }
    .tagline i { color: #2d3d66; margin-right: 0.3rem; }

    .social-links {
      margin-top: 1.2rem;
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
    }
    .social-links a {
      background: #f0f4fd;
      padding: 0.3rem 1.2rem 0.3rem 0.9rem;
      border-radius: 60px;
      text-decoration: none;
      color: #1f2a44;
      font-weight: 500;
      font-size: 0.95rem;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      transition: 0.2s;
      border: 1px solid transparent;
    }
    .social-links a i { font-size: 1.2rem; color: #1f2a44; }
    .social-links a:hover {
      background: #dce6f5;
      border-color: #b0c2df;
      transform: translateY(-2px);
    }

    .section-title {
      font-size: 1.9rem;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 0.75rem;
      margin: 2rem 0 1.2rem;
      color: #0b1a2e;
    }
    .section-title i { color: #2d3d66; font-size: 1.7rem; }

    .about-text {
      background: #f8faff;
      padding: 1.5rem 2rem;
      border-radius: 2.2rem;
      border-left: 6px solid #2d3d66;
      color: #1a2b44;
      font-size: 1.1rem;
      max-width: 850px;
    }

    .skills-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 0.9rem 1.5rem;
      background: #f8faff;
      padding: 1.8rem 2rem;
      border-radius: 2.5rem;
    }
    .skill-item {
      background: white;
      padding: 0.4rem 1.2rem 0.4rem 1rem;
      border-radius: 60px;
      border: 1px solid #dfe8f2;
      font-weight: 500;
      color: #1f2a44;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    .skill-item i { color: #2d3d66; width: 1.3rem; }

    .project-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 2rem;
      margin-top: 0.8rem;
    }
    .project-card {
      background: white;
      border-radius: 2rem;
      padding: 1.8rem 1.5rem;
      border: 1px solid #e5edf8;
      transition: 0.25s;
      box-shadow: 0 6px 14px rgba(0,0,0,0.01);
    }
    .project-card:hover {
      transform: translateY(-6px);
      border-color: #a5bada;
      box-shadow: 0 20px 30px -14px rgba(26, 42, 80, 0.12);
    }
    .project-card i { font-size: 2.2rem; color: #2d3d66; margin-bottom: 0.5rem; }
    .project-card h3 { font-size: 1.3rem; margin-bottom: 0.2rem; color: #0b1a2e; }
    .project-card p { color: #2d405b; font-size: 0.95rem; margin: 0.5rem 0 1rem; }
    .project-tag {
      display: inline-block;
      background: #e7eefa;
      color: #1f2a44;
      font-size: 0.7rem;
      font-weight: 600;
      padding: 0.2rem 1rem;
      border-radius: 40px;
      margin-right: 0.3rem;
    }
    .btn-outline {
      display: inline-block;
      margin-top: 0.8rem;
      border: 1.5px solid #d0ddea;
      padding: 0.2rem 1.4rem;
      border-radius: 60px;
      text-decoration: none;
      font-weight: 500;
      font-size: 0.8rem;
      color: #1f2a44;
      transition: 0.2s;
    }
    .btn-outline:hover {
      background: #1f2a44;
      color: white;
      border-color: #1f2a44;
    }

    /* page cards (for the additional pages) */
    .page-card-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 1.5rem;
      margin-top: 1rem;
    }
    .page-card {
      background: #f8faff;
      border-radius: 2rem;
      padding: 1.8rem 1.5rem;
      border: 1px solid #e5edf8;
      transition: 0.2s;
    }
    .page-card:hover { border-color: #a5bada; }
    .page-card i { font-size: 2rem; color: #2d3d66; margin-bottom: 0.3rem; }
    .page-card h4 { font-size: 1.2rem; margin-bottom: 0.2rem; }
    .page-card p { font-size: 0.9rem; color: #1f2a44; }

    .footer-note {
      margin-top: 3rem;
      padding-top: 1.8rem;
      border-top: 2px solid #eaf0f6;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
      color: #2d405b;
    }
    .footer-note a { color: #1f2a44; font-weight: 500; text-decoration: none; border-bottom: 1px dotted #bac9e0; }
    .footer-note a:hover { color: #0b1a2e; }

    .page-indicator {
      text-align: center;
      margin: 1.8rem 0 0.2rem;
      font-size: 0.8rem;
      color: #6d7f9e;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.6rem 1.2rem;
    }
    .page-indicator span {
      background: #eef3fc;
      padding: 0.15rem 1rem;
      border-radius: 60px;
    }
    .page-indicator i { color: #2d3d66; margin-right: 4px; }

    @media (max-width: 650px) {
      .container { padding: 1.5rem; }
      .intro { flex-direction: column; text-align: center; }
      .avatar { width: 110px; height: 110px; font-size: 2.8rem; }
      .intro-text h1 { font-size: 2.3rem; }
      .social-links { justify-content: center; }
      .top-nav { gap: 0.4rem; }
      .nav-btn { font-size: 0.7rem; padding: 0.3rem 0.8rem; }
      .project-grid { grid-template-columns: 1fr; }
      .page-card-grid { grid-template-columns: 1fr; }
      .footer-note { flex-direction: column; text-align: center; }
    }
  </style>
</head>
<body>

<div class="container">

  <!-- ===== NAVIGATION (10 clickable pages) ===== -->
  <div class="top-nav" id="navBar">
    <button class="nav-btn active" data-page="page1"><i class="fas fa-home"></i> Home</button>
    <button class="nav-btn" data-page="page2"><i class="fas fa-user"></i> About</button>
    <button class="nav-btn" data-page="page3"><i class="fas fa-code"></i> Skills</button>
    <button class="nav-btn" data-page="page4"><i class="fas fa-briefcase"></i> Work</button>
    <button class="nav-btn" data-page="page5"><i class="fas fa-pen-fancy"></i> Blog</button>
    <button class="nav-btn" data-page="page6"><i class="fas fa-images"></i> Gallery</button>
    <button class="nav-btn" data-page="page7"><i class="fas fa-star"></i> Testimonials</button>
    <button class="nav-btn" data-page="page8"><i class="fas fa-award"></i> Achievements</button>
    <button class="nav-btn" data-page="page9"><i class="fas fa-calendar-alt"></i> Timeline</button>
    <button class="nav-btn" data-page="page10"><i class="fas fa-envelope"></i> Contact</button>
  </div>

  <!-- ============================================================ -->
  <!-- PAGE 1: HOME -->
  <div id="page1" class="page active-page">
    <div class="intro">
      <div class="avatar">MM</div>
      <div class="intro-text">
        <h1>Mustapha <span>Mutawakkil</span></h1>
        <div class="tagline"><i class="fas fa-laptop-code"></i> Full-stack developer · problem solver</div>
        <div class="social-links">
          <a href="#"><i class="fab fa-github"></i> github</a>
          <a href="#"><i class="fab fa-linkedin-in"></i> linkedin</a>
          <a href="#"><i class="fab fa-x-twitter"></i> x</a>
          <a href="#"><i class="fas fa-envelope"></i> mail</a>
        </div>
      </div>
    </div>

    <div class="about-text">
      <i class="fas fa-quote-left" style="color:#2d3d66; margin-right:8px;"></i>
      I'm Mustapha -- a developer who loves turning complex ideas into clean, functional code. 
      With a background in full-stack engineering and a passion for design, I build products 
      that are both beautiful and reliable.
    </div>

    <div class="section-title"><i class="fas fa-cog"></i> Core competencies</div>
    <div class="skills-grid">
      <span class="skill-item"><i class="fab fa-html5"></i> HTML5</span>
      <span class="skill-item"><i class="fab fa-css3-alt"></i> CSS3</span>
      <span class="skill-item"><i class="fab fa-js"></i> JavaScript</span>
      <span class="skill-item"><i class="fab fa-react"></i> React</span>
      <span class="skill-item"><i class="fab fa-node"></i> Node.js</span>
      <span class="skill-item"><i class="fas fa-database"></i> MongoDB</span>
      <span class="skill-item"><i class="fab fa-python"></i> Python</span>
      <span class="skill-item"><i class="fas fa-code-branch"></i> Git</span>
    </div>

    <div class="section-title"><i class="fas fa-rocket"></i> Featured projects</div>
    <div class="project-grid">
      <div class="project-card">
        <i class="fas fa-chart-line"></i>
        <h3>InsightFlow</h3>
        <p>Analytics dashboard with real-time data visualization.</p>
        <span class="project-tag">React</span><span class="project-tag">D3</span>
        <div><a href="#" class="btn-outline">demo →</a></div>
      </div>
      <div class="project-card">
        <i class="fas fa-store"></i>
        <h3>MarketHub</h3>
        <p>E‑commerce platform with AI product recommendations.</p>
        <span class="project-tag">Next</span><span class="project-tag">Stripe</span>
        <div><a href="#" class="btn-outline">demo →</a></div>
      </div>
      <div class="project-card">
        <i class="fas fa-calendar-check"></i>
        <h3>TaskBridge</h3>
        <p>Collaborative project management tool for teams.</p>
        <span class="project-tag">Vue</span><span class="project-tag">Firebase</span>
        <div><a href="#" class="btn-outline">demo →</a></div>
      </div>
    </div>
  </div>

  <!-- ============================================================ -->
  <!-- PAGE 2: ABOUT (expanded) -->
  <div id="page2" class="page">
    <div class="section-title"><i class="fas fa-user"></i> About me</div>
    <div style="background:#f8faff; border-radius:2rem; padding:2rem; max-width:800px;">
      <p style="font-size:1.1rem; color:#1a2b44;">I'm Mustapha Mutawakkil, a full-stack developer with 4+ years of experience. I thrive on building scalable web applications and enjoy mentoring junior developers. My journey started with a curiosity for how things work on the web, and today I lead projects that blend clean architecture with great user experience.</p>
      <p style="margin-top:1rem; color:#2d405b;"><i class="fas fa-map-pin" style="color:#2d3d66;"></i> Based in Abuja, Nigeria · <i class="fas fa-globe" style="color:#2d3d66;"></i> Remote-friendly</p>
    </div>
  </div>

  <!-- PAGE 3: SKILLS (detailed) -->
  <div id="page3" class="page">
    <div class="section-title"><i class="fas fa-code"></i> Tech stack & tools</div>
    <div style="background:#f8faff; border-radius:2rem; padding:1.8rem 2rem;">
      <div style="display:flex; flex-wrap:wrap; gap:1.2rem 2rem;">
        <div><i class="fab fa-react" style="color:#2d3d66; width:1.8rem;"></i> React & Next.js</div>
        <div><i class="fab fa-node" style="color:#2d3d66; width:1.8rem;"></i> Node.js / Express</div>
        <div><i class="fab fa-python" style="color:#2d3d66; width:1.8rem;"></i> Python (Flask, FastAPI)</div>
        <div><i class="fas fa-database" style="color:#2d3d66; width:1.8rem;"></i> MongoDB, PostgreSQL</div>
        <div><i class="fab fa-aws" style="color:#2d3d66; width:1.8rem;"></i> AWS (EC2, S3, Lambda)</div>
        <div><i class="fab fa-docker" style="color:#2d3d66; width:1.8rem;"></i> Docker / Kubernetes</div>
        <div><i class="fas fa-code-branch" style="color:#2d3d66; width:1.8rem;"></i> Git & CI/CD</div>
      </div>
    </div>
  </div>

  <!-- PAGE 4: WORK / experience -->
  <div id="page4" class="page">
    <div class="section-title"><i class="fas fa-briefcase"></i> Experience</div>
    <div style="display:grid; gap:1.5rem; grid-template-columns: repeat(auto-fill, minmax(240px,1fr));">
      <div style="background:#f8faff; border-radius:2rem; padding:1.5rem;"><i class="fas fa-building" style="color:#2d3d66;"></i> <strong>Lead Dev</strong> @ TechVault (2023–present)</div>
      <div style="background:#f8faff; border-radius:2rem; padding:1.5rem;"><i class="fas fa-code" style="color:#2d3d66;"></i> <strong>Full-stack</strong> @ DataPulse (2021–2023)</div>
      <div style="background:#f8faff; border-radius:2rem; padding:1.5rem;"><i class="fas fa-user-tie" style="color:#2d3d66;"></i> <strong>Freelance</strong> · web & mobile (2020–now)</div>
    </div>
  </div>

  <!-- PAGE 5: BLOG -->
  <div id="page5" class="page">
    <div class="section-title"><i class="fas fa-pen-fancy"></i> Blog</div>
    <div style="background:#f8faff; border-radius:2rem; padding:1.8rem;">
      <p><i class="fas fa-file-alt" style="color:#2d3d66;"></i> "Clean code is not optional" -- read my latest articles on dev.to and my personal blog.</p>
      <p style="margin-top:0.5rem;"><i class="fas fa-tag" style="color:#2d3d66;"></i> Topics: architecture, remote work, performance, design systems.</p>
    </div>
  </div>

  <!-- PAGE 6: GALLERY -->
  <div id="page6" class="page">
    <div class="section-title"><i class="fas fa-images"></i> Gallery</div>
    <div style="display:grid; grid-template-columns: repeat(auto-fill, minmax(140px,1fr)); gap:1.2rem;">
      <div style="background:#e7eefa; border-radius:2rem; padding:1.5rem; text-align:center;"><i class="fas fa-paint-brush" style="font-size:2.2rem; color:#2d3d66;"></i><br>UI concepts</div>
      <div style="background:#e7eefa; border-radius:2rem; padding:1.5rem; text-align:center;"><i class="fas fa-mobile-alt" style="font-size:2.2rem; color:#2d3d66;"></i><br>App screens</div>
      <div style="background:#e7eefa; border-radius:2rem; padding:1.5rem; text-align:center;"><i class="fas fa-code" style="font-size:2.2rem; color:#2d3d66;"></i><br>Code snippets</div>
    </div>
  </div>

  <!-- PAGE 7: TESTIMONIALS -->
  <div id="page7" class="page">
    <div class="section-title"><i class="fas fa-star"></i> Testimonials</div>
    <div style="background:#f8faff; border-radius:2rem; padding:1.8rem;">
      <p><i class="fas fa-quote-right" style="color:#2d3d66;"></i> "Mustapha is a brilliant engineer -- he delivered ahead of schedule and the code was a joy to work with." -- CTO, Finly</p>
      <p style="margin-top:0.8rem;"><i class="fas fa-quote-right" style="color:#2d3d66;"></i> "His ability to architect scalable solutions is exceptional. Highly recommend." -- Lead PM, DataPulse</p>
      <a href="https://www.freecodecamp.org/certification/fcc-5016d83d-8d83-4f58-be2b-d20cc530b45d/responsive-web-design" target="_blank" class="cert-btn">
  <i class="fas fa-certificate"></i> View Certificate
</a>
    </div>
  </div>

  <!-- PAGE 8: ACHIEVEMENTS -->
  <div id="page8" class="page">
    <div class="section-title"><i class="fas fa-award"></i> Achievements</div>
    <div style="display:flex; flex-wrap:wrap; gap:1.5rem;">
      <span style="background:#f8faff; border-radius:2rem; padding:0.8rem 1.8rem;"><i class="fas fa-trophy" style="color:#2d3d66;"></i> Hackathon winner 2023</span>
      <span style="background:#f8faff; border-radius:2rem; padding:0.8rem 1.8rem;"><i class="fas fa-certificate" style="color:#2d3d66;"></i> AWS Certified Developer</span>
      <span style="background:#f8faff; border-radius:2rem; padding:0.8rem 1.8rem;"><i class="fas fa-code-branch" style="color:#2d3d66;"></i> 5+ open-source contributions</span>
    </div>
  </div>

  <!-- PAGE 9: TIMELINE -->
  <div id="page9" class="page">
    <div class="section-title"><i class="fas fa-calendar-alt"></i> Timeline</div>
    <div style="background:#f8faff; border-radius:2rem; padding:1.8rem;">
      <p><i class="fas fa-circle" style="color:#2d3d66; font-size:0.6rem;"></i> 2020 -- Started coding (self-taught)</p>
      <p><i class="fas fa-circle" style="color:#2d3d66; font-size:0.6rem;"></i> 2021 -- First full-stack role @ DataPulse</p>
      <p><i class="fas fa-circle" style="color:#2d3d66; font-size:0.6rem;"></i> 2023 -- Lead engineer @ TechVault</p>
      <p><i class="fas fa-circle" style="color:#2d3d66; font-size:0.6rem;"></i> 2025 -- Currently building AI-powered tools</p>
    </div>
  </div>

  <!-- PAGE 10: CONTACT -->
  <div id="page10" class="page">
    <div class="section-title"><i class="fas fa-envelope"></i> Contact</div>
    <div style="background:#f8faff; border-radius:2rem; padding:2rem;">
      <p><i class="fas fa-envelope" style="color:#2d3d66; width:1.8rem;"></i> <a href="mailto:m.mutawakkil@dev.me" style="color:#1f2a44;">werleed00@gmail.com</a></p>
      <p><i class="fas fa-phone-alt" style="color:#2d3d66; width:1.8rem;"></i> +234 8147046173</p>
      <p><i class="fab fa-github" style="color:#2d3d66; width:1.8rem;"></i>https://github.com/werleed00-prog</p>
    </div>
  </div>

  <!-- ===== FOOTER ===== -->
  <div class="footer-note">
    <p><i class="fas fa-map-pin"></i> Kano. NG · <i class="fas fa-clock"></i> UTC+1</p>
    <p><i class="fas fa-envelope"></i> <a href="mailto:m.mutawakkil@dev.me">werleed00@gmail.com</a> · <i class="fas fa-phone-alt"></i> +234 8147046173</p>
    <p style="font-size:0.8rem; color:#6d7f9e;"><i class="far fa-copyright"></i> 2026 Mustapha M.</p>
  </div>

  <!-- page indicator -->
  <div class="page-indicator">
    <span><i class=
