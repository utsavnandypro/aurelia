:root {
  --plum: #2A1E3B;
  --plum-soft: #3B2A52;
  --flame: #F4B84A;
  --flame-hot: #FFE3A0;
  --mist: #F5F1F6;
  --lilac: #E7DEEC;
  --muted: #655873;
  --serif: "Instrument Serif", Georgia, "Times New Roman", serif;
  --sans: "Hanken Grotesk", system-ui, -apple-system, "Segoe UI", sans-serif;
}

*, *::before, *::after { box-sizing: border-box; }
html { scroll-behavior: smooth; }
body { margin: 0; background: var(--mist); color: var(--plum); font: 400 1.0625rem/1.6 var(--sans); }
img, svg { max-width: 100%; }
h1, h2, h3, p, ul, ol { margin: 0; }
a { color: inherit; }
:focus-visible { outline: 3px solid #6B3FD0; outline-offset: 3px; }
.on-dark :focus-visible { outline-color: var(--flame); }

.wrap { width: min(1200px, 100% - 3rem); margin-inline: auto; }
.skip { position: absolute; left: 1rem; top: -4rem; background: var(--flame); color: var(--plum); padding: .5rem 1rem; z-index: 10; }
.skip:focus { top: 1rem; }
.on-dark { background: var(--plum); color: var(--mist); }

/* Type */
h1, h2, h3, .mark { font-family: var(--serif); font-weight: 400; }
h1 { font-size: clamp(3.25rem, 8vw, 6.5rem); line-height: .96; letter-spacing: -.015em; }
h2 { font-size: clamp(2.25rem, 4.5vw, 3.5rem); line-height: 1.05; }
h3 { font-size: 1.6rem; line-height: 1.15; }
.lead { margin-top: 1rem; max-width: 34rem; color: var(--muted); }
.on-dark .lead { color: var(--lilac); }

/* Buttons */
.btn { display: inline-block; padding: .85rem 1.6rem; border: 0; border-radius: 999px; background: var(--flame); color: var(--plum); font: 600 1rem var(--sans); text-decoration: none; cursor: pointer; }
.btn:hover { background: var(--flame-hot); }
.btn-quiet { background: transparent; color: inherit; box-shadow: inset 0 0 0 1.5px currentColor; }
.btn-quiet:hover { background: rgba(245, 241, 246, .12); }

/* Header + hero */
.stage { overflow: clip; }
.top { display: flex; flex-wrap: wrap; align-items: baseline; justify-content: space-between; gap: .75rem 2rem; padding-block: 1.75rem; }
.mark { font-size: 2rem; text-decoration: none; letter-spacing: .01em; }
.top nav { display: flex; flex-wrap: wrap; gap: .5rem 1.75rem; }
.top nav a { text-decoration: none; }
.top nav a:hover { text-decoration: underline; text-underline-offset: 6px; }

.hero { display: grid; grid-template-columns: 1.1fr .9fr; align-items: center; gap: 2rem; min-height: min(80vh, 760px); padding-block: 2rem 3rem; }
.hero-copy p { margin-top: 1.5rem; max-width: 30rem; font-size: 1.25rem; color: var(--lilac); }
.actions { display: flex; flex-wrap: wrap; gap: .75rem; margin-top: 2rem; }

/* The one memorable thing: a lit candle, pure CSS and inline SVG */
.scene { position: relative; width: min(100%, 380px); height: 520px; margin-inline: auto; }
.glow { position: absolute; left: 50%; top: 110px; width: 560px; height: 560px; border-radius: 50%; transform: translate(-50%, -50%); background: radial-gradient(circle, rgba(244, 184, 74, .5) 0%, rgba(244, 184, 74, .16) 35%, transparent 65%); animation: breathe 5s ease-in-out infinite; }
.flame { position: absolute; left: 50%; top: 40px; width: 44px; height: 88px; margin-left: -22px; transform-origin: 50% 100%; animation: flicker 3.4s ease-in-out infinite; }
.wick { position: absolute; left: 50%; top: 124px; width: 3px; height: 24px; margin-left: -1.5px; border-radius: 2px; background: #1A1222; }
.pillar { position: absolute; left: 50%; top: 146px; bottom: 26px; width: 160px; margin-left: -80px; border-radius: 6px 6px 12px 12px; background: linear-gradient(90deg, #CDBFD6 0%, #EFE6EF 30%, #F7F0F7 55%, #D9CDE0 100%); box-shadow: inset 0 50px 50px -30px rgba(244, 184, 74, .6); }
.pillar::before { content: ""; position: absolute; left: 0; right: 0; top: -9px; height: 18px; border-radius: 50%; background: radial-gradient(ellipse at 50% 60%, #FFE3A0, #E9CF9C 55%, #D4BFA8); }
.pillar::after { content: ""; position: absolute; left: 24px; top: 8px; width: 14px; height: 72px; border-radius: 0 0 7px 7px; background: linear-gradient(#F7F0F7, #E6DAE8); box-shadow: 2px 0 4px rgba(42, 30, 59, .12); }
.dish { position: absolute; bottom: 0; left: 50%; width: 250px; height: 40px; margin-left: -125px; border-radius: 50%; background: radial-gradient(ellipse at 50% 30%, #5A4577, var(--plum-soft) 70%); box-shadow: 0 0 40px rgba(244, 184, 74, .18); z-index: -1; }

@keyframes flicker {
  0%, 100% { transform: scale(1, 1) rotate(0deg); }
  18% { transform: scale(.96, 1.05) rotate(-1.5deg); }
  37% { transform: scale(1.03, .97) rotate(1.2deg); }
  55% { transform: scale(.98, 1.04) rotate(-.8deg); }
  78% { transform: scale(1.02, .98) rotate(1deg); }
}
@keyframes breathe {
  0%, 100% { opacity: .85; transform: translate(-50%, -50%) scale(1); }
  50% { opacity: 1; transform: translate(-50%, -50%) scale(1.05); }
}

.facts { display: grid; grid-template-columns: repeat(3, 1fr); gap: 2rem; padding: 2rem 0 3rem; border-top: 1px solid rgba(245, 241, 246, .2); list-style: none; color: var(--lilac); }
.facts strong { display: block; color: var(--mist); font-weight: 600; }

/* Sections */
.section { padding-block: clamp(4rem, 9vw, 7.5rem); }
.tinted { background: var(--lilac); }

/* Products */
.grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 3.5rem 2rem; margin-top: 3.5rem; }
.tile { display: flex; align-items: flex-end; justify-content: center; aspect-ratio: 4 / 5; padding-bottom: 12%; margin-bottom: 1.25rem; border-radius: 50% 50% 14px 14px / 40% 40% 14px 14px; background: var(--tint); }
.product p { color: var(--muted); }
.buy { display: flex; align-items: baseline; justify-content: space-between; margin-top: .75rem; }
.buy b { color: var(--plum); font-weight: 600; }
.buy a { color: var(--plum); text-underline-offset: 5px; }
.buy a:hover { text-decoration-thickness: 2px; }

.jar { position: relative; width: 52%; aspect-ratio: 1 / 1.02; container-type: inline-size; border-radius: 8px 8px 22px 22px; background: linear-gradient(100deg, rgba(255, 255, 255, .35), rgba(255, 255, 255, 0) 30%, rgba(0, 0, 0, .16) 100%), var(--jar); box-shadow: 0 18px 24px -14px rgba(42, 30, 59, .5); }
.jar::before { content: ""; position: absolute; left: 0; right: 0; top: -6%; height: 12%; border-radius: 50%; background: var(--jar); filter: brightness(1.08); }
.jar::after { content: ""; position: absolute; left: 50%; top: -17%; width: 2px; height: 14%; margin-left: -1px; background: #2B2230; }
.jar span { position: absolute; inset: 30% 14% 14%; display: grid; place-content: center; text-align: center; border-radius: 3px; background: var(--mist); color: var(--plum); font-family: var(--serif); line-height: 1.1; }
.jar b { font-weight: 400; font-size: 13px; font-size: 11cqw; }
.jar em { font-size: 9px; font-size: 8cqw; }
.spark { position: absolute; left: 50%; top: -42%; width: 12%; height: 26%; margin-left: -6%; border-radius: 50% 50% 50% 50% / 70% 70% 30% 30%; background: radial-gradient(ellipse at 50% 75%, #FFF6D6, var(--flame) 60%, transparent 85%); box-shadow: 0 0 24px 6px rgba(244, 184, 74, .5); opacity: 0; transition: opacity .3s; pointer-events: none; }
.product:hover .spark, .product:focus-within .spark { opacity: 1; }

/* Craft + care */
.split { display: grid; grid-template-columns: 1fr 1.2fr; gap: 3rem 5rem; align-items: start; }
.steps { list-style: none; counter-reset: step; display: grid; gap: 2rem; }
.steps li { counter-increment: step; display: grid; grid-template-columns: 3rem 1fr; column-gap: 1rem; }
.steps li::before { content: counter(step); grid-row: span 2; font: 400 2.5rem/1 var(--serif); color: var(--muted); }
.steps p { color: var(--muted); max-width: 32rem; }

.faq details { padding-block: 1.25rem; border-bottom: 1px solid var(--lilac); }
.faq details:first-child { border-top: 1px solid var(--lilac); }
.faq summary { display: flex; justify-content: space-between; gap: 1rem; font: 400 1.5rem/1.2 var(--serif); cursor: pointer; list-style: none; }
.faq summary::-webkit-details-marker { display: none; }
.faq summary::after { content: "+"; transition: transform .2s; }
.faq details[open] summary::after { transform: rotate(45deg); }
.faq p { margin-top: .75rem; max-width: 32rem; color: var(--muted); }

/* Footer */
.foot { padding-block: 4rem; }
.foot-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2.5rem; align-items: start; }
.foot p:last-child { margin-top: .5rem; color: var(--lilac); }
.foot label { display: block; margin-bottom: .75rem; font: 400 1.75rem/1.2 var(--serif); }
.row { display: flex; flex-wrap: wrap; gap: .75rem; }
.row input { flex: 1 1 14rem; padding: .85rem 1.25rem; border: 1.5px solid var(--lilac); border-radius: 999px; background: transparent; color: var(--mist); font: inherit; }
.row input::placeholder { color: #B5A6C4; }
.foot small { display: block; margin-top: .75rem; color: var(--lilac); }

/* Layout: wider screens stagger the middle column; narrow screens stack */
@media (min-width: 900px) {
  .grid { grid-template-columns: repeat(3, 1fr); }
  .product:nth-child(3n + 2) { margin-top: 3rem; }
}
@media (max-width: 820px) {
  .hero, .split, .foot-grid, .facts { grid-template-columns: 1fr; }
  .hero { min-height: 0; }
  .scene { height: 460px; }
}
@media (prefers-reduced-motion: reduce) {
  html { scroll-behavior: auto; }
  .flame, .glow { animation: none; }
  .spark { transition: none; }
}
