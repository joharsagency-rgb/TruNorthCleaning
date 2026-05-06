# TruNorthCleaning
. <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TruNorth Cleaning — Spotless. Every Time.</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --navy: #0d1b2a;
    --midnight: #07111c;
    --ice: #c8e8f0;
    --frost: #e8f5f9;
    --arctic: #4db8d4;
    --white: #f9fbfc;
    --muted: #8ba3b0;
    --gold: #d4a843;
    --serif: 'Playfair Display', Georgia, serif;
    --sans: 'DM Sans', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--sans);
    background: var(--navy);
    color: var(--white);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.4rem 5vw;
    background: rgba(13,27,42,0.85);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid rgba(200,232,240,0.08);
    transition: background 0.3s;
  }

  .logo {
    font-family: var(--serif);
    font-size: 1.55rem;
    font-weight: 700;
    letter-spacing: -0.02em;
    color: var(--white);
    text-decoration: none;
    display: flex; align-items: center; gap: 0.5rem;
  }
  .logo span { color: var(--arctic); }
  .logo-icon {
    width: 32px; height: 32px;
    background: var(--arctic);
    clip-path: polygon(50% 0%, 100% 38%, 82% 100%, 18% 100%, 0% 38%);
    display: flex; align-items: center; justify-content: center;
    font-size: 0.85rem;
  }

  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    font-size: 0.88rem; font-weight: 500; letter-spacing: 0.04em;
    text-transform: uppercase; color: var(--muted);
    text-decoration: none; transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--white); }

  .nav-cta {
    background: var(--arctic);
    color: var(--midnight) !important;
    padding: 0.6rem 1.4rem !important;
    border-radius: 2px !important;
    font-weight: 500 !important;
    transition: background 0.2s, transform 0.2s !important;
  }
  .nav-cta:hover { background: var(--ice) !important; transform: translateY(-1px); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 0 5vw;
    position: relative;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 60% 60% at 75% 50%, rgba(77,184,212,0.12) 0%, transparent 70%),
      radial-gradient(ellipse 40% 80% at 10% 80%, rgba(77,184,212,0.06) 0%, transparent 60%),
      linear-gradient(160deg, var(--midnight) 0%, #0a1929 60%, #0d2233 100%);
  }

  /* Snowflake-like geometric deco */
  .hero-deco {
    position: absolute; right: 5vw; top: 50%;
    transform: translateY(-50%);
    width: min(45vw, 560px); height: min(45vw, 560px);
    opacity: 0.07;
    animation: slowSpin 40s linear infinite;
  }
  @keyframes slowSpin { to { transform: translateY(-50%) rotate(360deg); } }

  .hero-content {
    position: relative; z-index: 2;
    max-width: 640px;
    animation: fadeUp 1s ease both;
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .hero-eyebrow {
    font-size: 0.78rem; font-weight: 500; letter-spacing: 0.18em;
    text-transform: uppercase; color: var(--arctic);
    margin-bottom: 1.4rem;
    display: flex; align-items: center; gap: 0.8rem;
  }
  .hero-eyebrow::before {
    content: ''; display: block;
    width: 32px; height: 1px; background: var(--arctic);
  }

  .hero h1 {
    font-family: var(--serif);
    font-size: clamp(3rem, 6vw, 5.5rem);
    font-weight: 900;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 1.8rem;
  }
  .hero h1 em {
    font-style: italic; color: var(--arctic);
    display: block;
  }

  .hero-sub {
    font-size: 1.05rem; font-weight: 300;
    color: var(--muted); line-height: 1.7;
    max-width: 480px;
    margin-bottom: 2.8rem;
    animation: fadeUp 1s 0.2s ease both;
  }

  .hero-actions {
    display: flex; gap: 1.2rem; flex-wrap: wrap;
    animation: fadeUp 1s 0.35s ease both;
  }

  .btn-primary {
    background: var(--arctic);
    color: var(--midnight);
    padding: 1rem 2.2rem;
    font-family: var(--sans); font-size: 0.9rem; font-weight: 500;
    letter-spacing: 0.05em; text-transform: uppercase;
    border: none; cursor: pointer; text-decoration: none;
    display: inline-flex; align-items: center; gap: 0.5rem;
    transition: background 0.2s, transform 0.2s, box-shadow 0.2s;
    clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 10px, 100% 100%, 10px 100%, 0 calc(100% - 10px));
  }
  .btn-primary:hover {
    background: var(--ice);
    transform: translateY(-2px);
    box-shadow: 0 12px 32px rgba(77,184,212,0.3);
  }

  .btn-outline {
    border: 1px solid rgba(200,232,240,0.25);
    color: var(--white);
    padding: 1rem 2.2rem;
    font-family: var(--sans); font-size: 0.9rem; font-weight: 400;
    letter-spacing: 0.05em; text-transform: uppercase;
    background: transparent; cursor: pointer; text-decoration: none;
    display: inline-flex; align-items: center; gap: 0.5rem;
    transition: border-color 0.2s, color 0.2s;
  }
  .btn-outline:hover { border-color: var(--arctic); color: var(--arctic); }

  .hero-stats {
    display: flex; gap: 3rem;
    margin-top: 4rem; padding-top: 3rem;
    border-top: 1px solid rgba(200,232,240,0.1);
    animation: fadeUp 1s 0.5s ease both;
  }
  .stat-num {
    font-family: var(--serif); font-size: 2.2rem; font-weight: 700;
    color: var(--white); line-height: 1;
  }
  .stat-label {
    font-size: 0.78rem; font-weight: 400; letter-spacing: 0.06em;
    color: var(--muted); text-transform: uppercase; margin-top: 0.3rem;
  }

  /* ── SECTION SHARED ── */
  section { padding: 7rem 5vw; }

  .section-label {
    font-size: 0.75rem; font-weight: 500; letter-spacing: 0.2em;
    text-transform: uppercase; color: var(--arctic);
    margin-bottom: 1rem;
    display: flex; align-items: center; gap: 0.8rem;
  }
  .section-label::before {
    content: ''; display: block;
    width: 24px; height: 1px; background: var(--arctic);
  }

  .section-title {
    font-family: var(--serif);
    font-size: clamp(2rem, 3.5vw, 3.2rem);
    font-weight: 700; line-height: 1.15;
    letter-spacing: -0.02em;
  }

  /* ── SERVICES ── */
  .services { background: var(--midnight); }

  .services-header {
    display: flex; justify-content: space-between; align-items: flex-end;
    flex-wrap: wrap; gap: 2rem;
    margin-bottom: 4rem;
  }
  .services-intro {
    font-size: 0.95rem; color: var(--muted); max-width: 340px; line-height: 1.7;
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5px;
    background: rgba(200,232,240,0.06);
  }

  .service-card {
    background: var(--midnight);
    padding: 3rem 2.5rem;
    position: relative; overflow: hidden;
    transition: background 0.3s;
    cursor: default;
  }
  .service-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--arctic), transparent);
    transform: scaleX(0); transition: transform 0.4s;
  }
  .service-card:hover { background: #0c1e30; }
  .service-card:hover::before { transform: scaleX(1); }

  .service-icon {
    width: 52px; height: 52px;
    background: rgba(77,184,212,0.1);
    border: 1px solid rgba(77,184,212,0.2);
    border-radius: 4px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.5rem;
    margin-bottom: 2rem;
    transition: background 0.3s, border-color 0.3s;
  }
  .service-card:hover .service-icon {
    background: rgba(77,184,212,0.18);
    border-color: rgba(77,184,212,0.4);
  }

  .service-name {
    font-family: var(--serif); font-size: 1.3rem; font-weight: 700;
    margin-bottom: 1rem; letter-spacing: -0.01em;
  }
  .service-desc {
    font-size: 0.88rem; color: var(--muted); line-height: 1.75;
  }
  .service-price {
    margin-top: 2rem;
    font-size: 0.8rem; font-weight: 500;
    letter-spacing: 0.06em; text-transform: uppercase;
    color: var(--arctic);
    display: flex; align-items: center; gap: 0.5rem;
  }
  .service-price::after {
    content: '→';
  }

  /* ── WHY US ── */
  .why { background: var(--navy); }

  .why-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 6rem; align-items: center;
    margin-top: 4rem;
  }

  .why-visual {
    position: relative;
  }
  .why-big-num {
    font-family: var(--serif);
    font-size: clamp(8rem, 15vw, 14rem);
    font-weight: 900;
    line-height: 0.85;
    color: transparent;
    -webkit-text-stroke: 1px rgba(77,184,212,0.15);
    pointer-events: none;
    user-select: none;
  }
  .why-badge {
    position: absolute; bottom: 1rem; right: 0;
    background: var(--arctic);
    color: var(--midnight);
    padding: 1.5rem;
    text-align: center;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
  }
  .why-badge-num {
    font-family: var(--serif); font-size: 2.2rem; font-weight: 900; display: block;
  }
  .why-badge-label { font-size: 0.7rem; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; }

  .why-features { display: flex; flex-direction: column; gap: 0.4rem; }
  .why-feature {
    padding: 1.8rem 2rem;
    border: 1px solid rgba(200,232,240,0.07);
    border-radius: 2px;
    transition: border-color 0.3s, background 0.3s;
    display: flex; gap: 1.5rem; align-items: flex-start;
  }
  .why-feature:hover { border-color: rgba(77,184,212,0.25); background: rgba(77,184,212,0.03); }
  .why-feat-icon { font-size: 1.4rem; flex-shrink: 0; margin-top: 0.1rem; }
  .why-feat-title { font-family: var(--serif); font-size: 1.05rem; font-weight: 700; margin-bottom: 0.4rem; }
  .why-feat-desc { font-size: 0.85rem; color: var(--muted); line-height: 1.65; }

  /* ── PROCESS ── */
  .process { background: var(--midnight); }
  .process-steps {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 0; margin-top: 4rem;
    position: relative;
  }
  .process-steps::before {
    content: '';
    position: absolute; top: 2.8rem; left: 12.5%; right: 12.5%;
    height: 1px; background: rgba(77,184,212,0.2);
    z-index: 0;
  }
  .step { text-align: center; padding: 0 1.5rem; position: relative; z-index: 1; }
  .step-num {
    width: 56px; height: 56px; border-radius: 50%;
    background: var(--midnight); border: 1px solid rgba(77,184,212,0.35);
    display: flex; align-items: center; justify-content: center;
    margin: 0 auto 1.8rem;
    font-family: var(--serif); font-size: 1.2rem; font-weight: 700; color: var(--arctic);
    position: relative;
  }
  .step:first-child .step-num { background: var(--arctic); color: var(--midnight); border-color: var(--arctic); }
  .step-title { font-family: var(--serif); font-size: 1.1rem; font-weight: 700; margin-bottom: 0.8rem; }
  .step-desc { font-size: 0.83rem; color: var(--muted); line-height: 1.7; }

  /* ── TESTIMONIALS ── */
  .testimonials { background: var(--navy); }
  .testimonials-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem; margin-top: 4rem;
  }
  .testimonial {
    padding: 2.5rem;
    border: 1px solid rgba(200,232,240,0.08);
    border-radius: 2px;
    position: relative;
    transition: border-color 0.3s;
  }
  .testimonial:hover { border-color: rgba(77,184,212,0.2); }
  .testimonial::before {
    content: '\201C';
    font-family: var(--serif); font-size: 5rem; font-weight: 900;
    color: rgba(77,184,212,0.12); line-height: 1;
    position: absolute; top: 1rem; right: 1.5rem;
  }
  .testimonial-stars { color: var(--gold); font-size: 0.85rem; letter-spacing: 0.1em; margin-bottom: 1.2rem; }
  .testimonial-text { font-size: 0.9rem; color: #b0cdd8; line-height: 1.8; margin-bottom: 2rem; }
  .testimonial-author { display: flex; align-items: center; gap: 1rem; }
  .testimonial-avatar {
    width: 42px; height: 42px; border-radius: 50%;
    background: linear-gradient(135deg, var(--arctic), #2980a8);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--serif); font-size: 1rem; font-weight: 700; color: var(--midnight);
    flex-shrink: 0;
  }
  .testimonial-name { font-size: 0.88rem; font-weight: 500; }
  .testimonial-loc { font-size: 0.75rem; color: var(--muted); margin-top: 0.2rem; }

  /* ── CTA ── */
  .cta-section {
    background: var(--midnight);
    padding: 7rem 5vw;
    text-align: center;
    position: relative; overflow: hidden;
  }
  .cta-section::before {
    content: '';
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 50% 80% at 50% 100%, rgba(77,184,212,0.1) 0%, transparent 60%);
  }
  .cta-section .section-label { justify-content: center; }
  .cta-section .section-title { margin: 0 auto 1.5rem; }
  .cta-sub { font-size: 1rem; color: var(--muted); margin-bottom: 3rem; }
  .cta-actions { display: flex; gap: 1.2rem; justify-content: center; flex-wrap: wrap; }

  .contact-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 1px; background: rgba(200,232,240,0.06);
    margin-top: 5rem;
  }
  .contact-item {
    background: var(--midnight); padding: 2.5rem 2rem; text-align: center;
  }
  .contact-item-icon { font-size: 1.8rem; margin-bottom: 1rem; }
  .contact-item-label { font-size: 0.75rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--muted); margin-bottom: 0.5rem; }
  .contact-item-value { font-family: var(--serif); font-size: 1.1rem; font-weight: 700; color: var(--arctic); }

  /* ── FOOTER ── */
  footer {
    background: var(--midnight);
    border-top: 1px solid rgba(200,232,240,0.06);
    padding: 3rem 5vw;
    display: flex; justify-content: space-between; align-items: center;
    flex-wrap: wrap; gap: 1.5rem;
  }
  .footer-copy { font-size: 0.8rem; color: var(--muted); }
  .footer-links { display: flex; gap: 2rem; }
  .footer-links a { font-size: 0.8rem; color: var(--muted); text-decoration: none; transition: color 0.2s; }
  .footer-links a:hover { color: var(--arctic); }

  /* ── BANNER STRIPE ── */
  .banner-stripe {
    background: var(--arctic);
    color: var(--midnight);
    padding: 0.8rem 5vw;
    text-align: center;
    font-size: 0.82rem; font-weight: 500; letter-spacing: 0.06em;
    text-transform: uppercase;
  }
  .banner-stripe strong { font-weight: 700; }

  /* ── MOBILE ── */
  @media (max-width: 768px) {
    .nav-links { display: none; }
    .why-grid { grid-template-columns: 1fr; gap: 3rem; }
    .why-visual { display: none; }
    .process-steps { grid-template-columns: 1fr 1fr; gap: 2rem; }
    .process-steps::before { display: none; }
    .testimonials-grid { grid-template-columns: 1fr; }
    .contact-grid { grid-template-columns: 1fr; }
    .hero-stats { gap: 2rem; flex-wrap: wrap; }
  }
</style>
</head>
<body>

<!-- Banner -->
<div class="banner-stripe">
  📍 Serving Chatham-Kent &amp; surrounding areas — <strong>Book online & save 15% on your first clean</strong>
</div>

<!-- Nav -->
<nav>
  <a href="#" class="logo">
    <div class="logo-icon"></div>
    Tru<span>North</span> Cleaning
  </a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#why">Why Us</a></li>
    <li><a href="#process">Process</a></li>
    <li><a href="#testimonials">Reviews</a></li>
    <li><a href="#contact" class="nav-cta">Book Now</a></li>
  </ul>
</nav>

<!-- Hero -->
<section class="hero" id="home">
  <div class="hero-bg"></div>

  <!-- Geometric deco -->
  <svg class="hero-deco" viewBox="0 0 400 400" fill="none" xmlns="http://www.w3.org/2000/svg">
    <circle cx="200" cy="200" r="190" stroke="white" stroke-width="0.5"/>
    <circle cx="200" cy="200" r="140" stroke="white" stroke-width="0.5"/>
    <circle cx="200" cy="200" r="90" stroke="white" stroke-width="0.5"/>
    <line x1="200" y1="10" x2="200" y2="390" stroke="white" stroke-width="0.5"/>
    <line x1="10" y1="200" x2="390" y2="200" stroke="white" stroke-width="0.5"/>
    <line x1="66" y1="66" x2="334" y2="334" stroke="white" stroke-width="0.5"/>
    <line x1="334" y1="66" x2="66" y2="334" stroke="white" stroke-width="0.5"/>
    <polygon points="200,20 380,110 380,290 200,380 20,290 20,110" stroke="white" stroke-width="0.5" fill="none"/>
    <polygon points="200,50 350,125 350,275 200,350 50,275 50,125" stroke="white" stroke-width="0.4" fill="none"/>
  </svg>

  <div class="hero-content">
    <p class="hero-eyebrow">Professional House Cleaning</p>
    <h1>A Cleaner Home.<br><em>True &amp; Thorough.</em></h1>
    <p class="hero-sub">TruNorth Cleaning delivers meticulous, reliable residential cleaning services. We treat your home like our own — with care, precision, and products that are safe for your family.</p>
    <div class="hero-actions">
      <a href="#contact" class="btn-primary">Get a Free Quote ✦</a>
      <a href="#services" class="btn-outline">Our Services →</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">500+</div>
        <div class="stat-label">Homes Cleaned</div>
      </div>
      <div>
        <div class="stat-num">4.9★</div>
        <div class="stat-label">Average Rating</div>
      </div>
      <div>
        <div class="stat-num">100%</div>
        <div class="stat-label">Satisfaction Promise</div>
      </div>
    </div>
  </div>
</section>

<!-- Services -->
<section class="services" id="services">
  <div class="services-header">
    <div>
      <p class="section-label">What We Offer</p>
      <h2 class="section-title">Cleaning Services<br>Built Around You</h2>
    </div>
    <p class="services-intro">Every home is different. We offer flexible packages tailored to your schedule, budget, and standards — because clean shouldn't be one-size-fits-all.</p>
  </div>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">🏠</div>
      <div class="service-name">Regular Maintenance</div>
      <p class="service-desc">Weekly, bi-weekly, or monthly cleans to keep your home consistently fresh. Dusting, vacuuming, mopping, bathrooms, kitchen surfaces — everything covered, every visit.</p>
      <div class="service-price">Starting at $120</div>
    </div>
    <div class="service-card">
      <div class="service-icon">✨</div>
      <div class="service-name">Deep Clean</div>
      <p class="service-desc">A top-to-bottom intensive clean. Inside appliances, baseboards, ceiling fans, grout scrubbing, and every corner you've been meaning to get to. Perfect for a seasonal reset.</p>
      <div class="service-price">Starting at $240</div>
    </div>
    <div class="service-card">
      <div class="service-icon">📦</div>
      <div class="service-name">Move In / Move Out</div>
      <p class="service-desc">Transition stress-free. We make sure every surface, cabinet, and closet is spotless so your old place passes inspection or your new one feels like home from day one.</p>
      <div class="service-price">Starting at $200</div>
    </div>
    <div class="service-card">
      <div class="service-icon">🎉</div>
      <div class="service-name">Post-Event Clean</div>
      <p class="service-desc">Host without the aftermath. After your gathering, we come in and restore your space quickly so you can relax — not scrub.</p>
      <div class="service-price">Starting at $150</div>
    </div>
    <div class="service-card">
      <div class="service-icon">🌿</div>
      <div class="service-name">Eco-Friendly Options</div>
      <p class="service-desc">All-natural, non-toxic cleaning products safe for children, pets, and sensitive individuals. Just as effective, even better for your household.</p>
      <div class="service-price">Available Add-on</div>
    </div>
    <div class="service-card">
      <div class="service-icon">🏢</div>
      <div class="service-name">Small Office Cleaning</div>
      <p class="service-desc">Keep your workspace as professional as you are. Scheduled office cleans for small to medium businesses — reliable, discreet, and thorough.</p>
      <div class="service-price">Custom Quote</div>
    </div>
  </div>
</section>

<!-- Why Us -->
<section class="why" id="why">
  <div class="why-grid">
    <div class="why-visual">
      <div class="why-big-num">5★</div>
      <div class="why-badge">
        <span class="why-badge-num">100%</span>
        <span class="why-badge-label">Satisfaction Guarantee</span>
      </div>
    </div>
    <div>
      <p class="section-label">Why TruNorth</p>
      <h2 class="section-title" style="margin-bottom: 2.5rem;">Local. Trusted.<br>Exceptional.</h2>
      <div class="why-features">
        <div class="why-feature">
          <div class="why-feat-icon">🔒</div>
          <div>
            <div class="why-feat-title">Insured &amp; Background-Checked</div>
            <p class="why-feat-desc">Every TruNorth cleaner is fully insured and has passed a thorough background check. Your home and family are always safe.</p>
          </div>
        </div>
        <div class="why-feature">
          <div class="why-feat-icon">⏰</div>
          <div>
            <div class="why-feat-title">Punctual. Every Single Time.</div>
            <p class="why-feat-desc">We respect your schedule. If we're late, you get a discount — no excuses. Reliability is part of the service.</p>
          </div>
        </div>
        <div class="why-feature">
          <div class="why-feat-icon">🧹</div>
          <div>
            <div class="why-feat-title">Hospital-Grade Attention to Detail</div>
            <p class="why-feat-desc">We don't cut corners — we clean them. Our thorough checklist ensures nothing is missed, every visit.</p>
          </div>
        </div>
        <div class="why-feature">
          <div class="why-feat-icon">💬</div>
          <div>
            <div class="why-feat-title">Easy Communication</div>
            <p class="why-feat-desc">Book online, reschedule by text, pay by e-transfer. Simple, transparent, and always friendly.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Process -->
<section class="process" id="process">
  <div style="text-align: center; margin-bottom: 1rem;">
    <p class="section-label" style="justify-content: center;">How It Works</p>
    <h2 class="section-title">From Booking to<br>Brilliantly Clean</h2>
  </div>
  <div class="process-steps">
    <div class="step">
      <div class="step-num">1</div>
      <div class="step-title">Get a Quote</div>
      <p class="step-desc">Fill out our quick form or give us a call. We'll provide a transparent, no-obligation estimate within hours.</p>
    </div>
    <div class="step">
      <div class="step-num">2</div>
      <div class="step-title">Pick Your Time</div>
      <p class="step-desc">Choose a date and time that works for you. We offer flexible morning and afternoon slots, including weekends.</p>
    </div>
    <div class="step">
      <div class="step-num">3</div>
      <div class="step-title">We Do the Work</div>
      <p class="step-desc">Our team arrives on time, equipped with everything needed, and gets to work. No supervision required.</p>
    </div>
    <div class="step">
      <div class="step-num">4</div>
      <div class="step-title">Enjoy Your Home</div>
      <p class="step-desc">Come home to a spotless space. If anything isn't right, we'll come back and fix it — free of charge.</p>
    </div>
  </div>
</section>

<!-- Testimonials -->
<section class="testimonials" id="testimonials">
  <p class="section-label">Happy Clients</p>
  <h2 class="section-title" style="margin-bottom: 0.5rem;">Trusted by<br>Hundreds of Families</h2>
  <div class="testimonials-grid">
    <div class="testimonial">
      <div class="testimonial-stars">★★★★★</div>
      <p class="testimonial-text">TruNorth has been cleaning our home for over a year now. The consistency is remarkable — every single visit our home looks incredible. They genuinely care about what they do.</p>
      <div class="testimonial-author">
        <div class="testimonial-avatar">SM</div>
        <div>
          <div class="testimonial-name">Sarah M.</div>
          <div class="testimonial-loc">Chatham, ON</div>
        </div>
      </div>
    </div>
    <div class="testimonial">
      <div class="testimonial-stars">★★★★★</div>
      <p class="testimonial-text">Used them for a move-out clean and my landlord was blown away. Got my full deposit back. Absolutely worth every penny — will use again in my new place.</p>
      <div class="testimonial-author">
        <div class="testimonial-avatar">JT</div>
        <div>
          <div class="testimonial-name">James T.</div>
          <div class="testimonial-loc">Tilbury, ON</div>
        </div>
      </div>
    </div>
    <div class="testimonial">
      <div class="testimonial-stars">★★★★★</div>
      <p class="testimonial-text">I have two dogs and a toddler — the house was a disaster. TruNorth came in and I barely recognized the place. So thorough. So professional. Booked monthly right away.</p>
      <div class="testimonial-author">
        <div class="testimonial-avatar">LK</div>
        <div>
          <div class="testimonial-name">Lindsay K.</div>
          <div class="testimonial-loc">Blenheim, ON</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA / Contact -->
<section class="cta-section" id="contact">
  <div style="position: relative; z-index: 1;">
    <p class="section-label">Get Started</p>
    <h2 class="section-title" style="max-width: 540px; margin: 0 auto 1.5rem;">Ready for a Cleaner<br>Home?</h2>
    <p class="cta-sub">Book your first clean today and save 15%. No contracts, no commitments.</p>
    <div class="cta-actions">
      <a href="tel:+15191234567" class="btn-primary">📞 Call to Book</a>
      <a href="mailto:hello@trunorthcleaning.ca" class="btn-outline">Email Us →</a>
    </div>
    <div class="contact-grid">
      <div class="contact-item">
        <div class="contact-item-icon">📞</div>
        <div class="contact-item-label">Phone</div>
        <div class="contact-item-value">(519) 123-4567</div>
      </div>
      <div class="contact-item">
        <div class="contact-item-icon">✉️</div>
        <div class="contact-item-label">Email</div>
        <div class="contact-item-value">hello@trunorthcleaning.ca</div>
      </div>
      <div class="contact-item">
        <div class="contact-item-icon">📍</div>
        <div class="contact-item-label">Service Area</div>
        <div class="contact-item-value">Chatham-Kent, ON</div>
      </div>
    </div>
  </div>
</section>

<!-- Footer -->
<footer>
  <div>
    <a href="#" class="logo" style="font-size: 1.2rem;">
      <div class="logo-icon" style="width: 24px; height: 24px; font-size: 0.65rem;"></div>
      Tru<span>North</span> Cleaning
    </a>
    <p class="footer-copy" style="margin-top: 0.5rem;">© 2025 TruNorth Cleaning. Serving Chatham-Kent with pride.</p>
  </div>
  <div class="footer-links">
    <a href="#services">Services</a>
    <a href="#why">About</a>
    <a href="#testimonials">Reviews</a>
    <a href="#contact">Contact</a>
  </div>
</footer>

<script>
  // Smooth nav background on scroll
  const nav = document.querySelector('nav');
  window.addEventListener('scroll', () => {
    nav.style.background = window.scrollY > 60
      ? 'rgba(7,17,28,0.97)'
      : 'rgba(13,27,42,0.85)';
  });

  // Fade-in on scroll
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.service-card, .why-feature, .step, .testimonial, .contact-item').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
