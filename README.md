<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Healthy Sense — Wellness That Actually Works</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --sage: #7A9E7E;
    --sage-light: #B8D4BA;
    --sage-dark: #4A6B4E;
    --cream: #F9F5EF;
    --warm-white: #FDFAF6;
    --charcoal: #1C1C1A;
    --stone: #6B6560;
    --gold: #C8A96E;
    --gold-light: #E8D5B0;
    --blush: #E8D5C4;
    --terracotta: #C4785A;
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--warm-white);
    color: var(--charcoal);
    overflow-x: hidden;
  }

  /* ─── NAV ─────────────────────────────────── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    padding: 24px 60px;
    display: flex; align-items: center; justify-content: space-between;
    background: rgba(253,250,246,0.85);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(122,158,126,0.15);
    transition: all 0.3s ease;
  }
  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.5rem; font-weight: 600; letter-spacing: 0.04em;
    color: var(--sage-dark);
    text-decoration: none;
  }
  .nav-logo span { color: var(--gold); }
  .nav-links { display: flex; gap: 36px; list-style: none; }
  .nav-links a {
    font-size: 0.82rem; letter-spacing: 0.1em; text-transform: uppercase;
    color: var(--stone); text-decoration: none; font-weight: 500;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--sage-dark); }
  .nav-cta {
    background: var(--sage-dark); color: #fff;
    padding: 11px 26px; border-radius: 2px;
    font-size: 0.78rem; letter-spacing: 0.12em; text-transform: uppercase;
    text-decoration: none; font-weight: 500;
    transition: background 0.25s, transform 0.2s;
  }
  .nav-cta:hover { background: var(--sage); transform: translateY(-1px); }

  /* ─── HERO ────────────────────────────────── */
  .hero {
    min-height: 100vh;
    display: grid; grid-template-columns: 1fr 1fr;
    padding-top: 80px;
    position: relative; overflow: hidden;
  }
  .hero-left {
    display: flex; flex-direction: column; justify-content: center;
    padding: 80px 60px 80px 80px;
    position: relative; z-index: 2;
  }
  .hero-eyebrow {
    display: inline-flex; align-items: center; gap: 10px;
    font-size: 0.72rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--terracotta); font-weight: 500; margin-bottom: 28px;
  }
  .hero-eyebrow::before {
    content: ''; width: 30px; height: 1px; background: var(--terracotta);
  }
  h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3rem, 5vw, 4.8rem);
    font-weight: 300; line-height: 1.1;
    color: var(--charcoal); margin-bottom: 28px;
  }
  h1 em { font-style: italic; color: var(--sage-dark); }
  .hero-sub {
    font-size: 1.05rem; line-height: 1.7; color: var(--stone);
    max-width: 440px; margin-bottom: 44px; font-weight: 300;
  }
  .hero-actions { display: flex; gap: 16px; align-items: center; }
  .btn-primary {
    background: var(--sage-dark); color: #fff;
    padding: 16px 36px; border-radius: 2px;
    font-size: 0.82rem; letter-spacing: 0.12em; text-transform: uppercase;
    text-decoration: none; font-weight: 500;
    transition: all 0.25s;
    border: none; cursor: pointer;
  }
  .btn-primary:hover { background: var(--sage); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(74,107,78,0.25); }
  .btn-ghost {
    color: var(--sage-dark); font-size: 0.82rem; letter-spacing: 0.1em;
    text-transform: uppercase; text-decoration: none; font-weight: 500;
    display: flex; align-items: center; gap: 8px;
    border-bottom: 1px solid var(--sage-light); padding-bottom: 2px;
    transition: all 0.2s;
  }
  .btn-ghost:hover { color: var(--sage-dark); border-color: var(--sage-dark); gap: 14px; }
  .hero-trust {
    margin-top: 52px; display: flex; align-items: center; gap: 24px;
  }
  .trust-stars { display: flex; gap: 3px; }
  .trust-stars span { color: var(--gold); font-size: 1rem; }
  .trust-text { font-size: 0.8rem; color: var(--stone); }
  .trust-text strong { color: var(--charcoal); }

  .hero-right {
    position: relative; background: var(--cream);
    display: flex; align-items: center; justify-content: center;
    overflow: hidden;
  }
  .hero-visual {
    width: 100%; height: 100%; position: relative;
    display: flex; align-items: center; justify-content: center;
  }
  /* Decorative plant-like SVG background */
  .hero-blob {
    position: absolute; width: 500px; height: 500px;
    background: radial-gradient(ellipse at 40% 40%, var(--sage-light) 0%, transparent 70%);
    border-radius: 50%; opacity: 0.6; top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    animation: breathe 6s ease-in-out infinite;
  }
  @keyframes breathe {
    0%,100% { transform: translate(-50%,-50%) scale(1); }
    50% { transform: translate(-50%,-50%) scale(1.08); }
  }
  .hero-card {
    position: relative; z-index: 2;
    background: #fff; border-radius: 4px;
    padding: 40px; max-width: 340px;
    box-shadow: 0 20px 60px rgba(28,28,26,0.08);
  }
  .hero-card-icon {
    width: 52px; height: 52px; background: var(--sage-light);
    border-radius: 50%; display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem; margin-bottom: 20px;
  }
  .hero-card h3 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.4rem; font-weight: 600; margin-bottom: 10px;
  }
  .hero-card p { font-size: 0.88rem; color: var(--stone); line-height: 1.6; }
  .hero-badge {
    position: absolute; top: 30px; right: 30px;
    background: var(--terracotta); color: #fff;
    padding: 8px 16px; border-radius: 2px;
    font-size: 0.72rem; letter-spacing: 0.14em; text-transform: uppercase;
    font-weight: 500;
  }
  .hero-stats {
    position: absolute; bottom: 40px; left: 40px;
    display: flex; gap: 32px;
  }
  .stat { text-align: left; }
  .stat-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2rem; font-weight: 600; color: var(--sage-dark);
    line-height: 1;
  }
  .stat-label { font-size: 0.72rem; color: var(--stone); text-transform: uppercase; letter-spacing: 0.1em; }

  /* ─── SECTION BASE ────────────────────────── */
  section { padding: 100px 80px; }
  .section-label {
    font-size: 0.72rem; letter-spacing: 0.22em; text-transform: uppercase;
    color: var(--terracotta); font-weight: 500; margin-bottom: 16px;
    display: flex; align-items: center; gap: 10px;
  }
  .section-label::before { content: ''; width: 24px; height: 1px; background: var(--terracotta); }
  h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2.2rem, 3.5vw, 3.4rem);
    font-weight: 300; line-height: 1.15;
    color: var(--charcoal);
  }
  h2 em { font-style: italic; color: var(--sage-dark); }

  /* ─── PROBLEM BAR ─────────────────────────── */
  .problem-bar {
    background: var(--charcoal); color: var(--cream);
    padding: 28px 80px;
    display: flex; align-items: center; justify-content: space-between;
    gap: 40px;
  }
  .problem-bar p {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.2rem; font-style: italic; font-weight: 300;
    opacity: 0.8; flex: 1;
  }
  .problem-bar p strong { color: var(--gold); font-style: normal; font-weight: 600; opacity: 1; }

  /* ─── PROBLEM SECTION ─────────────────────── */
  .problem-section { background: var(--cream); }
  .problem-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 80px; margin-top: 60px; align-items: center;
  }
  .problem-list { display: flex; flex-direction: column; gap: 28px; }
  .problem-item {
    display: flex; gap: 20px; align-items: flex-start;
    padding: 24px; background: var(--warm-white);
    border-left: 3px solid var(--terracotta); border-radius: 0 4px 4px 0;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .problem-item:hover { transform: translateX(4px); box-shadow: -4px 0 0 var(--sage-dark), 4px 8px 24px rgba(0,0,0,0.06); }
  .problem-icon { font-size: 1.4rem; flex-shrink: 0; margin-top: 2px; }
  .problem-item h4 { font-size: 1rem; font-weight: 500; margin-bottom: 6px; }
  .problem-item p { font-size: 0.88rem; color: var(--stone); line-height: 1.6; }
  .problem-visual {
    background: var(--sage-dark); border-radius: 4px;
    padding: 50px 40px; color: #fff; text-align: center;
    position: relative; overflow: hidden;
  }
  .problem-visual::before {
    content: ''; position: absolute; top: -30px; right: -30px;
    width: 180px; height: 180px;
    border: 40px solid rgba(255,255,255,0.06);
    border-radius: 50%;
  }
  .problem-visual blockquote {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.6rem; font-style: italic; font-weight: 300;
    line-height: 1.4; margin-bottom: 24px;
    position: relative; z-index: 1;
  }
  .problem-visual cite {
    font-size: 0.78rem; letter-spacing: 0.12em; text-transform: uppercase;
    opacity: 0.6; font-style: normal;
  }

  /* ─── SOLUTION / HOW IT WORKS ─────────────── */
  .solution-section { background: var(--warm-white); }
  .solution-steps {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 2px; margin-top: 60px;
  }
  .step {
    padding: 50px 36px; background: var(--cream);
    position: relative; overflow: hidden;
    transition: background 0.3s;
  }
  .step:hover { background: var(--sage-dark); color: #fff; }
  .step:hover .step-desc { color: rgba(255,255,255,0.7); }
  .step:hover .step-num { color: rgba(255,255,255,0.15); }
  .step-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 5rem; font-weight: 600; color: var(--sage-light);
    line-height: 1; margin-bottom: 24px;
    transition: color 0.3s;
  }
  .step-icon { font-size: 2rem; margin-bottom: 16px; }
  .step h3 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.5rem; font-weight: 600; margin-bottom: 12px;
    transition: color 0.3s;
  }
  .step-desc {
    font-size: 0.88rem; color: var(--stone); line-height: 1.7;
    transition: color 0.3s;
  }
  .step-cta-link {
    display: inline-block; margin-top: 20px;
    font-size: 0.78rem; letter-spacing: 0.12em; text-transform: uppercase;
    color: var(--sage-dark); text-decoration: none; font-weight: 500;
    border-bottom: 1px solid var(--sage-light);
    transition: all 0.2s;
  }
  .step:hover .step-cta-link { color: var(--gold-light); border-color: rgba(232,213,176,0.5); }

  /* ─── PRODUCTS ────────────────────────────── */
  .products-section { background: var(--cream); }
  .products-header {
    display: flex; justify-content: space-between; align-items: flex-end;
    margin-bottom: 50px;
  }
  .products-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }
  .product-card {
    background: var(--warm-white); border-radius: 4px; overflow: hidden;
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: pointer;
  }
  .product-card:hover { transform: translateY(-6px); box-shadow: 0 20px 50px rgba(28,28,26,0.1); }
  .product-img {
    height: 240px; position: relative;
    display: flex; align-items: center; justify-content: center;
    font-size: 5rem;
  }
  .product-img-bg-1 { background: linear-gradient(135deg, var(--sage-light) 0%, var(--blush) 100%); }
  .product-img-bg-2 { background: linear-gradient(135deg, var(--gold-light) 0%, var(--sage-light) 100%); }
  .product-img-bg-3 { background: linear-gradient(135deg, var(--blush) 0%, var(--gold-light) 100%); }
  .product-tag {
    position: absolute; top: 16px; left: 16px;
    background: var(--charcoal); color: #fff;
    padding: 5px 12px; border-radius: 2px;
    font-size: 0.68rem; letter-spacing: 0.14em; text-transform: uppercase;
  }
  .product-body { padding: 28px; }
  .product-body h3 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.4rem; font-weight: 600; margin-bottom: 8px;
  }
  .product-body p { font-size: 0.85rem; color: var(--stone); line-height: 1.6; margin-bottom: 20px; }
  .product-footer {
    display: flex; align-items: center; justify-content: space-between;
  }
  .price {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.5rem; font-weight: 600; color: var(--sage-dark);
  }
  .price span { font-size: 0.85rem; color: var(--stone); font-family: 'DM Sans', sans-serif; font-weight: 300; }
  .add-btn {
    background: var(--sage-dark); color: #fff;
    padding: 10px 20px; border-radius: 2px; border: none; cursor: pointer;
    font-size: 0.78rem; letter-spacing: 0.1em; text-transform: uppercase;
    font-family: 'DM Sans', sans-serif; font-weight: 500;
    transition: background 0.2s;
  }
  .add-btn:hover { background: var(--sage); }

  /* ─── PROOF / TESTIMONIALS ────────────────── */
  .proof-section { background: var(--warm-white); }
  .proof-intro {
    display: grid; grid-template-columns: 1fr 2fr;
    gap: 80px; margin-bottom: 60px; align-items: end;
  }
  .testimonials-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 20px;
  }
  .testimonial {
    background: var(--cream); padding: 32px;
    border-radius: 4px; position: relative;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .testimonial:hover { transform: translateY(-4px); box-shadow: 0 12px 36px rgba(28,28,26,0.08); }
  .testimonial:nth-child(2) { margin-top: 24px; }
  .testimonial-quote {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3rem; color: var(--sage-light); line-height: 0.5;
    margin-bottom: 16px;
  }
  .testimonial p {
    font-size: 0.9rem; line-height: 1.7; color: var(--stone); margin-bottom: 24px;
    font-style: italic; font-family: 'Cormorant Garamond', serif; font-size: 1.05rem;
  }
  .testimonial-author { display: flex; align-items: center; gap: 14px; }
  .author-avatar {
    width: 40px; height: 40px; border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem; background: var(--sage-light);
  }
  .author-name { font-weight: 500; font-size: 0.88rem; }
  .author-detail { font-size: 0.75rem; color: var(--stone); }
  .review-stars { display: flex; gap: 2px; margin-bottom: 12px; }
  .review-stars span { color: var(--gold); font-size: 0.85rem; }

  /* ─── CREDENTIALS / TRUST ─────────────────── */
  .trust-section {
    background: var(--sage-dark); color: #fff;
    padding: 80px;
  }
  .trust-grid {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 40px; margin-top: 50px;
  }
  .trust-item { text-align: center; }
  .trust-icon { font-size: 2.2rem; margin-bottom: 16px; }
  .trust-item h4 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.2rem; font-weight: 600; margin-bottom: 8px;
  }
  .trust-item p { font-size: 0.82rem; opacity: 0.65; line-height: 1.6; }
  .trust-logos {
    display: flex; gap: 50px; align-items: center;
    margin-top: 60px; padding-top: 50px;
    border-top: 1px solid rgba(255,255,255,0.1);
    opacity: 0.45;
  }
  .trust-logos span {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.1rem; letter-spacing: 0.1em; text-transform: uppercase;
  }
  .featured-label { font-size: 0.68rem; letter-spacing: 0.2em; text-transform: uppercase; opacity: 0.5; margin-right: 10px; }

  /* ─── GUARANTEE ───────────────────────────── */
  .guarantee-section { background: var(--cream); }
  .guarantee-inner {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 80px; align-items: center;
  }
  .guarantee-badge {
    width: 200px; height: 200px; border-radius: 50%;
    background: var(--sage-dark); color: #fff;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    text-align: center; margin: 0 auto;
    position: relative;
  }
  .guarantee-badge::before {
    content: ''; position: absolute; inset: -8px;
    border-radius: 50%; border: 2px dashed var(--sage);
    animation: spin 20s linear infinite;
  }
  @keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
  .guarantee-badge .big-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3.5rem; font-weight: 600; line-height: 1; color: var(--gold);
  }
  .guarantee-badge p { font-size: 0.72rem; letter-spacing: 0.15em; text-transform: uppercase; opacity: 0.85; margin-top: 4px; }
  .guarantee-text h2 { margin-bottom: 20px; }
  .guarantee-text p { font-size: 0.95rem; line-height: 1.75; color: var(--stone); margin-bottom: 20px; }
  .guarantee-points { list-style: none; display: flex; flex-direction: column; gap: 12px; margin-bottom: 36px; }
  .guarantee-points li {
    display: flex; align-items: center; gap: 12px;
    font-size: 0.9rem; color: var(--charcoal);
  }
  .guarantee-points li::before {
    content: '✓'; width: 22px; height: 22px;
    background: var(--sage-light); border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 0.75rem; color: var(--sage-dark); font-weight: 700;
    flex-shrink: 0;
  }

  /* ─── CTA SECTION ─────────────────────────── */
  .cta-section {
    background: var(--charcoal); color: #fff;
    text-align: center; padding: 120px 80px;
    position: relative; overflow: hidden;
  }
  .cta-section::before {
    content: ''; position: absolute; top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(122,158,126,0.15) 0%, transparent 70%);
    border-radius: 50%;
  }
  .cta-section h2 { color: #fff; margin-bottom: 16px; font-size: clamp(2.4rem, 4vw, 4rem); }
  .cta-section h2 em { color: var(--gold); }
  .cta-section p {
    font-size: 1rem; color: rgba(255,255,255,0.55); max-width: 480px;
    margin: 0 auto 44px; line-height: 1.7; font-weight: 300;
  }
  .cta-actions { display: flex; gap: 16px; justify-content: center; align-items: center; }
  .btn-gold {
    background: var(--gold); color: var(--charcoal);
    padding: 18px 44px; border-radius: 2px;
    font-size: 0.85rem; letter-spacing: 0.12em; text-transform: uppercase;
    text-decoration: none; font-weight: 500;
    transition: all 0.25s;
  }
  .btn-gold:hover { background: var(--gold-light); transform: translateY(-2px); box-shadow: 0 10px 30px rgba(200,169,110,0.3); }
  .btn-outline-white {
    border: 1px solid rgba(255,255,255,0.25); color: rgba(255,255,255,0.75);
    padding: 17px 36px; border-radius: 2px;
    font-size: 0.82rem; letter-spacing: 0.1em; text-transform: uppercase;
    text-decoration: none; font-weight: 500;
    transition: all 0.25s;
  }
  .btn-outline-white:hover { border-color: rgba(255,255,255,0.6); color: #fff; }
  .cta-urgency {
    margin-top: 32px; font-size: 0.78rem; color: rgba(255,255,255,0.35);
    letter-spacing: 0.08em;
  }
  .cta-urgency strong { color: var(--terracotta); font-weight: 500; }

  /* ─── FOOTER ──────────────────────────────── */
  footer {
    background: #111; color: rgba(255,255,255,0.4);
    padding: 60px 80px 40px;
  }
  .footer-top {
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr;
    gap: 60px; margin-bottom: 50px;
  }
  .footer-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.6rem; color: #fff; margin-bottom: 16px; display: block;
    text-decoration: none;
  }
  .footer-logo span { color: var(--gold); }
  .footer-tagline { font-size: 0.85rem; line-height: 1.6; margin-bottom: 24px; }
  .footer-col h5 {
    font-size: 0.72rem; letter-spacing: 0.18em; text-transform: uppercase;
    color: rgba(255,255,255,0.5); margin-bottom: 20px; font-weight: 500;
  }
  .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
  .footer-col a {
    font-size: 0.85rem; color: rgba(255,255,255,0.4); text-decoration: none;
    transition: color 0.2s;
  }
  .footer-col a:hover { color: rgba(255,255,255,0.8); }
  .footer-bottom {
    border-top: 1px solid rgba(255,255,255,0.06);
    padding-top: 30px; display: flex; justify-content: space-between; align-items: center;
  }
  .footer-bottom p { font-size: 0.78rem; }

  /* ─── ANIMATIONS ──────────────────────────── */
  .fade-up {
    opacity: 0; transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .fade-up.visible { opacity: 1; transform: translateY(0); }
  .fade-up-delay-1 { transition-delay: 0.1s; }
  .fade-up-delay-2 { transition-delay: 0.2s; }
  .fade-up-delay-3 { transition-delay: 0.3s; }

  /* ─── STICKY BANNER ───────────────────────── */
  .sticky-offer {
    position: fixed; bottom: 0; left: 0; right: 0; z-index: 99;
    background: var(--gold); color: var(--charcoal);
    padding: 14px 40px;
    display: flex; align-items: center; justify-content: center; gap: 20px;
    font-size: 0.82rem; font-weight: 500; letter-spacing: 0.05em;
    transform: translateY(100%);
    transition: transform 0.4s ease;
  }
  .sticky-offer.show { transform: translateY(0); }
  .sticky-offer a {
    background: var(--charcoal); color: #fff;
    padding: 8px 20px; border-radius: 2px; text-decoration: none;
    font-size: 0.75rem; letter-spacing: 0.12em; text-transform: uppercase;
    transition: background 0.2s;
  }
  .sticky-offer a:hover { background: var(--sage-dark); }
  .sticky-close {
    position: absolute; right: 20px; top: 50%; transform: translateY(-50%);
    cursor: pointer; font-size: 1.2rem; opacity: 0.5; background: none; border: none;
  }

  /* ─── RESPONSIVE ──────────────────────────── */
  @media (max-width: 900px) {
    nav { padding: 20px 24px; }
    .nav-links { display: none; }
    section { padding: 70px 24px; }
    .hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-left { padding: 100px 24px 50px; }
    .hero-right { min-height: 360px; }
    .hero-stats { position: relative; bottom: auto; left: auto; padding: 24px; }
    .problem-grid, .guarantee-inner, .solution-steps, .products-grid, .testimonials-grid, .trust-grid { grid-template-columns: 1fr; }
    .footer-top { grid-template-columns: 1fr 1fr; }
    .problem-bar { flex-direction: column; text-align: center; }
    .cta-actions { flex-direction: column; }
    .trust-logos { flex-wrap: wrap; gap: 24px; }
    .products-header { flex-direction: column; gap: 20px; align-items: flex-start; }
  }
</style>
</head>
<body>

<!-- ─── STICKY OFFER BANNER ─────────────────────────────────── -->
<div class="sticky-offer" id="stickyOffer">
  🌿 Limited time: <strong>Free Wellness Assessment</strong> with first order
  <a href="#shop">Claim Offer →</a>
  <button class="sticky-close" onclick="document.getElementById('stickyOffer').classList.remove('show')">✕</button>
</div>

<!-- ─── NAVIGATION ──────────────────────────────────────────── -->
<nav>
  <a href="#" class="nav-logo">Healthy<span>Sense</span></a>
  <ul class="nav-links">
    <li><a href="#how-it-works">How It Works</a></li>
    <li><a href="#shop">Products</a></li>
    <li><a href="#proof">Results</a></li>
    <li><a href="#about">About</a></li>
  </ul>
  <a href="#shop" class="nav-cta">Start Today</a>
</nav>

<!-- ─── SECTION 1: HERO ─────────────────────────────────────── -->
<!-- PURPOSE: Capture attention in 3 seconds. Answer "Is this for me?" instantly. -->
<section class="hero" id="home">
  <div class="hero-left">
    <div class="hero-eyebrow fade-up">Science-backed wellness</div>
    <h1 class="fade-up fade-up-delay-1">
      Feel your<br><em>absolute best</em><br>every single day.
    </h1>
    <p class="hero-sub fade-up fade-up-delay-2">
      Healthy Sense translates complex nutrition science into simple, effective daily rituals. No guesswork. No overwhelm. Just results you can feel.
    </p>
    <div class="hero-actions fade-up fade-up-delay-3">
      <a href="#shop" class="btn-primary">Shop Now →</a>
      <a href="#how-it-works" class="btn-ghost">See how it works</a>
    </div>
    <div class="hero-trust fade-up">
      <div class="trust-stars">
        <span>★</span><span>★</span><span>★</span><span>★</span><span>★</span>
      </div>
      <p class="trust-text"><strong>4.9/5</strong> from over 12,000 verified reviews</p>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-blob"></div>
    <div class="hero-visual">
      <div class="hero-card fade-up fade-up-delay-2">
        <div class="hero-badge">Best Seller</div>
        <div class="hero-card-icon">🌿</div>
        <h3>Daily Wellness Bundle</h3>
        <p>Your complete foundation for energy, clarity, and resilience — in one elegant ritual.</p>
      </div>
      <div class="hero-stats">
        <div class="stat">
          <div class="stat-num">93%</div>
          <div class="stat-label">feel results in 2 weeks</div>
        </div>
        <div class="stat">
          <div class="stat-num">12k+</div>
          <div class="stat-label">happy customers</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ─── SOCIAL PROOF BAR ─────────────────────────────────────── -->
<!-- PURPOSE: Instant credibility after the hero. Kill doubt before it forms. -->
<div class="problem-bar">
  <p>"Finally, a wellness brand that <strong>actually explains why</strong> each ingredient works." — Sarah M.</p>
  <p>"I've tried everything. <strong>Healthy Sense is the first thing that stuck.</strong>" — James T.</p>
  <p>"My doctor was <strong>impressed by my bloodwork</strong> after 60 days." — Rachel L.</p>
</div>

<!-- ─── SECTION 2: PROBLEM ──────────────────────────────────── -->
<!-- PURPOSE: Mirror the customer's pain so deeply they feel understood. Creates emotional bond. -->
<section class="problem-section" id="problem">
  <div class="section-label fade-up">The problem</div>
  <h2 class="fade-up fade-up-delay-1">The wellness world<br><em>is overwhelming</em> you.</h2>

  <div class="problem-grid">
    <div class="problem-list">
      <div class="problem-item fade-up">
        <div class="problem-icon">😵</div>
        <div>
          <h4>Too much conflicting advice</h4>
          <p>One expert says eat this. Another says avoid it. You spend hours researching and end up more confused than when you started.</p>
        </div>
      </div>
      <div class="problem-item fade-up fade-up-delay-1">
        <div class="problem-icon">💸</div>
        <div>
          <h4>Wasting money on products that don't work</h4>
          <p>The supplements sit in your cabinet half-used. You felt nothing, or stopped before seeing any real change.</p>
        </div>
      </div>
      <div class="problem-item fade-up fade-up-delay-2">
        <div class="problem-icon">😔</div>
        <div>
          <h4>Feeling like your energy is gone</h4>
          <p>By 2pm, you're running on caffeine. Sleep isn't restoring you. You know something is off but don't know where to start.</p>
        </div>
      </div>
    </div>
    <div class="problem-visual fade-up fade-up-delay-1">
      <blockquote>"I used to take 11 different supplements based on random YouTube videos. I still felt terrible. I needed someone to just tell me what I actually needed."</blockquote>
      <cite>— Emma K., now a Healthy Sense member for 14 months</cite>
    </div>
  </div>
</section>

<!-- ─── SECTION 3: HOW IT WORKS ─────────────────────────────── -->
<!-- PURPOSE: Reduce friction. Make the purchase process feel easy and logical. -->
<section class="solution-section" id="how-it-works">
  <div class="section-label fade-up">How it works</div>
  <h2 class="fade-up fade-up-delay-1">Three steps to feeling<br><em>genuinely well.</em></h2>

  <div class="solution-steps">
    <div class="step fade-up">
      <div class="step-num">01</div>
      <div class="step-icon">🧬</div>
      <h3>Assess Your Needs</h3>
      <p class="step-desc">Take our 3-minute wellness questionnaire built with licensed nutritionists. We identify your specific gaps and goals — not generic ones.</p>
      <a href="#" class="step-cta-link">Take the quiz →</a>
    </div>
    <div class="step fade-up fade-up-delay-1">
      <div class="step-num">02</div>
      <div class="step-icon">📦</div>
      <h3>Get Your Protocol</h3>
      <p class="step-desc">Receive your personalized bundle with clear instructions. Every ingredient is explained. Every dose is calibrated. No guesswork.</p>
      <a href="#" class="step-cta-link">See products →</a>
    </div>
    <div class="step fade-up fade-up-delay-2">
      <div class="step-num">03</div>
      <div class="step-icon">✨</div>
      <h3>Track Your Progress</h3>
      <p class="step-desc">Log how you feel with our app check-ins. Our team adjusts your protocol based on your feedback. Wellness that evolves with you.</p>
      <a href="#" class="step-cta-link">Learn more →</a>
    </div>
  </div>
</section>

<!-- ─── SECTION 4: PRODUCTS / OFFER ─────────────────────────── -->
<!-- PURPOSE: Present the offer. Make price feel like a no-brainer. -->
<section class="products-section" id="shop">
  <div class="products-header">
    <div>
      <div class="section-label fade-up">Our products</div>
      <h2 class="fade-up fade-up-delay-1">Formulated to work.<br><em>Designed to last.</em></h2>
    </div>
    <a href="#" class="btn-ghost fade-up">View all products</a>
  </div>

  <div class="products-grid">
    <div class="product-card fade-up">
      <div class="product-img product-img-bg-1">
        🌿
        <span class="product-tag">Most Popular</span>
      </div>
      <div class="product-body">
        <h3>Daily Foundations</h3>
        <p>Our flagship multi-system supplement. Energy, immunity, gut health, and mental clarity — all in one morning ritual.</p>
        <div class="product-footer">
          <div class="price">$49 <span>/month</span></div>
          <button class="add-btn">Add to Cart</button>
        </div>
      </div>
    </div>
    <div class="product-card fade-up fade-up-delay-1">
      <div class="product-img product-img-bg-2">
        🧠
        <span class="product-tag">New</span>
      </div>
      <div class="product-body">
        <h3>Focus & Flow</h3>
        <p>Nootropic blend clinically studied to enhance mental clarity, reduce brain fog, and sustain deep work sessions.</p>
        <div class="product-footer">
          <div class="price">$59 <span>/month</span></div>
          <button class="add-btn">Add to Cart</button>
        </div>
      </div>
    </div>
    <div class="product-card fade-up fade-up-delay-2">
      <div class="product-img product-img-bg-3">
        😴
        <span class="product-tag">Best Value</span>
      </div>
      <div class="product-body">
        <h3>Deep Rest Bundle</h3>
        <p>Science-backed sleep stack with magnesium glycinate, l-theanine, and adaptogens. Wake up actually restored.</p>
        <div class="product-footer">
          <div class="price">$79 <span>/month</span></div>
          <button class="add-btn">Add to Cart</button>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ─── SECTION 5: SOCIAL PROOF / TESTIMONIALS ──────────────── -->
<!-- PURPOSE: Let customers sell for you. Real voices remove final doubt. -->
<section class="proof-section" id="proof">
  <div class="proof-intro">
    <div>
      <div class="section-label fade-up">Real results</div>
      <h2 class="fade-up fade-up-delay-1">12,000+ people who made the switch.</h2>
    </div>
    <p class="fade-up fade-up-delay-1" style="font-size:1rem; color:var(--stone); line-height:1.7; align-self: end;">
      We don't cherry-pick our reviews. Every testimonial below is verified by a third-party platform. This is what happens when the science is right and the product actually delivers.
    </p>
  </div>

  <div class="testimonials-grid">
    <div class="testimonial fade-up">
      <div class="review-stars"><span>★</span><span>★</span><span>★</span><span>★</span><span>★</span></div>
      <div class="testimonial-quote">"</div>
      <p>I've been on Healthy Sense for four months. My chronic afternoon fatigue is gone. My partner noticed the change before I did — I'm just happier and sharper.</p>
      <div class="testimonial-author">
        <div class="author-avatar">👩</div>
        <div>
          <div class="author-name">Priya N.</div>
          <div class="author-detail">Verified buyer · Teacher, 34</div>
        </div>
      </div>
    </div>
    <div class="testimonial fade-up fade-up-delay-1">
      <div class="review-stars"><span>★</span><span>★</span><span>★</span><span>★</span><span>★</span></div>
      <div class="testimonial-quote">"</div>
      <p>What sold me was the transparency. They show you exactly what's in each formula and why. I felt the difference within 10 days. My sleep is now genuinely deep for the first time in years.</p>
      <div class="testimonial-author">
        <div class="author-avatar">👨</div>
        <div>
          <div class="author-name">Marcus D.</div>
          <div class="author-detail">Verified buyer · Engineer, 41</div>
        </div>
      </div>
    </div>
    <div class="testimonial fade-up fade-up-delay-2">
      <div class="review-stars"><span>★</span><span>★</span><span>★</span><span>★</span><span>★</span></div>
      <div class="testimonial-quote">"</div>
      <p>As a nurse, I'm extremely skeptical of supplements. But the clinical research behind Healthy Sense is legitimate. I now recommend it to patients who ask about daily wellness routines.</p>
      <div class="testimonial-author">
        <div class="author-avatar">👩‍⚕️</div>
        <div>
          <div class="author-name">Claire B., RN</div>
          <div class="author-detail">Verified buyer · Healthcare, 38</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ─── SECTION 6: CREDENTIALS / TRUST ──────────────────────── -->
<!-- PURPOSE: Establish scientific authority and eliminate "is this legit?" concerns. -->
<section class="trust-section" id="about">
  <div class="section-label" style="color:var(--sage-light);">Why trust us</div>
  <h2 style="color:#fff;" class="fade-up">Built on science.<br><em style="color:var(--gold);">Held to a higher standard.</em></h2>

  <div class="trust-grid">
    <div class="trust-item fade-up">
      <div class="trust-icon">🔬</div>
      <h4>Clinically Studied</h4>
      <p>Every formula references peer-reviewed clinical research. We cite our sources. Always.</p>
    </div>
    <div class="trust-item fade-up fade-up-delay-1">
      <div class="trust-icon">🧪</div>
      <h4>Third-Party Tested</h4>
      <p>Each batch is independently tested for purity, potency, and contaminants before shipping.</p>
    </div>
    <div class="trust-item fade-up fade-up-delay-2">
      <div class="trust-icon">👩‍⚕️</div>
      <h4>Expert Formulated</h4>
      <p>Our advisory board includes MDs, RDs, and PhDs in nutrition and functional medicine.</p>
    </div>
    <div class="trust-item fade-up fade-up-delay-3">
      <div class="trust-icon">🏭</div>
      <h4>GMP Certified</h4>
      <p>Manufactured in FDA-registered, GMP-certified facilities. No shortcuts, ever.</p>
    </div>
  </div>

  <div class="trust-logos">
    <span class="featured-label">As seen in</span>
    <span>Well+Good</span>
    <span>MindBodyGreen</span>
    <span>Forbes Health</span>
    <span>Healthline</span>
    <span>The Zoe Report</span>
  </div>
</section>

<!-- ─── SECTION 7: GUARANTEE ─────────────────────────────────── -->
<!-- PURPOSE: Remove ALL remaining purchase risk. The final objection killer. -->
<section class="guarantee-section" id="guarantee">
  <div class="guarantee-inner">
    <div class="fade-up">
      <div class="guarantee-badge">
        <div class="big-num">60</div>
        <p>Day Money<br>Back Guarantee</p>
      </div>
    </div>
    <div class="guarantee-text fade-up fade-up-delay-1">
      <div class="section-label">Zero risk</div>
      <h2>Try it for 60 days.<br><em>Love it or we refund you.</em></h2>
      <p>We know healthy changes take time. That's why we give you a full 60 days to feel the difference. If you don't notice a meaningful improvement in how you feel, we'll refund every dollar — no questions, no hoops.</p>
      <ul class="guarantee-points">
        <li>No return required on used product</li>
        <li>No time-wasting customer service runaround</li>
        <li>Full refund, including your first order</li>
        <li>Refund processed within 3 business days</li>
      </ul>
      <a href="#shop" class="btn-primary">Start Risk-Free →</a>
    </div>
  </div>
</section>

<!-- ─── SECTION 8: FINAL CTA ─────────────────────────────────── -->
<!-- PURPOSE: One last, clear, urgent call to action. Make it NOW. -->
<section class="cta-section">
  <h2 class="fade-up">Your best self<br>isn't a <em>maybe.</em></h2>
  <p class="fade-up fade-up-delay-1">Join 12,000+ people who stopped guessing and started feeling the difference. Your protocol takes 3 minutes to build.</p>
  <div class="cta-actions fade-up fade-up-delay-2">
    <a href="#" class="btn-gold">Take the Free Quiz →</a>
    <a href="#shop" class="btn-outline-white">Shop All Products</a>
  </div>
  <p class="cta-urgency fade-up fade-up-delay-3">
    <strong>⏳ Free shipping ends Sunday.</strong> &nbsp;|&nbsp; 60-day guarantee &nbsp;|&nbsp; Cancel anytime
  </p>
</section>

<!-- ─── FOOTER ───────────────────────────────────────────────── -->
<footer>
  <div class="footer-top">
    <div>
      <a href="#" class="footer-logo">Healthy<span>Sense</span></a>
      <p class="footer-tagline">Science-backed wellness products designed to help you feel genuinely well — not just temporarily better.</p>
      <p style="font-size:0.75rem; letter-spacing:0.05em;">hello@healthysense.com</p>
    </div>
    <div class="footer-col">
      <h5>Products</h5>
      <ul>
        <li><a href="#">Daily Foundations</a></li>
        <li><a href="#">Focus & Flow</a></li>
        <li><a href="#">Deep Rest Bundle</a></li>
        <li><a href="#">All Products</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h5>Company</h5>
      <ul>
        <li><a href="#">Our Story</a></li>
        <li><a href="#">Science</a></li>
        <li><a href="#">Advisors</a></li>
        <li><a href="#">Press</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h5>Support</h5>
      <ul>
        <li><a href="#">FAQ</a></li>
        <li><a href="#">Shipping</a></li>
        <li><a href="#">Returns</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2026 Healthy Sense. All rights reserved.</p>
    <p>Privacy Policy · Terms · Accessibility</p>
  </div>
</footer>

<script>
  // Intersection Observer for fade-up animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  // Sticky offer banner (shows after scroll)
  const banner = document.getElementById('stickyOffer');
  let bannerShown = false;
  window.addEventListener('scroll', () => {
    if (window.scrollY > 600 && !bannerShown) {
      banner.classList.add('show');
      bannerShown = true;
    }
  });

  // Nav shadow on scroll
  const nav = document.querySelector('nav');
  window.addEventListener('scroll', () => {
    nav.style.boxShadow = window.scrollY > 40
      ? '0 2px 20px rgba(28,28,26,0.08)'
      : 'none';
  });

  // Product card add-to-cart micro-interaction
  document.querySelectorAll('.add-btn').forEach(btn => {
    btn.addEventListener('click', function() {
      const orig = this.textContent;
      this.textContent = '✓ Added!';
      this.style.background = 'var(--sage)';
      setTimeout(() => {
        this.textContent = orig;
        this.style.background = '';
      }, 1800);
    });
  });
</script>
</body>
</html>
