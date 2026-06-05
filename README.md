# GORDON-NST.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title> [Gordon Ng] — Sciencetific research </title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  /* ============================================================
     PERSONALISATION GUIDE
     ============================================================
     To update your info, find the section marked with:
       <!-- EDIT: section name -->
     and change the text between the tags.

     Sections you can edit:
       1. HERO       — Your name, title, tagline
       2. ABOUT      — Short bio paragraph
       3. EXPERTISE  — Your 3 areas of focus (cards)
       4. EXPERIENCE — Your career timeline
       5. STATS      — Key numbers / achievements
       6. CONTACT    — Email, location, links
       7. THEME      — Colors (CSS variables below)
     ============================================================ */

  :root {
    /* === THEME: Change these to customise colors === */
    --accent: #0B6E5A;
    --accent-light: #E1F5EE;
    --accent-mid: #1D9E75;
    --ink: #0f1c18;
    --ink-soft: #3a4f47;
    --paper: #f7faf9;
    --paper-card: #ffffff;
    --border: rgba(11,110,90,0.15);
    /* ================================================ */

    --serif: 'DM Serif Display', Georgia, serif;
    --sans: 'DM Sans', system-ui, sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--sans);
    background: var(--paper);
    color: var(--ink);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.25rem 3rem;
    background: rgba(247,250,249,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    font-family: var(--serif);
    font-size: 1.1rem;
    color: var(--accent);
    text-decoration: none;
  }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    font-size: 0.85rem; letter-spacing: 0.08em; text-transform: uppercase;
    color: var(--ink-soft); text-decoration: none; font-weight: 500;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--accent); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-top: 5rem;
    overflow: hidden;
  }
  .hero-left {
    display: flex; flex-direction: column; justify-content: center;
    padding: 4rem 3rem 4rem 4rem;
  }
  .hero-eyebrow {
    font-size: 0.78rem; letter-spacing: 0.18em; text-transform: uppercase;
    color: var(--accent-mid); font-weight: 600; margin-bottom: 1.5rem;
    display: flex; align-items: center; gap: 0.75rem;
  }
  .hero-eyebrow::before {
    content: ''; width: 2rem; height: 2px; background: var(--accent-mid);
  }
  .hero-name {
    font-family: var(--serif);
    font-size: clamp(2.8rem, 5vw, 4.5rem);
    line-height: 1.05;
    color: var(--ink);
    margin-bottom: 1.5rem;
  }
  .hero-name em {
    font-style: italic;
    color: var(--accent);
  }
  /* EDIT: tagline */
  .hero-tagline {
    font-size: 1.1rem; line-height: 1.7; color: var(--ink-soft);
    max-width: 480px; margin-bottom: 2.5rem;
  }
  .hero-cta {
    display: flex; gap: 1rem; flex-wrap: wrap;
  }
  .btn {
    padding: 0.85rem 2rem; border-radius: 100px;
    font-size: 0.9rem; font-weight: 600; letter-spacing: 0.03em;
    text-decoration: none; transition: all 0.2s; cursor: pointer;
    border: 2px solid transparent;
  }
  .btn-primary {
    background: var(--accent); color: #fff;
  }
  .btn-primary:hover { background: #094f41; }
  .btn-outline {
    background: transparent; color: var(--accent);
    border-color: var(--accent);
  }
  .btn-outline:hover { background: var(--accent-light); }

  .hero-right {
    position: relative; background: var(--accent-light);
    display: flex; align-items: center; justify-content: center;
    overflow: hidden;
  }
  .hero-art {
    width: 100%; height: 100%;
    display: flex; align-items: center; justify-content: center;
  }
  .hero-art svg { width: 80%; max-width: 420px; }

  /* ── SECTION BASE ── */
  section { padding: 6rem 4rem; }
  .section-label {
    font-size: 0.75rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--accent-mid); font-weight: 600; margin-bottom: 1rem;
  }
  .section-title {
    font-family: var(--serif);
    font-size: clamp(2rem, 4vw, 3rem);
    line-height: 1.1;
    color: var(--ink);
    margin-bottom: 3rem;
  }

  /* ── ABOUT ── */
  #about { background: var(--paper-card); }
  .about-grid {
    display: grid; grid-template-columns: 1fr 2fr; gap: 4rem;
    align-items: start;
  }
  .about-aside {}
  .about-stat {
    margin-bottom: 2rem;
  }
  .about-stat-num {
    font-family: var(--serif); font-size: 3.5rem;
    color: var(--accent); line-height: 1;
  }
  .about-stat-label {
    font-size: 0.8rem; text-transform: uppercase; letter-spacing: 0.1em;
    color: var(--ink-soft); margin-top: 0.25rem;
  }
  .about-bio {
    font-size: 1.1rem; line-height: 1.85; color: var(--ink-soft);
  }
  .about-bio p + p { margin-top: 1.25rem; }

  /* ── EXPERTISE ── */
  #expertise { background: var(--paper); }
  .expertise-grid {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem;
  }
  .expertise-card {
    background: var(--paper-card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 2.5rem 2rem;
    position: relative; overflow: hidden;
    transition: transform 0.25s, box-shadow 0.25s;
  }
  .expertise-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 16px 40px rgba(11,110,90,0.1);
  }
  .expertise-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px;
    background: var(--accent);
  }
  .expertise-icon {
    width: 52px; height: 52px; border-radius: 12px;
    background: var(--accent-light);
    display: flex; align-items: center; justify-content: center;
    margin-bottom: 1.5rem;
  }
  .expertise-icon svg { width: 26px; height: 26px; stroke: var(--accent); fill: none; stroke-width: 1.8; stroke-linecap: round; stroke-linejoin: round; }
  .expertise-card h3 {
    font-family: var(--serif); font-size: 1.4rem;
    margin-bottom: 0.75rem; color: var(--ink);
  }
  .expertise-card p {
    font-size: 0.95rem; line-height: 1.7; color: var(--ink-soft);
  }

  /* ── EXPERIENCE ── */
  #experience { background: var(--paper-card); }
  .timeline { max-width: 720px; }
  .timeline-item {
    display: grid; grid-template-columns: 120px 1fr;
    gap: 2rem; margin-bottom: 3rem; position: relative;
  }
  .timeline-item:not(:last-child)::after {
    content: ''; position: absolute;
    left: 120px; top: 2.5rem; bottom: -1.5rem; width: 1px;
    background: var(--border);
    transform: translateX(calc(-50% + 1rem));
  }
  .timeline-year {
    font-family: var(--serif); font-size: 1.2rem;
    color: var(--accent); padding-top: 0.2rem; text-align: right;
  }
  .timeline-dot {
    position: absolute; left: 120px; top: 0.5rem;
    width: 10px; height: 10px; border-radius: 50%;
    background: var(--accent); transform: translateX(-50%);
    border: 2px solid var(--paper-card);
    box-shadow: 0 0 0 3px var(--accent-light);
  }
  .timeline-body { padding-left: 1.5rem; }
  .timeline-role {
    font-size: 1.1rem; font-weight: 600; color: var(--ink);
    margin-bottom: 0.25rem;
  }
  .timeline-org {
    font-size: 0.85rem; color: var(--accent-mid); font-weight: 500;
    text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 0.75rem;
  }
  .timeline-desc {
    font-size: 0.95rem; line-height: 1.7; color: var(--ink-soft);
  }

  /* ── CONTACT ── */
  #contact {
    background: var(--ink);
    color: #fff;
  }
  #contact .section-label { color: var(--accent-mid); }
  #contact .section-title { color: #fff; }
  .contact-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start;
  }
  .contact-blurb {
    font-size: 1.05rem; line-height: 1.8; color: rgba(255,255,255,0.65);
  }
  .contact-links { display: flex; flex-direction: column; gap: 1rem; }
  .contact-link {
    display: flex; align-items: center; gap: 1rem;
    padding: 1.25rem 1.5rem; border-radius: 12px;
    border: 1px solid rgba(255,255,255,0.1);
    text-decoration: none; color: #fff;
    transition: background 0.2s;
  }
  .contact-link:hover { background: rgba(255,255,255,0.06); }
  .contact-link-icon {
    width: 40px; height: 40px; border-radius: 10px;
    background: var(--accent); display: flex; align-items: center;
    justify-content: center; flex-shrink: 0;
  }
  .contact-link-icon svg { width: 18px; height: 18px; stroke: #fff; fill: none; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round; }
  .contact-link-label { font-size: 0.75rem; color: rgba(255,255,255,0.45); letter-spacing: 0.08em; text-transform: uppercase; }
  .contact-link-value { font-size: 0.95rem; font-weight: 500; margin-top: 2px; }

  /* ── FOOTER ── */
  footer {
    background: var(--ink); border-top: 1px solid rgba(255,255,255,0.05);
    padding: 2rem 4rem;
    display: flex; justify-content: space-between; align-items: center;
  }
  footer p { font-size: 0.8rem; color: rgba(255,255,255,0.3); }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; }
    .hero-right { min-height: 300px; }
    .hero-left { padding: 3rem 1.5rem; }
    section { padding: 4rem 1.5rem; }
    .about-grid, .contact-grid, .expertise-grid { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 0.5rem; text-align: center; padding: 1.5rem; }
  }
</style>
</head>
<body>

<!-- ── NAV ── -->
<nav>
  <!-- EDIT: nav logo text (usually your name initials or short name) -->
  <a href="#" class="nav-logo">Dr. A. Lee</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#expertise">Expertise</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- ── HERO ── -->
<section class="hero" id="home">
  <div class="hero-left">
    <!-- EDIT: eyebrow label — your role/specialty -->
    <div class="hero-eyebrow">Physician · Researcher</div>

    <!-- EDIT: your name — wrap a word in <em> for italic green accent -->
    <h1 class="hero-name">Dr. Alex<br><em>Lee</em></h1>

    <!-- EDIT: one-sentence tagline describing what you do -->
    <p class="hero-tagline">
      Bridging clinical medicine and translational research to advance patient outcomes in oncology and precision diagnostics.
    </p>

    <div class="hero-cta">
      <a href="#contact" class="btn btn-primary">Get in touch</a>
      <a href="#experience" class="btn btn-outline">View my work</a>
    </div>
  </div>

  <div class="hero-right">
    <div class="hero-art">
      <!-- Decorative DNA / science illustration -->
      <svg viewBox="0 0 420 520" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="g1" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="0%" stop-color="#0B6E5A" stop-opacity="0.18"/>
            <stop offset="100%" stop-color="#0B6E5A" stop-opacity="0.04"/>
          </linearGradient>
        </defs>
        <!-- Background blob -->
        <ellipse cx="210" cy="260" rx="180" ry="220" fill="url(#g1)"/>
        <!-- DNA helix left strand -->
        <path d="M160 60 C130 100 190 140 160 180 C130 220 190 260 160 300 C130 340 190 380 160 420 C130 460 190 460 160 460" stroke="#0B6E5A" stroke-width="3" stroke-linecap="round" fill="none" opacity="0.7"/>
        <!-- DNA helix right strand -->
        <path d="M260 60 C290 100 230 140 260 180 C290 220 230 260 260 300 C290 340 230 380 260 420 C290 460 230 460 260 460" stroke="#1D9E75" stroke-width="3" stroke-linecap="round" fill="none" opacity="0.7"/>
        <!-- Rungs -->
        <line x1="160" y1="110" x2="260" y2="110" stroke="#0B6E5A" stroke-width="2" stroke-linecap="round" opacity="0.4"/>
        <line x1="160" y1="160" x2="260" y2="160" stroke="#0B6E5A" stroke-width="2" stroke-linecap="round" opacity="0.4"/>
        <line x1="160" y1="210" x2="260" y2="210" stroke="#0B6E5A" stroke-width="2" stroke-linecap="round" opacity="0.4"/>
        <line x1="160" y1="260" x2="260" y2="260" stroke="#0B6E5A" stroke-width="2" stroke-linecap="round" opacity="0.4"/>
        <line x1="160" y1="310" x2="260" y2="310" stroke="#0B6E5A" stroke-width="2" stroke-linecap="round" opacity="0.4"/>
        <line x1="160" y1="360" x2="260" y2="360" stroke="#0B6E5A" stroke-width="2" stroke-linecap="round" opacity="0.4"/>
        <line x1="160" y1="410" x2="260" y2="410" stroke="#0B6E5A" stroke-width="2" stroke-linecap="round" opacity="0.4"/>
        <!-- Dots on rungs -->
        <circle cx="160" cy="110" r="6" fill="#0B6E5A" opacity="0.8"/>
        <circle cx="260" cy="110" r="6" fill="#1D9E75" opacity="0.8"/>
        <circle cx="160" cy="210" r="6" fill="#1D9E75" opacity="0.8"/>
        <circle cx="260" cy="210" r="6" fill="#0B6E5A" opacity="0.8"/>
        <circle cx="160" cy="310" r="6" fill="#0B6E5A" opacity="0.8"/>
        <circle cx="260" cy="310" r="6" fill="#1D9E75" opacity="0.8"/>
        <circle cx="160" cy="410" r="6" fill="#1D9E75" opacity="0.8"/>
        <circle cx="260" cy="410" r="6" fill="#0B6E5A" opacity="0.8"/>
        <!-- Floating molecules -->
        <circle cx="90" cy="180" r="18" stroke="#0B6E5A" stroke-width="1.5" fill="none" opacity="0.25"/>
        <circle cx="90" cy="180" r="8" fill="#0B6E5A" opacity="0.15"/>
        <circle cx="340" cy="320" r="24" stroke="#1D9E75" stroke-width="1.5" fill="none" opacity="0.25"/>
        <circle cx="340" cy="320" r="10" fill="#1D9E75" opacity="0.15"/>
        <circle cx="320" cy="150" r="14" stroke="#0B6E5A" stroke-width="1.5" fill="none" opacity="0.2"/>
        <circle cx="80" cy="380" r="12" stroke="#1D9E75" stroke-width="1.5" fill="none" opacity="0.2"/>
        <!-- Plus markers -->
        <text x="330" y="100" font-family="serif" font-size="28" fill="#0B6E5A" opacity="0.2">+</text>
        <text x="70" y="270" font-family="serif" font-size="22" fill="#1D9E75" opacity="0.2">+</text>
      </svg>
    </div>
  </div>
</section>

<!-- ── ABOUT ── -->
<section id="about">
  <div class="about-grid">
    <div class="about-aside">
      <p class="section-label">About me</p>

      <!-- EDIT: replace these three stats with your own numbers -->
      <div class="about-stat">
        <div class="about-stat-num">12+</div>
        <div class="about-stat-label">Years in practice</div>
      </div>
      <div class="about-stat">
        <div class="about-stat-num">40+</div>
        <div class="about-stat-label">Publications</div>
      </div>
      <div class="about-stat">
        <div class="about-stat-num">3K+</div>
        <div class="about-stat-label">Patients treated</div>
      </div>
    </div>

    <div>
      <h2 class="section-title">Driven by science,<br>guided by patients.</h2>

      <!-- EDIT: your bio — keep it 3-4 short paragraphs -->
      <div class="about-bio">
        <p>
          I am a physician-scientist specialising in oncology and molecular diagnostics. My clinical work focuses on personalised treatment strategies, while my research explores biomarkers that can predict therapy response in solid tumours.
        </p>
        <p>
          I trained at [University / Hospital Name] and have held appointments at [Institution]. My laboratory collaborates with industry and academic partners across Southeast Asia and Europe to accelerate discoveries from bench to bedside.
        </p>
        <p>
          Outside the clinic and lab, I am passionate about science communication and mentoring the next generation of clinician-scientists.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- ── EXPERTISE ── -->
<section id="expertise">
  <p class="section-label">What I do</p>
  <h2 class="section-title">Areas of expertise</h2>

  <!-- EDIT: change the three cards — icon, title, and description -->
  <div class="expertise-grid">

    <div class="expertise-card">
      <div class="expertise-icon">
        <!-- Microscope icon -->
        <svg viewBox="0 0 24 24"><path d="M6 21h12M9 21V10m6 11V10M5 10h14M8 10V4h8v6"/></svg>
      </div>
      <!-- EDIT: expertise area 1 -->
      <h3>Clinical Oncology</h3>
      <p>Diagnosis and management of solid tumours, with a focus on lung and gastrointestinal cancers. Integration of genomic profiling into treatment planning.</p>
    </div>

    <div class="expertise-card">
      <div class="expertise-icon">
        <!-- DNA / research icon -->
        <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="3"/><path d="M12 2v4M12 18v4M4.93 4.93l2.83 2.83M16.24 16.24l2.83 2.83M2 12h4M18 12h4M4.93 19.07l2.83-2.83M16.24 7.76l2.83-2.83"/></svg>
      </div>
      <!-- EDIT: expertise area 2 -->
      <h3>Translational Research</h3>
      <p>Biomarker discovery and validation. Designing early-phase clinical trials that bridge molecular findings with patient benefit.</p>
    </div>

    <div class="expertise-card">
      <div class="expertise-icon">
        <!-- Chart / data icon -->
        <svg viewBox="0 0 24 24"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
      </div>
      <!-- EDIT: expertise area 3 -->
      <h3>Precision Diagnostics</h3>
      <p>Liquid biopsy, ctDNA analysis, and next-generation sequencing applied to early detection and real-time treatment monitoring.</p>
    </div>

  </div>
</section>

<!-- ── EXPERIENCE ── -->
<section id="experience">
  <p class="section-label">Career</p>
  <h2 class="section-title">Experience</h2>

  <!-- EDIT: add, remove, or modify timeline entries below -->
  <div class="timeline">

    <div class="timeline-item">
      <!-- EDIT: year -->
      <div class="timeline-year">2021–</div>
      <div class="timeline-dot"></div>
      <div class="timeline-body">
        <!-- EDIT: role, organisation, description -->
        <div class="timeline-role">Senior Consultant Oncologist</div>
        <div class="timeline-org">[Hospital / Institution Name]</div>
        <p class="timeline-desc">Leading the molecular tumour board and supervising a team of four registrars. Principal investigator on two active Phase II trials.</p>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-year">2017–21</div>
      <div class="timeline-dot"></div>
      <div class="timeline-body">
        <div class="timeline-role">Consultant & Research Fellow</div>
        <div class="timeline-org">[Hospital / Institution Name]</div>
        <p class="timeline-desc">Established the liquid biopsy programme. Published 14 peer-reviewed papers on ctDNA-guided therapy in lung adenocarcinoma.</p>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-year">2014–17</div>
      <div class="timeline-dot"></div>
      <div class="timeline-body">
        <div class="timeline-role">Medical Oncology Registrar</div>
        <div class="timeline-org">[Hospital / Institution Name]</div>
        <p class="timeline-desc">Rotations across inpatient oncology, outpatient clinics, and palliative care. Completed specialist training and board examinations.</p>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-year">2008–14</div>
      <div class="timeline-dot"></div>
      <div class="timeline-body">
        <div class="timeline-role">MBBS, Honours in Biochemistry</div>
        <div class="timeline-org">[University Name]</div>
        <p class="timeline-desc">Graduated with distinction. Undergraduate thesis on tumour microenvironment immunology.</p>
      </div>
    </div>

  </div>
</section>

<!-- ── CONTACT ── -->
<section id="contact">
  <div class="contact-grid">
    <div>
      <p class="section-label">Get in touch</p>
      <h2 class="section-title">Let's connect.</h2>
      <!-- EDIT: contact blurb -->
      <p class="contact-blurb">
        I welcome collaboration enquiries, speaking invitations, and patient referrals. The best way to reach me is by email.
      </p>
    </div>

    <div class="contact-links">

      <!-- EDIT: your email address -->
      <a href="mailto:your.email@hospital.com" class="contact-link">
        <div class="contact-link-icon">
          <svg viewBox="0 0 24 24"><rect x="2" y="4" width="20" height="16" rx="2"/><polyline points="2,4 12,13 22,4"/></svg>
        </div>
        <div>
          <div class="contact-link-label">Email</div>
          <div class="contact-link-value">your.email@hospital.com</div>
        </div>
      </a>

      <!-- EDIT: your location -->
      <a href="#" class="contact-link">
        <div class="contact-link-icon">
          <svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13S3 17 3 10a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
        </div>
        <div>
          <div class="contact-link-label">Location</div>
          <div class="contact-link-value">Singapore, SG</div>
        </div>
      </a>

      <!-- EDIT: your LinkedIn URL -->
      <a href="https://linkedin.com/in/yourprofile" target="_blank" class="contact-link">
        <div class="contact-link-icon">
          <svg viewBox="0 0 24 24"><rect x="2" y="2" width="20" height="20" rx="4"/><line x1="8" y1="11" x2="8" y2="16"/><line x1="8" y1="8" x2="8" y2="8.5"/><path d="M12 16v-5M16 16v-3a2 2 0 00-4 0"/></svg>
        </div>
        <div>
          <div class="contact-link-label">LinkedIn</div>
          <div class="contact-link-value">linkedin.com/in/yourprofile</div>
        </div>
      </a>

      <!-- EDIT: optional — add or remove a 4th link (e.g. Google Scholar, ResearchGate, Twitter/X) -->
      <a href="https://scholar.google.com" target="_blank" class="contact-link">
        <div class="contact-link-icon">
          <svg viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
        </div>
        <div>
          <div class="contact-link-label">Google Scholar</div>
          <div class="contact-link-value">View publications</div>
        </div>
      </a>

    </div>
  </div>
</section>

<!-- ── FOOTER ── -->
<footer>
  <!-- EDIT: your name in footer -->
  <p>© 2026 Gordon Ng. All rights reserved.</p>
  <p>Driven by curiosity.</p>
</footer>

</body>
</html>
