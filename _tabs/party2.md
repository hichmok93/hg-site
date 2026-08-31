<script>

/* =========================================================
   PARTY PAGE AUDIO / BOOT SYSTEM
   ========================================================= */

let bootActivated = false;
let audioStarted = false;
let ferroActive = false;


/* =========================================================
   CONFIG
   ========================================================= */

const CONFIG = {

  name: "The Ceremony",

  age: "33",

  eventTag: "An Evening Unfolds",

  tagline:
    "Join the party - Good food, warm people, a night that moves.",

  date: "18.09.2026",

  time: "20:00 — till late",

  location: "STRAATWEG 60B",

  address: "",

  dress: "QUEER FRIENDLY",

  plusOne:
    "+1 welcome — just let us know who's coming"

};


/* =========================================================
   AUDIO FILES
   ========================================================= */

const PS1_TRACK =
  "{{ site.baseurl }}/assets/music/FKA_TWIGS/PS1 Startup (Remastered) MP3.mp3";


const playlist = [

  "{{ site.baseurl }}/assets/music/FKA_TWIGS/2_FKA_twigs_EUSEXUA_The_Eleven_Girl_Feels_Good.mp3",

  "{{ site.baseurl }}/assets/music/FKA_TWIGS/3_FKA_twigs_EUSEXUA_The_Eleven_Perfect_Stranger.mp3",

  "{{ site.baseurl }}/assets/music/FKA_TWIGS/6_FKA_twigs_EUSEXUA_The_Eleven_Sticky_PA.mp3"

];


const trackNames = [

  "Girl Feels Good",

  "The Eleven Perfect Stranger",

  "The Eleven Sticky PA"

];


/* =========================================================
   AUDIO ELEMENTS
   ========================================================= */

const bgAudio =
  document.getElementById("bgAudio");


bgAudio.preload = "auto";

bgAudio.src =
  playlist[0];

bgAudio.volume = 0;


let currentTrack = 0;


const targetVolume = 0.55;

const fadeDuration = 2500;


/*
 * PS1 audio is created immediately.
 *
 * We DO NOT create it later inside activateBoot().
 */

const ps1Audio =
  document.createElement("audio");


ps1Audio.preload = "auto";

ps1Audio.src =
  PS1_TRACK;

ps1Audio.volume = 1;

ps1Audio.setAttribute(
  "playsinline",
  ""
);


/* =========================================================
   ELEMENTS
   ========================================================= */

const enterBtn =
  document.getElementById("enterBtn");


const bootBar =
  document.getElementById("bootBarFill");


const bootText =
  document.getElementById("bootText");


const audioToggle =
  document.getElementById("audioToggle");


const audioLabel =
  document.getElementById("audioLabel");


const skipBtn =
  document.getElementById("skipBtn");


const backBtn =
  document.getElementById("backBtn");


const floatingTrackName =
  document.getElementById("floatingTrackName");


/* =========================================================
   PRELOAD
   ========================================================= */

ps1Audio.load();

bgAudio.load();


/* =========================================================
   SCROLL LOCK
   ========================================================= */

function preventScroll(e){

  e.preventDefault();

}


/* =========================================================
   PS1 STARTUP SOUND
   ========================================================= */

let ps1Started = false;


async function playPS1Sound(){

  if(ps1Started){

    return true;

  }


  try{

    ps1Audio.currentTime = 0;

    ps1Audio.volume = 1;


    /*
     * CRITICAL:
     *
     * This play() is called from the first
     * pointerdown user interaction.
     */

    await ps1Audio.play();


    ps1Started = true;


    console.log(
      "PS1 startup sound started."
    );


    return true;


  }catch(error){

    console.warn(
      "PS1 startup sound was blocked:",
      error.name,
      error.message
    );


    ps1Started = false;


    return false;

  }

}


/* =========================================================
   FIRST USER INTERACTION
   ========================================================= */

async function firstUserInteraction(event){

  if(bootActivated){

    return;

  }


  console.log(
    "First user interaction:",
    event.type
  );


  /*
   * Mark boot as activated immediately.
   */

  bootActivated = true;


  /*
   * START PS1 IMMEDIATELY.
   *
   * This happens inside the user activation event.
   */

  await playPS1Sound();


  /*
   * Start visual boot sequence.
   */

  startBootSequence();

}


/*
 * PRIMARY EVENT
 *
 * pointerdown happens before click.
 */

document.addEventListener(

  "pointerdown",

  firstUserInteraction,

  {
    once:true,
    passive:true,
    capture:true
  }

);


/*
 * TOUCH FALLBACK
 */

document.addEventListener(

  "touchstart",

  firstUserInteraction,

  {
    once:true,
    passive:true,
    capture:true
  }

);


/*
 * KEYBOARD FALLBACK
 */

document.addEventListener(

  "keydown",

  function(event){

    if(bootActivated){

      return;

    }


    if(
      event.key === "Enter" ||
      event.key === " "
    ){

      bootActivated = true;

      playPS1Sound();

      startBootSequence();

    }

  },

  {
    once:true,
    capture:true
  }

);


/* =========================================================
   BOOT SEQUENCE
   ========================================================= */

function startBootSequence(){

  /*
   * Lock page scrolling.
   */

  document.body.style.overflow =
    "hidden";


  document.addEventListener(
    "wheel",
    preventScroll,
    {
      passive:false
    }
  );


  document.addEventListener(
    "touchmove",
    preventScroll,
    {
      passive:false
    }
  );


  /*
   * Disable Enter only AFTER the first
   * interaction has been captured.
   */

  enterBtn.disabled = true;

  enterBtn.style.opacity = "0.5";

  enterBtn.style.cursor =
    "not-allowed";


  /*
   * Loading text.
   */

  bootText.textContent =
    "loading...";

  bootText.style.color =
    "var(--chrome-3)";


  /*
   * Progress bar.
   */

  setTimeout(

    function(){

      bootBar.style.transition =
        "width 14.4s linear";

      bootBar.style.width =
        "100%";

    },

    50

  );


  /*
   * Boot finished.
   */

  setTimeout(

    function(){

      bootText.textContent =
        "Press join";

      bootText.style.color =
        "var(--ice)";


      enterBtn.disabled = false;

      enterBtn.style.opacity = "1";

      enterBtn.style.cursor =
        "pointer";


      enterBtn.textContent =
        "join";

      enterBtn.style.color =
        "var(--ice)";


      /*
       * Fade boot text.
       */

      setTimeout(

        function(){

          bootText.classList.add(
            "fade-out"
          );

        },

        1000

      );

    },

    14400

  );

}


/* =========================================================
   ENTER BUTTON
   ========================================================= */

enterBtn.addEventListener(

  "click",

  async function(){

    if(
      !bootActivated ||
      enterBtn.disabled
    ){

      return;

    }


    /*
     * Start background music.
     */

    if(!audioStarted){

      await startAudio();

    }else if(bgAudio.paused){

      try{

        await bgAudio.play();

        audioToggle.classList.add(
          "on"
        );

      }catch(error){

        console.warn(
          "Background audio playback failed:",
          error
        );

      }

    }


    /*
     * Activate ferrofluid.
     */

    ferroActive = true;

    triggerFerroSpike();


    /*
     * Enable scrolling.
     */

    document.body.style.overflow =
      "auto";


    document.removeEventListener(
      "wheel",
      preventScroll
    );


    document.removeEventListener(
      "touchmove",
      preventScroll
    );


    /*
     * Scroll to invitation.
     */

    setTimeout(
      smoothScrollToStage,
      500
    );

  }

);


/* =========================================================
   BACK BUTTON
   ========================================================= */

backBtn.addEventListener(

  "click",

  function(){

    /*
     * Stop background audio.
     */

    bgAudio.pause();

    bgAudio.currentTime = 0;


    audioStarted = false;


    /*
     * Stop PS1 audio.
     */

    ps1Audio.pause();

    ps1Audio.currentTime = 0;


    ps1Started = false;


    /*
     * Reset state.
     */

    bootActivated = false;


    /*
     * Reset progress.
     */

    bootBar.style.width = "0%";

    bootBar.style.transition =
      "none";


    /*
     * Reset text.
     */

    bootText.textContent =
      "Sound on · Touch or click to activate";

    bootText.style.color =
      "var(--chrome-3)";

    bootText.classList.remove(
      "fade-out"
    );


    /*
     * Reset button.
     */

    enterBtn.textContent =
      "Enter";

    enterBtn.style.color =
      "var(--void)";

    enterBtn.disabled = false;

    enterBtn.style.opacity =
      "1";

    enterBtn.style.cursor =
      "pointer";


    /*
     * Reset scrolling.
     */

    document.body.style.overflow =
      "auto";


    document.removeEventListener(
      "wheel",
      preventScroll
    );


    document.removeEventListener(
      "touchmove",
      preventScroll
    );


    /*
     * Reset audio UI.
     */

    audioToggle.classList.remove(
      "on"
    );


    /*
     * Reset ferrofluid.
     */

    ferroActive = false;


    /*
     * Scroll top.
     */

    window.scrollTo({

      top:0,

      behavior:"smooth"

    });


    /*
     * Reinstall first interaction.
     */

    setTimeout(

      function(){

        document.addEventListener(

          "pointerdown",

          firstUserInteraction,

          {
            once:true,
            passive:true,
            capture:true
          }

        );

      },

      100

    );

  }

);


/* =========================================================
   BACKGROUND MUSIC
   ========================================================= */

async function startAudio(){

  if(audioStarted){

    return true;

  }


  try{

    bgAudio.currentTime = 0;

    bgAudio.volume = 0;


    /*
     * Start immediately.
     */

    await bgAudio.play();


    audioStarted = true;


    audioToggle.classList.add(
      "on"
    );


    showFloatingTrackName();


    /*
     * Fade in.
     */

    const fadeStart =
      performance.now();


    function fade(t){

      const elapsed =
        t - fadeStart;


      const pct =
        Math.min(
          1,
          elapsed / fadeDuration
        );


      bgAudio.volume =
        pct * targetVolume;


      if(pct < 1){

        requestAnimationFrame(
          fade
        );

      }else{

        bgAudio.volume =
          targetVolume;

      }

    }


    requestAnimationFrame(
      fade
    );


    return true;


  }catch(error){

    console.error(
      "Background audio could not start:",
      error.name,
      error.message
    );


    audioStarted = false;


    audioToggle.classList.remove(
      "on"
    );


    return false;

  }

}


/* =========================================================
   NEXT TRACK
   ========================================================= */

bgAudio.addEventListener(

  "ended",

  async function(){

    currentTrack =
      (currentTrack + 1) %
      playlist.length;


    bgAudio.src =
      playlist[currentTrack];


    bgAudio.volume =
      targetVolume;


    try{

      await bgAudio.play();


      audioToggle.classList.add(
        "on"
      );


      showFloatingTrackName();


    }catch(error){

      console.warn(
        "Next track playback prevented:",
        error
      );

    }

  }

);


/* =========================================================
   SKIP
   ========================================================= */

skipBtn.addEventListener(

  "click",

  async function(event){

    event.stopPropagation();


    currentTrack =
      (currentTrack + 1) %
      playlist.length;


    bgAudio.src =
      playlist[currentTrack];


    bgAudio.currentTime = 0;


    bgAudio.volume =
      audioStarted
        ? targetVolume
        : 0;


    try{

      await bgAudio.play();


      audioStarted = true;


      audioToggle.classList.add(
        "on"
      );


      showFloatingTrackName();


    }catch(error){

      console.warn(
        "Skip playback prevented:",
        error
      );

    }

  }

);


/* =========================================================
   AUDIO TOGGLE
   ========================================================= */

audioToggle.addEventListener(

  "click",

  async function(event){

    event.stopPropagation();

    await toggleAudio();

  }

);


async function toggleAudio(){

  if(!audioStarted){

    await startAudio();

    return;

  }


  if(bgAudio.paused){

    try{

      await bgAudio.play();

      audioToggle.classList.add(
        "on"
      );

    }catch(error){

      console.warn(
        "Resume playback failed:",
        error
      );

    }

  }else{

    bgAudio.pause();

    audioToggle.classList.remove(
      "on"
    );

  }

}


/* =========================================================
   TRACK NAME
   ========================================================= */

function showFloatingTrackName(){

  if(!floatingTrackName){

    return;

  }


  floatingTrackName.textContent =
    trackNames[currentTrack];


  floatingTrackName.style.opacity =
    "1";


  floatingTrackName.style.animation =
    "none";


  setTimeout(

    function(){

      floatingTrackName.style.animation =
        "floatUp 2s ease-out forwards";

    },

    10

  );

}


/* =========================================================
   FERROFLUID
   ========================================================= */

const reduceMotion =
  window.matchMedia(
    "(prefers-reduced-motion: reduce)"
  ).matches;


const centerX =
  window.innerWidth / 2;


const centerY =
  window.innerHeight / 2;


let mx = centerX;

let my = centerY;


window.addEventListener(

  "pointermove",

  function(e){

    if(ferroActive){

      mx = e.clientX;

      my = e.clientY;

    }

  }

);


window.addEventListener(

  "touchmove",

  function(e){

    if(
      ferroActive &&
      e.touches[0]
    ){

      mx =
        e.touches[0].clientX;

      my =
        e.touches[0].clientY;

    }

  },

  {
    passive:true
  }

);


const ferroEls = [

  "ferro-1",

  "ferro-2",

  "ferro-3",

  "ferro-4"

].map(

  id =>
    document.getElementById(id)

);


const ferroState = [

  {
    x:centerX,
    y:centerY,
    vx:0,
    vy:0,
    k:0.05,
    d:0.86,
    ox:0,
    oy:0
  },

  {
    x:centerX,
    y:centerY,
    vx:0,
    vy:0,
    k:0.032,
    d:0.82,
    ox:60,
    oy:-30
  },

  {
    x:centerX,
    y:centerY,
    vx:0,
    vy:0,
    k:0.024,
    d:0.80,
    ox:-70,
    oy:40
  },

  {
    x:centerX,
    y:centerY,
    vx:0,
    vy:0,
    k:0.02,
    d:0.78,
    ox:20,
    oy:70
  }

];


const highlight =
  document.getElementById(
    "ferroHighlight"
  );


function stepFerro(){

  ferroState.forEach(

    function(s,i){

      const ax =
        (mx + s.ox - s.x) *
        s.k;


      const ay =
        (my + s.oy - s.y) *
        s.k;


      s.vx =
        (s.vx + ax) *
        s.d;


      s.vy =
        (s.vy + ay) *
        s.d;


      s.x += s.vx;

      s.y += s.vy;


      if(!reduceMotion){

        ferroEls[i].style.transform =
          `translate3d(${s.x}px,${s.y}px,0)
           translate3d(-50%,-50%,0)`;

      }

    }

  );


  if(!reduceMotion){

    highlight.style.transform =
      `translate3d(
        ${ferroState[0].x - 26}px,
        ${ferroState[0].y - 34}px,
        0
      )
      translate3d(-50%,-50%,0)`;

  }


  requestAnimationFrame(
    stepFerro
  );

}


stepFerro();


/* =========================================================
   FERRO SPIKE
   ========================================================= */

function triggerFerroSpike(){

  const originalK =
    ferroState.map(
      s => s.k
    );


  const spikeStart =
    performance.now();


  const spikeDuration =
    2500;


  function spikeFrame(t){

    const elapsed =
      t - spikeStart;


    const pct =
      Math.min(
        1,
        elapsed / spikeDuration
      );


    const intensity =
      Math.cos(
        pct * Math.PI
      ) * 1.2;


    ferroState.forEach(

      function(s,i){

        s.k =
          originalK[i] *
          (1 + intensity * 6);

      }

    );


    if(pct < 1){

      requestAnimationFrame(
        spikeFrame
      );

    }else{

      ferroState.forEach(

        function(s,i){

          s.k =
            originalK[i];

        }

      );

    }

  }


  requestAnimationFrame(
    spikeFrame
  );

}


/* =========================================================
   SMOOTH SCROLL
   ========================================================= */

function smoothScrollToStage(){

  const stage =
    document.getElementById(
      "stage"
    );


  const start =
    window.scrollY ||
    window.pageYOffset;


  const target =
    stage.offsetTop;


  const distance =
    target - start;


  const duration =
    3500;


  const startTime =
    performance.now();


  function scroll(t){

    const elapsed =
      t - startTime;


    const pct =
      Math.min(
        1,
        elapsed / duration
      );


    const easeOut =
      1 -
      Math.pow(
        1 - pct,
        3
      );


    window.scrollTo(

      0,

      start +
      distance *
      easeOut

    );


    if(pct < 1){

      requestAnimationFrame(
        scroll
      );

    }

  }


  requestAnimationFrame(
    scroll
  );

}


/* =========================================================
   PAGE CONTENT
   ========================================================= */

document.getElementById(
  "js-eyebrow"
).textContent =
  CONFIG.eventTag;


document.getElementById(
  "js-name"
).textContent =
  CONFIG.name;


document.getElementById(
  "js-turns"
).textContent =
  CONFIG.age;


document.getElementById(
  "js-tagline"
).textContent =
  CONFIG.tagline;


document.getElementById(
  "js-date"
).textContent =
  CONFIG.date;


document.getElementById(
  "js-time"
).textContent =
  CONFIG.time;


document.getElementById(
  "js-location"
).textContent =
  CONFIG.location;


document.getElementById(
  "js-address"
).textContent =
  CONFIG.address;


document.getElementById(
  "js-dress"
).textContent =
  CONFIG.dress;


document.getElementById(
  "js-plusone"
).textContent =
  CONFIG.plusOne;


document.getElementById(
  "js-footer-name"
).textContent =
  CONFIG.name;


document.getElementById(
  "js-footer-year"
).textContent =
  new Date().getFullYear();


/* =========================================================
   GOOGLE CALENDAR
   ========================================================= */

const calendarDate =
  "20260918T200000";


const calendarEndDate =
  "20260919T000000";


const calendarTitle =
  encodeURIComponent(
    "Hichmoki's Party - The Ceremony 33"
  );


const calendarLocation =
  encodeURIComponent(
    "Straatweg 60B, 3051 BH Rotterdam"
  );


const calendarDesc =
  encodeURIComponent(
    "Join the party. Good food, warm people, a night that moves. WhatsApp: https://chat.whatsapp.com/CzWo9BidWbLGTedkoEgUsX"
  );


const calendarUrl =
  `https://calendar.google.com/calendar/render?action=TEMPLATE&text=${calendarTitle}&dates=${calendarDate}/${calendarEndDate}&location=${calendarLocation}&details=${calendarDesc}`;


document.getElementById(
  "js-calendar-link"
).href =
  calendarUrl;


const detailCalendarLink =
  document.getElementById(
    "js-calendar-link-detail"
  );


if(detailCalendarLink){

  detailCalendarLink.href =
    calendarUrl;

}


/* =========================================================
   COUNTDOWN
   ========================================================= */

(function initCountdown(){

  const TARGET_DATE =
    "2026-09-18T20:00:00";


  const partyDate =
    new Date(
      TARGET_DATE
    );


  const elDays =
    document.getElementById(
      "cd-days"
    );


  const elHours =
    document.getElementById(
      "cd-hours"
    );


  const elMins =
    document.getElementById(
      "cd-mins"
    );


  const elSecs =
    document.getElementById(
      "cd-secs"
    );


  function tick(){

    const now =
      new Date();


    const diff =
      Math.max(
        0,
        partyDate - now
      );


    const days =
      Math.floor(
        diff / 86400000
      );


    const hours =
      Math.floor(
        (diff / 3600000) % 24
      );


    const mins =
      Math.floor(
        (diff / 60000) % 60
      );


    const secs =
      Math.floor(
        (diff / 1000) % 60
      );


    elDays.textContent =
      String(days).padStart(
        2,
        "0"
      );


    elHours.textContent =
      String(hours).padStart(
        2,
        "0"
      );


    elMins.textContent =
      String(mins).padStart(
        2,
        "0"
      );


    elSecs.textContent =
      String(secs).padStart(
        2,
        "0"
      );

  }


  tick();


  setInterval(
    tick,
    1000
  );

})();

</script>