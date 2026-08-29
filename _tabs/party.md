---
layout: page
icon: fas fa-mask
order: 3
redirect_to: /posts/2026-08-28-bday/
---

---
layout: html-only
title: Hichmoki Party - Welkom
date: 2026-08-29
categories: [party]
sitemap: false
published: false
permalink: /posts/2026-08-29-hichmoki-bday-party/
---
<!DOCTYPE html>
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
    --fs-display:clamp(2.4rem, 10vw, 7rem);
    --fs-h2:clamp(1.2rem, 3vw, 1.8rem);
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
    overflow:hidden;
    height:100vh;
    cursor:crosshair;
    backface-visibility:hidden;
    -webkit-backface-visibility:hidden;
    transform:translate3d(0,0,0);
  }

  a, button{ cursor:pointer; }

  ::selection{ background:var(--ice); color:var(--void); }

  a{ color:inherit; text-decoration:none; }

  button{ font-family:inherit; border:none; background:none; color:inherit; cursor:pointer; }

  :focus-visible{ outline:2px solid var(--ice); outline-offset:4px; }

  /* film grain overlay */
  .grain{
    position:fixed; inset:0; z-index:60; pointer-events:none;
    opacity:0.05; mix-blend-mode:overlay;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  }

  .scanlines{
    position:fixed; inset:0; z-index:59; pointer-events:none; opacity:0.06;
    background:repeating-linear-gradient(0deg, #fff 0px, transparent 1px, transparent 3px);
  }

  /* ferrofluid / magnetic-liquid blob cluster */
  .blob-wrap{ position:fixed; inset:0; z-index:0; pointer-events:none; overflow:hidden; }
  .ferro-goo{ position:absolute; inset:0; filter:url(#gooMerge); }
  .ferro-blob{
    position:absolute; top:0; left:0;
    border-radius:50%;
    background:
      radial-gradient(circle at 40% 30%, #8fd3ff 0%, #7fc0ff 6%, #6ab3ff 12%, #9a9da3 18%, #7a7d82 24%, #6a7077 30%, #5a6066 38%, #4a5056 48%, #3a4046 60%, #2a3036 75%, #1a2026 88%, #000 100%);
    will-change:transform;
    transform:translate3d(-50%,-50%,0);
    animation:ferroColorShift 10s ease-in-out infinite;
    box-shadow:
      inset -20px -20px 40px rgba(0,0,0,0.3),
      inset 15px 15px 30px rgba(120,180,255,0.25),
      0 0 80px rgba(100,160,255,0.5),
      0 0 150px rgba(74,144,226,0.3);
  }
  @keyframes ferroColorShift{
    0%{
      background:radial-gradient(circle at 40% 30%, #8fd3ff 0%, #7fc0ff 6%, #6ab3ff 12%, #9a9da3 18%, #7a7d82 24%, #6a7077 30%, #5a6066 38%, #4a5056 48%, #3a4046 60%, #2a3036 75%, #1a2026 88%, #000 100%);
      box-shadow:
        inset -20px -20px 40px rgba(0,0,0,0.3),
        inset 15px 15px 30px rgba(120,180,255,0.25),
        0 0 80px rgba(100,160,255,0.5),
        0 0 150px rgba(74,144,226,0.3);
    }
    50%{
      background:radial-gradient(circle at 40% 30%, #c488ff 0%, #b366d9 6%, #9d4eca 12%, #9a9da3 18%, #7a7d82 24%, #6a7077 30%, #5a6066 38%, #4a5056 48%, #3a4046 60%, #2a3036 75%, #1a2026 88%, #000 100%);
      box-shadow:
        inset -20px -20px 40px rgba(0,0,0,0.3),
        inset 15px 15px 30px rgba(200,140,255,0.3),
        0 0 100px rgba(196,136,255,0.6),
        0 0 180px rgba(179,102,217,0.4);
    }
    100%{
      background:radial-gradient(circle at 40% 30%, #8fd3ff 0%, #7fc0ff 6%, #6ab3ff 12%, #9a9da3 18%, #7a7d82 24%, #6a7077 30%, #5a6066 38%, #4a5056 48%, #3a4046 60%, #2a3036 75%, #1a2026 88%, #000 100%);
      box-shadow:
        inset -20px -20px 40px rgba(0,0,0,0.3),
        inset 15px 15px 30px rgba(120,180,255,0.25),
        0 0 80px rgba(100,160,255,0.5),
        0 0 150px rgba(74,144,226,0.3);
    }
  }
  #ferro-1{ width:min(28vw,200px); height:min(28vw,200px); }
  #ferro-2{ width:min(18vw,140px); height:min(18vw,140px); }
  #ferro-3{ width:min(13vw,100px); height:min(13vw,100px); }
  #ferro-4{ width:min(9vw,70px); height:min(9vw,70px); }

  .ferro-oil{ position:absolute; inset:0; filter:url(#liquidFilter); mix-blend-mode:normal; }

  .ferro-highlight{
    position:absolute; top:0; left:0;
    width:min(14vw,110px); height:min(14vw,110px);
    border-radius:50%;
    background:radial-gradient(circle, rgba(255,255,255,0.9) 0%, var(--ice) 30%, transparent 72%);
    filter:blur(10px);
    mix-blend-mode:screen;
    opacity:0.55;
    will-change:transform;
    transform:translate3d(-50%,-50%,0);
  }

  /* chrome text */
  .chrome-text{
    background:linear-gradient(112deg,
      var(--chrome-3) 0%, var(--chrome-1) 14%, var(--chrome-2) 26%,
      #ffffff 38%, var(--chrome-4) 50%, var(--chrome-2) 64%,
      var(--chrome-1) 78%, var(--chrome-3) 100%);
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

  #stage{
    position:relative;
    z-index:1;
    min-height:100svh;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    text-align:center;
    gap:2.4rem;
    padding:2rem 6vw;
  }

  h1{
    font-family:'Unbounded', sans-serif;
    font-weight:900;
    font-size:var(--fs-display);
    line-height:1.1;
    letter-spacing:-0.01em;
    text-transform:uppercase;
    margin:0;
    filter:url(#liquidFilterSoft);
  }

  .age-text{
    font-size:var(--fs-h2);
    color:var(--ice);
    font-weight:600;
    margin:0.6rem 0 0;
  }

  .message{
    max-width:45ch;
    font-size:var(--fs-body);
    color:var(--chrome-2);
    line-height:1.7;
    margin:1.2rem 0;
  }

  .whatsapp-link{
    display:inline-block;
    margin-top:2rem;
    padding:1.1em 2.8em;
    border-radius:999px;
    border:1px solid var(--chrome-2);
    font-family:'Space Mono', monospace;
    letter-spacing:0.28em;
    font-size:0.78rem;
    text-transform:uppercase;
    position:relative;
    overflow:hidden;
    transition:letter-spacing 0.4s ease, border-color 0.4s ease, color 0.4s ease;
  }

  .whatsapp-link:hover{
    letter-spacing:0.38em;
    border-color:var(--ice);
    color:var(--ice);
  }

  #backBtn{
    position:fixed; bottom:1.4rem; left:1.4rem; z-index:55;
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
  }

  #backBtn:hover{ border-color:var(--ice); color:var(--ice); }

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

  /* audio toggle */
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

  @media (prefers-reduced-motion: reduce){
    .chrome-text, h1{ animation:none !important; }
  }
</style>
</head>
<body>

<!-- SVG filters powering the liquid-metal look -->
<svg width="0" height="0" style="position:absolute">
  <filter id="liquidFilter" x="-40%" y="-40%" width="180%" height="180%">
    <feTurbulence type="fractalNoise" baseFrequency="0.010 0.018" numOctaves="2" seed="11" result="noise">
      <animate attributeName="baseFrequency" dur="22s" values="0.010 0.018;0.017 0.026;0.010 0.018" repeatCount="indefinite" />
    </feTurbulence>
    <feDisplacementMap in="SourceGraphic" in2="noise" scale="70" xChannelSelector="R" yChannelSelector="G" />
  </filter>
  <filter id="gooMerge" x="-60%" y="-60%" width="220%" height="220%">
    <feGaussianBlur in="SourceGraphic" stdDeviation="18" result="blur" />
    <feColorMatrix in="blur" type="matrix"
      values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 26 -11" result="goo" />
    <feTurbulence type="fractalNoise" baseFrequency="0.006 0.012" numOctaves="2" seed="9" result="oilNoise">
      <animate attributeName="baseFrequency" dur="30s" values="0.006 0.012;0.011 0.02;0.006 0.012" repeatCount="indefinite" />
    </feTurbulence>
    <feDisplacementMap in="goo" in2="oilNoise" scale="46" xChannelSelector="R" yChannelSelector="G" result="oiled" />
    <feComposite in="oiled" in2="oiled" operator="atop" />
  </filter>
  <filter id="liquidFilterSoft" x="-30%" y="-30%" width="160%" height="160%">
    <feTurbulence type="fractalNoise" baseFrequency="0.012 0.02" numOctaves="2" seed="4" result="n2">
      <animate attributeName="baseFrequency" dur="16s" values="0.012 0.02;0.02 0.03;0.012 0.02" repeatCount="indefinite" />
    </feTurbulence>
    <feDisplacementMap in="SourceGraphic" in2="n2" scale="10" xChannelSelector="R" yChannelSelector="G" />
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

<!-- ============== PARTY PAGE ============== -->
<div id="stage">
  <div>
    <h1 class="chrome-text">Hichmoki<br>Party</h1>
    <div class="age-text">33 Years Celebrated</div>
  </div>

  <p class="message">
    An evening where boundaries dissolve and we move as one. Yours to join.
  </p>

  <a href="https://chat.whatsapp.com/CzWo9BidWbLGTedkoEgUsX" target="_blank" class="whatsapp-link">
    Join WhatsApp Group
  </a>
</div>

<audio id="bgAudio" src="/assets/music/FKA_TWIGS/2_FKA_twigs_EUSEXUA_The_Eleven_Girl_Feels_Good.mp3" preload="auto"></audio>

<div id="audioToggle">
  <div class="dot"></div>
  <div class="bars"><i></i><i></i><i></i></div>
  <span id="audioLabel">Sound</span>
</div>

<div id="backBtn">← Back</div>

<a id="menuBtn" href="{{ site.baseurl }}/posts/2026-08-28-bday/">Menu</a>

<script>
/* ferrofluid cursor cluster */
const reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
let mx = window.innerWidth / 2, my = window.innerHeight / 2;

window.addEventListener('pointermove', (e) => { mx = e.clientX; my = e.clientY; });
window.addEventListener('touchmove', (e) => {
  if (e.touches[0]) { mx = e.touches[0].clientX; my = e.touches[0].clientY; }
}, { passive: true });

const ferroEls = ['ferro-1', 'ferro-2', 'ferro-3', 'ferro-4'].map(id => document.getElementById(id));
const ferroState = [
  { x: mx, y: my, vx: 0, vy: 0, k: 0.05, d: 0.86, ox: 0, oy: 0 },
  { x: mx, y: my, vx: 0, vy: 0, k: 0.032, d: 0.82, ox: 60, oy: -30 },
  { x: mx, y: my, vx: 0, vy: 0, k: 0.024, d: 0.80, ox: -70, oy: 40 },
  { x: mx, y: my, vx: 0, vy: 0, k: 0.02, d: 0.78, ox: 20, oy: 70 }
];

let spike = 0;
const highlight = document.getElementById('ferroHighlight');

function stepFerro() {
  ferroState.forEach((s, i) => {
    const tx = mx + s.ox * (1 + spike * 0.02);
    const ty = my + s.oy * (1 + spike * 0.02);
    const ax = (tx - s.x) * s.k;
    const ay = (ty - s.y) * s.k;
    s.vx = (s.vx + ax) * s.d;
    s.vy = (s.vy + ay) * s.d;
    s.x += s.vx;
    s.y += s.vy;
    if (!reduceMotion) ferroEls[i].style.transform = `translate3d(${s.x}px, ${s.y}px, 0) translate3d(-50%, -50%, 0)`;
  });

  if (!reduceMotion) {
    highlight.style.transform = `translate3d(${ferroState[0].x - 26}px, ${ferroState[0].y - 34}px, 0) translate3d(-50%, -50%, 0)`;
  }

  if (spike > 0) spike *= 0.9;
  requestAnimationFrame(stepFerro);
}
stepFerro();

function triggerSpike() {
  spike = 40;
  ferroState.forEach(s => { s.vx += (Math.random() - 0.5) * 12; s.vy += (Math.random() - 0.5) * 12; });
}
window.addEventListener('pointerdown', triggerSpike);
document.addEventListener('click', triggerSpike);

document.getElementById('backBtn').addEventListener('click', () => {
  window.history.back();
});

/* Audio playback */
const bgAudio = document.getElementById('bgAudio');
const audioToggle = document.getElementById('audioToggle');
const audioSrc = '{{ site.baseurl }}/assets/music/FKA_TWIGS/3_FKA_twigs_EUSEXUA_The_Eleven_Perfect_Stranger.mp3';
bgAudio.src = audioSrc;
bgAudio.loop = true;
bgAudio.volume = 0;
let audioStarted = false;
const targetVolume = 0.55;
const fadeDuration = 2500;

function startAudio() {
  if (audioStarted) return;
  audioStarted = true;

  bgAudio.currentTime = 0;
  bgAudio.volume = 0;
  bgAudio.play().catch(err => console.log('Autoplay prevented:', err));

  const fadeStart = performance.now();
  function fade(t) {
    const elapsed = t - fadeStart;
    const pct = Math.min(1, elapsed / fadeDuration);
    bgAudio.volume = pct * targetVolume;
    if (pct < 1) requestAnimationFrame(fade);
  }
  requestAnimationFrame(fade);
  audioToggle.classList.add('on');
}

function toggleAudio() {
  if (!audioStarted) {
    startAudio();
  } else if (bgAudio.paused) {
    bgAudio.play();
    audioToggle.classList.add('on');
  } else {
    bgAudio.pause();
    audioToggle.classList.remove('on');
  }
}

audioToggle.addEventListener('click', toggleAudio);

// Auto-start on page load
window.addEventListener('load', () => {
  setTimeout(startAudio, 500);
});
</script>

</body>
</html>
