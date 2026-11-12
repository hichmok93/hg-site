---
layout: none
title: "Pastelaria Nata - Vers in Rotterdam"
date: 2026-11-11 12:00:00 +0100
permalink: /pastel-de-nata/
---
<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Pastelaria Nata — Ambachtelijke Pastéis de Nata in Rotterdam</title>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,600;0,700;1,600&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
  
  <!-- Three.js & OrbitControls -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/controls/OrbitControls.js"></script>

  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            serif: ['"Cormorant Garamond"', 'Georgia', 'serif'],
            sans: ['"Plus Jakarta Sans"', 'sans-serif'],
          },
          colors: {
            cream: '#FAF6F0',
            custard: '#F4B942',
            caramel: '#B85D19',
            crust: '#D99B52',
            azulejo: '#1E4E79',
            espresso: '#23170F',
          }
        }
      }
    }
  </script>

  <style>
    body {
      background-color: #FAF6F0;
      color: #23170F;
      overflow-x: hidden;
    }

    .azulejo-pattern {
      background-color: #1E4E79;
      background-image: 
        radial-gradient(circle at 100% 150%, #1E4E79 24%, #2B6CB0 25%, #2B6CB0 28%, #1E4E79 29%, #1E4E79 36%, #2B6CB0 36%, #2B6CB0 40%, transparent 40%, transparent),
        radial-gradient(circle at 0    150%, #1E4E79 24%, #2B6CB0 25%, #2B6CB0 28%, #1E4E79 29%, #1E4E79 36%, #2B6CB0 36%, #2B6CB0 40%, transparent 40%, transparent),
        radial-gradient(circle at 50%  100%, #2B6CB0 10%, #1E4E79 11%, #1E4E79 23%, #2B6CB0 24%, #2B6CB0 30%, #1E4E79 31%, #1E4E79 43%, #2B6CB0 44%, #2B6CB0 50%, #1E4E79 51%, #1E4E79 63%, #2B6CB0 64%, #2B6CB0 71%, transparent 71%, transparent);
      background-size: 40px 20px;
    }

    #nata-canvas {
      cursor: grab;
      touch-action: none;
    }
    #nata-canvas:active {
      cursor: grabbing;
    }

    .ring-btn {
      transition: all 0.25s cubic-bezier(0.34, 1.56, 0.64, 1);
    }
    .ring-btn:hover {
      transform: scale(1.12);
    }
    .ring-btn.active {
      background-color: #23170F;
      color: #FAF6F0;
      border-color: #F4B942;
      transform: scale(1.15);
      box-shadow: 0 10px 25px -5px rgba(35, 23, 15, 0.4);
    }

    .drawer-enter {
      transform: translateX(0%);
    }
    .drawer-exit {
      transform: translateX(100%);
    }
  </style>
</head>
<body class="font-sans antialiased selection:bg-custard selection:text-espresso">

  <!-- Navigatie -->
  <header class="sticky top-0 z-40 bg-cream/90 backdrop-blur-md border-b border-espresso/10">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 h-16 flex items-center justify-between">
      <a href="#" class="flex items-center gap-2.5">
        <span class="w-8 h-8 rounded-full bg-espresso text-custard flex items-center justify-center font-serif font-bold text-xl">P</span>
        <div>
          <span class="font-serif font-bold text-xl tracking-tight text-espresso block leading-none">Pastelaria Nata</span>
          <span class="text-[11px] uppercase tracking-widest text-caramel font-semibold">Rotterdam • Ovenvers</span>
        </div>
      </a>

      <nav class="hidden md:flex items-center gap-8 text-sm font-medium text-espresso/80">
        <a href="#bestellen" class="hover:text-caramel transition">3D Bestelring</a>
        <a href="#grondstoffen" class="hover:text-caramel transition">Grondstoffen & Kostprijs</a>
        <a href="#bakkerij" class="hover:text-caramel transition">Bedrijfspand Rotterdam</a>
      </nav>

      <button onclick="toggleCart(true)" class="relative flex items-center gap-2 bg-espresso text-cream px-4 py-2 rounded-full text-sm font-medium hover:bg-caramel transition shadow-sm">
        <svg class="w-4 h-4 text-custard" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"></path></svg>
        <span>Winkelwagen</span>
        <span id="cart-badge" class="bg-custard text-espresso text-xs font-bold px-1.5 py-0.5 rounded-full">0</span>
      </button>
    </div>
  </header>

  <!-- Hero & 3D Interactieve Bestelring -->
  <section id="bestellen" class="relative pt-8 pb-16 md:py-16 overflow-hidden">
    <div class="max-w-6xl mx-auto px-4 sm:px-6">
      <div class="text-center max-w-2xl mx-auto mb-6">
        <span class="inline-block px-3 py-1 rounded-full bg-custard/25 text-caramel text-xs font-bold uppercase tracking-wider mb-3">
          Vandaag gebakken aan de Lloydkade • Bezorging in Rotterdam
        </span>
        <h1 class="font-serif text-4xl sm:text-5xl md:text-6xl font-bold text-espresso leading-tight">
          Krokant bladerdeeg, warme gekarameliseerde custard.
        </h1>
        <p class="mt-3 text-espresso/75 text-base sm:text-lg">
          Draai de Pastel de Nata in 3D, kies je aantal op de ring en bestel direct ovenvers aan huis.
        </p>
      </div>

      <!-- 3D Viewport + Bestelring Container -->
      <div class="relative max-w-xl mx-auto aspect-square flex items-center justify-center my-2">
        <!-- Decoratieve achtergrondcirkel -->
        <div class="absolute inset-8 sm:inset-12 rounded-full border-2 border-dashed border-caramel/30 pointer-events-none"></div>
        <div class="absolute inset-16 sm:inset-24 rounded-full bg-gradient-to-b from-custard/20 to-transparent pointer-events-none"></div>

        <!-- Three.js Canvas -->
        <div id="canvas-wrapper" class="w-full h-full relative z-10">
          <canvas id="nata-canvas" class="w-full h-full"></canvas>
        </div>

        <!-- Interactieve Aantal-knoppen rondom de 3D Pastel de Nata -->
        <button onclick="selectQty(1)" id="qty-btn-1" class="ring-btn active absolute top-3 sm:top-5 left-1/2 -translate-x-1/2 z-20 w-16 h-16 sm:w-20 sm:h-20 rounded-full bg-white border-2 border-espresso/15 shadow-lg flex flex-col items-center justify-center">
          <span class="font-serif font-bold text-xl sm:text-2xl leading-none">1x</span>
          <span class="text-[11px] font-semibold opacity-80 mt-0.5">€ 2,95</span>
        </button>

        <button onclick="selectQty(2)" id="qty-btn-2" class="ring-btn absolute top-[22%] right-2 sm:right-5 z-20 w-16 h-16 sm:w-20 sm:h-20 rounded-full bg-white border-2 border-espresso/15 shadow-lg flex flex-col items-center justify-center">
          <span class="font-serif font-bold text-xl sm:text-2xl leading-none">2x</span>
          <span class="text-[11px] font-semibold opacity-80 mt-0.5">€ 5,80</span>
        </button>

        <button onclick="selectQty(4)" id="qty-btn-4" class="ring-btn absolute bottom-[18%] right-3 sm:right-7 z-20 w-16 h-16 sm:w-20 sm:h-20 rounded-full bg-white border-2 border-espresso/15 shadow-lg flex flex-col items-center justify-center">
          <span class="font-serif font-bold text-xl sm:text-2xl leading-none">4x</span>
          <span class="text-[11px] font-semibold opacity-80 mt-0.5">€ 11,20</span>
        </button>

        <button onclick="selectQty(6)" id="qty-btn-6" class="ring-btn absolute bottom-[18%] left-3 sm:left-7 z-20 w-16 h-16 sm:w-20 sm:h-20 rounded-full bg-white border-2 border-espresso/15 shadow-lg flex flex-col items-center justify-center">
          <span class="text-[9px] uppercase font-bold text-caramel tracking-tighter">Doos</span>
          <span class="font-serif font-bold text-xl sm:text-2xl leading-none">6x</span>
          <span class="text-[11px] font-semibold opacity-80">€ 16,50</span>
        </button>

        <button onclick="selectQty(12)" id="qty-btn-12" class="ring-btn absolute top-[22%] left-2 sm:left-5 z-20 w-16 h-16 sm:w-20 sm:h-20 rounded-full bg-white border-2 border-espresso/15 shadow-lg flex flex-col items-center justify-center">
          <span class="text-[9px] uppercase font-bold text-caramel tracking-tighter">Feestdoos</span>
          <span class="font-serif font-bold text-xl sm:text-2xl leading-none">12x</span>
          <span class="text-[11px] font-semibold opacity-80">€ 31,00</span>
        </button>

        <!-- Hint -->
        <div class="absolute bottom-2 left-1/2 -translate-x-1/2 z-20 bg-white/80 backdrop-blur px-3 py-1 rounded-full text-[11px] text-espresso/70 border border-espresso/10 pointer-events-none">
          ↻ Sleep om 360° te bekijken
        </div>
      </div>

      <!-- Direct Bestellen Balk & Bezorgcheck -->
      <div class="max-w-2xl mx-auto mt-6 bg-white rounded-2xl p-5 sm:p-6 shadow-xl border border-espresso/10">
        <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 pb-5 border-b border-espresso/10">
          <div>
            <div class="flex items-center gap-2">
              <h2 id="selected-title" class="font-serif text-2xl font-bold text-espresso">1x Ambachtelijke Pastel de Nata</h2>
              <span id="discount-badge" class="hidden bg-emerald-100 text-emerald-800 text-xs font-bold px-2 py-0.5 rounded-full">Staffelkorting</span>
            </div>
            <p class="text-sm text-espresso/70 mt-0.5">Inclusief zakje Ceylon kaneel & poedersuiker</p>
          </div>
          <div class="flex items-center gap-4">
            <div class="text-right">
              <span id="selected-price" class="font-serif text-3xl font-bold text-espresso">€ 2,95</span>
              <span id="unit-price-note" class="block text-xs text-espresso/60">€ 2,95 per stuk</span>
            </div>
            <button onclick="addSelectedToCart()" class="bg-espresso hover:bg-caramel text-cream font-semibold px-6 py-3.5 rounded-xl transition shadow-md flex items-center gap-2 whitespace-nowrap">
              <span>In doos plaatsen</span>
              <span>+</span>
            </button>
          </div>
        </div>

        <!-- Postcode & Bezorging in Rotterdam -->
        <div class="pt-4 flex flex-col sm:flex-row items-stretch sm:items-center justify-between gap-3">
          <div class="flex items-center gap-2 text-sm font-medium text-espresso">
            <span class="w-2.5 h-2.5 rounded-full bg-emerald-500 animate-pulse"></span>
            <span>Bezorgcheck Rotterdam:</span>
          </div>
          <div class="flex items-center gap-2">
            <input id="postcode-input" type="text" maxlength="7" placeholder="Bijv. 3024 EA" class="border border-espresso/20 rounded-lg px-3 py-1.5 text-sm w-32 focus:outline-none focus:border-caramel uppercase" />
            <button onclick="checkDelivery()" class="bg-cream hover:bg-custard/30 text-espresso border border-espresso/15 text-sm font-semibold px-3.5 py-1.5 rounded-lg transition">
              Check
            </button>
          </div>
        </div>
        <p id="delivery-feedback" class="text-xs text-espresso/70 mt-2">
          Gratis bezorging in Rotterdam (3000–3099) vanaf € 25,00. Anders € 2,95 per fietskoerier.
        </p>
      </div>
    </div>
  </section>

  <!-- Grondstoffen & Kostprijsopbouw -->
  <section id="grondstoffen" class="py-16 bg-white border-y border-espresso/10">
    <div class="max-w-6xl mx-auto px-4 sm:px-6">
      <div class="max-w-2xl mb-10">
        <span class="text-xs font-bold uppercase tracking-widest text-caramel">Transparante Ambacht</span>
        <h2 class="font-serif text-3xl sm:text-4xl font-bold text-espresso mt-1">Grondstoffen & Prijzen per stuk</h2>
        <p class="text-espresso/75 mt-2 text-sm sm:text-base">
          Geen prefab diepvriesdeeg of kunstmatige aroma's. Elke ochtend vanaf 05:30 uur toeren wij ons bladerdeeg met de hand en koken we de custard op basis van pure ingrediënten.
        </p>
      </div>

      <div class="grid md:grid-cols-2 gap-8 items-start">
        <!-- Tabel met grondstoffen -->
        <div class="bg-cream rounded-2xl p-6 border border-espresso/10">
          <h3 class="font-serif text-2xl font-bold mb-4">Ingrediënten & Inkoopwaarde (per Nata ± 65g)</h3>
          <div class="divide-y divide-espresso/10 text-sm">
            <div class="py-3 flex justify-between items-center">
              <div>
                <p class="font-semibold text-espresso">Franse Roomboter (82% vet, toerboter)</p>
                <p class="text-xs text-espresso/60">16g per stuk • € 11,50 / kg inkoop</p>
              </div>
              <span class="font-mono font-semibold text-espresso">€ 0,18</span>
            </div>
            <div class="py-3 flex justify-between items-center">
              <div>
                <p class="font-semibold text-espresso">Vrije-uitloop Eidooiers (vers gescheiden)</p>
                <p class="text-xs text-espresso/60">1,1 dooier per stuk • € 0,24 / dooier</p>
              </div>
              <span class="font-mono font-semibold text-espresso">€ 0,26</span>
            </div>
            <div class="py-3 flex justify-between items-center">
              <div>
                <p class="font-semibold text-espresso">Biologische Volle Melk & Slagroom</p>
                <p class="text-xs text-espresso/60">24ml per stuk • € 1,85 / liter</p>
              </div>
              <span class="font-mono font-semibold text-espresso">€ 0,05</span>
            </div>
            <div class="py-3 flex justify-between items-center">
              <div>
                <p class="font-semibold text-espresso">T55 Patentbloem & Kristalsuiker</p>
                <p class="text-xs text-espresso/60">22g bloem + 14g suiker voor siroop</p>
              </div>
              <span class="font-mono font-semibold text-espresso">€ 0,06</span>
            </div>
            <div class="py-3 flex justify-between items-center">
              <div>
                <p class="font-semibold text-espresso">Ceylon Kaneelstokjes, Bourbon Vanille & Citroenschil</p>
                <p class="text-xs text-espresso/60">Infusie voor de suikersiroop & strooikaneel</p>
              </div>
              <span class="font-mono font-semibold text-espresso">€ 0,09</span>
            </div>
            <div class="py-3 flex justify-between items-center">
              <div>
                <p class="font-semibold text-espresso">Bakvormpje, kraft doosje & kaneelzakje</p>
                <p class="text-xs text-espresso/60">Vetvrij bakpapier & bedrukte verpakking</p>
              </div>
              <span class="font-mono font-semibold text-espresso">€ 0,14</span>
            </div>
            <div class="pt-4 flex justify-between items-center font-bold text-base text-caramel">
              <span>Totale directe grondstof- & verpakkingskosten</span>
              <span class="font-mono">€ 0,78 / stuk</span>
            </div>
          </div>
        </div>

        <!-- Marge & Staffel Uitleg -->
        <div class="space-y-6">
          <div class="azulejo-pattern text-white rounded-2xl p-6 sm:p-8 shadow-lg">
            <h3 class="font-serif text-2xl sm:text-3xl font-bold mb-2">Waarom € 2,95 per stuk?</h3>
            <p class="text-white/90 text-sm leading-relaxed mb-4">
              Een Pastel de Nata vereist 3 dagen voorbereiding voor het lamineren en rusten van het bladerdeeg, plus afbakken op 290°C in onze steenoven aan de Lloydkade.
            </p>
            <div class="grid grid-cols-3 gap-3 text-center pt-2">
              <div class="bg-white/10 backdrop-blur rounded-xl p-3">
                <span class="block font-serif text-2xl font-bold text-custard">26%</span>
                <span class="text-[11px] uppercase tracking-wider">Grondstoffen</span>
              </div>
              <div class="bg-white/10 backdrop-blur rounded-xl p-3">
                <span class="block font-serif text-2xl font-bold text-custard">44%</span>
                <span class="text-[11px] uppercase tracking-wider">Arbeid & Oven</span>
              </div>
              <div class="bg-white/10 backdrop-blur rounded-xl p-3">
                <span class="block font-serif text-2xl font-bold text-custard">30%</span>
                <span class="text-[11px] uppercase tracking-wider">Pand & Marge</span>
              </div>
            </div>
          </div>

          <div class="bg-cream rounded-2xl p-6 border border-espresso/10">
            <h4 class="font-serif text-xl font-bold mb-3">Staffelprijzen Webshop</h4>
            <div class="grid grid-cols-2 sm:grid-cols-3 gap-3 text-sm">
              <div class="bg-white p-3 rounded-xl border border-espresso/10">
                <span class="font-bold block">1 stuk</span>
                <span class="text-caramel font-semibold">€ 2,95</span>
              </div>
              <div class="bg-white p-3 rounded-xl border border-espresso/10">
                <span class="font-bold block">Doos van 6</span>
                <span class="text-caramel font-semibold">€ 16,50 (€ 2,75/st)</span>
              </div>
              <div class="bg-white p-3 rounded-xl border border-espresso/10 col-span-2 sm:col-span-1">
                <span class="font-bold block">Feestdoos 12</span>
                <span class="text-caramel font-semibold">€ 31,00 (€ 2,58/st)</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Bedrijfspand & Zelfgehoste Architectuur -->
  <section id="bakkerij" class="py-16">
    <div class="max-w-6xl mx-auto px-4 sm:px-6">
      <div class="grid md:grid-cols-2 gap-10 items-center">
        <!-- Visuele voorstelling van het bedrijfspand -->
        <div class="relative rounded-2xl overflow-hidden shadow-xl border border-espresso/15 bg-espresso text-cream p-8">
          <div class="flex items-center justify-between border-b border-white/15 pb-4 mb-6">
            <div>
              <span class="text-xs uppercase tracking-widest text-custard font-bold">Productielocatie & Afhaalpunt</span>
              <h3 class="font-serif text-2xl font-bold mt-0.5">Lloydkade 42, 3024 EA Rotterdam</h3>
            </div>
            <span class="px-3 py-1 rounded-full bg-emerald-500/20 text-emerald-300 text-xs font-semibold">Open 08:00 - 18:00</span>
          </div>

          <!-- Architectonische plattegrond / pand schets in SVG -->
          <svg viewBox="0 0 400 210" class="w-full h-auto rounded-xl bg-[#18100A] border border-white/10 p-3 mb-6">
            <rect x="20" y="30" width="360" height="150" rx="6" fill="#2A1C12" stroke="#D99B52" stroke-width="2"/>
            <!-- Ramen pui -->
            <rect x="35" y="45" width="90" height="60" fill="#F4B942" fill-opacity="0.18" stroke="#F4B942" stroke-width="1.5"/>
            <text x="80" y="80" fill="#FAF6F0" font-size="10" text-anchor="middle" font-family="sans-serif">Etalage & Afhaal</text>
            <!-- Open Bakkerij -->
            <rect x="140" y="45" width="120" height="60" fill="#1E4E79" fill-opacity="0.45" stroke="#63B3ED" stroke-width="1.5"/>
            <text x="200" y="80" fill="#FAF6F0" font-size="10" text-anchor="middle" font-family="sans-serif">Toer- & Koelruimte</text>
            <!-- Steenoven -->
            <rect x="275" y="45" width="90" height="60" fill="#B85D19" fill-opacity="0.5" stroke="#F4B942" stroke-width="1.5"/>
            <text x="320" y="80" fill="#FAF6F0" font-size="10" text-anchor="middle" font-family="sans-serif">290°C Steenoven</text>
            <!-- Bezorging -->
            <line x1="20" y1="130" x2="380" y2="130" stroke="#FAF6F0" stroke-opacity="0.2" stroke-dasharray="4 4"/>
            <text x="200" y="158" fill="#F4B942" font-size="11" text-anchor="middle" font-family="sans-serif">Laadzone Elektrische Bakfietsen • Direct naar klant</text>
          </svg>

          <div class="grid grid-cols-2 gap-4 text-sm">
            <div>
              <span class="text-white/60 block text-xs">Oppervlakte Bedrijfspand</span>
              <span class="font-semibold">115 m² (Begane grond, Lloydkwartier)</span>
            </div>
            <div>
              <span class="text-white/60 block text-xs">Capaciteit</span>
              <span class="font-semibold">1.200 Pastéis de Nata per dag</span>
            </div>
          </div>
        </div>

        <!-- Zelfgehoste Webshop Uitleg -->
        <div>
          <span class="text-xs font-bold uppercase tracking-widest text-caramel">Zelfgehoste Webshop Demo</span>
          <h2 class="font-serif text-3xl sm:text-4xl font-bold text-espresso mt-1">Volledig in eigen beheer, nul commissie</h2>
          <p class="text-espresso/75 mt-3 leading-relaxed">
            In plaats van 30% commissie af te dragen aan bezorgplatforms draait deze webshop zelfgehost op je eigen domein (bijv. via GitHub Pages of een eigen VPS met Mollie/Stripe webhook).
          </p>
          <ul class="mt-5 space-y-3 text-sm text-espresso/85">
            <li class="flex items-start gap-2.5">
              <span class="text-caramel font-bold">✓</span>
              <span><strong>Directe bezorging vanuit Rotterdam:</strong> Koppeling op postcodegebied (3000–3199) met tijdvakken voor ovenverse levering.</span>
            </li>
            <li class="flex items-start gap-2.5">
              <span class="text-caramel font-bold">✓</span>
              <span><strong>Interactieve 3D productbeleving:</strong> Gebouwd met pure HTML, Tailwind en Three.js — laadt razendsnel zonder zware plugins.</span>
            </li>
            <li class="flex items-start gap-2.5">
              <span class="text-caramel font-bold">✓</span>
              <span><strong>Klaar voor koppeling:</strong> Eenvoudig te verbinden met Mollie iDEAL-betaallinks en je eigen bezorgplanning.</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-espresso text-cream/70 py-10 text-sm">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 flex flex-col sm:flex-row items-center justify-between gap-4">
      <div>
        <span class="font-serif text-lg font-bold text-cream">Pastelaria Nata Rotterdam</span>
        <span class="block text-xs mt-0.5">Lloydkade 42, 3024 EA Rotterdam • KvK Demo</span>
      </div>
      <div class="text-xs">
        Zelfgehoste 3D Webshop Demo • Vers gebakken op bestelling
      </div>
    </div>
  </footer>

  <!-- Winkelwagen Slide-over Drawer -->
  <div id="cart-overlay" onclick="toggleCart(false)" class="fixed inset-0 bg-espresso/50 backdrop-blur-xs z-50 hidden transition-opacity"></div>
  <aside id="cart-drawer" class="fixed top-0 right-0 h-full w-full max-w-md bg-cream z-50 shadow-2xl border-l border-espresso/15 flex flex-col transition-transform duration-300 drawer-exit">
    <div class="p-5 bg-white border-b border-espresso/10 flex items-center justify-between">
      <h3 class="font-serif text-2xl font-bold text-espresso">Jouw Bestelling</h3>
      <button onclick="toggleCart(false)" class="p-2 rounded-lg hover:bg-cream text-espresso/70">✕</button>
    </div>

    <div id="cart-items" class="flex-1 overflow-y-auto p-5 space-y-4">
      <!-- Items worden dynamisch ingeladen -->
    </div>

    <!-- Bezorgopties & Afrekenen -->
    <div class="p-5 bg-white border-t border-espresso/10 space-y-4">
      <div>
        <label class="block text-xs font-bold uppercase tracking-wider text-espresso/70 mb-1.5">Bezorging of Afhalen (Rotterdam)</label>
        <select id="delivery-slot" class="w-full border border-espresso/20 rounded-xl px-3 py-2 text-sm bg-cream">
          <option value="2.95">Bezorgen Rotterdam — Vandaag ovenvers (14:00 - 17:00)</option>
          <option value="2.95">Bezorgen Rotterdam — Vandaag avond (18:00 - 20:30)</option>
          <option value="0">Afhalen Lloydkade 42, Rotterdam (Gratis)</option>
        </select>
      </div>

      <div class="space-y-1 text-sm">
        <div class="flex justify-between text-espresso/70">
          <span>Subtotaal</span>
          <span id="cart-subtotal">€ 0,00</span>
        </div>
        <div class="flex justify-between text-espresso/70">
          <span>Bezorgkosten</span>
          <span id="cart-shipping">€ 2,95</span>
        </div>
        <div class="flex justify-between font-bold text-lg text-espresso pt-2 border-t border-espresso/10">
          <span>Totaal (incl. 9% btw)</span>
          <span id="cart-total">€ 0,00</span>
        </div>
      </div>

      <button onclick="checkoutDemo()" class="w-full bg-espresso hover:bg-caramel text-cream font-bold py-3.5 rounded-xl transition shadow-md">
        Demo Bestelling Plaatsen (iDEAL)
      </button>
    </div>
  </aside>

  <!-- Bevestigingsmodal voor Demo Bestelling -->
  <div id="order-modal" class="fixed inset-0 bg-espresso/60 backdrop-blur-xs z-50 hidden items-center justify-center p-4">
    <div class="bg-white rounded-2xl max-w-md w-full p-6 sm:p-8 text-center shadow-2xl border border-espresso/10">
      <div class="w-14 h-14 rounded-full bg-emerald-100 text-emerald-700 flex items-center justify-center mx-auto text-2xl font-bold mb-4">✓</div>
      <h3 class="font-serif text-3xl font-bold text-espresso">De oven gaat aan!</h3>
      <p class="text-sm text-espresso/75 mt-2">
        Bedankt voor je testbestelling bij <strong>Pastelaria Nata Rotterdam</strong>. In een live productie-omgeving word je nu doorgestuurd naar Mollie iDEAL en ontvangt de bakkerij aan de Lloydkade direct de bakbon.
      </p>
      <div id="order-summary-box" class="mt-4 bg-cream rounded-xl p-4 text-left text-xs space-y-1 border border-espresso/10"></div>
      <button onclick="closeOrderModal()" class="mt-6 w-full bg-espresso text-cream font-semibold py-3 rounded-xl hover:bg-caramel transition">
        Terug naar de 3D webshop
      </button>
    </div>
  </div>

  <script>
    // ==========================================
    // 1. PRODUCTPRIJZEN & WINKELWAGEN LOGICA
    // ==========================================
    const bundles = {
      1:  { qty: 1,  price: 2.95,  label: '1x Ambachtelijke Pastel de Nata', badge: false },
      2:  { qty: 2,  price: 5.80,  label: '2x Ambachtelijke Pastéis de Nata', badge: false },
      4:  { qty: 4,  price: 11.20, label: '4x Doosje Pastéis de Nata', badge: true },
      6:  { qty: 6,  price: 16.50, label: '6x Cadeaudoos Pastéis de Nata', badge: true },
      12: { qty: 12, price: 31.00, label: '12x Feestdoos Pastéis de Nata', badge: true }
    };

    let currentSelection = 1;
    let cart = [];

    function formatEuro(amount) {
      return '€ ' + amount.toFixed(2).replace('.', ',');
    }

    function selectQty(qty) {
      currentSelection = qty;
      const item = bundles[qty];

      document.querySelectorAll('.ring-btn').forEach(btn => btn.classList.remove('active'));
      document.getElementById(`qty-btn-${qty}`).classList.add('active');

      document.getElementById('selected-title').textContent = item.label;
      document.getElementById('selected-price').textContent = formatEuro(item.price);
      document.getElementById('unit-price-note').textContent = `${formatEuro(item.price / item.qty)} per stuk`;

      const badge = document.getElementById('discount-badge');
      if (item.badge) {
        badge.classList.remove('hidden');
      } else {
        badge.classList.add('hidden');
      }

      // Kleine bounce animatie op het 3D model bij wisselen van aantal
      if (window.nataGroup) {
        window.nataBounce = 0.25;
      }
    }

    function addSelectedToCart() {
      const item = bundles[currentSelection];
      const existing = cart.find(c => c.qty === item.qty);
      if (existing) {
        existing.count += 1;
      } else {
        cart.push({ ...item, count: 1 });
      }
      renderCart();
      toggleCart(true);
    }

    function updateCartItem(index, delta) {
      cart[index].count += delta;
      if (cart[index].count <= 0) {
        cart.splice(index, 1);
      }
      renderCart();
    }

    function renderCart() {
      const container = document.getElementById('cart-items');
      const totalItems = cart.reduce((sum, item) => sum + (item.qty * item.count), 0);
      document.getElementById('cart-badge').textContent = totalItems;

      if (cart.length === 0) {
        container.innerHTML = `
          <div class="text-center py-12 text-espresso/60">
            <p class="font-serif text-xl mb-1">Je doos is nog leeg</p>
            <p class="text-xs">Kies een aantal rondom de 3D Pastel de Nata om te beginnen.</p>
          </div>`;
        document.getElementById('cart-subtotal').textContent = '€ 0,00';
        document.getElementById('cart-shipping').textContent = '€ 0,00';
        document.getElementById('cart-total').textContent = '€ 0,00';
        return;
      }

      let subtotal = 0;
      container.innerHTML = cart.map((item, idx) => {
        const lineTotal = item.price * item.count;
        subtotal += lineTotal;
        return `
          <div class="bg-white p-4 rounded-xl border border-espresso/10 flex items-center justify-between gap-3">
            <div>
              <p class="font-bold text-sm text-espresso">${item.label}</p>
              <p class="text-xs text-espresso/60">${formatEuro(item.price)} per verpakking</p>
            </div>
            <div class="flex items-center gap-2">
              <button onclick="updateCartItem(${idx}, -1)" class="w-7 h-7 rounded-lg bg-cream font-bold text-espresso hover:bg-custard/40">-</button>
              <span class="text-sm font-bold w-5 text-center">${item.count}</span>
              <button onclick="updateCartItem(${idx}, 1)" class="w-7 h-7 rounded-lg bg-cream font-bold text-espresso hover:bg-custard/40">+</button>
              <span class="font-bold text-sm w-16 text-right">${formatEuro(lineTotal)}</span>
            </div>
          </div>
        `;
      }).join('');

      const slotSelect = document.getElementById('delivery-slot');
      let shipping = parseFloat(slotSelect.value);
      if (subtotal >= 25) shipping = 0;

      document.getElementById('cart-subtotal').textContent = formatEuro(subtotal);
      document.getElementById('cart-shipping').textContent = shipping === 0 ? 'Gratis' : formatEuro(shipping);
      document.getElementById('cart-total').textContent = formatEuro(subtotal + shipping);
    }

    document.getElementById('delivery-slot').addEventListener('change', renderCart);

    function toggleCart(open) {
      const overlay = document.getElementById('cart-overlay');
      const drawer = document.getElementById('cart-drawer');
      if (open) {
        overlay.classList.remove('hidden');
        drawer.classList.remove('drawer-exit');
        drawer.classList.add('drawer-enter');
      } else {
        overlay.classList.add('hidden');
        drawer.classList.remove('drawer-enter');
        drawer.classList.add('drawer-exit');
      }
    }

    function checkDelivery() {
      const raw = document.getElementById('postcode-input').value.trim().toUpperCase();
      const feedback = document.getElementById('delivery-feedback');
      const digits = parseInt(raw.substring(0, 4), 10);

      if (!digits || digits < 1000 || digits > 9999) {
        feedback.innerHTML = `<span class="text-caramel font-semibold">Vul een geldige Nederlandse postcode in (bijv. 3024 EA).</span>`;
        return;
      }

      if (digits >= 3000 && digits <= 3099) {
        feedback.innerHTML = `<span class="text-emerald-700 font-semibold">✓ Top! Postcode ${raw} valt binnen Rotterdam Centrum/Noord/Zuid/West/Oost. Vandaag ovenvers bezorgd per fietskoerier!</span>`;
      } else if (digits >= 3100 && digits <= 3199) {
        feedback.innerHTML = `<span class="text-emerald-700 font-semibold">✓ Postcode ${raw} (Schiedam/Vlaardingen/Hoogvliet) valt binnen onze regio-bezorging!</span>`;
      } else {
        feedback.innerHTML = `<span class="text-caramel font-semibold">Postcode ${raw} ligt buiten onze directe fietskoerier-zone. Verzending per gekoelde pakketdienst (volgende werkdag) is wel mogelijk!</span>`;
      }
    }

    function checkoutDemo() {
      if (cart.length === 0) return;
      const total = document.getElementById('cart-total').textContent;
      const slot = document.getElementById('delivery-slot').selectedOptions[0].text;
      document.getElementById('order-summary-box').innerHTML = `
        <p><strong>Totaalbedrag:</strong> ${total}</p>
        <p><strong>Levermethode:</strong> ${slot}</p>
        <p><strong>Bakkerij:</strong> Lloydkade 42, Rotterdam</p>
      `;
      toggleCart(false);
      const modal = document.getElementById('order-modal');
      modal.classList.remove('hidden');
      modal.classList.add('flex');
      cart = [];
      renderCart();
    }

    function closeOrderModal() {
      const modal = document.getElementById('order-modal');
      modal.classList.add('hidden');
      modal.classList.remove('flex');
    }

    // ==========================================
    // 2. THREE.JS 3D PASTEL DE NATA MODEL
    // ==========================================
    function init3DNata() {
      const canvas = document.getElementById('nata-canvas');
      const wrapper = document.getElementById('canvas-wrapper');

      const scene = new THREE.Scene();
      const camera = new THREE.PerspectiveCamera(36, wrapper.clientWidth / wrapper.clientHeight, 0.1, 100);
      camera.position.set(0, 3.6, 5.2);

      const renderer = new THREE.WebGLRenderer({ canvas, antialias: true, alpha: true });
      renderer.setSize(wrapper.clientWidth, wrapper.clientHeight);
      renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
      renderer.shadowMap.enabled = true;
      renderer.shadowMap.type = THREE.PCFSoftShadowMap;

      // Verlichting
      const ambientLight = new THREE.AmbientLight(0xfff5e6, 0.75);
      scene.add(ambientLight);

      const keyLight = new THREE.DirectionalLight(0xfffaed, 1.15);
      keyLight.position.set(4, 7, 5);
      keyLight.castShadow = true;
      keyLight.shadow.mapSize.width = 1024;
      keyLight.shadow.mapSize.height = 1024;
      scene.add(keyLight);

      const rimLight = new THREE.DirectionalLight(0xf4b942, 0.55);
      rimLight.position.set(-5, 3, -4);
      scene.add(rimLight);

      const nataGroup = new THREE.Group();
      window.nataGroup = nataGroup;
      window.nataBounce = 0;

      // Portugees Azulejo Schoteltje
      const plateGeo = new THREE.CylinderGeometry(2.05, 1.55, 0.16, 48);
      const plateMat = new THREE.MeshStandardMaterial({
        color: 0xffffff,
        roughness: 0.18,
        metalness: 0.05
      });
      const plate = new THREE.Mesh(plateGeo, plateMat);
      plate.position.y = -0.68;
      plate.receiveShadow = true;
      nataGroup.add(plate);

      // Blauwe Azulejo rand op het schoteltje
      const ringGeo = new THREE.RingGeometry(1.62, 1.88, 48);
      const ringMat = new THREE.MeshStandardMaterial({
        color: 0x1E4E79,
        roughness: 0.25,
        side: THREE.DoubleSide
      });
      const ring = new THREE.Mesh(ringGeo, ringMat);
      ring.rotation.x = -Math.PI / 2;
      ring.position.y = -0.598;
      nataGroup.add(ring);

      // Bladerdeeg Kuipje (met gelamineerde ribbels)
      const crustGroup = new THREE.Group();
      const layers = 14;
      for (let i = 0; i < layers; i++) {
        const t = i / (layers - 1);
        const radiusBottom = 0.92 + t * 0.42;
        const radiusTop = 0.96 + t * 0.46;
        const height = 0.09;
        const geo = new THREE.CylinderGeometry(radiusTop, radiusBottom, height, 40, 1, false);
        
        // Lichte variatie in goudbruine tinten voor bladerdeeg-effect
        const shade = new THREE.Color().setHSL(0.085, 0.65, 0.42 + (i % 3) * 0.05);
        const mat = new THREE.MeshStandardMaterial({
          color: shade,
          roughness: 0.72,
          metalness: 0.02
        });
        const layerMesh = new THREE.Mesh(geo, mat);
        layerMesh.position.y = -0.55 + i * 0.075;
        layerMesh.castShadow = true;
        layerMesh.receiveShadow = true;
        crustGroup.add(layerMesh);
      }

      // Gekartelde krokante bovenrand van het bladerdeeg
      const rimCount = 36;
      for (let i = 0; i < rimCount; i++) {
        const angle = (i / rimCount) * Math.PI * 2;
        const puffGeo = new THREE.DodecahedronGeometry(0.13, 1);
        const puffMat = new THREE.MeshStandardMaterial({
          color: i % 2 === 0 ? 0xC97A2B : 0xA85719,
          roughness: 0.78
        });
        const puff = new THREE.Mesh(puffGeo, puffMat);
        puff.position.set(
          Math.cos(angle) * 1.38,
          0.46 + Math.sin(i * 3) * 0.03,
          Math.sin(angle) * 1.38
        );
        puff.scale.set(1.1, 0.85, 0.8);
        puff.castShadow = true;
        crustGroup.add(puff);
      }
      nataGroup.add(crustGroup);

      // Custard Vulling met gekarameliseerde blaren (canvas texture)
      const custardCanvas = document.createElement('canvas');
      custardCanvas.width = 512;
      custardCanvas.height = 512;
      const ctx = custardCanvas.getContext('2d');

      // Romige gele custard basis
      const grad = ctx.createRadialGradient(256, 256, 30, 256, 256, 256);
      grad.addColorStop(0, '#F7C948');
      grad.addColorStop(0.75, '#E5A124');
      grad.addColorStop(1, '#B85D19');
      ctx.fillStyle = grad;
      ctx.fillRect(0, 0, 512, 512);

      // Karakteristieke donkere karamel-vlekken bovenop
      const spots = [
        { x: 210, y: 195, r: 58, a: 0.82 },
        { x: 305, y: 230, r: 46, a: 0.78 },
        { x: 245, y: 310, r: 52, a: 0.85 },
        { x: 175, y: 280, r: 34, a: 0.72 },
        { x: 315, y: 165, r: 28, a: 0.68 },
        { x: 265, y: 145, r: 24, a: 0.65 }
      ];

      spots.forEach(s => {
        const sGrad = ctx.createRadialGradient(s.x, s.y, 4, s.x, s.y, s.r);
        sGrad.addColorStop(0, `rgba(38, 16, 4, ${s.a})`);
        sGrad.addColorStop(0.65, `rgba(92, 38, 9, ${s.a * 0.75})`);
        sGrad.addColorStop(1, 'rgba(229, 161, 36, 0)');
        ctx.fillStyle = sGrad;
        ctx.beginPath();
        ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
        ctx.fill();
      });

      // Subtiel kaneelpoeder
      for (let i = 0; i < 450; i++) {
        const rx = Math.random() * 512;
        const ry = Math.random() * 512;
        ctx.fillStyle = 'rgba(110, 48, 12, 0.35)';
        ctx.fillRect(rx, ry, 2, 2);
      }

      const custardTexture = new THREE.CanvasTexture(custardCanvas);
      const custardGeo = new THREE.CylinderGeometry(1.33, 1.25, 0.14, 48);
      const custardMat = new THREE.MeshStandardMaterial({
        map: custardTexture,
        roughness: 0.22,
        metalness: 0.04
      });
      const custard = new THREE.Mesh(custardGeo, custardMat);
      custard.position.y = 0.42;
      nataGroup.add(custard);

      scene.add(nataGroup);

      // OrbitControls voor 360° draaien
      const controls = new THREE.OrbitControls(camera, renderer.domElement);
      controls.enableDamping = true;
      controls.dampingFactor = 0.06;
      controls.enableZoom = false;
      controls.enablePan = false;
      controls.minPolarAngle = 0.25;
      controls.maxPolarAngle = Math.PI / 2.05;

      // Animatieloop
      let clock = new THREE.Clock();
      function animate() {
        requestAnimationFrame(animate);
        const dt = clock.getDelta();

        nataGroup.rotation.y += dt * 0.35;

        if (window.nataBounce > 0) {
          nataGroup.position.y = Math.sin(window.nataBounce * Math.PI * 4) * 0.14;
          window.nataBounce -= dt * 1.4;
          if (window.nataBounce < 0) {
            window.nataBounce = 0;
            nataGroup.position.y = 0;
          }
        }

        controls.update();
        renderer.render(scene, camera);
      }
      animate();

      // Responsief schalen bij vensterwijziging
      window.addEventListener('resize', () => {
        if (!wrapper.clientWidth) return;
        camera.aspect = wrapper.clientWidth / wrapper.clientHeight;
        camera.updateProjectionMatrix();
        renderer.setSize(wrapper.clientWidth, wrapper.clientHeight);
      });
    }

    window.addEventListener('DOMContentLoaded', () => {
      init3DNata();
      renderCart();
    });
  </script>
</body>
</html>
