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
  <link href="https://fonts.googleapis.com/css2?family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&family=Raleway:wght@200;300;400&family=Pinyon+Script&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --cream: #f8f4ee;
      --parchment: #ede5d0;
      --gold: #b09060;
      --gold-light: #cbb07a;
      --dark: #5c4a38;
      --ink: #6b5744;
      --muted: #9c8672;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background-color: var(--cream);
      background-image:
        radial-gradient(ellipse at 20% 20%, rgba(184,150,46,0.06) 0%, transparent 60%),
        radial-gradient(ellipse at 80% 80%, rgba(184,150,46,0.05) 0%, transparent 55%);
      color: var(--ink);
      font-family: 'Raleway', sans-serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 60px 20px;
    }

    .menu-card {
      max-width: 680px;
      width: 100%;
      background: #fefcf8;
      border: 1px solid rgba(176,144,96,0.2);
      box-shadow:
        0 0 0 6px #fefcf8,
        0 0 0 7px rgba(176,144,96,0.15),
        0 20px 60px rgba(92,74,56,0.08);
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
      font-family: 'Raleway', sans-serif;
      font-weight: 300;
      font-size: 9.5px;
      letter-spacing: 0.38em;
      color: var(--gold);
      text-transform: uppercase;
      display: block;
      margin-bottom: 14px;
      animation: fadeIn 1.4s ease 0.2s both;
    }

    .menu-header h1 {
      font-family: 'Pinyon Script', cursive;
      font-size: 62px;
      font-weight: 400;
      color: var(--dark);
      letter-spacing: 0.02em;
      line-height: 1.1;
      animation: fadeIn 1.4s ease 0.3s both;
    }

    .menu-header .subtitle {
      font-family: 'Raleway', sans-serif;
      font-weight: 200;
      font-size: 11px;
      color: var(--muted);
      margin-top: 10px;
      letter-spacing: 0.22em;
      text-transform: uppercase;
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
      font-family: 'Raleway', sans-serif;
      font-weight: 300;
      font-size: 8px;
      letter-spacing: 0.32em;
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
      font-family: 'Libre Baskerville', Georgia, serif;
      font-size: 18px;
      font-weight: 400;
      font-style: italic;
      color: var(--dark);
      margin-bottom: 8px;
      letter-spacing: 0.01em;
    }

    .dish-desc {
      font-family: 'Raleway', sans-serif;
      font-weight: 300;
      font-size: 13.5px;
      color: var(--muted);
      line-height: 1.8;
    }

    .dish-sub {
      font-family: 'Raleway', sans-serif;
      font-weight: 300;
      font-size: 13px;
      color: var(--muted);
      line-height: 1.8;
      margin-top: 10px;
    }

    .dish-options {
      list-style: none;
      margin-top: 10px;
    }
    .dish-options li {
      font-family: 'Raleway', sans-serif;
      font-weight: 300;
      font-size: 13px;
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
      font-family: 'Libre Baskerville', serif;
      font-style: italic;
      font-size: 14px;
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
    <span class="overline">hichmoki TikTok Foodie Dinner</span>
    <h1>Menu Classico</h1>
    <div class="header-rule"><span>❧</span></div>
  </header>

  <!-- Pane -->
  <div class="course">
    <div class="course-label">Pane Artigianale</div>
    <div class="dish-name">Versgebakken Volkorenbrood</div>
    <div class="dish-desc">Geserveerd met huisgemaakte burro alle erbe, een subtiele toets van peperoncino en extra vergine olijfolie van eerste persing.</div>
  </div>

  <!-- Antipasto -->
  <div class="course">
    <div class="course-label">Antipasto</div>
    <div class="dish-name">Zuppa di Verdure con Brodo d'Agnello</div>
    <div class="dish-desc">Seizoensgroenten in een verfijnde, langzaam getrokken lamsbouillon. Zacht van structuur en rijk van smaak.</div>
  </div>

  <div class="ornament-divider">· · ✦ · ·</div>

  <!-- Piatto Principale -->
  <div class="course">
    <div class="course-label">Piatto Principale</div>
    <div class="dish-name">Risotto all'Ossobuco alla Milanese</div>
    <div class="dish-desc">Romige risotto op klassieke wijze bereid, verrijkt met kalfsossobuco — langzaam gegaard tot boterzacht en vol van smaak. Afgewerkt met frisse gremolata van peterselie, knoflook en citroenrasp.</div>
  </div>

  <!-- Vini -->
  <div class="course">
    <div class="course-label">Abbinamento Vini</div>
    <div class="dish-name">Rood of Wit</div>
    <div class="dish-desc">Keuze uit een elegante rode of frisse witte wijn, zorgvuldig geselecteerd ter begeleiding van het gerecht.</div>
  </div>

  <div class="ornament-divider">· · ✦ · ·</div>

  <!-- Dolce -->
  <div class="course">
    <div class="course-label">Dolce</div>
    <div class="dish-name">Gelato alla Vaniglia fatto in casa</div>
    <div class="dish-desc">Ambachtelijk bereid vanille-ijs, geserveerd met warme fondente chocoladesaus of zachte karamelsaus.</div>
  </div>

  <!-- Caffè -->
  <div class="course">
    <div class="course-label">Caffè</div>
    <div class="dish-name">Espresso · Ristretto · Lungo</div>
    <div class="dish-desc">Of een selectie van verfijnde theeën.</div>
  </div>

  <footer class="menu-footer">
    <p>Buon appetito &nbsp;✦&nbsp; Bitch x</p>
  </footer>
</div>

<header class="menu-header">
    <span class="overline">hichmoki TikTok Foodie Dinner</span>
    <h1>2026</h1>
    <div class="header-rule"><span>❧</span></div>
  </header>

</body>
</html>
 