---
layout: html-only
title: Party
icon: fa-solid fa-cake-candles
permalink: /party/
order: 1
---

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title></title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@400;700;900&family=Manrope:wght@300;400;600&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root{
    --void:#07080a;
    --void-2:#0d0f12;
    --chrome-1:#f2f4f6;
    --chrome-2:#b9c0c7;
    --chrome-3:#71787f;
    --chrome-4:#26292d;
    --ice:#9fe8ff;
    --ice-dim:rgba(159,232,255,0.35);
    --line:rgba(255,255,255,0.14);
    --fs-display:clamp(3.2rem, 13vw, 9.5rem);
    --fs-h2:clamp(1.4rem, 4vw, 2rem);
    --fs-body:clamp(0.95rem, 2vw, 1.05rem);
    --fs-mono:clamp(0.68rem, 1.6vw, 0.78rem);
  }

  *{box-sizing:border-box; margin:0; padding:0;}
  html{background:var(--void);}
  body{
    background:var(--void);
    color:var(--chrome-1);
    font-family:'Manrope', sans-serif;
    font-weight:300;
    overflow-y:auto;
    overflow-x:hidden;
    min-height:100vh;
    cursor:crosshair;
  }

  ::selection{ background:var(--ice); color:var(--void); }
  a{ color:inherit; }
  button{ font-family:inherit; border:none; background:none; color:inherit; cursor:pointer; }
  :focus-visible{ outline:2px solid var(--ice); outline-offset:4px; }

  .grain{
    position:fixed; inset:0; z-index:60; pointer-events:none;
    opacity:0.05; mix-blend-mode:overlay;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  }

  .scanlines{
    position:fixed; inset:0; z-index:59; pointer-events:none; opacity:0.06;
    background:repeating-linear-gradient(0deg, #fff 0px, transparent 1px, transparent 3px);
  }

  .blob-wrap{ position:fixed; inset:0; z-index:1; pointer-events:none; overflow:hidden; }
  .ferro-goo{ position:absolute; inset:0; filter:url(#gooMerge); }
  .ferro-blob{
    position:absolute; top:0; left:0; border-radius:50%;
    background:radial-gradient(circle at 34% 26%, #7a7d82 0%, #2c2e32 20%, #131417 42%, #050506 68%, #000 100%);
    will-change:transform; transform:translate3d(-50%,-50%,0);
  }


  #ferro-1{ width:min(46vw,340px); height:min(46vw,340px); }
  #ferro-2{ width:min(30vw,220px); height:min(30vw,220px); }
  #ferro-3{ width:min(22vw,160px); height:min(22vw,160px); }
  #ferro-4{ width:min(16vw,120px); height:min(16vw,120px); }

  .ferro-oil{ position:absolute; inset:0; filter:url(#liquidFilter); }
  .ferro-highlight{
    position:absolute; top:0; left:0;
    width:min(14vw,110px); height:min(14vw,110px); border-radius:50%;
    background:radial-gradient(circle, rgba(255,255,255,0.9) 0%, var(--ice) 30%, transparent 72%);
    filter:blur(10px); mix-blend-mode:screen; opacity:0.55;
    will-change:transform; transform:translate3d(-50%,-50%,0);
  }

  .chrome-text{
    background:linear-gradient(112deg, var(--chrome-3) 0%, var(--chrome-1) 14%, var(--chrome-2) 26%, #ffffff 38%, var(--chrome-4) 50%, var(--chrome-2) 64%, var(--chrome-1) 78%, var(--chrome-3) 100%);
    background-size:280% 280%;
    -webkit-background-clip:text; background-clip:text; color:transparent;
    animation:chromeShift 9s ease-in-out infinite;
  }

  @keyframes chromeShift{
    0%{ background-position:0% 50%; }
    50%{ background-position:100% 50%; }
    100%{ background-position:0% 50%; }
  }

  .mono{
    font-family:'Space Mono', monospace;
    letter-spacing:0.22em;
    text-transform:uppercase;
    font-size:var(--fs-mono);
    color:var(--chrome-2);
  }

  #gate{
    position:relative;
    z-index:10;
    min-height:100vh;
    display:flex; flex-direction:column; align-items:center; justify-content:center; gap:2.2rem;
    background:var(--void);
    padding:2rem 0;
  }

  .gate-mark{
    font-family:'Unbounded', sans-serif;
    font-weight:900;
    font-size:clamp(2.2rem, 9vw, 4.2rem);
    letter-spacing:0.02em;
    filter:url(#liquidFilterSoft);
  }

  .enter-btn{
    position:relative;
    padding:1.05em 2.6em;
    border:1px solid var(--line);
    border-radius:999px;
    font-family:'Space Mono', monospace;
    letter-spacing:0.3em;
    font-size:0.78rem;
    text-transform:uppercase;
    color:var(--void);
    background:linear-gradient(120deg,var(--chrome-2),var(--chrome-1) 40%,var(--chrome-3) 70%,var(--chrome-1));
    background-size:220% 220%;
    animation:chromeShift 6s ease-in-out infinite;
    transition:transform 0.35s ease, box-shadow 0.35s ease;
    box-shadow:0 0 0 rgba(159,232,255,0);
    cursor:pointer;
  }

  .enter-btn:hover{ transform:scale(1.06); box-shadow:0 0 42px var(--ice-dim); }
  .enter-btn:active{
    transform:scale(0.97);
    box-shadow:0 0 0 0 rgba(168, 85, 247, 0.9);
    animation:purpleMetallicGlow 0.8s ease-out;
  }

  @keyframes purpleMetallicGlow{
    0%{ box-shadow:0 0 20px 0 rgba(168, 85, 247, 1), inset 0 0 20px rgba(200, 150, 255, 0.6); text-shadow:0 0 10px rgba(168, 85, 247, 0.8); }
    50%{ box-shadow:0 0 40px 10px rgba(168, 85, 247, 0.6), inset 0 0 10px rgba(200, 150, 255, 0.3); }
    100%{ box-shadow:0 0 0 20px rgba(168, 85, 247, 0), inset 0 0 0 rgba(200, 150, 255, 0); }
  }

  .gate-hint{ color:var(--chrome-3); font-size:0.72rem; }

  #stage{ position:relative; z-index:10; padding-top:2rem; }
  .wrap{ max-width:960px; margin:0 auto; padding:0 6vw; }

  header.hero{
    min-height:100svh;
    display:flex; flex-direction:column; align-items:center; justify-content:center;
    text-align:center; gap:1.6rem;
    position:relative;
  }

  .eyebrow{ display:flex; align-items:center; gap:0.8em; color:var(--ice); }
  .eyebrow::before, .eyebrow::after{ content:""; width:2.4em; height:1px; background:var(--ice-dim); }

  h1.name{
    font-family:'Unbounded', sans-serif;
    font-weight:900;
    font-size:var(--fs-display);
    line-height:0.92;
    letter-spacing:-0.01em;
    text-transform:uppercase;
    filter:url(#liquidFilterSoft);
  }

  h1.name .turns{
    display:block;
    font-size:0.34em;
    font-weight:700;
    letter-spacing:0.08em;
    margin-top:0.5em;
    -webkit-text-stroke:1px var(--chrome-2);
    color:transparent;
  }

  .tagline{
    max-width:34ch;
    font-size:var(--fs-body);
    color:var(--chrome-2);
    font-weight:300;
    line-height:1.6;
  }

  .scroll-cue{
    position:absolute; bottom:2.4rem; left:50%; transform:translateX(-50%);
    width:1px; height:52px;
    background:linear-gradient(var(--ice), transparent);
    animation:scrollPulse 2.4s ease-in-out infinite;
  }

  @keyframes scrollPulse{ 0%,100%{ opacity:0.15; } 50%{ opacity:0.85; } }

  section.details{ padding:8rem 0 7rem; }
  .divider{ height:1px; background:linear-gradient(90deg, transparent, var(--line) 20%, var(--line) 80%, transparent); margin-bottom:5rem; }

  .details-grid{
    display:flex;
    flex-wrap:wrap;
    justify-content:center;
    gap:3.4rem 5rem;
    text-align:center;
  }

  .detail-cell{
    display:flex; flex-direction:column; gap:1rem;
    align-items:center;
    flex:1 1 240px;
    max-width:320px;
  }

  .detail-cell .label{ color:var(--ice); }
  .detail-cell .value{
    font-family:'Unbounded', sans-serif;
    font-weight:700;
    font-size:clamp(1.3rem, 3.6vw, 1.9rem);
    text-transform:uppercase;
    line-height:1.15;
    filter:url(#liquidFilterSoft);
  }

  .detail-cell .sub{ color:var(--chrome-3); font-size:0.85rem; font-weight:300; }

  section.rsvp{
    padding:4rem 0 9rem;
    text-align:center;
    display:flex; flex-direction:column; align-items:center; gap:1.8rem;
  }

  .rsvp h2{
    font-family:'Unbounded', sans-serif; font-weight:700;
    font-size:var(--fs-h2); text-transform:uppercase; letter-spacing:0.01em;
  }

  .rsvp p{ color:var(--chrome-2); max-width:38ch; font-size:var(--fs-body); line-height:1.6; }

  .rsvp-btn{
    margin-top:0.6rem;
    padding:1.1em 2.8em;
    border-radius:999px;
    border:1px solid var(--chrome-2);
    font-family:'Space Mono', monospace;
    letter-spacing:0.28em; font-size:0.78rem; text-transform:uppercase;
    position:relative; overflow:hidden;
    transition:letter-spacing 0.4s ease, border-color 0.4s ease, color 0.4s ease;
    cursor:pointer;
  }

  .rsvp-btn:hover{ letter-spacing:0.38em; border-color:var(--ice); color:var(--ice); }

  footer{
    padding:3rem 0 4rem; text-align:center;
    color:var(--chrome-4); font-family:'Space Mono', monospace;
    font-size:0.7rem; letter-spacing:0.18em; text-transform:uppercase;
  }

  footer span{ color:var(--chrome-3); }

  #audioToggle{
    position:fixed; bottom:1.4rem; right:1.4rem; z-index:55;
    display:flex; align-items:center; gap:0.6em;
    padding:0.7em 1.1em;
    border:1px solid var(--line);
    border-radius:999px;
    background:rgba(13,15,18,0.7);
    backdrop-filter:blur(6px);
    font-family:'Space Mono', monospace;
    font-size:0.66rem; letter-spacing:0.18em; text-transform:uppercase;
    color:var(--chrome-2);
    cursor:pointer;
  }

  #audioToggle .dot{ width:7px; height:7px; border-radius:50%; background:var(--chrome-4); transition:background 0.3s ease, box-shadow 0.3s ease; }
  #audioToggle.on .dot{ background:var(--ice); box-shadow:0 0 8px var(--ice); }
  .bars{ display:flex; align-items:flex-end; gap:2px; height:10px; }
  .bars i{ width:2px; background:var(--chrome-3); display:block; height:3px; transition:height 0.15s ease; }
  #audioToggle.on .bars i{ background:var(--ice); animation:barBounce 0.9s ease-in-out infinite; }
  #audioToggle.on .bars i:nth-child(2){ animation-delay:0.15s; }
  #audioToggle.on .bars i:nth-child(3){ animation-delay:0.3s; }

  @keyframes barBounce{ 0%,100%{ height:3px; } 50%{ height:10px; } }

  @keyframes floatUp{
    0%{ transform:translateY(0); opacity:1; }
    100%{ transform:translateY(-50px); opacity:0; }
  }

  .countdown-row{
    display:flex;
    gap:clamp(1.2rem, 4vw, 2.6rem);
    justify-content:center;
    margin-top:0.6rem;
  }

  .countdown-cell{
    display:flex;
    flex-direction:column;
    align-items:center;
    gap:0.5rem;
  }

  .countdown-cell .num{
    font-weight:700;
    font-size:clamp(1.5rem, 4.4vw, 2.3rem);
    font-variant-numeric:tabular-nums;
    letter-spacing:0.02em;
  }

  .countdown-cell .lbl{
    letter-spacing:0.22em;
    text-transform:uppercase;
    font-size:0.62rem;
    opacity:0.6;
  }

  #menuBtn{
    position:fixed; top:1.4rem; right:1.4rem; z-index:55;
    padding:0.7em 1.1em;
    border:1px solid var(--line);
    border-radius:999px;
    background:rgba(13,15,18,0.7);
    backdrop-filter:blur(6px);
    font-family:'Space Mono', monospace;
    font-size:0.66rem;
    letter-spacing:0.18em;
    text-transform:uppercase;
    color:var(--chrome-2);
    transition:border-color 0.3s ease, color 0.3s ease;
    text-decoration:none;
  }

  #menuBtn:hover{ border-color:var(--ice); color:var(--ice); }

  #audioToggle {
    display:flex;
    align-items:center;
    gap:0.8em;
  }

  .audio-control {
    width:24px;
    height:24px;
    display:flex;
    align-items:center;
    justify-content:center;
    cursor:pointer;
    transition:transform 0.2s ease;
  }

  .audio-control:hover {
    transform:scale(1.2);
  }

  @media (max-width:768px){
    :root{
      --fs-display:clamp(2.2rem, 10vw, 4rem);
      --fs-h2:clamp(1.1rem, 3vw, 1.4rem);
      --fs-body:clamp(0.9rem, 1.8vw, 1rem);
      --fs-mono:clamp(0.6rem, 1.4vw, 0.7rem);
    }
    
    body{ cursor:auto; }
    .wrap{ padding:0 4vw; }
    
    header.hero{ gap:1.2rem; }
    h1.name .turns{ font-size:0.3em; margin-top:0.4em; }
    
    .details-grid{ gap:2rem 3rem; }
    .detail-cell{ flex:1 1 180px; max-width:250px; }
    
    section.rsvp{ padding:3rem 0 6rem; gap:1.2rem; }
    
    .rsvp-btn{ padding:0.9em 2.2em; font-size:0.7rem; letter-spacing:0.25em; }
    .rsvp-btn:hover{ letter-spacing:0.32em; }
    
    #audioToggle{ bottom:1rem; right:1rem; padding:0.6em 0.9em; font-size:0.6rem; }
    #menuBtn{ top:1rem; right:1rem; padding:0.6em 0.9em; font-size:0.6rem; }
    
    .enter-btn{ padding:0.95em 2.2em; font-size:0.72rem; }
  }

  @media (prefers-reduced-motion: reduce){
    .chrome-text, .enter-btn, .scroll-cue{ animation:none !important; }
  }
</style>
</head>
<body>

<svg width="0" height="0" style="position:absolute">
  <filter id="liquidFilter" x="-40%" y="-40%" width="180%" height="180%">
    <feTurbulence type="fractalNoise" baseFrequency="0.010 0.018" numOctaves="2" seed="11" result="noise">
      <animate attributeName="baseFrequency" dur="22s" values="0.010 0.018;0.017 0.026;0.010 0.018" repeatCount="indefinite" />
    </feTurbulence>
    <feDisplacementMap in="SourceGraphic" in2="noise" scale="70" xChannelSelector="R" yChannelSelector="G" />
  </filter>
  <filter id="gooMerge" x="-60%" y="-60%" width="220%" height="220%">
    <feGaussianBlur in="SourceGraphic" stdDeviation="18" result="blur" />
    <feColorMatrix in="blur" type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 26 -11" result="goo" />
    <feTurbulence type="fractalNoise" baseFrequency="0.006 0.012" numOctaves="2" seed="9" result="oilNoise">
      <animate attributeName="baseFrequency" dur="30s" values="0.006 0.012;0.011 0.02;0.006 0.012" repeatCount="indefinite" />
    </feTurbulence>
    <feDisplacementMap in="goo" in2="oilNoise" scale="46" xChannelSelector="R" yChannelSelector="G" result="oiled" />
    <feComposite in="oiled" in2="oiled" operator="atop" />
  </filter>
  <filter id="liquidFilterSoft" x="-30%" y="-30%" width="160%" height="160%">
    <feTurbulence type="fractalNoise" baseFrequency="0.012 0.02" numOctaves="2" seed="4" result="n2" />
    <feDisplacementMap in="SourceGraphic" in2="n2" scale="8" xChannelSelector="R" yChannelSelector="G" />
  </filter>
</svg>

<div class="grain"></div>
<div class="scanlines"></div>
<div class="blob-wrap">
  <div class="ferro-oil">
    <div class="ferro-goo">
      <div class="ferro-blob" id="ferro-1"></div>
      <div class="ferro-blob" id="ferro-2"></div>
      <div class="ferro-blob" id="ferro-3"></div>
      <div class="ferro-blob" id="ferro-4"></div>
    </div>
  </div>
  <div class="ferro-highlight" id="ferroHighlight"></div>
</div>

<!-- GATE SECTION -->
<div id="gate">
  
  <div class="gate-mark chrome-text">Join the Party</div>
  <button class="enter-btn" id="enterBtn">Enter</button>
  <div class="gate-hint mono">Sound on · tap to begin</div>
  <div style="font-family:'Unbounded', sans-serif; font-weight:700; font-size:clamp(1rem, 3vw, 1.6rem); text-transform:uppercase; letter-spacing:0.08em; -webkit-text-stroke:1px var(--chrome-2); color:transparent; margin-top:2rem;">Hichmoki Bday 2026</div>
</div>

<!-- STAGE SECTION -->
<div id="stage">
  <header class="hero wrap">
    <div class="eyebrow mono" id="js-eyebrow">Hichmoki Birthday Party</div>
    <h1 class="name chrome-text">
      <span id="js-name">NAME</span>
      <span class="turns" id="js-turns"> AGE</span>
    </h1>
    <p class="tagline" id="js-tagline">A night dissolves into dance. Come lose your shape with us.</p>
    
    <div class="countdown-row" id="js-countdown" style="margin-top:2.4rem; gap:2rem;">
      <div class="countdown-cell">
        <div class="num chrome-text" id="cd-days">00</div>
        <div class="lbl mono">Days</div>
      </div>
      <div class="countdown-cell">
        <div class="num chrome-text" id="cd-hours">00</div>
        <div class="lbl mono">Hrs</div>
      </div>
      <div class="countdown-cell">
        <div class="num chrome-text" id="cd-mins">00</div>
        <div class="lbl mono">Min</div>
      </div>
      <div class="countdown-cell">
        <div class="num chrome-text" id="cd-secs">00</div>
        <div class="lbl mono">Sec</div>
      </div>
    </div>
    
    <div class="scroll-cue"></div>
  </header>

  <section class="details wrap">
    <div class="divider"></div>
    <div class="details-grid">
      <div class="detail-cell">
        <div class="label mono">Date</div>
        <div class="value chrome-text" id="js-date">DATE</div>
        <a id="js-calendar-link-detail" style="margin-top:0.8rem; font-family:'Space Mono', monospace; letter-spacing:0.18em; font-size:0.75rem; text-transform:uppercase; color:var(--ice); text-decoration:none; transition:opacity 0.3s ease;" href="#" target="_blank">[Add to Calendar]</a>
      </div>
      <div class="detail-cell">
        <div class="label mono">Time</div>
        <div class="value chrome-text" id="js-time">TIME</div>
      </div>
      <div class="detail-cell">
        <div class="label mono">Location</div>
        <div class="value chrome-text" id="js-location">LOCATION</div>
        <div class="sub" id="js-address"></div>
        <a href="https://maps.google.com/?q=Straatweg+60B,+3051+BH+Rotterdam" target="_blank" style="margin-top:0.8rem; font-family:'Space Mono', monospace; letter-spacing:0.18em; font-size:0.75rem; text-transform:uppercase; color:var(--ice); text-decoration:none; transition:opacity 0.3s ease;">[Open Location]</a>
      </div>
      <div class="detail-cell">
        <div class="label mono">Dress Code</div>
        <div class="value chrome-text" id="js-dress">CHROME / BLACK</div>
        <div class="sub" id="js-plusone" style="margin-top:0.6rem; color:var(--chrome-3); font-size:0.8rem;">+1 welcome — just let us know</div>
      </div>
    </div>
  </section>

  <section class="rsvp wrap">
    <h2 class="chrome-text">Are you in?</h2>
    <p id="js-rsvp-note">If you are attending, join the WhatsApp group.</p>
    <div style="display:flex; gap:1rem; justify-content:center; flex-wrap:wrap; margin-top:1.2rem;">
      <a class="rsvp-btn" id="js-rsvp-link" href="https://chat.whatsapp.com/CzWo9BidWbLGTedkoEgUsX" target="_blank">Join WhatsApp</a>
      <a class="rsvp-btn" id="js-calendar-link" href="#" target="_blank">Add to Calendar</a>
      <a class="rsvp-btn" href="https://open.spotify.com/playlist/6ptthqzOyKUF7rwsvEL8kp?si=5cdccd3d0d774a73" target="_blank"> Join Spotify</a>
    </div>
    <div style="display:flex; gap:1rem; justify-content:center; flex-wrap:wrap; margin-top:1.8rem;">
      <a href="https://wa.me/31681348625" target="_blank" style="color:var(--chrome-3); font-size:0.8rem; text-decoration:none; border:none; background:none; cursor:pointer; transition:color 0.3s ease; font-family:'Space Mono', monospace; letter-spacing:0.1em; border-bottom:1px solid var(--chrome-3); padding-bottom:0.3em;">[Can't make it? Let us know]</a>
    </div>
  </section>

  <section style="padding:6rem 0 4rem; text-align:center;">
    <div style="font-family:'Unbounded', sans-serif; font-weight:700; font-size:clamp(1.2rem, 3vw, 1.8rem); text-transform:uppercase; letter-spacing:0.05em; background:linear-gradient(112deg, #71787f 0%, #f2f4f6 14%, #b9c0c7 26%, #ffffff 38%, #26292d 50%, #b9c0c7 64%, #f2f4f6 78%, #71787f 100%); background-size:280% 280%; -webkit-background-clip:text; background-clip:text; color:transparent; animation:chromeShift 6s ease-in-out infinite; filter:url(#liquidFilterSoft);">Hichmoki Bday 2026</div>
  </section>

  <footer>
    <span id="js-footer-name">NAME</span> &nbsp;·&nbsp; <span id="js-footer-year"></span>
  </footer>
</div>

<audio id="bgAudio" preload="auto"></audio>

<a id="menuBtn" href="https://hichmok93.github.io/hg-site/">Menu</a>

<div id="floatingTrackName" style="position:fixed; bottom:6.5rem; right:1.4rem; z-index:54; opacity:0; pointer-events:none; font-family:'Space Mono', monospace; font-size:0.65rem; letter-spacing:0.08em; text-transform:uppercase; color:var(--chrome-3);"></div>

<div id="audioToggle">
  <div class="dot"></div>
  <div class="bars"><i></i><i></i><i></i></div>
  <span id="audioLabel">Sound</span>
  <div class="audio-control" id="skipBtn" title="Skip to next track">⏭</div>
</div>

<script>
const CONFIG = {
  name: "The Ceremony",
  age: "33",
  eventTag: "An Evening Unfolds",
  tagline: "Join the party - Good food, warm people, a night that moves. ",
  date: "18.09.2026",
  time: "20:00 — till late",
  location: "STRAATWEG 60B",
  address: "",
  dress: "QUEER FRIENDLY",
  plusOne: "+1 welcome — just let us know who's coming",

};

document.getElementById('js-eyebrow').textContent = CONFIG.eventTag;
document.getElementById('js-name').textContent = CONFIG.name;
document.getElementById('js-turns').textContent = CONFIG.age;
document.getElementById('js-tagline').textContent = CONFIG.tagline;
document.getElementById('js-date').textContent = CONFIG.date;
document.getElementById('js-time').textContent = CONFIG.time;
document.getElementById('js-location').textContent = CONFIG.location;
document.getElementById('js-address').textContent = CONFIG.address;
document.getElementById('js-dress').textContent = CONFIG.dress;
document.getElementById('js-footer-name').textContent = CONFIG.name;
document.getElementById('js-footer-year').textContent = new Date().getFullYear();

const calendarDate = '20260918T200000';
const calendarEndDate = '20260919T000000';
const calendarTitle = encodeURIComponent('Hichmoki\'s Party - The Ceremony 33');
const calendarLocation = encodeURIComponent('Straatweg 60B, 3051 BH Rotterdam');
const calendarDesc = encodeURIComponent('Join the party. Good food, warm people, a night that moves. WhatsApp: https://chat.whatsapp.com/CzWo9BidWbLGTedkoEgUsX');
const calendarUrl = `https://calendar.google.com/calendar/render?action=TEMPLATE&text=${calendarTitle}&dates=${calendarDate}/${calendarEndDate}&location=${calendarLocation}&details=${calendarDesc}`;
document.getElementById('js-calendar-link').href = calendarUrl;
if (document.getElementById('js-calendar-link-detail')) {
  document.getElementById('js-calendar-link-detail').href = calendarUrl;
}

const reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
const centerX = window.innerWidth / 2, centerY = window.innerHeight / 2;
let mx = centerX, my = centerY;
let ferroActive = false;
window.addEventListener('pointermove', (e) => { if (ferroActive) { mx = e.clientX; my = e.clientY; } });
window.addEventListener('touchmove', (e) => { if (ferroActive && e.touches[0]) { mx = e.touches[0].clientX; my = e.touches[0].clientY; } }, { passive: true });

const ferroEls = ['ferro-1','ferro-2','ferro-3','ferro-4'].map(id => document.getElementById(id));
const ferroState = [
  { x: centerX, y: centerY, vx: 0, vy: 0, k: 0.05,  d: 0.86, ox: 0,   oy: 0 },
  { x: centerX, y: centerY, vx: 0, vy: 0, k: 0.032, d: 0.82, ox: 60,  oy: -30 },
  { x: centerX, y: centerY, vx: 0, vy: 0, k: 0.024, d: 0.80, ox: -70, oy: 40 },
  { x: centerX, y: centerY, vx: 0, vy: 0, k: 0.02,  d: 0.78, ox: 20,  oy: 70 }
];
const highlight = document.getElementById('ferroHighlight');

function stepFerro(){
  ferroState.forEach((s,i) => {
    const ax = (mx + s.ox - s.x) * s.k;
    const ay = (my + s.oy - s.y) * s.k;
    s.vx = (s.vx + ax) * s.d; s.vy = (s.vy + ay) * s.d;
    s.x += s.vx; s.y += s.vy;
    if (!reduceMotion) ferroEls[i].style.transform = `translate3d(${s.x}px, ${s.y}px, 0) translate3d(-50%, -50%, 0)`;
  });
  if (!reduceMotion) highlight.style.transform = `translate3d(${ferroState[0].x - 26}px, ${ferroState[0].y - 34}px, 0) translate3d(-50%, -50%, 0)`;
  requestAnimationFrame(stepFerro);
}
stepFerro();

const bgAudio = document.getElementById('bgAudio');
const trackNames = [
  'Girl Feels Good',
  'The Eleven Perfect Stranger',
  'The Eleven Sticky PA'
];
const playlist = [
  '{{ site.baseurl }}/assets/music/FKA_TWIGS/2_FKA_twigs_EUSEXUA_The_Eleven_Girl_Feels_Good.mp3',
  '{{ site.baseurl }}/assets/music/FKA_TWIGS/3_FKA_twigs_EUSEXUA_The_Eleven_Perfect_Stranger.mp3',
  '{{ site.baseurl }}/assets/music/FKA_TWIGS/6_FKA_twigs_EUSEXUA_The_Eleven_Sticky_PA.mp3'
];
let currentTrack = 0;
bgAudio.src = playlist[currentTrack];
bgAudio.volume = 0;
let audioStarted = false;
const targetVolume = 0.55;
const fadeDuration = 2500;

const skipBtn = document.getElementById('skipBtn');

bgAudio.addEventListener('ended', () => {
  currentTrack = (currentTrack + 1) % playlist.length;
  bgAudio.src = playlist[currentTrack];
  bgAudio.play().catch(err => console.log('Autoplay prevented:', err));
});

skipBtn.addEventListener('click', () => {
  const wasPlaying = !bgAudio.paused;
  const currentVolume = bgAudio.volume > 0 ? bgAudio.volume : targetVolume;
  currentTrack = (currentTrack + 1) % playlist.length;
  bgAudio.src = playlist[currentTrack];
  bgAudio.volume = currentVolume;
  bgAudio.currentTime = 0;
  bgAudio.play().catch(err => console.log('Autoplay prevented:', err));
  showFloatingTrackName();
  if (!audioStarted) {
    audioStarted = true;
  }
  document.getElementById('audioToggle').classList.add('on');
});

function showFloatingTrackName() {
  const floatingEl = document.getElementById('floatingTrackName');
  floatingEl.textContent = trackNames[currentTrack];
  floatingEl.style.opacity = '1';
  floatingEl.style.animation = 'none';
  setTimeout(() => {
    floatingEl.style.animation = 'floatUp 2s ease-out forwards';
  }, 10);
}

function startAudio() {
  if (audioStarted) return;
  audioStarted = true;
  bgAudio.currentTime = 0;
  bgAudio.volume = 0;
  bgAudio.play().catch(err => console.log('Autoplay prevented:', err));
  showFloatingTrackName();
  const fadeStart = performance.now();
  function fade(t) {
    const elapsed = t - fadeStart;
    const pct = Math.min(1, elapsed / fadeDuration);
    bgAudio.volume = pct * targetVolume;
    if (pct < 1) requestAnimationFrame(fade);
  }
  requestAnimationFrame(fade);
  document.getElementById('audioToggle').classList.add('on');
}

function toggleAudio() {
  const el = document.getElementById('audioToggle');
  if (!audioStarted) {
    startAudio();
  } else if (bgAudio.paused) {
    bgAudio.play();
    el.classList.add('on');
  } else {
    bgAudio.pause();
    el.classList.remove('on');
  }
}

function triggerFerroSpike() {
  const originalK = ferroState.map(s => s.k);
  const spikeStart = performance.now();
  const spikeDuration = 2500;
  
  function spikeFrame(t) {
    const elapsed = t - spikeStart;
    const pct = Math.min(1, elapsed / spikeDuration);
    const intensity = Math.cos(pct * Math.PI) * 1.2;
    
    ferroState.forEach((s, i) => {
      s.k = originalK[i] * (1 + intensity * 6);
    });
    
    if (pct < 1) {
      requestAnimationFrame(spikeFrame);
    } else {
      ferroState.forEach((s, i) => {
        s.k = originalK[i];
      });
    }
  }
  requestAnimationFrame(spikeFrame);
}

function smoothScrollToStage() {
  const stage = document.getElementById('stage');
  const start = window.scrollY || window.pageYOffset;
  const target = stage.offsetTop;
  const distance = target - start;
  const duration = 3500;
  const startTime = performance.now();
  
  function scroll(t) {
    const elapsed = t - startTime;
    const pct = Math.min(1, elapsed / duration);
    const easeOut = 1 - Math.pow(1 - pct, 3);
    window.scrollTo(0, start + distance * easeOut);
    if (pct < 1) requestAnimationFrame(scroll);
  }
  requestAnimationFrame(scroll);
}

document.getElementById('enterBtn').addEventListener('click', () => {
  if (!audioStarted) {
    startAudio();
  } else if (bgAudio.paused) {
    bgAudio.play().catch(err => console.log('Autoplay prevented:', err));
  }
  document.getElementById('audioToggle').classList.add('on');
  ferroActive = true;
  triggerFerroSpike();
  setTimeout(smoothScrollToStage, 500);
});

document.getElementById('audioToggle').addEventListener('click', toggleAudio);

(function initCountdown(){
  const TARGET_DATE = '2026-09-18T20:00:00';

  const partyDate = new Date(TARGET_DATE);

  // Gate countdown
  const elDays = document.getElementById('cd-days');
  const elHours = document.getElementById('cd-hours');
  const elMins = document.getElementById('cd-mins');
  const elSecs = document.getElementById('cd-secs');

  function tick(){
    const now = new Date();
    const diff = Math.max(0, partyDate - now);

    const days = Math.floor(diff / 86400000);
    const hours = Math.floor((diff / 3600000) % 24);
    const mins = Math.floor((diff / 60000) % 60);
    const secs = Math.floor((diff / 1000) % 60);

    // Update gate countdown
    elDays.textContent = String(days).padStart(2, '0');
    elHours.textContent = String(hours).padStart(2, '0');
    elMins.textContent = String(mins).padStart(2, '0');
    elSecs.textContent = String(secs).padStart(2, '0');
  }
  tick();
  setInterval(tick, 1000);
})();
</script>

</body>
</html>
