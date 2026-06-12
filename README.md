<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mustapha | Frontend Developer</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0a0f1e;
      --surface: #111827;
      --card: #1a2235;
      --accent: #00d4aa;
      --accent2: #7c6af7;
      --text: #e8edf5;
      --muted: #8a95a8;
      --border: #1e2d45;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Space Grotesk', sans-serif;
      line-height: 1.7;
    }

    /* NAV */
    nav {
      position: fixed; top: 0; width: 100%; z-index: 100;
      background: rgba(10,15,30,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
      padding: 1rem 2rem;
      display: flex; justify-content: space-between; align-items: center;
    }
    .nav-logo {
      font-family: 'Fira Code', monospace;
      font-size: 1.1rem;
      color: var(--accent);
      font-weight: 500;
    }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      color: var(--muted); text-decoration: none; font-size: 0.9rem;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--accent); }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: flex; align-items: center;
      padding: 6rem 2rem 4rem;
      max-width: 1100px; margin: 0 auto;
      position: relative;
    }
    .hero-content { max-width: 680px; }
    .hero-tag {
      font-family: 'Fira Code', monospace;
      font-size: 0.85rem;
      color: var(--accent);
      margin-bottom: 1.2rem;
      display: flex; align-items: center; gap: 0.5rem;
    }
    .hero-tag::before {
      content: '';
      display: inline-block; width: 28px; height: 2px;
      background: var(--accent);
    }
    .hero h1 {
      font-size: clamp(2.4rem, 6vw, 4rem);
      font-weight: 700;
      line-height: 1.1;
      margin-bottom: 1.2rem;
      letter-spacing: -0.02em;
    }
    .hero h1 span {
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .hero p {
      font-size: 1.1rem; color: var(--muted);
      margin-bottom: 2.5rem; max-width: 520px;
    }
    .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }
    .btn-primary {
      background: var(--accent); color: #0a0f1e;
      padding: 0.75rem 1.8rem; border-radius: 6px;
      font-weight: 600; font-size: 0.95rem;
      text-decoration: none; transition: opacity 0.2s;
    }
    .btn-primary:hover { opacity: 0.85; }
    .btn-outline {
      border: 1.5px solid var(--border); color: var(--text);
      padding: 0.75rem 1.8rem; border-radius: 6px;
      font-weight: 500; font-size: 0.95rem;
      text-decoration: none; transition: border-color 0.2s;
    }
    .btn-outline:hover { border-color: var(--accent); color: var(--accent); }

    /* FLOATING BADGES */
    .hero-badge {
      position: absolute; right: 2rem; top: 50%;
      transform: translateY(-50%);
      display: flex; flex-direction: column; gap: 1rem;
    }
    .badge {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 0.8rem 1.2rem;
      font-family: 'Fira Code', monospace;
      font-size: 0.8rem;
      color: var(--accent);
      animation: float 3s ease-in-out infinite;
    }
    .badge:nth-child(2) { animation-delay: 0.5s; color: var(--accent2); }
    .badge:nth-child(3) { animation-delay: 1s; color: #f7c26a; }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-8px); }
    }

    /* SECTIONS */
    section {
      max-width: 1100px; margin: 0 auto;
      padding: 5rem 2rem;
    }
    .section-label {
      font-family: 'Fira Code', monospace;
      font-size: 0.8rem; color: var(--accent);
      letter-spacing: 0.1em; text-transform: uppercase;
      margin-bottom: 0.5rem;
    }
    .section-title {
      font-size: clamp(1.6rem, 3vw, 2.2rem);
      font-weight: 700; margin-bottom: 1rem;
      letter-spacing: -0.02em;
    }
    .section-divider {
      width: 48px; height: 3px;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      border-radius: 2px; margin-bottom: 3rem;
    }

    /* ABOUT */
    .about-grid {
      display: grid; grid-template-columns: 1fr 1fr;
      gap: 3rem; align-items: center;
    }
    .about-text p { color: var(--muted); margin-bottom: 1rem; font-size: 1rem; }
    .about-stats {
      display: grid; grid-template-columns: 1fr 1fr;
      gap: 1.2rem;
    }
    .stat-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 1.5rem;
      text-align: center;
      transition: border-color 0.2s;
    }
    .stat-card:hover { border-color: var(--accent); }
    .stat-num {
      font-size: 2rem; font-weight: 700;
      color: var(--accent); display: block;
    }
    .stat-label { font-size: 0.85rem; color: var(--muted); }

    /* SKILLS */
    .skills-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.5rem;
    }
    .skill-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 1.8rem;
      transition: border-color 0.2s, transform 0.2s;
    }
    .skill-card:hover { border-color: var(--accent); transform: translateY(-4px); }
    .skill-icon { font-size: 1.8rem; margin-bottom: 0.8rem; }
    .skill-card h3 { font-size: 1rem; font-weight: 600; margin-bottom: 0.5rem; }
    .skill-card p { font-size: 0.87rem; color: var(--muted); }
    .skill-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: 1rem; }
    .tag {
      background: rgba(0,212,170,0.1);
      color: var(--accent);
      border: 1px solid rgba(0,212,170,0.2);
      border-radius: 4px;
      padding: 0.2rem 0.6rem;
      font-size: 0.75rem;
      font-family: 'Fira Code', monospace;
    }
    .tag.purple {
      background: rgba(124,106,247,0.1);
      color: var(--accent2);
      border-color: rgba(124,106,247,0.2);
    }
    .tag.yellow {
      background: rgba(247,194,106,0.1);
      color: #f7c26a;
      border-color: rgba(247,194,106,0.2);
    }

    /* PROJECTS */
    .projects-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 1.5rem;
    }
    .project-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
      transition: border-color 0.2s, transform 0.2s;
    }
    .project-card:hover { border-color: var(--accent2); transform: translateY(-4px); }
    .project-top {
      padding: 1.8rem 1.8rem 0;
      display: flex; justify-content: space-between; align-items: flex-start;
    }
    .project-icon {
      font-size: 2rem;
    }
    .project-links { display: flex; gap: 0.8rem; }
    .project-links a {
      color: var(--muted); text-decoration: none;
      font-size: 0.8rem; font-family: 'Fira Code', monospace;
      transition: color 0.2s;
    }
    .project-links a:hover { color: var(--accent); }
    .project-body { padding: 1rem 1.8rem 1.8rem; }
    .project-body h3 { font-size: 1.05rem; font-weight: 600; margin-bottom: 0.5rem; }
    .project-body p { font-size: 0.87rem; color: var(--muted); margin-bottom: 1rem; }
    .project-stack { display: flex; flex-wrap: wrap; gap: 0.4rem; }

    /* CONTACT */
    .contact-wrapper {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 3rem;
      display: grid; grid-template-columns: 1fr 1fr;
      gap: 3rem; align-items: center;
    }
    .contact-info h3 { font-size: 1.5rem; font-weight: 700; margin-bottom: 0.8rem; }
    .contact-info p { color: var(--muted); margin-bottom: 1.5rem; }
    .contact-links { display: flex; flex-direction: column; gap: 0.8rem; }
    .contact-link {
      display: flex; align-items: center; gap: 0.8rem;
      color: var(--muted); text-decoration: none; font-size: 0.9rem;
      transition: color 0.2s;
    }
    .contact-link:hover { color: var(--accent); }
    .contact-link span:first-child {
      font-family: 'Fira Code', monospace;
      color: var(--accent); font-size: 0.8rem;
    }

    /* FORM */
    .contact-form { display: flex; flex-direction: column; gap: 1rem; }
    .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
    .form-group label { font-size: 0.85rem; color: var(--muted); }
    .form-group input, .form-group textarea {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 0.75rem 1rem;
      color: var(--text);
      font-family: 'Space Grotesk', sans-serif;
      font-size: 0.9rem;
      outline: none;
      transition: border-color 0.2s;
    }
    .form-group input:focus, .form-group textarea:focus { border-color: var(--accent); }
    .form-group textarea { resize: vertical; min-height: 100px; }
    .btn-send {
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      color: #fff; border: none; border-radius: 8px;
      padding: 0.85rem; font-size: 0.95rem;
      font-weight: 600; cursor: pointer;
      font-family: 'Space Grotesk', sans-serif;
      transition: opacity 0.2s;
    }
    .btn-send:hover { opacity: 0.85; }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border);
      text-align: center;
      padding: 2rem;
      color: var(--muted);
      font-size: 0.85rem;
      font-family: 'Fira Code', monospace;
    }
    footer span { color: var(--accent); }

    /* RESPONSIVE */
    @media (max-width: 768px) {
      .hero-badge { display: none; }
      .about-grid, .contact-wrapper { grid-template-columns: 1fr; }
      .nav-links { display: none; }
    }

    /* SCROLL REVEAL */
    .reveal {
      opacity: 0; transform: translateY(24px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }
    .reveal.visible { opacity: 1; transform: translateY(0); }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">&lt;mustapha /&gt;</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="hero-content">
    <div class="hero-tag">Available for opportunities</div>
    <h1>Building the web,<br><span>one pixel at a time.</span></h1>
    <p>Junior Frontend Developer passionate about creating clean, responsive, and user-friendly web experiences using modern technologies.</p>
    <div class="hero-btns">
      <a href="#projects" class="btn-primary">View My Work</a>
      <a href="#contact" class="btn-outline">Get In Touch</a>
    </div>
  </div>
  <div class="hero-badge">
    <div class="badge">⚡ HTML5 / CSS3</div>
    <div class="badge">⚛️ React.js</div>
    <div class="badge">🟨 JavaScript</div>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="reveal">
    <div class="section-label">01 — About</div>
    <h2 class="section-title">Who I Am</h2>
    <div class="section-divider"></div>
  </div>
  <div class="about-grid reveal">
    <div class="about-text">
      <p>I'm a self-driven frontend developer based in Nigeria with a strong interest in building visually engaging and functional web applications. I combine technical skills with a user-first mindset to craft experiences that are not only good-looking but genuinely useful.</p>
      <p>When I'm not coding, I run a tech-focused social media community, explore cybersecurity, and experiment with Web3 technologies. I believe technology should empower people — and that's the philosophy behind every project I build.</p>
      <p>I'm actively looking for junior frontend opportunities where I can contribute, learn, and grow with a team that values clean code and good design.</p>
    </div>
    <div class="about-stats">
      <div class="stat-card">
        <span class="stat-num">5+</span>
        <span class="stat-label">Projects Built</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">3+</span>
        <span class="stat-label">Tech Courses</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">1K+</span>
        <span class="stat-label">Community Members</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">∞</span>
        <span class="stat-label">Curiosity</span>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="reveal">
    <div class="section-label">02 — Skills</div>
    <h2 class="section-title">What I Work With</h2>
    <div class="section-divider"></div>
  </div>
  <div class="skills-grid">
    <div class="skill-card reveal">
      <div class="skill-icon">🏗️</div>
      <h3>Structure & Styling</h3>
      <p>Building well-structured, semantic, and accessible web pages with modern HTML and CSS techniques.</p>
      <div class="skill-tags">
        <span class="tag">HTML5</span>
        <span class="tag">CSS3</span>
        <span class="tag">Flexbox</span>
        <span class="tag">Grid</span>
      </div>
    </div>
    <div class="skill-card reveal">
      <div class="skill-icon">⚡</div>
      <h3>JavaScript</h3>
      <p>Writing modern ES6+ JavaScript for dynamic, interactive user interfaces and browser logic.</p>
      <div class="skill-tags">
        <span class="tag purple">ES6+</span>
        <span class="tag purple">DOM API</span>
        <span class="tag purple">Async/Await</span>
        <span class="tag purple">Fetch API</span>
      </div>
    </div>
    <div class="skill-card reveal">
      <div class="skill-icon">⚛️</div>
      <h3>React.js</h3>
      <p>Building component-based UIs with React, managing state and props for scalable applications.</p>
      <div class="skill-tags">
        <span class="tag yellow">Components</span>
        <span class="tag yellow">useState</span>
        <span class="tag yellow">useEffect</span>
        <span class="tag yellow">Props</span>
      </div>
    </div>
    <div class="skill-card reveal">
      <div class="skill-icon">🎨</div>
      <h3>UI Frameworks</h3>
      <p>Rapidly building responsive layouts and styled components using utility-first CSS frameworks.</p>
      <div class="skill-tags">
        <span class="tag">Tailwind CSS</span>
        <span class="tag">Bootstrap</span>
        <span class="tag">Responsive</span>
      </div>
    </div>
    <div class="skill-card reveal">
      <div class="skill-icon">🛠️</div>
      <h3>Dev Tools</h3>
      <p>Using industry-standard tools for version control, package management, and development workflow.</p>
      <div class="skill-tags">
        <span class="tag purple">Git</span>
        <span class="tag purple">GitHub</span>
        <span class="tag purple">VS Code</span>
        <span class="tag purple">npm</span>
      </div>
    </div>
    <div class="skill-card reveal">
      <div class="skill-icon">🐍</div>
      <h3>Python (Learning)</h3>
      <p>Expanding into backend development and scripting with Python, covering lists, loops, and OOP basics.</p>
      <div class="skill-tags">
        <span class="tag yellow">Python 3</span>
        <span class="tag yellow">Scripting</span>
        <span class="tag yellow">In Progress</span>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="reveal">
    <div class="section-label">03 — Projects</div>
    <h2 class="section-title">Things I've Built</h2>
    <div class="section-divider"></div>
  </div>
  <div class="projects-grid">
    <div class="project-card reveal">
      <div class="project-top">
        <div class="project-icon">🔐</div>
        <div class="project-links">
          <a href="#">GitHub →</a>
          <a href="#">Live →</a>
        </div>
      </div>
      <div class="project-body">
        <h3>Cybersecurity Info Hub</h3>
        <p>A fully responsive website presenting cybersecurity concepts, history timeline, and resources. Built as part of a personal learning portfolio.</p>
        <div class="project-stack">
          <span class="tag">HTML5</span>
          <span class="tag">CSS3</span>
          <span class="tag">JavaScript</span>
        </div>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-top">
        <div class="project-icon">📱</div>
        <div class="project-links">
          <a href="#">GitHub →</a>
          <a href="#">Live →</a>
        </div>
      </div>
      <div class="project-body">
        <h3>Social Media Growth Guide</h3>
        <p>A styled digital eBook landing page with clear CTA, testimonials section, and responsive layout — designed for Selar.co product listing.</p>
        <div class="project-stack">
          <span class="tag">HTML5</span>
          <span class="tag">CSS3</span>
          <span class="tag purple">Responsive</span>
        </div>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-top">
        <div class="project-icon">🌐</div>
        <div class="project-links">
          <a href="#">GitHub →</a>
          <a href="#">Live →</a>
        </div>
      </div>
      <div class="project-body">
        <h3>Personal Portfolio Website</h3>
        <p>This very portfolio — built from scratch using HTML, CSS, and vanilla JavaScript. Features scroll animations, responsive design, and a contact form.</p>
        <div class="project-stack">
          <span class="tag">HTML5</span>
          <span class="tag">CSS3</span>
          <span class="tag">JavaScript</span>
        </div>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-top">
        <div class="project-icon">☁️</div>
        <div class="project-links">
          <a href="#">GitHub →</a>
          <a href="#">Live →</a>
        </div>
      </div>
      <div class="project-body">
        <h3>Weather Dashboard</h3>
        <p>A JavaScript weather app that fetches live data from a public API and displays current conditions and forecasts with a clean UI.</p>
        <div class="project-stack">
          <span class="tag purple">JavaScript</span>
          <span class="tag purple">Fetch API</span>
          <span class="tag">CSS3</span>
        </div>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-top">
        <div class="project-icon">✅</div>
        <div class="project-links">
          <a href="#">GitHub →</a>
          <a href="#">Live →</a>
        </div>
      </div>
      <div class="project-body">
        <h3>Task Manager App</h3>
        <p>A React-based to-do application with add, complete, and delete functionality, demonstrating component-based architecture and state management.</p>
        <div class="project-stack">
          <span class="tag yellow">React.js</span>
          <span class="tag yellow">useState</span>
          <span class="tag">Tailwind CSS</span>
        </div>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-top">
        <div class="project-icon">🧮</div>
        <div class="project-links">
          <a href="#">GitHub →</a>
          <a href="#">Live →</a>
        </div>
      </div>
      <div class="project-body">
        <h3>JavaScript Calculator</h3>
        <p>A fully functional calculator built with pure JavaScript, featuring keyboard support, chained operations, and error handling.</p>
        <div class="project-stack">
          <span class="tag purple">Java
