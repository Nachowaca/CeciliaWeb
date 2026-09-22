# Handoff: Home — Cecilia Rodríguez Lisboa (Galería + Remates)

## Overview
Home page for a painter's web app that combines a gallery and artwork auctions ("remates"). It shows the artist's identity, an animated featured painting in a museum scene, main navigation and a footer with a simulated contact chatbot that forwards leads to the artist.

## About the Design Files
The files in this bundle are **design references created in HTML** — a prototype showing intended look and behavior, not production code to copy directly. The task is to **recreate this design in the target codebase's environment** (React, Next.js, Vue, etc.) using its established patterns. If no codebase exists yet, pick an appropriate framework (suggested: Next.js or Astro + plain CSS / CSS modules) and implement it there.

Open `Cecilia Home.html` in a browser to see it running (it loads `styles.css` and `templates/landing/image-slot.js` relative to itself; Lucide icons and Archivo font load from CDN).

## Fidelity
**High-fidelity.** Final colors, type, spacing, borders and animation. Recreate pixel-accurately. Placeholder content to replace: painting image, painting label text, "Sala 01", email `contacto@cecilia.uy`.

## Design System
Built on the **Modernist** system (`styles.css`): flat, architectural, Archivo only, zero border radius, 2px divider rules, red accent. This page overrides the background to a warm bone white. Page-local CSS lives in the `<style>` block of the HTML.

## Screens / Views

### 1. Header (sticky not required)
- Full-width, bottom border `2px solid var(--color-divider)`.
- Inner container: `max-width:1360px`, horizontal padding 32px (16px ≤900px), vertical padding 16px.
- Grid: `minmax(0,1fr) auto`, gap 24px. Stacks to one column ≤620px; menu wraps.
- **Brand (left)**: 28×3px ink bar above text; "Cecilia / Rodríguez Lisboa" on two lines; Archivo 800, 15px, line-height 1.05, letter-spacing .02em, uppercase. Click → Home.
- **Menu (right)**: flex, gap 24px (16px ≤900px). Items: Galería, Talleres, Clases → text buttons, Archivo 600 14px, padding 6px 0, 2px transparent bottom border; hover color accent; active page = 2px ink bottom border.
- **Remates CTA**: filled button, bg `--color-accent` #ec3013, text bone #f5f0e8, padding 10px 16px, radius 0, gavel icon (Lucide `gavel`, 16px) + label, gap 8px. Hover bg #dd2b0f; active #ae1800.

### 2. Artist box
- Margin-top 32px; `border:2px solid var(--color-divider)`.
- Grid `minmax(0,1.3fr) minmax(0,1fr)`; single column ≤900px (divider switches from right border to bottom border).
- **Left cell** (padding 24px, right border 2px): kicker "Galería + Remates" (11px, 600, uppercase, letter-spacing .12em) at top; H1 "Cecilia Rodríguez Lisboa" at bottom — Archivo 800, `clamp(34px,4.6vw,64px)`, line-height .98, letter-spacing −.03em, `text-wrap:balance`. Space-between vertically, gap 24px.
- **Right cell**: two equal rows separated by a 2px rule. Each row grid `48px 1fr`, padding 16px 24px:
  - Number (accent, 12px, 800): "01" / "02"
  - Text (600, `clamp(16px,1.6vw,21px)`, lh 1.3):
    - 01 — "Artista / Profesora / Tallerista"
    - 02 — "Bellas Artes / Escenógrafa / Realización Teatral"

### 3. Museum scene (featured painting)
- Wrapper: margin-top 24px, 2px border on sides/bottom (no top).
- Scene viewport: height `clamp(420px,68vh,760px)`, `overflow:hidden`, bg wall `#ebe3d6`.
- Layers inside an animated "world" (absolute, inset 0, transform-origin 50% 48%):
  - **Wall**: extends −30% beyond left/right/top, bottom at 22%; radial gradient spotlight `ellipse 30% 55% at 50% 18%` from 55% white mix to wall color at 70%.
  - **Baseboard**: 14px strip at bottom 22%, color = floor mixed 70% with ink.
  - **Floor**: `#cfc4b3`, bottom −30%, height 52%.
  - **Piece**: centered at 50% / 48%; grid of frame + wall label, gap 28px, aligned to bottom.
    - Frame: bg `#231f1c`, padding 16px, inset bevel shadows (`inset 0 0 0 2px #3a332d, inset 0 0 0 6px #231f1c, inset 0 0 0 7px #4a4038`), drop shadows `0 22px 40px rgba(45,43,43,.30), 0 4px 8px rgba(45,43,43,.25)`.
    - Mat (passe-partout): `#faf7f1`, padding `clamp(18px,2.4vw,34px)`, `inset 0 2px 6px rgba(0,0,0,.22)`.
    - Canvas: aspect 4/5, width `min(clamp(220px,26vw,380px), (sceneHeight − 150px) × .8)` so it always fits vertically. Holds the painting image (object-fit: cover). **Show in full color** (do NOT apply the system's `.grayscale`).
    - Wall label (hidden ≤900px): 150px wide, bg `#fbf8f2`, padding 12px 14px, 11px text lh 1.45, shadow `0 2px 4px rgba(45,43,43,.18)`, margin-bottom 12%. Content: **Título de la obra** / Óleo sobre tela / 100 × 80 cm, 2026.
- **Scene bar** (bottom): grid `1fr auto`, top border 2px, padding 12px 24px. Left kicker "Obra destacada · Sala 01" (neutral-700). Right: secondary button "Volver a recorrer" with Lucide `rotate-ccw`.

### 4. Section pages (stubs)
Galería, Talleres, Clases, Remates currently render a placeholder: kicker "Sección" (accent), H2 section name (`clamp(40px,6vw,88px)`, −.03em), line "Esta sección se diseña en el próximo paso.", secondary button "Volver al inicio". Implement as real routes; design pending.

### 5. Footer
- Top border 2px. Grid `1fr 1fr 1.4fr` (single column ≤900px with horizontal rules between).
- Columns separated by 2px left borders, padding 24px (bottom 32px).
- Col 1: kicker "Cecilia Rodríguez Lisboa" + nav list (Galería, Talleres, Clases, Remates), 14px, gap 6px, hover accent.
- Col 2: kicker "Contacto" + `contacto@cecilia.uy` (link) + "Montevideo, Uruguay".
- Col 3: kicker "Consultas" + **chat widget** (below).
- Legal bar: top border 2px, 12px neutral-700 text, space-between: "© 2026 Cecilia Rodríguez Lisboa" / "Galería y remates de obra".

### 6. Chat widget
- Box: 2px divider border, bg page color, margin-top 12px.
- Header: 8px accent dot + "Asistente de la galería" (13px, 800) + right-aligned "Le avisa a Cecilia" (12px, neutral-700); bottom border 2px; padding 10px 14px.
- Messages area: height 210px, scroll, padding 14px, gap 10px, `aria-live="polite"`.
  - Bot bubble: bg surface `#ece5da`, left-aligned. User bubble: bg ink `#201e1d`, text bone, right-aligned. Success bubble: bg `#fff2ef`, text `#7c1405`. Max-width 85%, 13.5px, lh 1.45, padding 8px 12px, radius 0.
  - Typing indicator "Escribiendo…" (12px neutral-700) shown 700ms before each bot reply.
- Quick replies (chips): "¿Cómo funcionan los remates?", "Talleres y clases", "Quiero comprar una obra" — 12px, padding 5px 10px, 1px divider border; hover accent border+text.
- Input row: grid `1fr auto`, top border 2px; input placeholder "Escribí tu consulta…"; primary square send button (Lucide `send`).

## Interactions & Behavior

### Navigation
Header menu, brand and footer links switch view. Active menu item gets `aria-current="page"`. Returning to Home replays the scene animation. Smooth scroll to top on navigation.

### Scene animation ("walking toward the wall")
- On load / on Home / on "Volver a recorrer":
  - World: `@keyframes approach { from { transform: scale(.62) translateY(4%) } to { transform: scale(1) translateY(0) } }`, **9s**, `cubic-bezier(.33,.08,.18,1)`, fill forwards.
  - Inner layer footstep bob: `translateY(0 → −3px)`, 1.1s ease-in-out, 7 iterations, alternate.
- Replay = remove class, force reflow, re-add class.
- `prefers-reduced-motion: reduce` → keep the approach (the client explicitly wants it visible), disable only the bob.

### Chatbot (simulated; replace with real backend later)
Keyword routing (case-insensitive), then a lead-capture flow:
- `remate|subast|puja|ofert` → explains Remates, offers to notify Cecilia.
- `taller|clase|curso|aprend` → offers to pass details for schedule/cupos.
- `compr|precio|obra|cuadro|vend` → starts lead flow.
- `si|sí|dale|ok|claro` → starts lead flow.
- Otherwise → fallback listing topics.
- Lead flow states: `idle → name → email → msg → idle`. Asks name → "¿A qué mail o WhatsApp…?" → "Contame en una línea…" → success bubble "Listo, le envié tu mensaje a Cecilia. Te va a responder a {contact}."
- Initial message: "Hola, soy el asistente de la galería. ¿En qué te ayudo?"
- Exact copy for every reply is in the `<script>` of the HTML.
- **Production**: on flow completion POST `{name, contact, message, transcript}` to a backend that emails/WhatsApps Cecilia.

## State Management
- `page`: `'home' | 'galeria' | 'talleres' | 'clases' | 'remates'` (use real routing).
- `sceneRunKey`: increments to replay the animation.
- Chat: `messages[] {role:'bot'|'me', text, variant?:'ok'}`, `typing:boolean`, `stage:'idle'|'name'|'email'|'msg'`, `lead {name, contact, message}`.

## Design Tokens
Colors
- Background (page override): `#f5f0e8` (bone)
- Surface (override): `#ece5da`
- Text / ink: `#201e1d`
- Divider: ink at 40% (`color-mix(in srgb,#201e1d 40%,transparent)`)
- Accent: `#ec3013`; hover `#dd2b0f`; pressed `#ae1800`; tint `#fff2ef`; deep `#7c1405`
- Neutral-700 (muted text): `#605d5d`
- Scene: wall `#ebe3d6`, floor `#cfc4b3`, frame `#231f1c`, mat `#faf7f1`, label `#fbf8f2`

Typography: Archivo (Google Fonts, 400/600/800) for everything. Body 15px/1.55. Headings 800. Kickers 11px 600 uppercase +.12em.

Spacing: 4, 8, 12, 16, 24, 32px. Radius: 0 everywhere (except the 8px chat status dot). Rules: 2px.

Shadows: only in the museum scene (listed above).

## Assets
- Painting image: placeholder — replace with Cecilia's artwork (4:5 recommended).
- Icons: Lucide (`gavel`, `rotate-ccw`, `arrow-left`, `send`), 16px.
- Font: Archivo via Google Fonts.

## Files
- `Cecilia Home.html` — the prototype (page CSS + JS inline).
- `styles.css` — Modernist design-system tokens and base component classes (`.btn`, `.btn-primary`, `.btn-secondary`, etc.).
- `templates/landing/image-slot.js` — prototype-only drag-and-drop image placeholder; replace with a normal `<img>`.
