---
layout: html-only
title: breathe work
icon: fa-solid fa-wind
permalink: /breathe/
order: 7
---

<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Jamila Mokhtari · Breathwork & Meditatie</title>
<meta name="description" content="Ademwerk- en meditatiesessies met breathing coach Jamila Mokhtari. Kom tot rust, adem bewust en keer terug naar jezelf.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#f6f1ea;
    --bg-soft:#efe7dc;
    --ink:#2b2a33;
    --muted:#6b6874;
    --deep:#2f3a4a;
    --deep-2:#3d4c63;
    --sage:#8fa595;
    --sage-soft:#dfe8e1;
    --gold:#b8935a;
    --rose:#d9b8a8;
    --card:#fffdf9;
    --line:rgba(47,58,74,.12);
    --serif:"Cormorant Garamond",Georgia,"Times New Roman",serif;
    --sans:"Inter",system-ui,-apple-system,"Segoe UI",Roboto,sans-serif;
    --radius:22px;
    --shadow:0 20px 50px -28px rgba(47,58,74,.35);
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html{scroll-behavior:smooth}
  body{font-family:var(--sans);font-weight:300;background:var(--bg);color:var(--ink);line-height:1.7;font-size:17px;-webkit-font-smoothing:antialiased}
  img,svg{max-width:100%;display:block}
  a{color:inherit}
  .wrap{width:min(1120px,92%);margin:0 auto}
  h1,h2,h3{font-family:var(--serif);font-weight:500;line-height:1.12;color:var(--deep);letter-spacing:.2px}
  h1{font-size:clamp(2.8rem,7vw,5.2rem)}
  h2{font-size:clamp(2rem,4.5vw,3.1rem);margin-bottom:.6rem}
  h3{font-size:1.55rem;margin-bottom:.4rem}
  .eyebrow{display:inline-block;font-size:.76rem;letter-spacing:.28em;text-transform:uppercase;color:var(--gold);font-weight:500;margin-bottom:1rem}
  .lead{font-size:1.15rem;color:var(--muted);max-width:56ch}
  section{padding:clamp(4rem,9vw,7.5rem) 0}
  .center{text-align:center}
  .center .lead{margin:0 auto}

  /* NAV */
  header{position:fixed;inset:0 0 auto 0;z-index:50;transition:background .4s,box-shadow .4s,padding .4s;padding:1.2rem 0}
  header.scrolled{background:rgba(246,241,234,.88);backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);box-shadow:0 1px 0 var(--line);padding:.7rem 0}
  .nav{display:flex;align-items:center;justify-content:space-between;gap:1rem}
  .brand{font-family:var(--serif);font-size:1.5rem;font-weight:600;text-decoration:none;color:var(--deep);letter-spacing:.5px}
  .brand span{color:var(--gold)}
  nav ul{display:flex;gap:2rem;list-style:none;align-items:center}
  nav a{text-decoration:none;font-size:.9rem;color:var(--deep);letter-spacing:.04em;position:relative}
  nav a:not(.btn)::after{content:"";position:absolute;left:0;bottom:-4px;height:1px;width:0;background:var(--gold);transition:width .3s}
  nav a:not(.btn):hover::after{width:100%}
  .burger{display:none;background:none;border:0;cursor:pointer;width:42px;height:42px;position:relative}
  .burger span,.burger span::before,.burger span::after{display:block;position:absolute;left:9px;width:24px;height:1.5px;background:var(--deep);content:"";transition:.3s}
  .burger span{top:20px}.burger span::before{top:-7px;left:0}.burger span::after{top:7px;left:0}
  .burger[aria-expanded="true"] span{background:transparent}
  .burger[aria-expanded="true"] span::before{top:0;transform:rotate(45deg)}
  .burger[aria-expanded="true"] span::after{top:0;transform:rotate(-45deg)}

  .btn{display:inline-block;padding:.95rem 2rem;border-radius:999px;background:var(--deep);color:#fff;text-decoration:none;font-size:.92rem;letter-spacing:.06em;border:1px solid var(--deep);cursor:pointer;font-family:var(--sans);font-weight:400;transition:transform .3s,background .3s,box-shadow .3s}
  .btn:hover{background:var(--deep-2);transform:translateY(-2px);box-shadow:0 14px 26px -14px rgba(47,58,74,.7)}
  .btn.ghost{background:transparent;color:var(--deep)}
  .btn.ghost:hover{background:var(--deep);color:#fff}
  .btn.small{padding:.6rem 1.4rem}

  /* HERO */
  .hero{min-height:100vh;display:flex;align-items:center;position:relative;overflow:hidden;
    background:radial-gradient(1200px 700px at 80% 20%,rgba(231,217,198,.55) 0%,transparent 60%),radial-gradient(900px 600px at 10% 90%,rgba(223,232,225,.6) 0%,transparent 60%);padding-top:6rem}
  .hero-grid{display:grid;grid-template-columns:1.15fr .85fr;gap:3rem;align-items:center}
  .hero h1 em{font-style:italic;color:var(--gold);font-weight:400}
  .hero p.lead{margin:1.6rem 0 2.2rem}
  .hero-cta{display:flex;gap:1rem;flex-wrap:wrap}
  .orb-wrap{position:relative;aspect-ratio:1;display:grid;place-items:center}
  .orb{position:absolute;border-radius:50%;animation:orb 9s ease-in-out infinite}
  .orb.o1{width:88%;height:88%;background:radial-gradient(circle,rgba(184,147,90,.18),rgba(184,147,90,0) 70%)}
  .orb.o2{width:66%;height:66%;background:radial-gradient(circle at 35% 30%,#fff 0%,var(--sage-soft) 40%,var(--sage) 100%);box-shadow:0 40px 80px -30px rgba(47,58,74,.45);animation-delay:-1.2s}
  .orb.o3{width:42%;height:42%;background:radial-gradient(circle at 35% 30%,#fff,var(--rose));opacity:.85;animation-delay:-2.4s}
  @keyframes orb{0%,100%{transform:scale(.9)}50%{transform:scale(1.06)}}
  .orb-caption{position:absolute;bottom:2%;font-family:var(--serif);font-style:italic;color:var(--deep);font-size:1.15rem;opacity:.8}
  .scroll-hint{position:absolute;bottom:1.6rem;left:50%;transform:translateX(-50%);font-size:.7rem;letter-spacing:.3em;text-transform:uppercase;color:var(--muted)}

  /* ABOUT */
  .about-grid{display:grid;grid-template-columns:.9fr 1.1fr;gap:4rem;align-items:center}
  .portrait{aspect-ratio:4/5;border-radius:var(--radius) var(--radius) 220px 220px;background:linear-gradient(160deg,var(--sage-soft),var(--rose));position:relative;overflow:hidden;box-shadow:var(--shadow);display:grid;place-items:center}
  .portrait::before{content:"";position:absolute;inset:14px;border:1px solid rgba(255,255,255,.7);border-radius:inherit}
  .portrait span{font-family:var(--serif);font-size:7rem;color:rgba(47,58,74,.55);font-style:italic}
  .portrait img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover}
  .about p+p{margin-top:1rem}
  .values{display:flex;gap:.7rem;flex-wrap:wrap;margin-top:1.8rem}
  .chip{padding:.45rem 1.1rem;border-radius:999px;background:var(--sage-soft);color:var(--deep);font-size:.85rem}

  /* OFFER */
  #flow{position:fixed;inset:0;width:100%;height:100%;z-index:0;pointer-events:none}
  main,footer{position:relative;z-index:1}
  .offer{background:rgba(239,231,220,.6)}
  .cards{display:grid;grid-template-columns:repeat(3,1fr);gap:1.6rem;margin-top:3.2rem}
  .card{background:var(--card);border-radius:var(--radius);padding:2.2rem 2rem;box-shadow:var(--shadow);border:1px solid var(--line);display:flex;flex-direction:column;transition:transform .4s}
  .card:hover{transform:translateY(-6px)}
  .card .ico{width:54px;height:54px;border-radius:50%;background:var(--sage-soft);display:grid;place-items:center;margin-bottom:1.3rem}
  .card .ico svg{width:26px;height:26px;stroke:var(--deep);fill:none;stroke-width:1.4;stroke-linecap:round;stroke-linejoin:round}
  .card p{color:var(--muted);font-size:.97rem;flex:1}
  .meta{display:flex;justify-content:space-between;margin-top:1.4rem;padding-top:1.1rem;border-top:1px solid var(--line);font-size:.85rem;color:var(--deep)}
  .card .btn{margin-top:1.4rem;text-align:center}

  /* BREATH TOOL */
  .tool{background:linear-gradient(180deg,var(--deep) 0%,#252f3d 100%);color:#e9e4dc;position:relative;overflow:hidden}
  .tool h2{color:#fff}
  .tool .lead{color:#bdb8b0}
  .tool .eyebrow{color:var(--rose)}
  .tool::before{content:"";position:absolute;width:800px;height:800px;border-radius:50%;background:radial-gradient(circle,rgba(143,165,149,.18),transparent 65%);top:-250px;right:-250px}
  .tool-grid{display:grid;grid-template-columns:1fr 1fr;gap:3rem;align-items:center;margin-top:3rem;position:relative}
  .stage{aspect-ratio:1;max-width:460px;margin:0 auto;width:100%;position:relative;display:grid;place-items:center}
  .ring{position:absolute;inset:0;border-radius:50%;border:1px dashed rgba(255,255,255,.2)}
  .ring.r2{inset:9%;border-style:solid;border-color:rgba(255,255,255,.1)}
  .breath{width:62%;height:62%;border-radius:50%;background:radial-gradient(circle at 35% 30%,#fff 0%,var(--sage-soft) 35%,var(--sage) 100%);box-shadow:0 0 90px 10px rgba(143,165,149,.35);transform:scale(.55);will-change:transform;display:grid;place-items:center}
  .stage-text{position:absolute;text-align:center;pointer-events:none}
  .stage-text .phase{font-family:var(--serif);font-size:clamp(1.8rem,4vw,2.6rem);color:#fff;text-shadow:0 2px 20px rgba(0,0,0,.35)}
  .stage-text .count{font-size:1rem;letter-spacing:.2em;color:#e3ddd2;margin-top:.1rem}
  .controls{display:grid;gap:1.6rem}
  .field label{display:block;font-size:.76rem;letter-spacing:.22em;text-transform:uppercase;color:var(--rose);margin-bottom:.6rem}
  .seg{display:flex;flex-wrap:wrap;gap:.5rem}
  .seg button{background:transparent;border:1px solid rgba(255,255,255,.25);color:#e9e4dc;padding:.6rem 1.15rem;border-radius:999px;cursor:pointer;font-family:var(--sans);font-size:.88rem;font-weight:300;transition:.3s}
  .seg button:hover{border-color:#fff}
  .seg button[aria-pressed="true"]{background:#fff;color:var(--deep);border-color:#fff}
  .pattern-desc{font-size:.95rem;color:#bdb8b0;min-height:3.4em}
  .tool .btn{background:#fff;color:var(--deep);border-color:#fff}
  .tool .btn:hover{background:var(--rose);border-color:var(--rose)}
  .progress{height:2px;background:rgba(255,255,255,.15);border-radius:2px;overflow:hidden}
  .progress i{display:block;height:100%;width:0;background:var(--rose)}
  .timer-line{display:flex;justify-content:space-between;font-size:.82rem;color:#bdb8b0;margin-top:.5rem}
  .done-msg{font-family:var(--serif);font-style:italic;font-size:1.3rem;color:#fff;min-height:1.6em}
  .note{font-size:.8rem;color:#9b968f}

  /* PROCESS */
  .steps{display:grid;grid-template-columns:repeat(3,1fr);gap:2.5rem;margin-top:3.4rem;counter-reset:s}
  .step{text-align:center;position:relative}
  .step::before{counter-increment:s;content:counter(s);display:grid;place-items:center;width:64px;height:64px;margin:0 auto 1.3rem;border-radius:50%;border:1px solid var(--gold);color:var(--gold);font-family:var(--serif);font-size:1.7rem}
  .step p{color:var(--muted);font-size:.97rem;max-width:34ch;margin:0 auto}

  /* BENEFITS */
  .benefits{background:rgba(223,232,225,.65)}
  .ben-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1.2rem;margin-top:3rem}
  .ben{background:rgba(255,255,255,.55);border-radius:18px;padding:1.6rem 1.3rem;text-align:center;font-family:var(--serif);font-size:1.3rem;color:var(--deep);line-height:1.3}
  .ben small{display:block;font-family:var(--sans);font-size:.82rem;color:var(--muted);margin-top:.5rem;line-height:1.5}

  /* SCHEDULE */
  .sched{display:grid;gap:1rem;margin-top:3rem;max-width:820px;margin-left:auto;margin-right:auto}
  .slot{display:grid;grid-template-columns:90px 1fr auto;gap:1.5rem;align-items:center;background:var(--card);padding:1.3rem 1.6rem;border-radius:18px;border:1px solid var(--line)}
  .date{text-align:center;font-family:var(--serif);color:var(--deep);line-height:1}
  .date b{display:block;font-size:2.2rem;font-weight:500}
  .date span{font-family:var(--sans);font-size:.72rem;letter-spacing:.2em;text-transform:uppercase;color:var(--gold)}
  .slot h3{font-size:1.3rem;margin:0}
  .slot p{font-size:.9rem;color:var(--muted)}

  /* FAQ */
  .faq{max-width:780px;margin:3rem auto 0}
  details{border-bottom:1px solid var(--line);padding:1.2rem 0}
  summary{cursor:pointer;list-style:none;display:flex;justify-content:space-between;align-items:center;gap:1rem;font-family:var(--serif);font-size:1.35rem;color:var(--deep)}
  summary::-webkit-details-marker{display:none}
  summary::after{content:"+";font-family:var(--sans);font-weight:200;font-size:1.6rem;color:var(--gold);transition:transform .3s}
  details[open] summary::after{transform:rotate(45deg)}
  details p{margin-top:.8rem;color:var(--muted);font-size:.97rem}

  /* CONTACT */
  .contact{background:rgba(239,231,220,.6)}
  .contact-grid{display:grid;grid-template-columns:.9fr 1.1fr;gap:4rem;align-items:start}
  .contact-info p{margin-top:1rem;color:var(--muted)}
  .contact-info ul{list-style:none;margin-top:1.8rem;display:grid;gap:.5rem;color:var(--deep)}
  form{background:var(--card);padding:2.4rem;border-radius:var(--radius);box-shadow:var(--shadow);border:1px solid var(--line);display:grid;gap:1.2rem}
  .row{display:grid;grid-template-columns:1fr 1fr;gap:1.2rem}
  form label{display:block;font-size:.78rem;letter-spacing:.14em;text-transform:uppercase;color:var(--muted);margin-bottom:.4rem}
  input,select,textarea{width:100%;font-family:var(--sans);font-size:1rem;font-weight:300;color:var(--ink);background:var(--bg);border:1px solid var(--line);border-radius:12px;padding:.85rem 1rem;transition:border .3s,box-shadow .3s}
  input:focus,select:focus,textarea:focus{outline:none;border-color:var(--sage);box-shadow:0 0 0 4px rgba(143,165,149,.2)}
  textarea{min-height:120px;resize:vertical}
  .check{display:flex;gap:.7rem;align-items:flex-start;font-size:.85rem;color:var(--muted)}
  .check input{width:auto;margin-top:.35rem}
  .form-msg{font-size:.92rem;color:var(--deep);min-height:1.3em}

  footer{background:var(--deep);color:#c9c4bb;padding:3.5rem 0 2rem;text-align:center}
  footer .brand{color:#fff;font-size:1.8rem}
  footer p{font-size:.85rem;margin-top:.8rem}
  footer .quote{font-family:var(--serif);font-style:italic;font-size:1.3rem;color:#e9e4dc;margin:1.2rem 0}
  footer small{display:block;margin-top:1.6rem;font-size:.75rem;color:#8d8a85;max-width:70ch;margin-left:auto;margin-right:auto}

  /* reveal */
  .reveal{opacity:0;transform:translateY(24px);transition:opacity 1s ease,transform 1s ease}
  .reveal.in{opacity:1;transform:none}

  @media (max-width:900px){
    .hero-grid,.about-grid,.tool-grid,.contact-grid{grid-template-columns:1fr}
    .orb-wrap{max-width:360px;margin:0 auto;order:-1}
    .hero{padding-top:7rem}
    .cards,.steps{grid-template-columns:1fr}
    .ben-grid{grid-template-columns:1fr 1fr}
    .portrait{max-width:340px;margin:0 auto}
    .burger{display:block}
    nav ul{position:absolute;top:100%;left:0;right:0;flex-direction:column;background:var(--bg);padding:1.5rem 0 2rem;gap:1.3rem;box-shadow:0 20px 30px -20px rgba(0,0,0,.2);display:none}
    nav ul.open{display:flex}
    .slot{grid-template-columns:70px 1fr}
    .slot .btn{grid-column:1/-1;text-align:center}
    .row{grid-template-columns:1fr}
    .scroll-hint{display:none}
  }
  @media (max-width:520px){ body{font-size:16px} .ben-grid{grid-template-columns:1fr} form{padding:1.6rem} }
  @media (prefers-reduced-motion:reduce){
    *{animation:none!important;transition:none!important;scroll-behavior:auto!important}
    .reveal{opacity:1;transform:none}
  }
</style>
</head>
<body>

<canvas id="flow" aria-hidden="true"></canvas>

<header id="top-bar">
  <div class="wrap nav">
    <a href="#top" class="brand">Jamila <span>Mokhtari</span></a>
    <nav aria-label="Hoofdmenu">
      <button class="burger" aria-label="Menu" aria-expanded="false" aria-controls="menu"><span></span></button>
      <ul id="menu">
        <li><a href="#over">Over mij</a></li>
        <li><a href="#sessies">Sessies</a></li>
        <li><a href="#adem">Adem mee</a></li>
        <li><a href="#agenda">Agenda</a></li>
        <li><a href="#faq">Vragen</a></li>
        <li><a href="#contact" class="btn small">Boek een sessie</a></li>
      </ul>
    </nav>
  </div>
</header>

<main id="top">

<!-- HERO -->
<section class="hero">
  <div class="wrap hero-grid">
    <div>
      <span class="eyebrow">Breathwork · Meditatie · Stilte</span>
      <h1>Adem in.<br>Kom thuis <em>bij jezelf.</em></h1>
      <p class="lead">Met begeleide ademsessies en meditatie nodig ik je uit om te vertragen, te voelen en je innerlijke rust weer te vinden. Zacht, veilig en met aandacht.</p>
      <div class="hero-cta">
        <a href="#contact" class="btn">Plan een sessie</a>
        <a href="#adem" class="btn ghost">Probeer een ademoefening</a>
      </div>
    </div>
    <div class="orb-wrap" aria-hidden="true">
      <div class="orb o1"></div><div class="orb o2"></div><div class="orb o3"></div>
      <span class="orb-caption">in … en uit</span>
    </div>
  </div>
  <div class="scroll-hint" aria-hidden="true">Scroll</div>
</section>

<!-- OVER -->
<section id="over" class="about">
  <div class="wrap about-grid">
    <div class="portrait reveal" role="img" aria-label="Portret van Jamila Mokhtari">
      <!-- Vervang onderstaande regel door je eigen foto: <img src="/assets/jamila.jpg" alt="Jamila Mokhtari"> -->
      <span>J</span>
    </div>
    <div class="reveal">
      <span class="eyebrow">Over Jamila</span>
      <h2>Je adem is de brug tussen lichaam en geest</h2>
      <p>Ik ben Jamila Mokhtari, breathing coach. Ik begeleid mensen die toe zijn aan meer ruimte, rust en verbinding, in een tijd waarin alles snel gaat en stilte zeldzaam is geworden.</p>
      <p>In mijn sessies combineer ik bewuste ademhaling, meditatie en ontspanning. Geen vaste regels of prestatiedruk: jij bepaalt het tempo en ik houd de ruimte. Zo kun je spanning loslaten en weer contact maken met wat er in jou leeft.</p>
      <div class="values">
        <span class="chip">Aandacht</span><span class="chip">Veiligheid</span><span class="chip">Verbinding</span><span class="chip">Vertrouwen</span>
      </div>
    </div>
  </div>
</section>

<!-- SESSIES -->
<section id="sessies" class="offer">
  <div class="wrap">
    <div class="center reveal">
      <span class="eyebrow">Aanbod</span>
      <h2>Kies de sessie die bij je past</h2>
      <p class="lead">Elke sessie begint met aankomen en eindigt met rust. Alles in jouw tempo.</p>
    </div>
    <div class="cards">
      <article class="card reveal">
        <div class="ico"><svg viewBox="0 0 24 24"><circle cx="12" cy="8" r="3.5"/><path d="M5 20c0-3.9 3.1-7 7-7s7 3.1 7 7"/></svg></div>
        <h3>Individuele sessie</h3>
        <p>Een persoonlijke ademreis, afgestemd op jouw vraag: stress, onrust, slaap of gewoon even terug naar jezelf. Met ruimte voor gesprek en nazorg.</p>
        <div class="meta"><span>1 op 1</span><span>Op afspraak</span></div>
        <a href="#contact" class="btn ghost small" data-pick="Individuele sessie">Aanvragen</a>
      </article>
      <article class="card reveal">
        <div class="ico"><svg viewBox="0 0 24 24"><circle cx="8" cy="9" r="2.8"/><circle cx="16.5" cy="9" r="2.8"/><path d="M2.5 19c0-3 2.5-5.3 5.5-5.3M21.5 19c0-3-2.5-5.3-5.5-5.3M8 19c0-2.6 1.8-4.6 4-4.6s4 2 4 4.6"/></svg></div>
        <h3>Groepssessie</h3>
        <p>Samen ademen, samen stil zijn. Een warme, begeleide groepssessie met meditatie en een lange eindontspanning. Geen voorkennis nodig.</p>
        <div class="meta"><span>Kleine groep</span><span>Zie agenda</span></div>
        <a href="#agenda" class="btn ghost small">Bekijk agenda</a>
      </article>
      <article class="card reveal">
        <div class="ico"><svg viewBox="0 0 24 24"><path d="M3 20h18M5 20V9l7-5 7 5v11M9 20v-6h6v6"/></svg></div>
        <h3>Workshop &amp; teams</h3>
        <p>Een rustpunt voor teams, scholen of organisaties. Praktische ademtechnieken voor focus en herstel, op locatie of online.</p>
        <div class="meta"><span>Op maat</span><span>Op aanvraag</span></div>
        <a href="#contact" class="btn ghost small" data-pick="Workshop / team">Vraag een voorstel</a>
      </article>
    </div>
  </div>
</section>

<!-- ADEM MEE -->
<section id="adem" class="tool">
  <div class="wrap">
    <div class="center reveal">
      <span class="eyebrow">Adem mee</span>
      <h2>Neem nu even een moment voor jezelf</h2>
      <p class="lead">Kies een ritme, ga comfortabel zitten en volg de cirkel. Laat hem groeien met je inademing en zachtjes krimpen met je uitademing.</p>
    </div>
    <div class="tool-grid">
      <div class="stage" aria-live="polite">
        <div class="ring"></div><div class="ring r2"></div>
        <div class="breath" id="breath"></div>
        <div class="stage-text">
          <div class="phase" id="phase">Klaar?</div>
          <div class="count" id="count">druk op start</div>
        </div>
      </div>
      <div class="controls">
        <div class="field">
          <label>Ademritme</label>
          <div class="seg" id="patterns" role="group" aria-label="Ademritme">
            <button type="button" data-p="rust" aria-pressed="true">Diepe rust</button>
            <button type="button" data-p="coherent" aria-pressed="false">Coherent</button>
            <button type="button" data-p="box" aria-pressed="false">Box</button>
            <button type="button" data-p="478" aria-pressed="false">4-7-8</button>
          </div>
          <p class="pattern-desc" id="pdesc"></p>
        </div>
        <div class="field">
          <label>Duur</label>
          <div class="seg" id="durations" role="group" aria-label="Duur">
            <button type="button" data-d="1" aria-pressed="false">1 min</button>
            <button type="button" data-d="3" aria-pressed="true">3 min</button>
            <button type="button" data-d="5" aria-pressed="false">5 min</button>
            <button type="button" data-d="10" aria-pressed="false">10 min</button>
          </div>
        </div>
        <div>
          <div class="progress"><i id="bar"></i></div>
          <div class="timer-line"><span id="elapsed">0:00</span><span id="total">3:00</span></div>
        </div>
        <div class="done-msg" id="done"></div>
        <div><button type="button" class="btn" id="go">Start</button></div>
        <p class="note">Adem door je neus en blijf ontspannen. Voel je je duizelig of onprettig? Stop dan en adem weer normaal. Niet geschikt tijdens autorijden of in het water.</p>
      </div>
    </div>
  </div>
</section>

<!-- VERLOOP -->
<section id="verloop">
  <div class="wrap">
    <div class="center reveal">
      <span class="eyebrow">Hoe een sessie verloopt</span>
      <h2>Een zachte reis in drie stappen</h2>
    </div>
    <div class="steps">
      <div class="step reveal"><h3>Aankomen</h3><p>We starten met een korte check-in. Je legt neer wat je meebrengt en we stemmen af wat je nodig hebt.</p></div>
      <div class="step reveal"><h3>Ademen</h3><p>Onder begeleiding verdiep je je adem. Met ruimte, ritme en muziek of stilte, helemaal in jouw tempo.</p></div>
      <div class="step reveal"><h3>Integreren</h3><p>Een lange ontspanning en meditatie, gevolgd door een rustig nagesprek en tips om thuis mee verder te gaan.</p></div>
    </div>
  </div>
</section>

<!-- VOORDELEN -->
<section class="benefits">
  <div class="wrap">
    <div class="center reveal">
      <span class="eyebrow">Wat het je kan brengen</span>
      <h2>Meer rust, meer ruimte</h2>
      <p class="lead">Bewuste ademhaling wordt door veel mensen ervaren als een eenvoudige manier om te ontspannen.</p>
    </div>
    <div class="ben-grid">
      <div class="ben reveal">Ontspanning<small>Minder spanning in lichaam en geest</small></div>
      <div class="ben reveal">Helderheid<small>Meer focus en overzicht</small></div>
      <div class="ben reveal">Veerkracht<small>Beter omgaan met drukte en stress</small></div>
      <div class="ben reveal">Verbinding<small>Contact met jezelf en je gevoel</small></div>
    </div>
  </div>
</section>

<!-- AGENDA -->
<section id="agenda">
  <div class="wrap">
    <div class="center reveal">
      <span class="eyebrow">Agenda</span>
      <h2>Aankomende sessies</h2>
      <p class="lead">Plekken zijn beperkt, zodat er ruimte is voor iedereen.</p>
    </div>
    <div class="sched" id="sched"></div>
  </div>
</section>

<!-- FAQ -->
<section id="faq" style="background:rgba(239,231,220,.6)">
  <div class="wrap">
    <div class="center reveal">
      <span class="eyebrow">Veelgestelde vragen</span>
      <h2>Goed om te weten</h2>
    </div>
    <div class="faq reveal">
      <details><summary>Heb ik ervaring nodig?</summary><p>Nee. Iedereen is welkom, ook als je nog nooit eerder aan ademwerk of meditatie hebt gedaan. Ik leg alles rustig uit en je mag altijd je eigen tempo volgen.</p></details>
      <details><summary>Wat moet ik meenemen?</summary><p>Draag comfortabele kleding en neem eventueel een deken en een kussen mee. Water en een matje zijn aanwezig of worden vooraf met je afgestemd.</p></details>
      <details><summary>Voor wie is ademwerk niet geschikt?</summary><p>Ademwerk kan intens zijn. Neem vooraf contact op als je zwanger bent, epilepsie hebt, hart- of vaatproblemen, hoge bloeddruk, een psychische kwetsbaarheid of andere medische klachten. Overleg bij twijfel met je huisarts. Ademwerk vervangt geen medische of psychologische behandeling.</p></details>
      <details><summary>Is het ook online mogelijk?</summary><p>Ja, individuele sessies en workshops kunnen ook online plaatsvinden. Je hebt alleen een rustige plek en een stabiele verbinding nodig.</p></details>
      <details><summary>Wat als ik moet annuleren?</summary><p>Laat het me zo vroeg mogelijk weten, dan kijken we samen naar een nieuwe afspraak. De exacte voorwaarden bespreek ik graag bij het boeken.</p></details>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" class="contact">
  <div class="wrap contact-grid">
    <div class="contact-info reveal">
      <span class="eyebrow">Contact</span>
      <h2>Laten we kennismaken</h2>
      <p>Heb je een vraag of wil je een sessie plannen? Laat een bericht achter en ik reageer zo snel mogelijk, meestal binnen twee werkdagen.</p>
      <ul>
        <li>✉ <span id="mailShow"></span></li>
        <li>☾ Op locatie of online</li>
      </ul>
    </div>
    <form id="form" class="reveal" novalidate>
      <div class="row">
        <div><label for="f-name">Naam</label><input id="f-name" name="name" required autocomplete="name"></div>
        <div><label for="f-mail">E-mail</label><input id="f-mail" name="email" type="email" required autocomplete="email"></div>
      </div>
      <div>
        <label for="f-type">Ik ben geïnteresseerd in</label>
        <select id="f-type" name="type">
          <option>Individuele sessie</option>
          <option>Groepssessie</option>
          <option>Workshop / team</option>
          <option>Eerst een kennismakingsgesprek</option>
        </select>
      </div>
      <div><label for="f-msg">Bericht</label><textarea id="f-msg" name="msg" placeholder="Vertel kort wat je zoekt of waar je naar uitkijkt…"></textarea></div>
      <label class="check"><input type="checkbox" id="f-ok" required> Ik geef toestemming dat Jamila mijn gegevens gebruikt om contact met me op te nemen.</label>
      <button class="btn" type="submit">Verstuur bericht</button>
      <div class="form-msg" id="formMsg" role="status"></div>
    </form>
  </div>
</section>

</main>

<footer>
  <div class="wrap">
    <a href="#top" class="brand">Jamila Mokhtari</a>
    <div class="quote">“Adem in rust, adem uit wat niet meer dient.”</div>
    <p>Breathing coach · Breathwork &amp; meditatie</p>
    <small>Ademwerk en meditatie zijn ondersteunend en vervangen geen medische of psychologische zorg. Raadpleeg bij gezondheidsklachten altijd je huisarts of behandelaar.</small>
    <small>© <span id="yr"></span> Jamila Mokhtari. Alle rechten voorbehouden.</small>
  </div>
</footer>

<script>
(function(){
  "use strict";

  /* ===== INSTELLINGEN: pas deze aan ===== */
  var CONFIG = {
    email: "info@jouwdomein.nl",   // e-mailadres waar het contactformulier naartoe gaat
    sessions: [                    // agenda: voeg toe, verwijder of pas aan
      { day: "06", month: "Dec", title: "Groepssessie: Rust & Reset", info: "Zaterdag · 10:00 – 11:30 · Locatie volgt" },
      { day: "13", month: "Dec", title: "Meditatie & Ademwerk", info: "Zaterdag · 10:00 – 11:30 · Online" },
      { day: "20", month: "Dec", title: "Winterstilte: lange ademreis", info: "Zaterdag · 19:30 – 21:30 · Locatie volgt" }
    ]
  };
  /* ======================================= */

  var $ = function(s,c){return (c||document).querySelector(s)};
  var $$ = function(s,c){return Array.prototype.slice.call((c||document).querySelectorAll(s))};

  $("#yr").textContent = new Date().getFullYear();
  $("#mailShow").textContent = CONFIG.email;

  /* ===== achtergrond: ademende flow (golven + ringen) ===== */
  (function(){
    var cv = $("#flow"), cx = cv && cv.getContext("2d");
    if(!cx) return;
    var W = 0, H = 0, dpr = 1;
    var reduce = window.matchMedia && window.matchMedia("(prefers-reduced-motion: reduce)").matches;
    var CYCLE = 10; /* seconden per ademhaling: 4 in, 6 uit */

    function size(){
      dpr = Math.min(window.devicePixelRatio || 1, 2);
      W = window.innerWidth; H = window.innerHeight;
      cv.width = W*dpr; cv.height = H*dpr;
      cx.setTransform(dpr,0,0,dpr,0,0);
      if(reduce) draw(3000);
    }
    function breath(t){
      var ph = (t % CYCLE)/CYCLE;
      var x = ph < .4 ? ph/.4 : 1 - (ph-.4)/.6;
      return .5 - Math.cos(Math.PI*x)/2;
    }
    function draw(ms){
      var t = ms/1000, b = breath(t), sy = window.scrollY || 0;
      cx.clearRect(0,0,W,H);

      /* 1. concentrische ringen: ademen mee, in het midden */
      var ox = W*.5, oy = H*.48 - sy*.04, base = Math.min(W,H)*.085, i, r, a;
      for(i = 1; i <= 8; i++){
        r = base*i*(.82 + .3*b) + i*i*1.2;
        a = .13 - i*.011;
        cx.beginPath();
        cx.arc(ox, oy, r, 0, Math.PI*2);
        cx.strokeStyle = (i % 3 === 0) ? "rgba(184,147,90,"+(a+.03)+")" : "rgba(143,165,149,"+(a+.05)+")";
        cx.lineWidth = 1;
        cx.stroke();
      }
      /* stippen die langzaam rond de ringen draaien */
      for(i = 0; i < 24; i++){
        var ang = i/24*Math.PI*2 + t*.04;
        var rr = base*5*(.82 + .3*b) + 25;
        cx.beginPath();
        cx.arc(ox + Math.cos(ang)*rr, oy + Math.sin(ang)*rr, 1.6 + b*1.2, 0, Math.PI*2);
        cx.fillStyle = "rgba(184,147,90,.28)";
        cx.fill();
      }

      /* 2. stromende golflijnen: golven worden groter bij inademing */
      var lines = 11, amp = 12 + 30*b, k, x, y, yb;
      for(k = 0; k < lines; k++){
        yb = H*(.12 + k*.078);
        cx.beginPath();
        for(x = -10; x <= W + 10; x += 10){
          y = yb
            + Math.sin(x*.0038 + t*.28 + k*.55)*amp*(1 + k*.04)
            + Math.sin(x*.0091 - t*.19 + k*1.3)*amp*.42;
          if(x === -10) cx.moveTo(x,y); else cx.lineTo(x,y);
        }
        cx.strokeStyle = (k % 2) ? "rgba(143,165,149,.2)" : "rgba(184,147,90,.15)";
        cx.lineWidth = 1;
        cx.stroke();
      }
    }
    var run = true;
    function loop(ms){ if(run) draw(ms); requestAnimationFrame(loop); }
    document.addEventListener("visibilitychange", function(){ run = !document.hidden; });
    window.addEventListener("resize", size);
    size();
    if(!reduce) requestAnimationFrame(loop);
  })();

  /* header + menu */
  var header = $("#top-bar");
  function onScroll(){ header.classList.toggle("scrolled", window.scrollY > 40); }
  window.addEventListener("scroll", onScroll, {passive:true}); onScroll();
  var burger = $(".burger"), menu = $("#menu");
  burger.addEventListener("click", function(){
    var open = menu.classList.toggle("open");
    burger.setAttribute("aria-expanded", open);
  });
  $$("#menu a").forEach(function(a){ a.addEventListener("click", function(){
    menu.classList.remove("open"); burger.setAttribute("aria-expanded","false");
  });});

  /* reveal on scroll */
  var rev = $$(".reveal");
  if("IntersectionObserver" in window){
    var io = new IntersectionObserver(function(es){
      es.forEach(function(e){ if(e.isIntersecting){ e.target.classList.add("in"); io.unobserve(e.target);} });
    },{threshold:.12});
    rev.forEach(function(r){io.observe(r)});
  } else { rev.forEach(function(r){r.classList.add("in")}); }

  /* agenda */
  var sched = $("#sched");
  CONFIG.sessions.forEach(function(s){
    var d = document.createElement("div");
    d.className = "slot reveal in";
    d.innerHTML = '<div class="date"><b></b><span></span></div><div><h3></h3><p></p></div><a href="#contact" class="btn ghost small">Reserveer</a>';
    $("b",d).textContent = s.day; $(".date span",d).textContent = s.month;
    $("h3",d).textContent = s.title; $("p",d).textContent = s.info;
    $("a",d).addEventListener("click", function(){ $("#f-type").value = "Groepssessie"; $("#f-msg").value = "Ik wil graag een plek reserveren voor: " + s.title + " (" + s.day + " " + s.month + ")."; });
    sched.appendChild(d);
  });

  /* card -> form prefill */
  $$("[data-pick]").forEach(function(b){
    b.addEventListener("click", function(){ $("#f-type").value = b.getAttribute("data-pick"); });
  });

  /* ===== breathing tool ===== */
  var PATTERNS = {
    rust:     { desc:"Rustig en verlengd: 4 tellen in, 6 tellen uit. Activeert ontspanning, fijn bij onrust of voor het slapen.", steps:[["in",4],["out",6]] },
    coherent: { desc:"Gelijkmatig en kalm: 5 tellen in, 5 tellen uit. Een zacht ritme voor balans en focus.", steps:[["in",5],["out",5]] },
    box:      { desc:"Box breathing: 4 in, 4 vast, 4 uit, 4 vast. Geeft structuur en helderheid in een drukke dag.", steps:[["in",4],["holdFull",4],["out",4],["holdEmpty",4]] },
    "478":    { desc:"4 in, 7 vast, 8 uit. Een diep ontspannend ritme. Houd de vasthoud-fase zacht, forceer niets.", steps:[["in",4],["holdFull",7],["out",8]] }
  };
  var LABEL = { "in":"Adem in", holdFull:"Houd vast", out:"Adem uit", holdEmpty:"Rust" };
  var MIN = .55, MAX = 1;

  var curP = "rust", curD = 3, running = false;
  var raf = 0, t0 = 0, phaseIdx = 0, phaseStart = 0, curScale = MIN;
  var el = { b:$("#breath"), ph:$("#phase"), ct:$("#count"), go:$("#go"), bar:$("#bar"), el:$("#elapsed"), tot:$("#total"), done:$("#done"), desc:$("#pdesc") };

  function fmt(s){ s=Math.max(0,Math.round(s)); return Math.floor(s/60)+":"+("0"+(s%60)).slice(-2); }
  function ease(x){ return .5 - Math.cos(Math.PI*x)/2; }
  function setScale(v){ curScale = v; el.b.style.transform = "scale("+v.toFixed(4)+")"; }
  function setDesc(){ el.desc.textContent = PATTERNS[curP].desc; }
  function setTotal(){ el.tot.textContent = fmt(curD*60); }
  setDesc(); setTotal(); setScale(MIN);

  function group(containerSel, attr, cb){
    var wrap = $(containerSel);
    $$("button", wrap).forEach(function(btn){
      btn.addEventListener("click", function(){
        $$("button", wrap).forEach(function(x){ x.setAttribute("aria-pressed","false"); });
        btn.setAttribute("aria-pressed","true");
        cb(btn.getAttribute(attr));
      });
    });
  }
  group("#patterns","data-p", function(v){ curP = v; setDesc(); if(running) stop(false); });
  group("#durations","data-d", function(v){ curD = +v; setTotal(); if(running) stop(false); });

  function stop(finished){
    running = false; cancelAnimationFrame(raf);
    el.go.textContent = "Start";
    el.bar.style.width = "0";
    el.el.textContent = "0:00";
    if(finished){
      el.ph.textContent = "Dank je wel";
      el.ct.textContent = "blijf nog even stil zitten";
      el.done.textContent = "Neem een moment om te voelen hoe je nu bent.";
    } else {
      el.ph.textContent = "Klaar?"; el.ct.textContent = "druk op start";
    }
    var from = curScale, s0 = performance.now();
    (function back(ts){
      var p = Math.min(1,(ts-s0)/1200);
      setScale(from + (MIN-from)*ease(p));
      if(p<1 && !running) requestAnimationFrame(back);
    })(s0);
  }

  function tick(ts){
    if(!running) return;
    var steps = PATTERNS[curP].steps, total = curD*60;
    var elapsed = (ts - t0)/1000;
    if(elapsed >= total){ stop(true); return; }

    var step = steps[phaseIdx], type = step[0], dur = step[1];
    var pe = (ts - phaseStart)/1000;
    if(pe >= dur){
      phaseIdx = (phaseIdx+1) % steps.length;
      phaseStart = ts; pe = 0;
      step = steps[phaseIdx]; type = step[0]; dur = step[1];
    }
    var p = Math.min(1, pe/dur), s;
    if(type==="in") s = MIN + (MAX-MIN)*ease(p);
    else if(type==="out") s = MAX - (MAX-MIN)*ease(p);
    else if(type==="holdFull") s = MAX;
    else s = MIN;
    setScale(s);

    el.ph.textContent = LABEL[type];
    el.ct.textContent = Math.max(1, Math.ceil(dur - pe));
    el.bar.style.width = (elapsed/total*100).toFixed(2)+"%";
    el.el.textContent = fmt(elapsed);
    raf = requestAnimationFrame(tick);
  }

  el.go.addEventListener("click", function(){
    if(running){ stop(false); return; }
    running = true; el.done.textContent = "";
    el.go.textContent = "Stop";
    phaseIdx = 0;
    var now = performance.now();
    t0 = now; phaseStart = now;
    // start from the current scale smoothly: first phase is inhale or begins at MIN
    raf = requestAnimationFrame(tick);
  });
  document.addEventListener("visibilitychange", function(){ if(document.hidden && running) stop(false); });

  /* ===== form: opent e-mailprogramma ===== */
  $("#form").addEventListener("submit", function(e){
    e.preventDefault();
    var n = $("#f-name").value.trim(), m = $("#f-mail").value.trim(), msg = $("#formMsg");
    if(!n || !/^\S+@\S+\.\S+$/.test(m)){ msg.textContent = "Vul je naam en een geldig e-mailadres in."; return; }
    if(!$("#f-ok").checked){ msg.textContent = "Geef eerst toestemming om contact op te nemen."; return; }
    var body = "Naam: "+n+"\nE-mail: "+m+"\nInteresse: "+$("#f-type").value+"\n\n"+$("#f-msg").value;
    window.location.href = "mailto:"+CONFIG.email+"?subject="+encodeURIComponent("Aanvraag: "+$("#f-type").value)+"&body="+encodeURIComponent(body);
    msg.textContent = "Dank je wel, " + n + ". Je e-mailprogramma opent nu met je bericht.";
  });
})();
</script>
</body>
</html>
