<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Toit Net – Toitures, Façades & Panneaux Solaires</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --sky: #0a84c8;
    --sky-light: #38b6f5;
    --sky-dark: #065a8a;
    --sun: #f5a623;
    --sun-light: #fdd57a;
    --dark: #0d1b2a;
    --dark2: #122236;
    --mid: #1e3a52;
    --light: #e8f4fd;
    --white: #ffffff;
    --gray: #7a9ab5;
    --green: #27ae60;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--dark);
    color: var(--white);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 18px 6vw;
    background: rgba(10,20,35,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(56,182,245,0.12);
  }
  .nav-logo {
    font-family: 'Syne', sans-serif;
    font-size: 1.35rem; font-weight: 800;
    color: var(--white);
    letter-spacing: -0.5px;
  }
  .nav-logo span { color: var(--sky-light); }
  .nav-links { display: flex; gap: 2.2rem; list-style: none; }
  .nav-links a {
    color: var(--gray); text-decoration: none;
    font-size: 0.88rem; font-weight: 500; letter-spacing: 0.5px;
    transition: color .2s;
  }
  .nav-links a:hover { color: var(--sky-light); }
  .nav-cta {
    background: var(--sky); color: var(--white) !important;
    padding: 9px 20px; border-radius: 8px;
    font-weight: 600 !important;
    transition: background .2s !important;
  }
  .nav-cta:hover { background: var(--sky-light) !important; color: var(--dark) !important; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column; justify-content: center;
    padding: 120px 6vw 80px;
    position: relative; overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0; z-index: 0;
    background: linear-gradient(135deg, #0d1b2a 0%, #0a2d45 55%, #0d3a5c 100%);
  }
  .hero-grid {
    position: absolute; inset: 0; z-index: 0;
    background-image:
      linear-gradient(rgba(56,182,245,.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(56,182,245,.04) 1px, transparent 1px);
    background-size: 60px 60px;
  }
  .hero-glow {
    position: absolute; top: -100px; right: -80px;
    width: 600px; height: 600px; border-radius: 50%; z-index: 0;
    background: radial-gradient(circle, rgba(10,132,200,0.18) 0%, transparent 65%);
  }
  .hero-glow2 {
    position: absolute; bottom: -120px; left: -60px;
    width: 500px; height: 500px; border-radius: 50%; z-index: 0;
    background: radial-gradient(circle, rgba(245,166,35,0.1) 0%, transparent 65%);
  }
  .hero-content { position: relative; z-index: 1; max-width: 680px; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(56,182,245,0.12);
    border: 1px solid rgba(56,182,245,0.25);
    padding: 7px 16px; border-radius: 50px;
    font-size: 0.8rem; font-weight: 500; color: var(--sky-light);
    margin-bottom: 2rem; letter-spacing: 0.5px;
  }
  .hero-badge::before {
    content: ''; width: 8px; height: 8px; border-radius: 50%;
    background: var(--sky-light);
    box-shadow: 0 0 8px var(--sky-light);
    animation: pulse 2s infinite;
  }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.4} }
  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.6rem, 5.5vw, 4.2rem);
    font-weight: 800; line-height: 1.08;
    letter-spacing: -1.5px;
    margin-bottom: 1.5rem;
  }
  h1 em { font-style: normal; color: var(--sky-light); }
  .hero-sub {
    font-size: 1.08rem; color: var(--gray);
    line-height: 1.7; margin-bottom: 2.5rem; max-width: 520px;
    font-weight: 300;
  }
  .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }
  .btn-primary {
    background: var(--sky); color: var(--white);
    padding: 14px 30px; border-radius: 10px;
    font-size: 0.95rem; font-weight: 600;
    text-decoration: none; border: none; cursor: pointer;
    transition: all .25s;
    box-shadow: 0 4px 24px rgba(10,132,200,0.35);
  }
  .btn-primary:hover { background: var(--sky-light); color: var(--dark); transform: translateY(-2px); }
  .btn-secondary {
    background: transparent; color: var(--white);
    padding: 14px 30px; border-radius: 10px;
    font-size: 0.95rem; font-weight: 500;
    text-decoration: none;
    border: 1px solid rgba(255,255,255,0.18);
    transition: all .25s;
  }
  .btn-secondary:hover { border-color: var(--sky-light); color: var(--sky-light); }

  .hero-stats {
    position: relative; z-index: 1;
    display: flex; gap: 3rem; margin-top: 4rem;
    padding-top: 2.5rem;
    border-top: 1px solid rgba(255,255,255,0.07);
  }
  .stat-val {
    font-family: 'Syne', sans-serif;
    font-size: 2rem; font-weight: 800; color: var(--sky-light);
  }
  .stat-lbl { font-size: 0.82rem; color: var(--gray); margin-top: 3px; }

  /* ── SECTION TITLES ── */
  section { padding: 100px 6vw; }
  .section-tag {
    display: inline-block;
    font-size: 0.75rem; font-weight: 600;
    letter-spacing: 2px; text-transform: uppercase;
    color: var(--sky-light); margin-bottom: 1rem;
  }
  h2 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(1.9rem, 3.5vw, 2.8rem);
    font-weight: 800; letter-spacing: -1px;
    margin-bottom: 1.2rem; line-height: 1.15;
  }
  .section-sub { color: var(--gray); font-size: 1rem; line-height: 1.7; max-width: 500px; }

  /* ── SERVICES ── */
  .services { background: var(--dark2); }
  .services-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem; margin-top: 3.5rem;
  }
  .service-card {
    background: var(--mid);
    border: 1px solid rgba(56,182,245,0.1);
    border-radius: 16px; padding: 2rem;
    transition: all .3s; position: relative; overflow: hidden;
  }
  .service-card::before {
    content: ''; position: absolute;
    top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--sky), var(--sky-light));
    transform: scaleX(0); transform-origin: left;
    transition: transform .3s;
  }
  .service-card:hover { transform: translateY(-5px); border-color: rgba(56,182,245,0.3); }
  .service-card:hover::before { transform: scaleX(1); }
  .service-icon {
    width: 52px; height: 52px; border-radius: 12px;
    background: rgba(10,132,200,0.15);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.6rem; margin-bottom: 1.2rem;
  }
  .service-card h3 {
    font-family: 'Syne', sans-serif;
    font-size: 1.15rem; font-weight: 700;
    margin-bottom: .6rem;
  }
  .service-card p { color: var(--gray); font-size: 0.9rem; line-height: 1.65; }
  .service-price {
    margin-top: 1.2rem; padding-top: 1.2rem;
    border-top: 1px solid rgba(255,255,255,0.06);
    font-size: 0.82rem; color: var(--sky-light); font-weight: 500;
  }

  /* ── AVANT/APRES ── */
  .gallery { background: var(--dark); }
  .gallery-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 1.5rem; margin-top: 3.5rem;
  }

  /* ── BEFORE / AFTER SLIDER ── */
  .ba-card {
    border-radius: 16px; overflow: hidden;
    border: 1px solid rgba(56,182,245,0.12);
    background: var(--mid);
    box-shadow: 0 8px 40px rgba(0,0,0,0.4);
  }
  .ba-wrapper {
    position: relative; width: 100%; aspect-ratio: 4/3;
    overflow: hidden; cursor: ew-resize; user-select: none;
    -webkit-user-select: none;
  }
  /* AFTER = full background, always visible underneath */
  .ba-after {
    position: absolute; inset: 0;
    background-size: cover; background-position: center;
  }
  /* BEFORE = sits on top, width shrinks as slider moves right */
  .ba-before {
    position: absolute; top: 0; left: 0; bottom: 0;
    width: 50%;
    overflow: hidden;
    background-size: cover; background-position: left center;
    z-index: 2;
  }
  /* The divider line */
  .ba-divider {
    position: absolute; top: 0; bottom: 0;
    width: 3px; background: var(--white);
    left: 50%;
    transform: translateX(-50%);
    z-index: 4; pointer-events: none;
    box-shadow: 0 0 10px rgba(0,0,0,0.5);
  }
  /* The round handle on the divider */
  .ba-handle {
    position: absolute; top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 44px; height: 44px; border-radius: 50%;
    background: var(--white);
    display: flex; align-items: center; justify-content: center;
    z-index: 5; pointer-events: none;
    box-shadow: 0 2px 12px rgba(0,0,0,0.5);
    font-size: 1rem; color: var(--dark); font-weight: 900;
    line-height: 1;
  }
  /* AVANT / APRÈS labels */
  .ba-label-avant {
    position: absolute; bottom: 12px; left: 14px;
    z-index: 6; pointer-events: none;
    background: rgba(0,0,0,0.65); backdrop-filter: blur(6px);
    color: #fff; font-size: 0.72rem; font-weight: 700;
    padding: 4px 10px; border-radius: 20px; letter-spacing: 1px;
    text-transform: uppercase;
  }
  .ba-label-apres {
    position: absolute; bottom: 12px; right: 14px;
    z-index: 3; pointer-events: none;
    background: rgba(10,132,200,0.8); backdrop-filter: blur(6px);
    color: #fff; font-size: 0.72rem; font-weight: 700;
    padding: 4px 10px; border-radius: 20px; letter-spacing: 1px;
    text-transform: uppercase;
  }
  .ba-info {
    padding: 1.1rem 1.3rem;
    display: flex; align-items: center; justify-content: space-between;
  }
  .ba-info h4 { font-family: 'Syne', sans-serif; font-size: 0.95rem; font-weight: 700; }
  .ba-info span { font-size: 0.78rem; color: var(--sky-light); }

  /* Photo placeholders with real-looking CSS scenes */
  .scene-toit-dirty {
    background:
      linear-gradient(180deg, #1a1a2e 0%, #2d2d2d 35%, #3a3a3a 60%, #4a4040 100%),
      url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='40' height='20'%3E%3Crect width='40' height='20' fill='%23333'/%3E%3Crect y='10' width='40' height='10' fill='%23444'/%3E%3Crect x='20' width='20' height='10' fill='%23555'/%3E%3C/svg%3E");
    background-size: cover;
  }
  .scene-panneau-dirty {
    background: linear-gradient(160deg, #1c2744 0%, #2a3a5c 50%, #1e3a2a 100%);
  }
  .scene-mousse {
    background: linear-gradient(170deg, #2d3a1e 0%, #3a4a22 40%, #4a5a2a 80%, #3a4520 100%);
  }

  /* CSS tile pattern for rooftop */
  .toit-visual {
    position: relative; overflow: hidden;
  }
  .toit-visual::before {
    content: '';
    position: absolute; inset: 0;
    background-image:
      repeating-linear-gradient(90deg, rgba(0,0,0,.15) 0, rgba(0,0,0,.15) 1px, transparent 1px, transparent 40px),
      repeating-linear-gradient(180deg, rgba(0,0,0,.15) 0, rgba(0,0,0,.15) 1px, transparent 1px, transparent 20px);
    z-index: 1;
  }
  /* Moss/lichen patches */
  .dirty-overlay {
    position: absolute; inset: 0; z-index: 2;
    background:
      radial-gradient(ellipse 80px 30px at 20% 30%, rgba(60,90,20,.7) 0%, transparent 70%),
      radial-gradient(ellipse 60px 25px at 65% 55%, rgba(50,80,15,.6) 0%, transparent 70%),
      radial-gradient(ellipse 50px 20px at 45% 75%, rgba(70,95,25,.5) 0%, transparent 65%),
      radial-gradient(ellipse 90px 35px at 80% 20%, rgba(55,75,18,.65) 0%, transparent 70%);
  }
  .clean-overlay {
    position: absolute; inset: 0; z-index: 2;
    background: linear-gradient(180deg, rgba(200,215,230,0.05) 0%, transparent 100%);
  }

  /* ── PROCESS ── */
  .process { background: var(--dark2); }
  .process-steps {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 0; margin-top: 3.5rem;
    position: relative;
  }
  .process-steps::before {
    content: ''; position: absolute;
    top: 28px; left: 0; right: 0; height: 1px;
    background: linear-gradient(90deg, transparent, var(--sky), transparent);
    z-index: 0;
  }
  .step {
    position: relative; z-index: 1;
    display: flex; flex-direction: column; align-items: center;
    text-align: center; padding: 0 1.5rem;
  }
  .step-num {
    width: 56px; height: 56px; border-radius: 50%;
    background: var(--dark2);
    border: 2px solid var(--sky);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif; font-size: 1.2rem; font-weight: 800;
    color: var(--sky-light); margin-bottom: 1.2rem;
    box-shadow: 0 0 20px rgba(10,132,200,0.2);
  }
  .step h4 { font-family: 'Syne', sans-serif; font-size: 0.95rem; font-weight: 700; margin-bottom: .5rem; }
  .step p { font-size: 0.84rem; color: var(--gray); line-height: 1.6; }

  /* ── DEVIS ── */
  .devis {
    background: linear-gradient(135deg, var(--sky-dark) 0%, var(--mid) 100%);
    border-radius: 24px; margin: 0 6vw 100px;
    padding: 60px 8vw;
    display: flex; align-items: center; justify-content: space-between;
    gap: 2rem; flex-wrap: wrap;
    border: 1px solid rgba(56,182,245,0.2);
    position: relative; overflow: hidden;
  }
  .devis::before {
    content: ''; position: absolute;
    top: -80px; right: -80px;
    width: 300px; height: 300px; border-radius: 50%;
    background: radial-gradient(circle, rgba(56,182,245,0.12) 0%, transparent 70%);
  }
  .devis-text h2 { font-size: clamp(1.6rem, 3vw, 2.2rem); margin-bottom: .5rem; }
  .devis-text p { color: rgba(255,255,255,0.75); font-size: 0.95rem; }
  .devis-form {
    display: flex; gap: 1rem; flex-wrap: wrap; position: relative; z-index: 1;
  }
  .devis-form input {
    background: rgba(255,255,255,0.1);
    border: 1px solid rgba(255,255,255,0.2);
    color: var(--white); padding: 13px 18px;
    border-radius: 10px; font-size: 0.9rem;
    font-family: 'DM Sans', sans-serif;
    outline: none; transition: border .2s; min-width: 200px;
  }
  .devis-form input::placeholder { color: rgba(255,255,255,0.5); }
  .devis-form input:focus { border-color: var(--sky-light); }

  /* ── FOOTER ── */
  footer {
    background: #070f18;
    padding: 50px 6vw 30px;
    border-top: 1px solid rgba(255,255,255,0.05);
  }
  .footer-top {
    display: flex; justify-content: space-between; flex-wrap: wrap;
    gap: 2rem; margin-bottom: 2.5rem;
  }
  .footer-brand .nav-logo { font-size: 1.5rem; }
  .footer-brand p { color: var(--gray); font-size: 0.85rem; margin-top: .6rem; max-width: 250px; line-height: 1.6; }
  .footer-col h5 {
    font-family: 'Syne', sans-serif; font-size: 0.82rem;
    font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase;
    color: var(--sky-light); margin-bottom: 1rem;
  }
  .footer-col ul { list-style: none; }
  .footer-col li { margin-bottom: .5rem; }
  .footer-col a { color: var(--gray); text-decoration: none; font-size: 0.88rem; transition: color .2s; }
  .footer-col a:hover { color: var(--white); }
  .footer-bottom {
    padding-top: 1.5rem;
    border-top: 1px solid rgba(255,255,255,0.05);
    display: flex; justify-content: space-between; flex-wrap: wrap; gap: 1rem;
  }
  .footer-bottom p { color: var(--gray); font-size: 0.8rem; }

  /* ── RESPONSIVE ── */
  @media(max-width: 768px) {
    .nav-links { display: none; }
    .hero-stats { gap: 1.5rem; flex-wrap: wrap; }
    .process-steps::before { display: none; }
    .step { margin-bottom: 2rem; }
    .devis { flex-direction: column; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Toit <span>Net</span></div>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#realisations">Réalisations</a></li>
    <li><a href="#processus">Comment ça marche</a></li>
    <li><a href="#contact" class="nav-cta">Devis gratuit</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <div class="hero-content">
    <div class="hero-badge">Micro-entreprise locale &amp; certifiée</div>
    <h1>Nettoyage de <em>toitures</em>, façades &amp; panneaux <em>solaires</em></h1>
    <p class="hero-sub">Redonnez éclat et longévité à votre toiture et à vos installations solaires grâce à un nettoyage professionnel, rapide et sans risque pour vos équipements.</p>
    <div class="hero-btns">
      <a href="#contact" class="btn-primary">Demander un devis gratuit</a>
      <a href="#realisations" class="btn-secondary">Voir mes réalisations</a>
    </div>
  </div>
  <div class="hero-stats">
    <div>
      <div class="stat-val">100%</div>
      <div class="stat-lbl">Satisfaction client</div>
    </div>
    <div>
      <div class="stat-val">+15%</div>
      <div class="stat-lbl">Rendement solaire retrouvé</div>
    </div>

  </div>
</section>

<!-- AVANT / APRES -->
<section class="gallery" id="realisations">
  <div class="section-tag">Mes réalisations</div>
  <h2>Avant / Après</h2>
  <p class="section-sub">Glissez la souris sur chaque photo pour comparer le résultat avant et après intervention.</p>
  <div class="gallery-grid">

    <!-- Card 1 – Toiture tuiles -->
    <div class="ba-card">
      <div class="ba-wrapper">
        <!-- APRÈS (dessous, toujours visible) -->
        <div class="ba-after" style="background: linear-gradient(170deg,#c0503a 0%,#b8503a 40%,#a84830 80%);"></div>
        <!-- AVANT (dessus, rétrécit vers la gauche) -->
        <div class="ba-before" style="background: linear-gradient(170deg,#2a2a30 0%,#3a3530 40%,#4a4038 80%);">
          <div style="position:absolute;inset:0;background:radial-gradient(ellipse 80px 30px at 20% 30%,rgba(60,90,20,.7) 0%,transparent 70%),radial-gradient(ellipse 60px 25px at 65% 55%,rgba(50,80,15,.6) 0%,transparent 70%),radial-gradient(ellipse 90px 35px at 80% 20%,rgba(55,75,18,.65) 0%,transparent 70%);"></div>
        </div>
        <div class="ba-divider"></div>
        <div class="ba-handle">◀▶</div>
        <div class="ba-label-avant">Avant</div>
        <div class="ba-label-apres">Après</div>
      </div>
      <div class="ba-info">
        <h4>Toiture en tuiles</h4>
        <span>Mousse &amp; lichens éliminés</span>
      </div>
    </div>

    <!-- Card 2 – Panneaux solaires -->
    <div class="ba-card">
      <div class="ba-wrapper">
        <!-- APRÈS -->
        <div class="ba-after" style="background: linear-gradient(150deg,#1a3a5c 0%,#1e4070 50%,#1a3860 100%);">
          <div style="position:absolute;inset:0;background-image:repeating-linear-gradient(0deg,rgba(56,182,245,.1) 0,rgba(56,182,245,.1) 1px,transparent 1px,transparent 60px),repeating-linear-gradient(90deg,rgba(56,182,245,.1) 0,rgba(56,182,245,.1) 1px,transparent 1px,transparent 80px);"></div>
        </div>
        <!-- AVANT -->
        <div class="ba-before" style="background: linear-gradient(150deg,#1a2535 0%,#243045 50%,#1e2e40 100%);">
          <div style="position:absolute;inset:0;background-image:repeating-linear-gradient(0deg,rgba(255,255,255,.04) 0,rgba(255,255,255,.04) 1px,transparent 1px,transparent 60px),repeating-linear-gradient(90deg,rgba(255,255,255,.04) 0,rgba(255,255,255,.04) 1px,transparent 1px,transparent 80px);"></div>
          <div style="position:absolute;inset:0;background:radial-gradient(ellipse 120px 40px at 30% 40%,rgba(180,150,80,.3) 0%,transparent 70%),radial-gradient(ellipse 80px 30px at 70% 65%,rgba(160,140,70,.25) 0%,transparent 70%);"></div>
        </div>
        <div class="ba-divider"></div>
        <div class="ba-handle">◀▶</div>
        <div class="ba-label-avant">Avant</div>
        <div class="ba-label-apres">Après</div>
      </div>
      <div class="ba-info">
        <h4>Panneaux solaires</h4>
        <span>+18 % rendement retrouvé</span>
      </div>
    </div>

    <!-- Card 3 – Façade -->
    <div class="ba-card">
      <div class="ba-wrapper">
        <!-- APRÈS -->
        <div class="ba-after" style="background: linear-gradient(160deg,#d4c5a0 0%,#c8b890 40%,#bfaa80 80%);"></div>
        <!-- AVANT -->
        <div class="ba-before" style="background: linear-gradient(160deg,#2a3020 0%,#303828 40%,#3a4232 80%);">
          <div style="position:absolute;inset:0;background:radial-gradient(ellipse 100px 35px at 15% 50%,rgba(80,110,30,.6) 0%,transparent 70%),radial-gradient(ellipse 70px 28px at 55% 30%,rgba(70,100,25,.5) 0%,transparent 65%),radial-gradient(ellipse 90px 32px at 80% 70%,rgba(60,90,20,.55) 0%,transparent 70%);"></div>
        </div>
        <div class="ba-divider"></div>
        <div class="ba-handle">◀▶</div>
        <div class="ba-label-avant">Avant</div>
        <div class="ba-label-apres">Après</div>
      </div>
      <div class="ba-info">
        <h4>Façade</h4>
        <span>Algues &amp; salissures retirées</span>
      </div>
    </div>

  </div>
  <p style="text-align:center;margin-top:2.5rem;color:var(--gray);font-size:0.85rem;">
    📸 Photos réelles de mes interventions à venir — emplacement réservé pour vos propres photos avant/après.
  </p>
</section>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="section-tag">Ce que je propose</div>
  <h2>Mes services</h2>
  <p class="section-sub">Des interventions sur-mesure pour protéger et valoriser votre bien immobilier.</p>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">🏠</div>
      <h3>Nettoyage de toiture</h3>
      <p>Élimination des mousses, lichens, algues et dépôts. Traitement hydrofuge pour une protection longue durée. Résultat garanti.</p>
      <div class="service-price">À partir de 8 €/m² — Devis gratuit</div>
    </div>
    <div class="service-card">
      <div class="service-icon">☀️</div>
      <h3>Nettoyage panneaux solaires</h3>
      <p>Nettoyage sans abrasif ni produit agressif. Restore jusqu'à 20 % de rendement perdu à cause des salissures et dépôts.</p>
      <div class="service-price">À partir de 5 €/panneau — Devis gratuit</div>
    </div>
    <div class="service-card">
      <div class="service-icon">🏗️</div>
      <h3>Nettoyage de façade</h3>
      <p>Élimination des mousses, algues, traces de pollution et salissures sur vos façades. Résultat impeccable, sans détérioration de votre revêtement.</p>
      <div class="service-price">À partir de 8 €/m² — Devis gratuit</div>
    </div>
    <div class="service-card">
      <div class="service-icon">🔍</div>
      <h3>Diagnostic gratuit</h3>
      <p>Inspection visuelle de votre toiture et de vos panneaux. Je vous fournis un rapport et un devis détaillé sans engagement.</p>
      <div class="service-price">Gratuit &amp; sans engagement</div>
    </div>
  </div>
</section>

<!-- PROCESSUS -->
<section class="process" id="processus">
  <div class="section-tag">Mon fonctionnement</div>
  <h2>Comment ça se passe ?</h2>
  <p class="section-sub">Une intervention simple, rapide et sans mauvaise surprise.</p>
  <div class="process-steps">
    <div class="step">
      <div class="step-num">1</div>
      <h4>Contact &amp; devis</h4>
      <p>Vous me contactez, je vous propose un diagnostic et un devis gratuit sous 24h.</p>
    </div>
    <div class="step">
      <div class="step-num">2</div>
      <h4>Planification</h4>
      <p>On choisit ensemble une date d'intervention selon votre disponibilité.</p>
    </div>
    <div class="step">
      <div class="step-num">3</div>
      <h4>Intervention</h4>
      <p>Nettoyage professionnel avec matériel adapté. Photos avant/après fournies.</p>
    </div>
    <div class="step">
      <div class="step-num">4</div>
      <h4>Résultat garanti</h4>
      <p>Votre satisfaction est ma priorité. Retour possible si le résultat ne vous convient pas.</p>
    </div>
  </div>
</section>

<!-- DEVIS CTA -->
<div class="devis" id="contact">
  <div class="devis-text">
    <h2>Demandez votre devis gratuit</h2>
    <p>Réponse sous 24h — J'interviens à Poitiers et dans un rayon de 20 km</p>
  </div>
  <div class="devis-form">
    <input type="text" placeholder="Votre nom">
    <input type="tel" placeholder="Votre téléphone">
    <input type="text" placeholder="Votre ville">
    <button class="btn-primary" onclick="alert('Merci ! Je vous recontacte sous 24h.')">Envoyer →</button>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <div class="nav-logo">Toit <span>Net</span></div>
      <p>Micro-entreprise spécialisée dans le nettoyage de toitures, façades et panneaux solaires. Basé à Poitiers, j'interviens dans un rayon de 20 km autour de la ville.</p>
    </div>
    <div class="footer-col">
      <h5>Services</h5>
      <ul>
        <li><a href="#">Nettoyage toiture</a></li>
        <li><a href="#">Nettoyage façade</a></li>
        <li><a href="#">Panneaux solaires</a></li>
        <li><a href="#">Diagnostic gratuit</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h5>Contact</h5>
      <ul>
        <li><a href="tel:+33647496518">📞 06 47 49 65 18</a></li>
        <li><a href="mailto:ToitNet.86@gmail.com">✉️ ToitNet.86@gmail.com</a></li>
        <li><a href="https://www.instagram.com/ToitNet.86" target="_blank">📸 Instagram : ToitNet.86</a></li>
        <li><a href="#">📍 Poitiers & 20 km alentours</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2025 Toit Net — Micro-entreprise</p>
    <p style="color:var(--sky-light);font-size:0.78rem;">Nettoyage professionnel · Devis gratuit · Résultat garanti</p>
  </div>
</footer>

<script>
document.querySelectorAll('.ba-wrapper').forEach(function(wrapper) {
  var before  = wrapper.querySelector('.ba-before');
  var divider = wrapper.querySelector('.ba-divider');
  var handle  = wrapper.querySelector('.ba-handle');

  function move(clientX) {
    var rect = wrapper.getBoundingClientRect();
    var pct  = Math.max(0, Math.min(100, (clientX - rect.left) / rect.width * 100));
    before.style.width  = pct + '%';
    divider.style.left  = pct + '%';
    handle.style.left   = pct + '%';
  }

  function reset() {
    before.style.width  = '50%';
    divider.style.left  = '50%';
    handle.style.left   = '50%';
  }

  wrapper.addEventListener('mousemove',  function(e) { move(e.clientX); });
  wrapper.addEventListener('mouseleave', reset);

  wrapper.addEventListener('touchmove', function(e) {
    e.preventDefault();
    move(e.touches[0].clientX);
  }, { passive: false });
  wrapper.addEventListener('touchend', reset);
});
</script>
</body>
</html>
