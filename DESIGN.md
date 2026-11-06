# Design System: Atelier Valorisation

## 1. Visual Theme & Atmosphere

A high-contrast editorial studio — like a top-tier photography gallery printed on matte black card stock. The atmosphere is aggressive yet precise: images command the room while the typography refuses to apologise for taking up space. Dense without being cluttered. Every section is a deliberate composition, not a template.

- **Creativity:** 9 / 10
- **Variance:** 8 / 10 — offset asymmetric grids, split-screen hero, left-aligned editorial hierarchy
- **Motion:** 6 / 10 — fluid CSS spring-feel reveals, perpetual subtle micro-loops, no cinematic overload
- **Density:** 5 / 10 — balanced; generous whitespace in light sections, controlled pressure in dark sections

The palette alternates between deep obsidian and warm linen: dark sections carry authority, light sections provide editorial breathing room. The single accent colour (electric ember) acts as a visual signature — never decorative, always functional.

---

## 2. Color Palette & Roles

- **Obsidian Canvas** (`#0B0B0B`) — Primary dark background. Never pure black. Used in hero, stats, testimonials, process, CTA sections.
- **Void Surface** (`#141414`) — Slightly elevated dark surface for ticker bar, code blocks, elevated dark cards.
- **Warm Linen** (`#F2EDE6`) — Light section background. Used in Pour Qui, Vidéo, FAQ. Warm, tactile, print-like.
- **Ink** (`#0F0F0F`) — Primary text on light surfaces. Off-black, never pure black.
- **Dust** (`#9A9A9A`) — Secondary text, captions, metadata on dark surfaces.
- **Linen Mist** (`#B8B0A4`) — Secondary text on light surfaces. Warm gray, not cold.
- **Ghost Border** (`rgba(255,255,255,0.07)`) — Structural dividers on dark surfaces.
- **Linen Border** (`rgba(15,15,15,0.10)`) — Structural dividers on light surfaces.
- **Electric Ember** (`#E84B1A`) — Single accent. All CTAs, active states, accent marks, the BA slider knob and line, counters, step numbers. Saturation is 85% but hue-shifted orange-red reads as calibrated, not garish.
- **Ember Dim** (`rgba(232,75,26,0.12)`) — Accent tint backgrounds, hover fills, label chips on dark.
- **White Signal** (`#FFFFFF`) — Text on accent-fill buttons only.

**Banned:** Pure `#000000`. Purple. Blue-neon. Multi-colour gradients on any header. Cool grays mixed with warm grays.

---

## 3. Typography Rules

- **Display / Headlines:** `Syne` — weight 800. Letter-spacing `−0.03em` to `−0.04em`. Line-height 0.96–1.0 for large displays, 1.1 for section headings. Scale via `clamp()`. This font's geometric boldness reads as craft and confidence, not aggression.
- **Body / UI / Labels:** `Outfit` — weight 300–500. Leading 1.8 for prose, 1.5 for UI labels. Fluid and readable without being anonymous. Replaces Inter, which is banned.
- **Mono / Numbers / Metadata:** `DM Mono` — For captions, timestamps, before/after labels, form handles. Adds technical credibility.
- **Banned:** `Inter` (banned in premium creative contexts), `Georgia`, `Times New Roman`, `Garamond`, `Helvetica Neue` as a primary. Never use `font-style: italic` on Syne — it has no true italic and fakes look weak.
- **Scale Anchors:**
  - Hero headline: `clamp(56px, 6vw, 92px)`
  - Section title: `clamp(42px, 5vw, 72px)`
  - Sub-headline: `clamp(22px, 2.4vw, 34px)`
  - Body: `clamp(13px, 1vw, 15px)`
  - Label/eyebrow: `9px`, letter-spacing `0.38em`, ALL CAPS

---

## 4. Component Stylings

**Buttons (Primary):**
Fill with Electric Ember (`#E84B1A`). Text White Signal (`#FFFFFF`). Syne 700. `9px` letter-spacing `0.2em` ALL CAPS. Zero border-radius — hard rectangular edge signals craft precision. On hover: `background #C73D13`, `translateY(-2px)`. On active: `translateY(0)`, `scale(0.98)` — tactile press. No outer glow. No box-shadow.

**Buttons (Ghost/Outline):**
Transparent fill, 1.5px border in Electric Ember. Text in Electric Ember. On hover: fill with Ember Dim. No border-radius.

**Buttons (Ghost Dark on Light):**
Transparent fill, 1px border `rgba(15,15,15,0.18)`. Text Linen Mist. On hover: border Ink, text Ink.

**Before/After Slider:**
The interactive centrepiece. Slider handle: solid Electric Ember circle, no border, shadow `0 4px 32px rgba(232,75,26,0.45)`. Divider line: 2px Electric Ember. "Avant" label: Obsidian Canvas background, White Signal text, Outfit 700. "Après" label: Electric Ember fill, White Signal text, Outfit 700. Slider background on dark section: `#1a1a1a`.

**Labels / Eyebrows:**
9px, letter-spacing 0.38em, Outfit 700, ALL CAPS. Color: Electric Ember at 65% opacity on dark sections. Electric Ember at 100% on light sections.

**Section Dividers:**
1px Ghost Border or Linen Border depending on section background. Never decorative gradients as dividers.

**Ticker:**
Outfit 700, 9px, letter-spacing 0.3em, Electric Ember at 40% opacity. Dark background (`#141414`). Top/bottom borders at Ghost Border.

**FAQ Accordion:**
Syne 700 question text. Plus/minus icon in a circle with Ember accent. On dark sections: Obsidian Canvas background, Ghost Border dividers, Warm Linen text. On light sections: Warm Linen background, Linen Border dividers, Ink text.

**Loaders:** Skeletal shimmer blocks matching layout shape. No spinners.

---

## 5. Layout Principles

**Hero:** Split-screen, 55/45 or 60/40 grid. Left: full dark panel with headline + CTA + eyebrow stacked left-aligned. Right: photograph bleeding to viewport edge with no overlay. Never centered. Never full-bleed with text overlay.

**Pour Qui (Audience List):** Editorial list rows with numbered index, title, description, and arrow icon. Grid: `56px | 1fr | auto`. Horizontal rule dividers only — no cards, no equal-width grids. Hover: title turns Electric Ember, arrow circle fills Electric Ember.

**Impact / Stats:** Three columns with a 2px Electric Ember accent bar at the top of each column (not a faint line — a solid accent bar). Numbers in Syne 800 at `clamp(56px, 7.5vw, 88px)`, Electric Ember. No card borders. Raw typographic power.

**Process:** Four-step horizontal list with a gradient connector line (Electric Ember → transparent). Step numbers in accent-bordered circles. Dark background. On mobile: two columns then single.

**Vidéo / 3D:** 50/50 grid on light background. Left: description text + devis badge. Right: vertical service list with accent-bordered icon circles. Service names in Syne 800, not body-weight.

**Testimonials:** Dark background. Feature testimonial with large quote text (Syne 700, not italic). Two secondary quotes below in a 2-column grid. Red accent tag on the result label.

**FAQ:** Light background. Max-width 800px centred list. No card wrapper — pure accordion on bare Warm Linen.

**CTA:** Dark background, centred text, primary + ghost button pair. Single line of contact metadata below.

**Max-width:** 1200px content container with `56px` horizontal padding (collapses to `28px` at < 960px).

**Banned layouts:** Equal 3-column card grids. Centered hero. Full-bleed image with dark overlay and centred text. Flexbox percentage hacks with `calc()`.

---

## 6. Motion & Interaction

**Scroll Reveals:** All `.reveal` elements: `opacity: 0; transform: translateY(28px)` → animate to `opacity: 1; transform: translateY(0)`. Duration: 0.9s, `power2.out` or `cubic-bezier(0.16,1,0.3,1)`. Trigger: when top of element hits 89% viewport height.

**Hero Entry Sequence (staggered):**
1. Eyebrow: delay 0.1s, 0.7s duration
2. H1: delay 0.3s, 0.95s duration
3. Body paragraph: delay 0.6s, 0.7s duration
4. CTA wrapper: delay 0.8s, 0.7s duration

**Scroll Line (hero):** Perpetual `scaleY` pulse animation, 2.2s ease-in-out infinite. Gradient from Electric Ember to transparent.

**Ticker:** `translateX` loop, 36s linear infinite. Pauses on `prefers-reduced-motion`.

**Nav:** Hides on scroll down (after 120px), reappears on scroll up. Transition: `translateY(-100%)`, 0.4s cubic. Blur backdrop: `blur(20px)`.

**Before/After Sliders:** Native pointer/touch events. Smooth `clip-path` clipping on drag. Keyboard accessible (`←→` keys, 5% increments).

**Cursor (desktop):** 6px solid Electric Ember dot. Scales to 38px transparent ring with 1px accent border on hover over interactive elements. No lag — direct position tracking, `opacity` transition only.

**Banned:** `transition: all`. Animating `width`, `height`, `top`, `left`, `margin`. GSAP ScrollSmoother (causes iOS issues). Custom scroll velocity distortion effects.

---

## 7. Anti-Patterns — Banned

- **No `Inter` font** — replaced by `Outfit` for body and UI, `Syne` for display
- **No pure `#000000`** — use Obsidian Canvas `#0B0B0B`
- **No centered Hero** — always split-screen or left-aligned
- **No 3-column equal card grids** — use editorial list rows or asymmetric grids
- **No italic `Syne`** — no true italic exists; fakes look broken
- **No emojis** — anywhere in the UI
- **No AI copywriting** — "Elevate", "Seamless", "Unleash", "Transform", "Next-Gen", "Discover" are banned
- **No neon glow box-shadows** — Electric Ember accent bar is flat, no luminous spread
- **No fabricated statistics** — only use verified data (+40% réservations, 73% décident sur photos, +20% tarif) already confirmed in project brief
- **No filler text** — "Scroll to explore", "Swipe down", bouncing chevrons are banned
- **No generic serif** — `Georgia`, `Garamond`, `Times New Roman` banned
- **No `LABEL // YEAR` formatting** — e.g. "STUDIO // 2024" is a lazy AI convention
- **No overlapping elements** — clean spatial separation; z-index stacking only for modals and fixed UI
- **No multi-stop rainbow gradients** on any visible surface
- **No custom mouse cursor shapes** — only scale/color transitions on the dot
- **No broken external image URLs** — all images are project assets in `/assets/`
- **No warm/cool gray mixing** — entire palette stays warm-toned neutral
