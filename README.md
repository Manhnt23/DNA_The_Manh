<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DNA Thương Hiệu Cá Nhân — Ánh Sáng Lặng</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:wght@300;400;500;600;700&family=Lora:ital,wght@0,400;0,500;1,400;1,500&family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400&display=swap" rel="stylesheet">

<style>
  :root {
    --navy: #1A1A2E;
    --parchment: #E8E0D0;
    --gold: #C8A96E;
    --navy-light: #252545;
    --gold-muted: #a88a52;
    --text-on-navy: #E8E0D0;
    --text-muted: #9a9070;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background-color: var(--navy);
    color: var(--parchment);
    font-family: 'Lora', Georgia, serif;
    line-height: 1.75;
    min-height: 100vh;
    position: relative;
    overflow-x: hidden;
  }

  /* Grain texture overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.06'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.4;
  }

  /* ─── NAVIGATION ─── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 1.2rem 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(26, 26, 46, 0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(200, 169, 110, 0.15);
  }

  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-style: italic;
    font-size: 1.1rem;
    color: var(--gold);
    letter-spacing: 0.05em;
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  .nav-links a {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.72rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--parchment);
    text-decoration: none;
    opacity: 0.6;
    transition: opacity 0.3s, color 0.3s;
  }

  .nav-links a:hover { opacity: 1; color: var(--gold); }

  /* ─── HERO ─── */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 8rem 2rem 4rem;
    position: relative;
  }

  .hero::after {
    content: '';
    position: absolute;
    width: 500px; height: 500px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(200,169,110,0.06) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-eyebrow {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 2rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.2s forwards;
  }

  .hero-title {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: clamp(3rem, 8vw, 7rem);
    font-weight: 700;
    line-height: 1.05;
    letter-spacing: -0.02em;
    color: var(--parchment);
    margin-bottom: 0.5rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.4s forwards;
  }

  .hero-title span { color: var(--gold); }

  .hero-subtitle {
    font-family: 'Cormorant Garamond', serif;
    font-style: italic;
    font-size: clamp(1.2rem, 3vw, 1.7rem);
    color: var(--text-muted);
    margin-bottom: 3rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.6s forwards;
  }

  .hero-tagline {
    max-width: 640px;
    font-family: 'Lora', serif;
    font-size: 1.05rem;
    color: var(--parchment);
    opacity: 0;
    animation: fadeUp 0.8s 0.8s forwards;
    line-height: 1.9;
  }

  /* Incomplete circle deco */
  .circle-mark {
    position: relative;
    display: inline-block;
    margin-top: 3rem;
    opacity: 0;
    animation: fadeUp 0.8s 1s forwards;
  }

  .circle-mark svg {
    width: 60px; height: 60px;
    animation: rotateSlow 20s linear infinite;
  }

  @keyframes rotateSlow {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  /* ─── SECTION BASE ─── */
  section {
    max-width: 1100px;
    margin: 0 auto;
    padding: 6rem 2rem;
  }

  .section-label {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.68rem;
    font-weight: 600;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: rgba(200,169,110,0.2);
  }

  .section-title {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: clamp(1.8rem, 4vw, 2.8rem);
    font-weight: 700;
    letter-spacing: -0.02em;
    color: var(--parchment);
    margin-bottom: 3rem;
    line-height: 1.2;
  }

  /* ─── DIVIDER ─── */
  .divider {
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(200,169,110,0.3), transparent);
    margin: 0 auto;
  }

  /* ─── LỚP 1: CÂU CHUYỆN ─── */
  .stories-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }

  .story-card {
    background: rgba(232, 224, 208, 0.04);
    border: 1px solid rgba(200, 169, 110, 0.15);
    border-radius: 2px;
    padding: 2.5rem 2rem;
    position: relative;
    transition: border-color 0.4s, background 0.4s;
  }

  .story-card:hover {
    border-color: rgba(200, 169, 110, 0.4);
    background: rgba(232, 224, 208, 0.07);
  }

  .story-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3.5rem;
    font-weight: 300;
    color: var(--gold);
    opacity: 0.25;
    position: absolute;
    top: 1.5rem;
    right: 1.5rem;
    line-height: 1;
  }

  .story-type {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.65rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }

  .story-card h3 {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 1rem;
    font-weight: 600;
    color: var(--parchment);
    margin-bottom: 1rem;
    line-height: 1.4;
  }

  .story-card p {
    font-size: 0.9rem;
    color: var(--text-muted);
    line-height: 1.8;
  }

  /* ─── INSIGHT CARDS ─── */
  .insight-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
    margin-top: 3rem;
  }

  .insight-full { grid-column: 1 / -1; }

  .insight-card {
    background: rgba(232, 224, 208, 0.04);
    border-left: 2px solid var(--gold);
    padding: 2rem 2rem 2rem 2.5rem;
    position: relative;
  }

  .insight-card .tag {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.62rem;
    font-weight: 700;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.8rem;
  }

  .insight-card h4 {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 1rem;
    font-weight: 600;
    color: var(--parchment);
    margin-bottom: 0.8rem;
  }

  .insight-card p {
    font-size: 0.88rem;
    color: var(--text-muted);
    line-height: 1.8;
  }

  .belief-block {
    background: rgba(200, 169, 110, 0.07);
    border: 1px solid rgba(200,169,110,0.3);
    padding: 2.5rem 3rem;
    text-align: center;
    margin-top: 3rem;
  }

  .belief-block blockquote {
    font-family: 'Cormorant Garamond', serif;
    font-style: italic;
    font-size: clamp(1.3rem, 3vw, 1.8rem);
    color: var(--parchment);
    line-height: 1.6;
  }

  .belief-block cite {
    display: block;
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.68rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    margin-top: 1.2rem;
    font-style: normal;
  }

  /* ─── DNA ARCHITECTURE ─── */
  .dna-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: rgba(200,169,110,0.1);
    border: 1px solid rgba(200,169,110,0.1);
  }

  .dna-cell {
    background: var(--navy);
    padding: 2.5rem 2rem;
    transition: background 0.3s;
  }

  .dna-cell:hover { background: rgba(232,224,208,0.04); }

  .dna-cell .label {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.62rem;
    font-weight: 700;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.8rem;
  }

  .dna-cell h4 {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 1.05rem;
    font-weight: 600;
    color: var(--parchment);
    margin-bottom: 0.6rem;
  }

  .dna-cell p {
    font-size: 0.85rem;
    color: var(--text-muted);
    line-height: 1.7;
  }

  .dna-cell.span2 { grid-column: span 2; }
  .dna-cell.span3 { grid-column: span 3; }

  /* Golden Why circle */
  .why-circle-wrap {
    display: flex;
    justify-content: center;
    margin: 4rem 0;
  }

  .why-circle {
    position: relative;
    width: 380px;
    height: 380px;
  }

  .why-circle .ring {
    position: absolute;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    text-align: center;
  }

  .ring-outer {
    inset: 0;
    background: rgba(200,169,110,0.06);
    border: 1px solid rgba(200,169,110,0.2);
  }

  .ring-mid {
    inset: 14%;
    background: rgba(200,169,110,0.08);
    border: 1px solid rgba(200,169,110,0.3);
  }

  .ring-inner {
    inset: 28%;
    background: rgba(200,169,110,0.15);
    border: 1px solid rgba(200,169,110,0.5);
  }

  .ring-label {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.3rem;
  }

  .ring-text {
    font-family: 'Lora', serif;
    font-size: 0.78rem;
    color: var(--parchment);
    padding: 0 1rem;
    line-height: 1.5;
  }

  .ring-inner .ring-text { font-size: 0.7rem; }

  /* Outer labels */
  .ring-outer-label {
    position: absolute;
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.6rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--text-muted);
  }

  /* ─── BLIND SPOT / CONTRAST ─── */
  .contrast-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 2rem;
  }

  .contrast-table th {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    padding: 1rem 1.5rem;
    text-align: left;
    border-bottom: 1px solid rgba(200,169,110,0.2);
  }

  .contrast-table td {
    font-size: 0.88rem;
    padding: 1.2rem 1.5rem;
    border-bottom: 1px solid rgba(255,255,255,0.04);
    color: var(--parchment);
    line-height: 1.6;
    vertical-align: top;
  }

  .contrast-table td:first-child { color: var(--text-muted); }
  .contrast-table tr:hover td { background: rgba(232,224,208,0.03); }

  .match-badge {
    display: inline-block;
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.58rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 0.2em 0.6em;
    border-radius: 2px;
    margin-left: 0.5rem;
  }

  .match { background: rgba(200,169,110,0.2); color: var(--gold); }
  .gap { background: rgba(232,224,208,0.07); color: var(--text-muted); }

  /* ─── COLOR PALETTE ─── */
  .palette-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
    margin-bottom: 3rem;
  }

  .color-card {
    border: 1px solid rgba(200,169,110,0.15);
    overflow: hidden;
    transition: transform 0.3s;
  }

  .color-card:hover { transform: translateY(-4px); }

  .color-swatch {
    height: 160px;
    position: relative;
    display: flex;
    align-items: flex-end;
    padding: 1rem;
  }

  .color-hex {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.1em;
    opacity: 0.7;
  }

  .color-info {
    padding: 1.5rem;
    background: rgba(232,224,208,0.04);
  }

  .color-role {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.4rem;
  }

  .color-name {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 1rem;
    font-weight: 600;
    color: var(--parchment);
    margin-bottom: 0.5rem;
  }

  .color-desc {
    font-size: 0.82rem;
    color: var(--text-muted);
    line-height: 1.7;
  }

  /* ─── FONT SHOWCASE ─── */
  .font-showcase {
    display: grid;
    gap: 1px;
    background: rgba(200,169,110,0.1);
    border: 1px solid rgba(200,169,110,0.1);
  }

  .font-row {
    background: var(--navy);
    padding: 2.5rem 2.5rem;
    display: grid;
    grid-template-columns: 200px 1fr;
    gap: 2rem;
    align-items: center;
    transition: background 0.3s;
  }

  .font-row:hover { background: rgba(232,224,208,0.04); }

  .font-meta .role {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.62rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.4rem;
  }

  .font-meta .name {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--parchment);
    margin-bottom: 0.3rem;
  }

  .font-meta .classification {
    font-size: 0.75rem;
    color: var(--text-muted);
  }

  .font-sample { line-height: 1.3; }

  /* ─── MARK ─── */
  .mark-demo {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 5rem;
    padding: 4rem;
    background: rgba(232,224,208,0.03);
    border: 1px solid rgba(200,169,110,0.1);
    flex-wrap: wrap;
  }

  .mark-item {
    text-align: center;
  }

  .mark-item .mark-label {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.62rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-top: 1.2rem;
  }

  /* ─── IMAGE STYLE ─── */
  .style-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }

  .style-block {
    padding: 2rem;
    background: rgba(232,224,208,0.03);
    border: 1px solid rgba(200,169,110,0.1);
  }

  .style-block h4 {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }

  .style-block p {
    font-size: 0.88rem;
    color: var(--parchment);
    line-height: 1.8;
  }

  /* ─── FORBIDDEN ─── */
  .forbidden-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }

  .forbidden-card {
    border: 1px solid rgba(255,100,80,0.15);
    padding: 2rem;
    position: relative;
    overflow: hidden;
  }

  .forbidden-card::before {
    content: '✕';
    position: absolute;
    top: 1rem; right: 1rem;
    color: rgba(255,100,80,0.3);
    font-size: 1.2rem;
    font-family: 'Be Vietnam Pro', sans-serif;
  }

  .forbidden-card h4 {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: rgba(255,100,80,0.7);
    margin-bottom: 1rem;
  }

  .forbidden-card ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
  }

  .forbidden-card li {
    font-size: 0.85rem;
    color: var(--text-muted);
    line-height: 1.5;
    padding-left: 1rem;
    position: relative;
  }

  .forbidden-card li::before {
    content: '—';
    position: absolute;
    left: 0;
    color: rgba(255,100,80,0.4);
  }

  /* ─── MANIFESTO ─── */
  .manifesto-wrap {
    max-width: 780px;
    margin: 0 auto;
    text-align: center;
    padding: 4rem 2rem;
  }

  .manifesto-wrap p {
    font-family: 'Lora', serif;
    font-size: clamp(1rem, 2.2vw, 1.2rem);
    line-height: 2;
    color: var(--parchment);
    margin-bottom: 1.5rem;
    opacity: 0.9;
  }

  .manifesto-wrap p strong {
    color: var(--gold);
    font-weight: 500;
  }

  /* ─── PITCH ─── */
  .pitch-cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }

  .pitch-card {
    padding: 2.5rem 2rem;
    background: rgba(232,224,208,0.03);
    border: 1px solid rgba(200,169,110,0.12);
    position: relative;
  }

  .pitch-card .pitch-label {
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.62rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.2rem;
  }

  .pitch-card p {
    font-size: 0.9rem;
    color: var(--parchment);
    line-height: 1.85;
  }

  /* ─── PROMPT ─── */
  .prompt-block {
    background: rgba(26,26,46,0.8);
    border: 1px solid rgba(200,169,110,0.25);
    padding: 2.5rem 3rem;
    position: relative;
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.88rem;
    line-height: 1.85;
    color: var(--parchment);
    border-radius: 2px;
  }

  .prompt-block::before {
    content: 'AI PROMPT';
    position: absolute;
    top: -0.6rem;
    left: 2rem;
    background: var(--navy);
    padding: 0 0.8rem;
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.2em;
    color: var(--gold);
  }

  .copy-btn {
    display: block;
    margin-top: 1.5rem;
    padding: 0.7rem 2rem;
    background: transparent;
    border: 1px solid rgba(200,169,110,0.4);
    color: var(--gold);
    font-family: 'Be Vietnam Pro', sans-serif;
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    cursor: pointer;
    transition: background 0.3s, border-color 0.3s;
    width: fit-content;
  }

  .copy-btn:hover {
    background: rgba(200,169,110,0.1);
    border-color: var(--gold);
  }

  /* ─── FOOTER ─── */
  footer {
    border-top: 1px solid rgba(200,169,110,0.12);
    padding: 3rem;
    text-align: center;
  }

  footer p {
    font-family: 'Cormorant Garamond', serif;
    font-style: italic;
    font-size: 1rem;
    color: var(--text-muted);
  }

  footer .mark-footer {
    margin: 1.5rem auto 0;
    display: flex;
    justify-content: center;
  }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .fade-in {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }

  .fade-in.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .stories-grid, .palette-row, .forbidden-grid, .pitch-cards { grid-template-columns: 1fr; }
    .dna-grid { grid-template-columns: 1fr; }
    .dna-cell.span2, .dna-cell.span3 { grid-column: span 1; }
    .font-row { grid-template-columns: 1fr; }
    .style-grid { grid-template-columns: 1fr; }
    .insight-row { grid-template-columns: 1fr; }
    .contrast-table { font-size: 0.8rem; }
    .contrast-table th, .contrast-table td { padding: 0.8rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Ánh Sáng Lặng</div>
  <ul class="nav-links">
    <li><a href="#story">Câu Chuyện</a></li>
    <li><a href="#dna">DNA</a></li>
    <li><a href="#nhan-dien">Nhận Diện</a></li>
    <li><a href="#tuyen-ngon">Tuyên Ngôn</a></li>
    <li><a href="#pitch">Pitch</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="top">
  <p class="hero-eyebrow">Bản Kiến Trúc DNA Thương Hiệu Cá Nhân</p>
  <h1 class="hero-title">Ánh <span>Sáng</span><br>Lặng</h1>
  <p class="hero-subtitle">Nhà Hiền Triết · Người Chữa Lành</p>
  <p class="hero-tagline">Tôi giúp người đang mắc kẹt nhìn thấy đúng điều đang giữ họ lại — bằng tư duy hệ thống và chiều sâu nội tâm — vì tôi tin tự do bắt đầu từ sự nhìn thấy.</p>
  <div class="circle-mark">
    <svg viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M 30 5 A 25 25 0 1 1 10 44" stroke="#C8A96E" stroke-width="1.2" stroke-linecap="round"/>
    </svg>
  </div>
</section>

<div class="divider"></div>

<!-- LỚP 1: CÂU CHUYỆN -->
<section id="story">
  <p class="section-label fade-in">Lớp 1 — Câu Chuyện Gốc</p>
  <h2 class="section-title fade-in">Ba Khoảnh Khắc<br>Định Hình Tôi</h2>

  <div class="stories-grid fade-in">
    <div class="story-card">
      <span class="story-number">01</span>
      <p class="story-type">Lần Tự Hào Nhất</p>
      <h3>Hành Trình Xuyên Việt & Thiền Viện</h3>
      <p>Đảm nhiệm MC khóa thiền dài ngày, tu tập 7 ngày tại thiền viện, rồi một chuyến đi xuyên Việt trải nghiệm. Lần đầu tiên thoát ra khỏi vùng an toàn, cảm nhận sự tự do thật sự và làm những điều chưa từng nghĩ tới.</p>
    </div>
    <div class="story-card">
      <span class="story-number">02</span>
      <p class="story-type">Lần Giúp Người Vui Nhất</p>
      <h3>Khai Vấn Cặp Vợ Chồng</h3>
      <p>Phân tích giúp hai vợ chồng hiểu nhau hơn, tháo gỡ hiểu lầm, vượt qua định kiến và nhìn lại ưu điểm của nhau. Khi thấy ánh mắt họ lên niềm tin — hạnh phúc sưởi ấm trong lòng tôi.</p>
    </div>
    <div class="story-card">
      <span class="story-number">03</span>
      <p class="story-type">Lần Trăn Trở Nhất</p>
      <h3>Sự Mù Quáng Không Được Nhận Ra</h3>
      <p>Trăn trở khi tôi hoặc ai đó không nhận ra vấn đề tâm lý hoặc cách ứng xử đang gặp vấn đề trong cuộc sống. Đây không chỉ là tiếc nuối — đó là điều không thể chấp nhận.</p>
    </div>
  </div>

  <div class="insight-row fade-in">
    <div class="insight-card">
      <p class="tag">Mô Thức Lặp Lại</p>
      <h4>Vượt Ra Ngoài Để Chạm Vào Người Khác</h4>
      <p>Cả 3 chuyện đều có một sợi chỉ: rời vùng an toàn (1), đi vào bên trong mối quan hệ (2), trăn trở khi ai mắc kẹt mà không biết (3).</p>
    </div>
    <div class="insight-card">
      <p class="tag">Thế Mạnh Ẩn</p>
      <h4>Đọc Điều Bị Che Khuất — Đặt Ngôn Ngữ Lên Đó</h4>
      <p>Năng lực đọc những gì bị che khuất trong một người, một mối quan hệ, một tình huống — rồi đặt ngôn ngữ chính xác để người khác tự nhìn thấy.</p>
    </div>
    <div class="insight-card">
      <p class="tag">Vùng Cấm Nội Tâm</p>
      <h4>Sự Mù Quáng Không Được Nhìn Nhận</h4>
      <p>Khi một người đang tổn thương hoặc sai mà không ai — kể cả chính họ — nhìn thấy. Với tôi, đó là điều không thể chấp nhận.</p>
    </div>
    <div class="insight-card">
      <p class="tag">Mâu Thuẫn Nội Tâm</p>
      <h4>Tự Do Cá Nhân ↔ Gắn Kết Người Khác</h4>
      <p>Khao khát tự do cá nhân (chuyện 1) nhưng hạnh phúc sâu nhất đến từ gắn kết (chuyện 2). Hai điều không loại trừ nhau — nhưng đôi khi kéo hai hướng.</p>
    </div>
  </div>

  <div class="belief-block fade-in">
    <blockquote>"Con người xứng đáng được tự do — và hạnh phúc thật sự chỉ đến khi được chia sẻ với người khác."</blockquote>
    <cite>— Niềm Tin Gốc</cite>
  </div>
</section>

<div class="divider"></div>

<!-- LỚP 2: BLIND SPOT -->
<section>
  <p class="section-label fade-in">Lớp 2 — Phân Tích Nhận Thức</p>
  <h2 class="section-title fade-in">Khoảng Cách<br>Trong-Ngoài</h2>

  <div class="fade-in">
    <table class="contrast-table">
      <thead>
        <tr>
          <th>Tôi Thấy Mình Là...</th>
          <th>Người Khác Thấy Tôi Là...</th>
          <th>Trạng Thái</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Người khao khát tự do</td>
          <td>Người ôm đồm, khó buông</td>
          <td><span class="match-badge gap">Lệch</span></td>
        </tr>
        <tr>
          <td>Người sống để chia sẻ & kết nối</td>
          <td>Người hơi khép kín</td>
          <td><span class="match-badge gap">Lệch</span></td>
        </tr>
        <tr>
          <td>Người hướng đến cảm xúc & hạnh phúc</td>
          <td>Người logic, lý thuyết, đôi khi vô cảm</td>
          <td><span class="match-badge gap">Lệch</span></td>
        </tr>
        <tr>
          <td>Người có chiều sâu nội tâm</td>
          <td>Người có chiều sâu nội tâm và nhiều góc nhìn</td>
          <td><span class="match-badge match">Khớp</span></td>
        </tr>
        <tr>
          <td>—</td>
          <td>Khách quan, không vụ lợi <em>(góc mù — tôi không thấy)</em></td>
          <td><span class="match-badge gap">Vàng Bị Bỏ Quên</span></td>
        </tr>
      </tbody>
    </table>
  </div>

  <div class="insight-row fade-in" style="margin-top:2rem">
    <div class="insight-card insight-full">
      <p class="tag">Góc Mù (Blind Spot)</p>
      <h4>Khách Quan & Không Vụ Lợi — Vàng Bị Bỏ Quên</h4>
      <p>Khả năng nhìn thẳng vào điểm tốt của người khác và điểm xấu của chính mình cùng lúc. Năng lực hiếm, thường chỉ có ở người đã qua nhiều va chạm nội tâm thật sự. Bạn coi đó là lẽ thường — người ngoài thấy đó là điều nổi bật nhất.</p>
    </div>
    <div class="insight-card insight-full">
      <p class="tag">Cảnh Báo Tự Lừa</p>
      <h4>Khao Khát Kết Nối — Nhưng Thể Hiện Ra Ngoài Còn Lạnh</h4>
      <p>Bạn muốn kết nối sâu, nhưng cách bạn hiện diện chưa truyền được điều đó ra ngoài. Lõi thật là ấm áp và khách quan — nhưng lớp ngoài đủ lạnh để người khác chưa chạm được vào lõi đó ngay.</p>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- LỚP 3: DNA ARCHITECTURE -->
<section id="dna">
  <p class="section-label fade-in">Lớp 3 — Kiến Trúc DNA</p>
  <h2 class="section-title fade-in">Bản DNA<br>Thương Hiệu Cá Nhân</h2>

  <!-- Nguyên mẫu -->
  <div class="dna-grid fade-in" style="margin-bottom: 1.5rem">
    <div class="dna-cell">
      <p class="label">Nguyên Mẫu Chính (Jung)</p>
      <h4>Nhà Hiền Triết (Sage)</h4>
      <p>Đọc điều bị che khuất, đặt ngôn ngữ chính xác lên đó để người khác tự nhìn thấy. Không dạy — soi sáng.</p>
    </div>
    <div class="dna-cell">
      <p class="label">Nguyên Mẫu Phụ</p>
      <h4>Người Chữa Lành (Healer)</h4>
      <p>Hạnh phúc đến từ khoảnh khắc "ánh mắt người khác lên niềm tin." Kết nối sâu là nguồn năng lượng thật.</p>
    </div>
    <div class="dna-cell">
      <p class="label">Nguyên Mẫu Đối Lập</p>
      <h4>Người Biểu Diễn (Entertainer)</h4>
      <p>Tôi không tạo cảm xúc bề mặt. Tôi không ở đây để làm vui — tôi ở đây để làm người khác thấy.</p>
    </div>
  </div>

  <!-- Vòng tròn vàng -->
  <div class="why-circle-wrap fade-in">
    <div class="why-circle">
      <div class="ring ring-outer">
        <div class="ring-label">LÀM CÁI GÌ</div>
        <div class="ring-text">Khai vấn · Đào tạo nhận thức · Thiền ứng dụng</div>
      </div>
      <div class="ring ring-mid">
        <div class="ring-label">LÀM THẾ NÀO</div>
        <div class="ring-text">Đọc mô thức ẩn → Đặt ngôn ngữ → Để họ tự nhìn thấy</div>
      </div>
      <div class="ring ring-inner">
        <div class="ring-label">TẠI SAO</div>
        <div class="ring-text" style="font-size:0.65rem">Vì tôi tin mỗi người đang bị mắc kẹt bởi điều họ chưa nhìn thấy — và khi thấy được, họ tự do.</div>
      </div>
    </div>
  </div>

  <!-- Điểm mạnh + Lăng kính -->
  <div class="dna-grid fade-in" style="margin-top: 1.5rem">
    <div class="dna-cell">
      <p class="label">Điểm Mạnh 1</p>
      <h4>Đọc Điểm Mù</h4>
      <p>Nhìn thấy vấn đề ẩn mà chính người trong cuộc không thấy. Dẫn chứng: khai vấn cặp vợ chồng, trăn trở về mù quáng tâm lý.</p>
    </div>
    <div class="dna-cell">
      <p class="label">Điểm Mạnh 2</p>
      <h4>Tư Duy Hệ Thống + Ngôn Ngữ Hóa</h4>
      <p>Logic, mạch lạc, đặt tên được cho những thứ mơ hồ. Người khác nhận xét: "logic, hệ thống, nhiều góc nhìn đặc biệt."</p>
    </div>
    <div class="dna-cell">
      <p class="label">Điểm Mạnh 3</p>
      <h4>Khách Quan Không Vụ Lợi</h4>
      <p>Nhìn điểm tốt của người khác và điểm xấu của mình cùng lúc, không bị cảm xúc che. Đây là điểm mạnh ẩn — tôi coi là lẽ thường.</p>
    </div>
    <div class="dna-cell span2">
      <p class="label">Lăng Kính — Học Viên Lý Tưởng</p>
      <h4>Người Đang Mắc Kẹt Nhưng Chưa Biết Mắc Ở Đâu</h4>
      <p>Có đủ dũng khí để nhìn thẳng vào mình. Học với tôi, họ cảm thấy mình đang tỉnh dậy — không phải được dạy, mà được thấy.</p>
    </div>
    <div class="dna-cell">
      <p class="label">Mối Quan Hệ Với Học Viên</p>
      <h4>Người Soi Gương</h4>
      <p>Không nói "bạn nên làm thế này." Đặt câu hỏi để học viên tự thấy mình trong đó.</p>
    </div>
    <div class="dna-cell span3">
      <p class="label">Khác Biệt Hóa (Neumeier) — Tôi Là Người Duy Nhất...</p>
      <h4>"Dùng tư duy hệ thống kết hợp chiều sâu nội tâm để giúp người học nhìn thấy đúng điểm mù đang giữ họ lại — không phán xét, không áp đặt."</h4>
      <p style="margin-top:0.8rem">Vùng giao giữa <em>nhận thức tâm lý</em> và <em>ứng dụng thực tế</em>. Không hoàn toàn là therapist, không hoàn toàn là coach kỹ năng.</p>
    </div>
  </div>

  <!-- Vùng cấm -->
  <div class="insight-row fade-in" style="margin-top: 1.5rem">
    <div class="insight-card">
      <p class="tag">Vùng Cấm 1</p>
      <h4>Không Nói Điều Tôi Không Tin</h4>
      <p>Dù khán giả muốn nghe. Sự chân thật là lõi — không thể thỏa hiệp.</p>
    </div>
    <div class="insight-card">
      <p class="tag">Vùng Cấm 2</p>
      <h4>Không Làm Thay — Không Tạo Phụ Thuộc</h4>
      <p>Giúp người học bằng cách làm thay sẽ tạo ra sự phụ thuộc, trái với mục tiêu tự do.</p>
    </div>
    <div class="insight-card insight-full" style="display:none"></div>
    <div class="insight-card">
      <p class="tag">Vùng Cấm 3</p>
      <h4>Không Bỏ Qua Dấu Hiệu Tâm Lý</h4>
      <p>Không bỏ qua dấu hiệu tâm lý có vấn đề để cho xong buổi học. Đây là ranh giới đạo đức không thể vượt.</p>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- HỆ THỐNG NHẬN DIỆN -->
<section id="nhan-dien">
  <p class="section-label fade-in">DNA Hình Ảnh — Ánh Sáng Lặng</p>
  <h2 class="section-title fade-in">Hệ Thống<br>Nhận Diện Hình Ảnh</h2>

  <!-- Bảng màu -->
  <div class="palette-row fade-in">
    <div class="color-card">
      <div class="color-swatch" style="background:#1A1A2E">
        <span class="color-hex" style="color:#E8E0D0">#1A1A2E</span>
      </div>
      <div class="color-info">
        <p class="color-role">Chủ Đạo — Nền Chính</p>
        <p class="color-name">Đêm Nhận Ra</p>
        <p class="color-desc">Sage + chiều sâu nội tâm. Eva Heller: xanh đen = trí tuệ, đáng tin, chiều sâu. Giữ đúng "lớp ngoài lạnh" trong DNA.</p>
      </div>
    </div>
    <div class="color-card">
      <div class="color-swatch" style="background:#E8E0D0; border: 1px solid rgba(200,169,110,0.2)">
        <span class="color-hex" style="color:#1A1A2E">#E8E0D0</span>
      </div>
      <div class="color-info">
        <p class="color-role">Phụ — Khối Nội Dung</p>
        <p class="color-name">Giấy Cũ</p>
        <p class="color-desc">Trắng ngà — sự thật được viết tay, không in máy. Tránh trắng vô cảm. Ấm, thật, không trình diễn.</p>
      </div>
    </div>
    <div class="color-card">
      <div class="color-swatch" style="background:#C8A96E">
        <span class="color-hex" style="color:#1A1A2E">#C8A96E</span>
      </div>
      <div class="color-info">
        <p class="color-role">Nhấn — Tiêu Đề & Dấu Ấn</p>
        <p class="color-name">Ánh Vàng Tĩnh</p>
        <p class="color-desc">Vàng đất = trí tuệ ứng dụng, chín muồi qua trải nghiệm. Vàng đã qua lửa — gợi bài học từ thất bại chứng khoán.</p>
      </div>
    </div>
  </div>

  <!-- Font showcase -->
  <div class="font-showcase fade-in">
    <div class="font-row">
      <div class="font-meta">
        <p class="role">Tiêu Đề</p>
        <p class="name">Be Vietnam Pro</p>
        <p class="classification">Linéale / Geometric Sans</p>
      </div>
      <div class="font-sample">
        <span style="font-family:'Be Vietnam Pro',sans-serif; font-size: clamp(1.5rem, 4vw, 2.8rem); font-weight:700; color:var(--parchment); letter-spacing:-0.02em; line-height:1.1">Nhìn Thấy Để Tự Do</span>
      </div>
    </div>
    <div class="font-row">
      <div class="font-meta">
        <p class="role">Nội Dung</p>
        <p class="name">Lora</p>
        <p class="classification">Transitional Serif</p>
      </div>
      <div class="font-sample">
        <span style="font-family:'Lora',serif; font-size: clamp(0.9rem, 2vw, 1.1rem); color:var(--parchment); line-height:1.8">Mỗi người đang bị mắc kẹt bởi điều gì đó họ chưa nhìn thấy. Và khi họ thấy được, họ tự do. Đây là thứ tôi tin — và thứ tôi làm mỗi ngày.</span>
      </div>
    </div>
    <div class="font-row">
      <div class="font-meta">
        <p class="role">Điểm Nhấn / Quote</p>
        <p class="name">Cormorant Garamond</p>
        <p class="classification">Classique / Old-style</p>
      </div>
      <div class="font-sample">
        <span style="font-family:'Cormorant Garamond',serif; font-style:italic; font-size: clamp(1.2rem, 3vw, 1.9rem); font-weight:300; color:var(--gold); line-height:1.4">"Tự do bắt đầu từ khoảnh khắc bạn nhìn thấy chính mình."</span>
      </div>
    </div>
  </div>

  <!-- Dấu ấn -->
  <div class="fade-in" style="margin-top: 3rem">
    <p class="section-label">Dấu Ấn Cá Nhân</p>
    <div class="mark-demo">
      <div class="mark-item">
        <svg width="80" height="80" viewBox="0 0 80 80" fill="none">
          <path d="M 40 8 A 32 32 0 1 1 15 62" stroke="#C8A96E" stroke-width="1.5" stroke-linecap="round"/>
        </svg>
        <p class="mark-label">Trên Nền Tối</p>
      </div>
      <div class="mark-item" style="background: var(--parchment); padding: 2rem; border-radius:2px">
        <svg width="80" height="80" viewBox="0 0 80 80" fill="none">
          <path d="M 40 8 A 32 32 0 1 1 15 62" stroke="#1A1A2E" stroke-width="1.5" stroke-linecap="round"/>
        </svg>
        <p class="mark-label" style="color:var(--navy)">Trên Nền Sáng</p>
      </div>
      <div class="mark-item">
        <svg width="120" height="120" viewBox="0 0 120 120" fill="none">
          <path d="M 60 10 A 50 50 0 1 1 20 92" stroke="#C8A96E" stroke-width="1.2" stroke-linecap="round"/>
          <text x="60" y="56" text-anchor="middle" font-family="Cormorant Garamond, serif" font-style="italic" font-size="10" fill="#E8E0D0" opacity="0.6">nhìn thấy</text>
          <text x="60" y="70" text-anchor="middle" font-family="Cormorant Garamond, serif" font-style="italic" font-size="10" fill="#C8A96E" opacity="0.8">để tự do</text>
        </svg>
        <p class="mark-label">Với Tagline</p>
      </div>
    </div>
    <p style="text-align:center; font-size:0.82rem; color:var(--text-muted); margin-top:1rem; font-style:italic">Vòng tròn không khép kín = "tự do chưa hoàn chỉnh, vẫn đang khám phá." Đặt góc dưới phải mọi thiết kế.</p>
  </div>

  <!-- Phong cách hình ảnh -->
  <div class="style-grid fade-in" style="margin-top:3rem">
    <div class="style-block">
      <h4>✓ Ánh Sáng</h4>
      <p>Tự nhiên một hướng — từ cửa sổ hoặc đèn đọc sách. Có vùng tối rõ ràng. Không đèn studio đều.</p>
    </div>
    <div class="style-block">
      <h4>✓ Tông Màu Ảnh</h4>
      <p>Desaturate nhẹ, warm shadow, không HDR. Ảnh trông như được chụp lúc sắp tối hoặc sáng sớm.</p>
    </div>
    <div class="style-block">
      <h4>✓ Bối Cảnh Ưu Tiên</h4>
      <p>Không gian tĩnh có chiều sâu — bàn làm việc có sách, cửa sổ nhìn ra ngoài, thiền viện, hành lang vắng. Không cần "đẹp" — cần "thật".</p>
    </div>
    <div class="style-block">
      <h4>✓ Góc Máy</h4>
      <p>Ngang mắt hoặc hơi cao — cảm giác đối thoại bình đẳng. Không nhìn xuống (dạy đời), không nhìn lên (ngưỡng mộ).</p>
    </div>
  </div>

  <!-- Bảng cấm -->
  <div class="fade-in" style="margin-top:3rem">
    <p class="section-label">Bảng Cấm — Anti-Style</p>
    <div class="forbidden-grid">
      <div class="forbidden-card">
        <h4>Màu Cấm</h4>
        <ul>
          <li><strong>#FF6B35 Cam Rực</strong> — ồn ào, vui vẻ bề mặt, trái Sage trầm tĩnh</li>
          <li><strong>#7B2D8B Tím Marketing</strong> — đại trà trong ngành, mất khác biệt</li>
          <li><strong>#FFFFFF Trắng Tinh</strong> — quá lạnh, vô cảm, trái DNA ấm</li>
        </ul>
      </div>
      <div class="forbidden-card">
        <h4>Font Cấm</h4>
        <ul>
          <li><strong>Montserrat Bold</strong> — quá phổ biến trong đào tạo, mất cá tính</li>
          <li><strong>Quicksand / Poppins</strong> — tròn trịa, dễ thương, gợi Entertainer</li>
          <li><strong>Font Hoa Decorative</strong> — hô hào, trình diễn, trái vùng cấm</li>
        </ul>
      </div>
      <div class="forbidden-card">
        <h4>Phong Cách Ảnh Cấm</h4>
        <ul>
          <li><strong>Stock cười tươi laptop</strong> — giả tạo, mất tính chân thật Sage</li>
          <li><strong>Infographic màu sắc rực rỡ</strong> — gợi "công thức 7 bước" mà DNA từ chối</li>
          <li><strong>Collage nhiều lớp hiệu ứng</strong> — loạn thị giác, trái khoảng trắng cố ý</li>
        </ul>
      </div>
    </div>
  </div>

  <!-- AI Prompt -->
  <div class="fade-in" style="margin-top:3rem">
    <p class="section-label">Mỏ Neo Phong Cách — AI Prompt</p>
    <div class="prompt-block" id="aiPrompt">
      A contemplative Vietnamese male educator in his late 20s, seated near a window with natural side-lighting casting soft shadows. Background: minimal desk with books, muted interior. Color palette: deep navy #1A1A2E, warm parchment #E8E0D0, brushed gold accent #C8A96E. Typography feel: clean geometric sans-serif with classical italic quote overlay. Subtle paper grain texture. One thin incomplete golden circle as personal mark, bottom-right corner. Mood: quiet intelligence, not performance. Editorial portrait, 4K, professional photography, Leica tone, no artificial studio light.
    </div>
    <button class="copy-btn" onclick="copyPrompt()">Copy Prompt</button>
  </div>
</section>

<div class="divider"></div>

<!-- TUYÊN NGÔN -->
<section id="tuyen-ngon" style="padding-bottom: 2rem">
  <p class="section-label fade-in" style="justify-content:center; text-align:center">Tuyên Ngôn DNA</p>
  <div class="manifesto-wrap fade-in">
    <p>Tôi không ở đây để làm <strong>người thông minh nhất phòng</strong>. Tôi ở đây vì tôi biết cảm giác bị mắc kẹt mà không biết mình đang mắc ở đâu.</p>
    <p>Thứ tôi làm tốt nhất không phải dạy — mà là giúp người khác <strong>nhìn thấy</strong>. Thấy điều đang bị che. Thấy mô thức đang lặp lại. Thấy chính mình rõ hơn một chút.</p>
    <p>Tôi sẽ không nói những gì người ta muốn nghe. Tôi sẽ nói thứ tôi thấy là <strong>thật</strong>.</p>
    <p>Tôi tin con người xứng đáng được tự do. Và tự do bắt đầu từ sự <strong>nhìn thấy</strong> — không phải từ thêm thông tin, thêm công thức, thêm động lực.</p>
    <p>Mỗi ngày tôi làm việc này — không phải vì nó dễ. Mà vì khoảnh khắc ai đó thấy ra điều họ chưa từng thấy — đó là thứ không có gì thay thế được.</p>
  </div>
</section>

<div class="divider"></div>

<!-- PITCH -->
<section id="pitch">
  <p class="section-label fade-in">Câu Neo Giới Thiệu</p>
  <h2 class="section-title fade-in">Ba Phiên Bản Pitch</h2>

  <div class="pitch-cards fade-in">
    <div class="pitch-card">
      <p class="pitch-label">1 Dòng</p>
      <p style="font-family:'Cormorant Garamond',serif; font-style:italic; font-size:1.15rem; line-height:1.7; color:var(--gold)">"Tôi giúp người đang mắc kẹt nhìn thấy đúng điều đang giữ họ lại — bằng tư duy hệ thống và chiều sâu nội tâm — vì tôi tin tự do bắt đầu từ sự nhìn thấy."</p>
    </div>
    <div class="pitch-card">
      <p class="pitch-label">3 Dòng — Mạng Xã Hội</p>
      <p>Hầu hết chúng ta không thiếu thông tin. Chúng ta thiếu một người giúp mình nhìn thấy đúng chỗ mình đang mù.</p>
      <p style="margin-top:0.8rem">Tôi không dạy công thức. Tôi giúp bạn đọc được chính mình — rõ hơn, thật hơn.</p>
      <p style="margin-top:0.8rem; color:var(--gold)">Vì khi thấy được — bạn tự biết phải làm gì.</p>
    </div>
    <div class="pitch-card">
      <p class="pitch-label">30 Giây — Sân Khấu</p>
      <p>Tôi từng nghĩ hiểu biết là đủ để thành công — cho đến khi tôi thua đúng lúc gần đích nhất. Bài học không phải là học thêm. Mà là nhìn thấy điểm mù mình đang có.</p>
      <p style="margin-top:0.8rem">Từ đó tôi làm một việc: giúp người khác nhìn thấy điều đang giữ họ lại — trong công việc, trong mối quan hệ, trong chính họ.</p>
      <p style="margin-top:0.8rem; color:var(--gold); font-style:italic">Tôi tin rằng tự do thật sự bắt đầu từ khoảnh khắc bạn nhìn thấy chính mình.</p>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>"Tự do bắt đầu từ khoảnh khắc bạn nhìn thấy chính mình."</p>
  <div class="mark-footer">
    <svg width="48" height="48" viewBox="0 0 48 48" fill="none">
      <path d="M 24 4 A 20 20 0 1 1 8 36" stroke="#C8A96E" stroke-width="1" stroke-linecap="round" opacity="0.5"/>
    </svg>
  </div>
  <p style="margin-top:1rem; font-family:'Be Vietnam Pro',sans-serif; font-size:0.65rem; letter-spacing:0.15em; text-transform:uppercase; opacity:0.3">DNA Thương Hiệu Cá Nhân — Ánh Sáng Lặng</p>
</footer>

<script>
  // Intersection Observer for fade-in
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => {
          entry.target.classList.add('visible');
        }, 100);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

  // Copy prompt
  function copyPrompt() {
    const text = document.getElementById('aiPrompt').innerText;
    navigator.clipboard.writeText(text).then(() => {
      const btn = document.querySelector('.copy-btn');
      btn.textContent = 'Đã Copy ✓';
      btn.style.color = '#C8A96E';
      btn.style.borderColor = '#C8A96E';
      setTimeout(() => {
        btn.textContent = 'Copy Prompt';
        btn.style.color = '';
        btn.style.borderColor = '';
      }, 2000);
    });
  }

  // Active nav on scroll
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a');

  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(section => {
      const top = section.offsetTop - 120;
      if (window.scrollY >= top) current = section.getAttribute('id');
    });
    navLinks.forEach(link => {
      link.style.opacity = link.getAttribute('href') === `#${current}` ? '1' : '0.5';
      link.style.color = link.getAttribute('href') === `#${current}` ? 'var(--gold)' : '';
    });
  });
</script>
</body>
</html>
