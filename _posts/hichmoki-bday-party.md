<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EUSEXUA // Birthday Transmission</title>
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
    overflow-x:hidden;
    min-height:100vh;
    cursor:default;
  }

  ::selection{ background:var(--ice); color:var(--void); }

  a{ color:inherit; }

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
      radial-gradient(circle at 34% 26%, #7a7d82 0%, #2c2e32 20%, #131417 42%, #050506 68%, #000 100%);
    will-change:transform;
    transform:translate3d(-50%,-50%,0);
  }
  #ferro-1{ width:min(46vw,340px); height:min(46vw,340px); }
  #ferro-2{ width:min(30vw,220px); height:min(30vw,220px); }
  #ferro-3{ width:min(22vw,160px); height:min(22vw,160px); }
  #ferro-4{ width:min(16vw,120px); height:min(16vw,120px); }

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

  /* ---------- gate ---------- */
  #gate{
    position:fixed; inset:0; z-index:50;
    display:flex; flex-direction:column; align-items:center; justify-content:center; gap:2.2rem;
    background:var(--void);
    transition:opacity 1.1s ease, visibility 1.1s ease;
  }
  #gate.hidden{ opacity:0; visibility:hidden; pointer-events:none; }

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
  }
  .enter-btn:hover{ transform:scale(1.06); box-shadow:0 0 42px var(--ice-dim); }
  .enter-btn:active{ transform:scale(0.97); }

  .gate-hint{ color:var(--chrome-3); font-size:0.72rem; }

  /* ---------- stage ---------- */
  #stage{ position:relative; z-index:1; opacity:0; transition:opacity 1.2s ease 0.2s; }
  #stage.show{ opacity:1; }

  .wrap{ max-width:960px; margin:0 auto; padding:0 6vw; }

  header.hero{
    min-height:100svh;
    display:flex; flex-direction:column; align-items:center; justify-content:center;
    text-align:center; gap:1.6rem;
    position:relative;
  }

  .eyebrow{ display:flex; align-items:center; gap:0.8em; color:var(--ice); }
  .eyebrow::before, .eyebrow::after{
    content:""; width:2.4em; height:1px; background:var(--ice-dim);
  }

  h1.name{
    font-family:'Unbounded', sans-serif;
    font-weight:900;
    font-size:var(--fs-display);
    line-height:0.92;
    letter-spacing:-0.01em;
    text-transform:uppercase;
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

  /* details — floating, unboxed, metallic */
  section.details{ padding:8rem 0 7rem; }

  .divider{
    height:1px;
    background:linear-gradient(90deg, transparent, var(--line) 20%, var(--line) 80%, transparent);
    margin-bottom:5rem;
  }

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

  /* rsvp */
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
  }
  .rsvp-btn:hover{ letter-spacing:0.38em; border-color:var(--ice); color:var(--ice); }

  footer{
    padding:3rem 0 4rem; text-align:center;
    color:var(--chrome-4); font-family:'Space Mono', monospace;
    font-size:0.7rem; letter-spacing:0.18em; text-transform:uppercase;
  }
  footer span{ color:var(--chrome-3); }

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
    opacity:0; visibility:hidden; transition:opacity 0.6s ease, visibility 0.6s ease;
  }
  #audioToggle.show{ opacity:1; visibility:visible; }
  #audioToggle .dot{ width:7px; height:7px; border-radius:50%; background:var(--chrome-4); transition:background 0.3s ease, box-shadow 0.3s ease; }
  #audioToggle.on .dot{ background:var(--ice); box-shadow:0 0 8px var(--ice); }
  .bars{ display:flex; align-items:flex-end; gap:2px; height:10px; }
  .bars i{ width:2px; background:var(--chrome-3); display:block; height:3px; transition:height 0.15s ease; }
  #audioToggle.on .bars i{ background:var(--ice); animation:barBounce 0.9s ease-in-out infinite; }
  #audioToggle.on .bars i:nth-child(2){ animation-delay:0.15s; }
  #audioToggle.on .bars i:nth-child(3){ animation-delay:0.3s; }
  @keyframes barBounce{ 0%,100%{ height:3px; } 50%{ height:10px; } }

  #backBtn{
    position:fixed; bottom:1.4rem; left:1.4rem; z-index:55;
    padding:0.7em 1.1em;
    border:1px solid var(--line);
    border-radius:999px;
    background:rgba(13,15,18,0.7);
    backdrop-filter:blur(6px);
    font-family:'Space Mono', monospace;
    font-size:0.66rem; letter-spacing:0.18em; text-transform:uppercase;
    color:var(--chrome-2);
    opacity:0; visibility:hidden; transition:opacity 0.6s ease, visibility 0.6s ease, border-color 0.3s ease, color 0.3s ease;
  }
  #backBtn.show{ opacity:1; visibility:visible; }
  #backBtn:hover{ border-color:var(--ice); color:var(--ice); }

  @media (prefers-reduced-motion: reduce){
    .chrome-text, .enter-btn, .scroll-cue{ animation:none !important; }
    .blob{ transition:none; }
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

<!-- ============== GATE ============== -->
<div id="gate">
  <div class="gate-mark chrome-text">EUSEXUA</div>
  <button class="enter-btn" id="enterBtn">Enter</button>
  <div class="gate-hint mono">Sound on · tap to begin</div>
</div>

<!-- ============== STAGE ============== -->
<div id="stage">
  <header class="hero wrap">
    <div class="eyebrow mono" id="js-eyebrow">Hichmoki Birthday Party</div>
    <h1 class="name chrome-text">
      <span id="js-name">NAME</span>
      <span class="turns" id="js-turns">TURNS AGE</span>
    </h1>
    <p class="tagline" id="js-tagline">A night dissolves into dance. Come lose your shape with us.</p>
    <div class="scroll-cue"></div>
  </header>

  <section class="details wrap">
    <div class="divider"></div>
    <div class="details-grid">
      <div class="detail-cell">
        <div class="label mono">Date</div>
        <div class="value chrome-text" id="js-date">DATE</div>
      </div>
      <div class="detail-cell">
        <div class="label mono">Time</div>
        <div class="value chrome-text" id="js-time">TIME</div>
      </div>
      <div class="detail-cell">
        <div class="label mono">Location</div>
        <div class="value chrome-text" id="js-location">LOCATION</div>
        <div class="sub" id="js-address"></div>
      </div>
      <div class="detail-cell">
        <div class="label mono">Dress Code</div>
        <div class="value chrome-text" id="js-dress">CHROME / BLACK</div>
      </div>
    </div>
  </section>

  <section class="rsvp wrap">
    <h2 class="chrome-text">Confirm your presence</h2>
    <p id="js-rsvp-note">One life, one liquid night. Let us know you're in.</p>
    <a class="rsvp-btn" id="js-rsvp-link" href="#">RSVP</a>
  </section>

  <footer>
    <span id="js-footer-name">NAME</span> &nbsp;·&nbsp; <span id="js-footer-year"></span>
  </footer>
</div>

<audio id="bgAudio" src="eusexua-track.mp3" loop preload="auto"></audio>

<div id="backBtn">← Back</div>

<div id="audioToggle">
  <div class="dot"></div>
  <div class="bars"><i></i><i></i><i></i></div>
  <span id="audioLabel">Sound</span>
</div>

<script>
/* =====================================================================
   EDIT EVERYTHING FOR THE INVITE HERE — this is the only block you need.
===================================================================== */
const CONFIG = {
  name: "HICHAM",             // birthday person's name
  age: "[AGE]",               // turning this age — fill in
  eventTag: "Hichmoki Birthday Party",
  tagline: "A night dissolves into dance. Come lose your shape with us.",
  date: "18.09.2026",
  time: "20:00 — till late",
  location: "STRAATWEG 60B",
  address: "",
  dress: "QUEER FRIENDLY",
  rsvpEmail: "[YOUR EMAIL]",         // fill in
  rsvpSubject: "I'm in — EUSEXUA night"
};
/* ===================================================================== */

document.getElementById('js-eyebrow').textContent = CONFIG.eventTag;

document.getElementById('js-name').textContent = CONFIG.name;
document.getElementById('js-turns').textContent = `TURNS ${CONFIG.age}`;
document.getElementById('js-tagline').textContent = CONFIG.tagline;
document.getElementById('js-date').textContent = CONFIG.date;
document.getElementById('js-time').textContent = CONFIG.time;
document.getElementById('js-location').textContent = CONFIG.location;
document.getElementById('js-address').textContent = CONFIG.address;
document.getElementById('js-dress').textContent = CONFIG.dress;
document.getElementById('js-footer-name').textContent = CONFIG.name;
document.getElementById('js-footer-year').textContent = new Date().getFullYear();
document.getElementById('js-rsvp-link').href =
  `mailto:${CONFIG.rsvpEmail}?subject=${encodeURIComponent(CONFIG.rsvpSubject)}&body=${encodeURIComponent("I'll be there.")}`;

/* ---------------- ferrofluid cursor cluster (heavy, magnetic-liquid feel) ---------------- */
const reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
let mx = window.innerWidth / 2, my = window.innerHeight / 2;

window.addEventListener('pointermove', (e) => { mx = e.clientX; my = e.clientY; });
window.addEventListener('touchmove', (e) => {
  if (e.touches[0]) { mx = e.touches[0].clientX; my = e.touches[0].clientY; }
}, { passive: true });

// each blob has its own mass (stiffness) and drag (damping) so the cluster
// trails the cursor unevenly, like a viscous magnetic fluid being pulled along
const ferroEls = ['ferro-1', 'ferro-2', 'ferro-3', 'ferro-4'].map(id => document.getElementById(id));
const ferroState = [
  { x: mx, y: my, vx: 0, vy: 0, k: 0.05, d: 0.86, ox: 0, oy: 0 },
  { x: mx, y: my, vx: 0, vy: 0, k: 0.032, d: 0.82, ox: 60, oy: -30 },
  { x: mx, y: my, vx: 0, vy: 0, k: 0.024, d: 0.80, ox: -70, oy: 40 },
  { x: mx, y: my, vx: 0, vy: 0, k: 0.02, d: 0.78, ox: 20, oy: 70 }
];

let spike = 0; // temporary burst added to displacement on click/tap
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

  // highlight trails the primary (heaviest) blob for a glossy specular feel
  if (!reduceMotion) {
    highlight.style.transform = `translate3d(${ferroState[0].x - 26}px, ${ferroState[0].y - 34}px, 0) translate3d(-50%, -50%, 0)`;
  }

  if (spike > 0) spike *= 0.9;
  requestAnimationFrame(stepFerro);
}
stepFerro();

// magnetic "spike" burst on tap/click, like a ferrofluid reacting to a magnet
function triggerSpike() {
  spike = 26;
  ferroState.forEach(s => { s.vx += (Math.random() - 0.5) * 8; s.vy += (Math.random() - 0.5) * 8; });
}
window.addEventListener('pointerdown', triggerSpike);

/* ---------------- background audio: track first, generative fallback ---------------- */
const bgAudio = document.getElementById('bgAudio');
let started = false;
let trackFailed = false;
let audioMode = 'track'; // 'track' | 'synth'
let ctx, master;

bgAudio.addEventListener('error', () => {
  trackFailed = true;
  if (started && audioMode === 'track') switchToSynth();
});

function startAudio() {
  if (started) return;
  started = true;
  if (trackFailed) { switchToSynth(); return; }

  bgAudio.volume = 0;
  const p = bgAudio.play();
  if (p && p.catch) p.catch(() => switchToSynth());

  const fadeStart = performance.now();
  const fadeMs = 2500, targetVol = 0.55;
  function fade(t) {
    if (audioMode !== 'track') return;
    const pct = Math.min(1, Math.max(0, (t - fadeStart) / fadeMs));
    bgAudio.volume = pct * targetVol;
    if (pct < 1) requestAnimationFrame(fade);
  }
  requestAnimationFrame(fade);
}

function switchToSynth() {
  if (audioMode === 'synth') return;
  audioMode = 'synth';
  bgAudio.pause();
  startSynthAudio();
  document.getElementById('audioToggle').classList.add('on');
}

/* generative dark-techno ambience — used only if the track can't load */
function startSynthAudio() {
  ctx = new (window.AudioContext || window.webkitAudioContext)();
  master = ctx.createGain();
  master.gain.value = 0;
  master.connect(ctx.destination);
  master.gain.linearRampToValueAtTime(0.32, ctx.currentTime + 3.5);

  const o1 = ctx.createOscillator(); o1.type = 'sine'; o1.frequency.value = 55;
  const o2 = ctx.createOscillator(); o2.type = 'sawtooth'; o2.frequency.value = 55.4;
  const droneFilter = ctx.createBiquadFilter();
  droneFilter.type = 'lowpass'; droneFilter.frequency.value = 380; droneFilter.Q.value = 6;
  const droneGain = ctx.createGain(); droneGain.gain.value = 0.5;
  o1.connect(droneFilter); o2.connect(droneFilter);
  droneFilter.connect(droneGain); droneGain.connect(master);

  const lfo = ctx.createOscillator(); lfo.frequency.value = 0.045;
  const lfoGain = ctx.createGain(); lfoGain.gain.value = 180;
  lfo.connect(lfoGain); lfoGain.connect(droneFilter.frequency);
  o1.start(); o2.start(); lfo.start();

  const bufferSize = 2 * ctx.sampleRate;
  const noiseBuffer = ctx.createBuffer(1, bufferSize, ctx.sampleRate);
  const data = noiseBuffer.getChannelData(0);
  for (let i = 0; i < bufferSize; i++) data[i] = (Math.random() * 2 - 1) * 0.5;
  const noise = ctx.createBufferSource();
  noise.buffer = noiseBuffer; noise.loop = true;
  const noiseFilter = ctx.createBiquadFilter();
  noiseFilter.type = 'bandpass'; noiseFilter.frequency.value = 900; noiseFilter.Q.value = 0.7;
  const noiseGain = ctx.createGain(); noiseGain.gain.value = 0.04;
  noise.connect(noiseFilter); noiseFilter.connect(noiseGain); noiseGain.connect(master);
  noise.start();

  scheduleMetallicPing();
}

function metallicPing() {
  if (!ctx) return;
  const now = ctx.currentTime;
  const freqs = [1200, 1800, 2600];
  const f = freqs[Math.floor(Math.random() * freqs.length)] * (0.9 + Math.random() * 0.2);
  const carrier = ctx.createOscillator(); carrier.type = 'triangle'; carrier.frequency.value = f;
  const overtone = ctx.createOscillator(); overtone.type = 'square'; overtone.frequency.value = f * 1.503;
  const bp = ctx.createBiquadFilter(); bp.type = 'bandpass'; bp.frequency.value = f; bp.Q.value = 14;
  const g = ctx.createGain(); g.gain.value = 0;
  carrier.connect(bp); overtone.connect(bp); bp.connect(g); g.connect(master);
  g.gain.setValueAtTime(0, now);
  g.gain.linearRampToValueAtTime(0.09, now + 0.02);
  g.gain.exponentialRampToValueAtTime(0.0001, now + 1.8);
  carrier.start(now); overtone.start(now);
  carrier.stop(now + 2); overtone.stop(now + 2);
}

function scheduleMetallicPing() {
  metallicPing();
  setTimeout(scheduleMetallicPing, 3000 + Math.random() * 5000);
}

function toggleAudio() {
  const el = document.getElementById('audioToggle');
  if (audioMode === 'track') {
    if (bgAudio.paused) { bgAudio.play().catch(() => switchToSynth()); el.classList.add('on'); }
    else { bgAudio.pause(); el.classList.remove('on'); }
  } else if (ctx) {
    if (ctx.state === 'running') { ctx.suspend(); el.classList.remove('on'); }
    else { ctx.resume(); el.classList.add('on'); }
  }
}

/* ---------------- gate interaction ---------------- */
document.getElementById('enterBtn').addEventListener('click', () => {
  startAudio();
  document.getElementById('gate').classList.add('hidden');
  document.getElementById('stage').classList.add('show');
  document.getElementById('audioToggle').classList.add('show', 'on');
  document.getElementById('backBtn').classList.add('show');
});

document.getElementById('audioToggle').addEventListener('click', toggleAudio);

document.getElementById('backBtn').addEventListener('click', () => {
  document.getElementById('stage').classList.remove('show');
  document.getElementById('gate').classList.remove('hidden');
  document.getElementById('audioToggle').classList.remove('show', 'on');
  document.getElementById('backBtn').classList.remove('show');
  bgAudio.pause();
  if (ctx && ctx.state === 'running') ctx.suspend();
});
</script>
</body>
</html>
