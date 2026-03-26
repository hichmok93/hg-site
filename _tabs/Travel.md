---
layout: page
title: menu
icon: fas fa-utensils
permalink: /Travel/
order: 1
---

<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Menu van de Avond</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Cinzel:wght@400;600&family=EB+Garamond:ital@1&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --cream: #f5f0e8;
      --parchment: #ede5d0;
      --gold: #b8962e;
      --gold-light: #d4af5a;
      --dark: #1c1812;
      --ink: #2e2416;
      --muted: #7a6a52;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background-color: var(--cream);
      background-image:
        radial-gradient(ellipse at 20% 20%, rgba(184,150,46,0.06) 0%, transparent 60%),
        radial-gradient(ellipse at 80% 80%, rgba(184,150,46,0.05) 0%, transparent 55%);
      color: var(--ink);
      font-family: 'Cormorant Garamond', Georgia, serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 60px 20px;
    }

    .menu-card {
      max-width: 680px;
      width: 100%;
      background: #fdfaf4;
      border: 1px solid rgba(184,150,46,0.25);
      box-shadow:
        0 0 0 6px #fdfaf4,
        0 0 0 7px rgba(184,150,46,0.2),
        0 20px 60px rgba(28,24,18,0.12);
      padding: 64px 72px;
      position: relative;
      animation: fadeIn 1.2s ease both;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* Corner ornaments */
    .menu-card::before,
    .menu-card::after {
      content: '✦';
      position: absolute;
      font-size: 11px;
      color: var(--gold);
      opacity: 0.5;
    }
    .menu-card::before { top: 18px; left: 22px; }
    .menu-card::after  { bottom: 18px; right: 22px; }

    .corner-br, .corner-tl {
      position: absolute;
      font-size: 11px;
      color: var(--gold);
      opacity: 0.5;
    }
    .corner-tl { top: 18px; right: 22px; }
    .corner-br { bottom: 18px; left: 22px; }

    /* Header */
    .menu-header {
      text-align: center;
      margin-bottom: 52px;
    }

    .menu-header .overline {
      font-family: 'Cinzel', serif;
      font-size: 10px;
      letter-spacing: 0.35em;
      color: var(--gold);
      text-transform: uppercase;
      display: block;
      margin-bottom: 16px;
      animation: fadeIn 1.4s ease 0.2s both;
    }

    .menu-header h1 {
      font-family: 'Cinzel', serif;
      font-size: 32px;
      font-weight: 600;
      color: var(--dark);
      letter-spacing: 0.06em;
      line-height: 1.2;
      animation: fadeIn 1.4s ease 0.3s both;
    }

    .menu-header .subtitle {
      font-family: 'Cormorant Garamond', serif;
      font-style: italic;
      font-size: 16px;
      color: var(--muted);
      margin-top: 10px;
      letter-spacing: 0.05em;
      animation: fadeIn 1.4s ease 0.4s both;
    }

    .header-rule {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-top: 28px;
      animation: fadeIn 1.4s ease 0.5s both;
    }
    .header-rule::before,
    .header-rule::after {
      content: '';
      flex: 1;
      height: 1px;
      background: linear-gradient(to right, transparent, var(--gold-light), transparent);
    }
    .header-rule span {
      color: var(--gold);
      font-size: 14px;
    }

    /* Courses */
    .course {
      margin-bottom: 44px;
      animation: fadeIn 1.4s ease both;
    }
    .course:nth-child(2) { animation-delay: 0.3s; }
    .course:nth-child(3) { animation-delay: 0.5s; }
    .course:nth-child(4) { animation-delay: 0.7s; }
    .course:nth-child(5) { animation-delay: 0.9s; }
    .course:nth-child(6) { animation-delay: 1.1s; }

    .course-label {
      font-family: 'Cinzel', serif;
      font-size: 9.5px;
      letter-spacing: 0.3em;
      color: var(--gold);
      text-transform: uppercase;
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 14px;
    }
    .course-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: linear-gradient(to right, rgba(184,150,46,0.3), transparent);
    }

    .dish-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 22px;
      font-weight: 600;
      color: var(--dark);
      margin-bottom: 7px;
      letter-spacing: 0.02em;
    }

    .dish-desc {
      font-family: 'Cormorant Garamond', serif;
      font-style: italic;
      font-size: 16px;
      color: var(--muted);
      line-height: 1.65;
    }

    .dish-sub {
      font-family: 'Cormorant Garamond', serif;
      font-size: 15.5px;
      color: var(--muted);
      line-height: 1.7;
      margin-top: 10px;
    }

    .dish-options {
      list-style: none;
      margin-top: 10px;
    }
    .dish-options li {
      font-family: 'Cormorant Garamond', serif;
      font-style: italic;
      font-size: 15.5px;
      color: var(--muted);
      padding: 3px 0;
      padding-left: 16px;
      position: relative;
    }
    .dish-options li::before {
      content: '—';
      position: absolute;
      left: 0;
      color: var(--gold-light);
    }

    /* Divider ornament */
    .ornament-divider {
      text-align: center;
      color: var(--gold-light);
      font-size: 13px;
      letter-spacing: 0.5em;
      margin: 36px 0;
      opacity: 0.6;
    }

    /* Footer */
    .menu-footer {
      text-align: center;
      margin-top: 48px;
      padding-top: 28px;
      border-top: 1px solid rgba(184,150,46,0.2);
      animation: fadeIn 1.6s ease 1.4s both;
    }
    .menu-footer p {
      font-family: 'Cormorant Garamond', serif;
      font-style: italic;
      font-size: 16px;
      color: var(--muted);
      letter-spacing: 0.04em;
    }

    @media (max-width: 600px) {
      .menu-card { padding: 40px 28px; }
      .menu-header h1 { font-size: 26px; }
    }
  </style>
</head>
<body>

<div class="menu-card">
  <span class="corner-tl">✦</span>
  <span class="corner-br">✦</span>

  <header class="menu-header">
    <span class="overline">hichmoki's TikTok Foody Dinner</span>
    <h1>Menu van de Avond</h1>
    <p class="subtitle">Huisgemaakt · Eerlijk · Met liefde bereid</p>
    <div class="header-rule"><span>❧</span></div>
  </header>

  <!-- Amuse -->
  <div class="course">
    <div class="course-label">Amuse</div>
    <div class="dish-name">Vers Gebakken Brood</div>
    <div class="dish-desc">Knapperig brood uit eigen oven, geserveerd met huisgemaakte kruidenboter, Spaanse peper en olijfolie.</div>
  </div>

  <!-- Voorgerecht -->
  <div class="course">
    <div class="course-label">Voorgerecht</div>
    <div class="dish-name">Groentesoep</div>
    <div class="dish-desc">Heldere soep op basis van zelfgemaakte lamsstock, vol van smaak en warm van karakter.</div>
  </div>

  <div class="ornament-divider">· · ✦ · ·</div>

  <!-- Hoofdgerecht -->
  <div class="course">
    <div class="course-label">Hoofdgerecht</div>
    <div class="dish-name">Risotto met Ossobuco</div>
    <div class="dish-desc">Romige risotto met langzaam gestoofde kalfssschenkel, afgemaakt met een klassieke gremolata.</div>
    <div class="dish-sub" style="margin-top:14px; font-size:13.5px; letter-spacing:0.04em;">
      <em>Bij het gerecht — optioneel</em><br>
      <span style="display:inline-block; margin-top:6px;">Wit &nbsp;·&nbsp; fris en licht &nbsp;&nbsp;|&nbsp;&nbsp; Rood &nbsp;·&nbsp; klassiek en vol</span>
    </div>
  </div>

  <div class="ornament-divider">· · ✦ · ·</div>

  <!-- Dessert -->
  <div class="course">
    <div class="course-label">Dessert</div>
    <div class="dish-name">Pannenkoek met Huisgemaakt Roomijs</div>
    <div class="dish-desc">Goudbruin gebakken pannenkoek met een bolletje zacht roomijs — naar keuze met chocoladedip of homemade karamel.</div>
  </div>

  <!-- Afsluiting -->
  <div class="course">
    <div class="course-label">Afsluiting</div>
    <div class="dish-name">Warme Dranken</div>
    <div class="dish-desc">Koffie &nbsp;·&nbsp; Espresso &nbsp;·&nbsp; Thee</div>
  </div>

  <footer class="menu-footer">
    <p>Smakelijk eten &nbsp;—&nbsp; geniet van de avond</p>
  </footer>
</div>

</body>
</html>
