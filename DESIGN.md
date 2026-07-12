---
name: Stepprs
description: >-
  Design system extracted from stepprs.com (Shopify storefront, customized
  Dawn-architecture "Elevate" theme build) on 2026-07-12. Token values and
  names come from the theme's own CSS custom properties (--color-base-*,
  --font-*, --buttons-*, --*-corner-radius, --jdgm-*), captured from the live
  homepage's inline :root/scheme blocks, base.css, template CSS, and section
  markup. Frequency counts cited in comments are occurrences in that captured
  data (third-party widget CSS tallied separately). Rem values resolve at
  1rem = 10px (html font-size: 62.5%, --font-body-scale: 1.0).
colors:
  # — Surfaces —
  surface: "#ffffff" # primary surface because highest-frequency non-text color: 68 theme occurrences (incl. --color-base-background-1 / --gradient-base-background-1); .color-background-1 appears 39x in homepage markup
  surface-container: "#f3f3f3" # low-confidence — verify on live site. Named --color-base-background-2 / --gradient-base-background-2 (value captured only 2x, but .color-background-2 class appears 9x in homepage markup)
  inverse-surface: "#2e2a39" # dark plum feature-section background: --color-background: 46,42,57 / --gradient-background: #2e2a39 in image-with-text scheme blocks (part of 13 total #2e2a39 captures)
  inverse-surface-dim: "#121212" # footer scheme background: --color-background: 18,18,18 / --gradient-background: #121212 (3 theme occurrences)
  # — Ink —
  on-surface: "#000000" # on-surface because most-used text color: 63 theme occurrences (--color-base-text: 0,0,0; 17 hits in text-category properties); also serves as announcement-bar / FAQ-section black surface
  on-surface-variant: "#2e2a39" # working body ink inside custom color-scheme sections: --color-foreground: 46,42,57 in 13 captured scheme var-defs
  on-inverse-surface: "#ffffff" # --color-foreground: 255,255,255 in every dark scheme block; 24 white hits in text-category properties overall
  # — Brand accents —
  primary: "#ff5b00" # brand primary because highest-frequency chromatic color: 18 occurrences — 6 var-defs (--color-base-accent-1, --color-base-accent-2, --color-base-outline-button-labels, --gradient-base-accent-1) + 12 box-shadow frames of the vendor-prefixed "glowing" keyframes (#ff5b004d = rgba(255,91,0,.30))
  on-primary: "#ffffff" # --color-base-solid-button-labels: 255,255,255 — label color on solid accent buttons
  primary-glow: "rgba(255, 91, 0, 0.3)" # 12 box-shadow keyframe frames, all literal #ff5b004d, across the vendor-prefixed "glowing" animation blocks — the animated CTA glow ring
  primary-dim: "#b64100" # low-confidence — verify on live site. Captured once, as the 85% end stop of --gradient-base-accent-2
  secondary: "#dd1d1d" # secondary because 13 theme occurrences: --color-button: 221,29,29 / --color-base-outline-button-labels in 12 scheme var-defs (featured-collection, newsletter, custom-columns, image-with-text) + 1 literal color; also the section-divider shape fill
  on-secondary: "#ffffff" # --color-button-text: 255,255,255 paired with the red button schemes
  # — Scoped / configured accents —
  highlight-collection: "#6d388b" # scoped override, not a global role: --color-base-accent-1 / --color-base-outline-button-labels / --hightlight-color on a single collection-list CTA (3 occurrences)
  reviews-accent: "#fe5b00" # merchant-configured Judge.me widget accent: 9 occurrences across --jdgm-primary-color, --jdgm-star-color, --jdgm-write-review-bg-color etc. Near-duplicate of primary (#ff5b00) — presumably intended to match; keep the one-digit drift in mind
  reviews-muted: "#7b7b7b" # low-confidence — verify on live site. Captured once (--jdgm-snippet-lighter-text-color)
  # — Functional alphas (derived from scheme foregrounds, not standalone literals) —
  link: "rgba(255, 91, 0, 0.85)" # --color-link: var(--color-base-outline-button-labels) at --alpha-link: .85 in :root/.color-background-1
  outline: "rgba(0, 0, 0, 0.55)" # input & variant-pill borders: rgba(var(--color-foreground), 0.55) via --inputs-border-opacity / --variant-pills-border-opacity
  outline-variant: "rgba(0, 0, 0, 0.15)" # picker/quantity borders at --pickers-border-opacity / --quantity-border-opacity: 0.15; card borders sit at 0.1
  scrim: "rgba(0, 0, 0, 0.3)" # 11 occurrences: media overlays and soft shadows (rgba(0,0,0,.3))
  shine: "rgba(255, 255, 255, 0.4)" # 3 background-image occurrences — hover shine sweep on media
  shadow: "#000000" # --color-shadow: 0,0,0 — base of every shadow, applied at 0.05–0.3 alpha
gradients: # custom extension key — captured verbatim from theme settings
  accent-flare: "linear-gradient(54deg, rgba(255, 91, 0, 1) 14%, rgba(182, 65, 0, 1) 85%)" # --gradient-base-accent-2 — orange-to-burnt-orange sweep backing accent-2 surfaces
typography:
  # Single-family system: --font-body-family and --font-heading-family are both "Poppins, sans-serif".
  # Rem root is 10px. Headings: line-height calc(1 + 0.3) = 1.3, letter-spacing --font-heading-letter-spacing: 0.06rem.
  display-lg:
    fontFamily: Poppins
    fontSize: 4.5rem # .h0 at >=990px; 4.25rem at 750–989px, 3.25rem below 750px
    fontWeight: "700" # --font-heading-weight: 700
    lineHeight: "1.3"
    letterSpacing: 0.06rem
  headline-lg:
    fontFamily: Poppins
    fontSize: 3rem # h1/.h1 at >=750px; 2.25rem below
    fontWeight: "700"
    lineHeight: "1.3"
    letterSpacing: 0.06rem
  headline-md:
    fontFamily: Poppins
    fontSize: 2.4rem # h2/.h2 at >=750px; 2rem below
    fontWeight: "700"
    lineHeight: "1.3"
    letterSpacing: 0.06rem
  headline-sm:
    fontFamily: Poppins
    fontSize: 1.8rem # h3/.h3 at >=750px; 1.7rem below
    fontWeight: "700"
    lineHeight: "1.3"
    letterSpacing: 0.06rem
  title-md:
    fontFamily: Poppins
    fontSize: 1.45rem # h4/.h4
    fontWeight: "700"
    lineHeight: "1.3"
    letterSpacing: 0.06rem
  title-sm:
    fontFamily: Poppins
    fontSize: 1.2rem # h5/.h5
    fontWeight: "700"
    lineHeight: "1.3"
    letterSpacing: 0.06rem
  body-md:
    fontFamily: Poppins
    fontSize: 1.5rem # body rule verbatim: font-size 1.5rem, letter-spacing .06rem, line-height calc(1 + .8) = 1.8, weight --font-body-weight: 400
    fontWeight: "400"
    lineHeight: "1.8"
    letterSpacing: 0.06rem
  body-sm:
    fontFamily: Poppins
    fontSize: 1.4rem # most frequent captured font-size (31x) — card meta, subtitles; .subtitle--small adds letter-spacing .1rem
    fontWeight: "400"
    lineHeight: "1.8"
    letterSpacing: 0.06rem
  label-lg:
    fontFamily: Poppins
    fontSize: 1.6rem # .button / .button-label / .price: 1.6rem, letter-spacing .1rem, line-height calc(1 + .2) = 1.2, weight 700
    fontWeight: "700"
    lineHeight: "1.2"
    letterSpacing: 0.1rem
  label-caps:
    fontFamily: Poppins
    fontSize: 1rem # .caption-with-letter-spacing: 1rem, letter-spacing .13rem, uppercase
    fontWeight: "400"
    lineHeight: "1.2"
    letterSpacing: 0.13rem
rounded:
  sm: 4px # --pickers-small-radius / --quantity-small-radius: 4.0px
  DEFAULT: 6px # --buttons-radius: 6px, --inputs-radius: 6px, --badge-corner-radius: 0.6rem (outset companions: 7–8px)
  md: 10px # --media-radius: 10px (a second captured settings group sets it to 0 — verify per template), --pickers-radius, --quantity-radius: 10px
  lg: 12px # --product-card-corner-radius / --blog-card-corner-radius: 1.2rem (collection cards drop to 1.0rem in the homepage-captured group)
  xl: 22px # --popup-corner-radius: 22px
  2xl: 24px # --text-boxes-radius: 24px
  pill: 40px # --variant-pills-radius: 40px
  full: 50% # swatches (--swatches-radius) and slider arrows (--slider-arrow-border-radius); 48 occurrences of 50%
spacing:
  unit: 0.5rem # 5px half-step on the 10px rem root — top captured padding/margin/gap values: 1rem x132, 1.5rem x87, 2rem x80, .5rem x76
  xs: 0.5rem
  sm: 1rem
  md: 1.5rem
  lg: 2rem
  xl: 3rem
  2xl: 4rem
  3xl: 5rem
  grid-gap-desktop: 20px # --grid-desktop-vertical/horizontal-spacing (one captured section group uses 40px)
  grid-gap-mobile: 15px # --grid-mobile-vertical/horizontal-spacing (one captured section group uses 20px)
  section-gap: 0px # --spacing-sections-desktop/mobile: 0 — sections butt flush; transitions are handled by wave dividers, not whitespace
  page-width: 120rem # --page-width = 1200px content column
components:
  button-primary:
    backgroundColor: "{colors.primary}" # default scheme: --color-button: var(--color-base-accent-1) at --alpha-button-background: 1
    textColor: "{colors.on-primary}"
    typography: "{typography.label-lg}"
    rounded: "{rounded.DEFAULT}"
    height: 49px # calc(4.5rem + 2 x --buttons-border-width: 2px); min-width calc(12rem + 4px)
    padding: "0 3rem"
  button-primary-promo:
    backgroundColor: "{colors.secondary}" # scheme override --color-button: 221,29,29 in featured-collection / newsletter / custom-columns schemes
    textColor: "{colors.on-secondary}"
    typography: "{typography.label-lg}"
    rounded: "{rounded.DEFAULT}"
    height: 49px
    padding: "0 3rem"
  button-secondary:
    backgroundColor: transparent # --alpha-button-background: 0; 2px ring drawn via box-shadow at --buttons-border-width
    textColor: "{colors.primary}" # --color-base-outline-button-labels: 255,91,0 at :root (white in footer scheme, red in promo schemes)
    typography: "{typography.label-lg}"
    rounded: "{rounded.DEFAULT}"
    height: 49px
    padding: "0 3rem"
  button-inverse:
    backgroundColor: "{colors.on-inverse-surface}" # footer scheme: --color-button: 255,255,255
    textColor: "{colors.inverse-surface-dim}" # --color-button-text: 18,18,18
    typography: "{typography.label-lg}"
    rounded: "{rounded.DEFAULT}"
    height: 49px
    padding: "0 3rem"
  input-field:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.label-lg}" # floating .field__label at 1.6rem, letter-spacing .1rem, fades to rgba(fg, .9)
    rounded: "{rounded.DEFAULT}" # 1px border at {colors.outline}; border opacity rises to 1 on hover (--inputs-hover-border-opacity)
    height: 49px
    padding: "1.5rem 2rem"
  product-card:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.lg}" # shadow: 0.2rem 0.6rem 1rem rgba(0,0,0,0.1) via --product-card-shadow-* settings
  collection-card:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.md}" # 1.0rem in homepage-captured group; shadow 1rem 1rem 3.5rem rgba(0,0,0,0.05); white title over bottom scrim
  variant-pill:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.pill}" # --variant-pills-radius: 40px, border 1px at {colors.outline}
    padding: "1rem 2rem" # --variant-pills-padding-y/x; text 1.4rem
  badge:
    backgroundColor: "{colors.surface}" # --color-badge-background: var(--color-background); border = foreground at --alpha-badge-border: .1
    textColor: "{colors.on-surface}"
    rounded: "{rounded.DEFAULT}" # --badge-corner-radius: 0.6rem
  price-sale:
    textColor: "{colors.primary}" # .price .price-item { color: rgb(var(--accent-color)); font-weight: 700 } — accent-color resolves to base-accent-1
    typography: "{typography.label-lg}"
  announcement-bar:
    backgroundColor: "{colors.on-surface}" # black ticker band; bold white uppercase messages with .1rem tracking
    textColor: "{colors.on-inverse-surface}"
    typography: "{typography.body-sm}"
  popup:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.xl}" # --popup-corner-radius: 22px; shadow 10px 12px 20px rgba(0,0,0,0.1)
---

## Brand & Style

Stepprs is a direct-to-consumer footcare brand ("Feel Like You're Walking on Air", 800,000+ customers) selling massage insoles, pads, and foot-relief kits. The visual identity is built on one move executed relentlessly: a single vivid orange owns the brand, and everything else stays monochrome so it can. Product photography is shot on saturated orange seamless backgrounds, the logo is a white wordmark in an orange chip, active nav items light up orange, sale prices are orange, and CTAs pulse with an animated orange glow.

The register is energetic commerce, not quiet editorial. A black uppercase announcement ticker runs sale messages on loop, circular "Limited Edition" stickers sit on full-bleed photographic heroes, and gamified discount popups take over the viewport in pure brand orange. Poppins — the only typeface in the system — keeps that energy friendly rather than aggressive: geometric, rounded, bold. Content alternates between a clean white commerce canvas and dark feature bands (plum `#2e2a39`, near-black `#121212`, black), stitched together with wavy full-width dividers instead of whitespace.

## Colors

The palette is a white stage for one hero chromatic. Orange `#ff5b00` (`--color-base-accent-1/-2`) is the brand driver — links, active states, sale prices, outline-button labels, heading highlights, glow shadows, and the photography itself. It out-frequencies every other chromatic in the captured data by roughly 2:1.

- **Surfaces:** White `#ffffff` is the default canvas; `#f3f3f3` (`--color-base-background-2`) is the quieter secondary band. Dark schemes flip sections to plum `#2e2a39`, footer `#121212`, or pure black.
- **Ink:** `#000000` is the root text color (`--color-base-text`); custom-scheme sections consistently override foreground to the warmer plum `#2e2a39`, so long-form copy reads slightly softened while headlines stay near-black.
- **Primary orange `#ff5b00`:** solid buttons, links at 0.85 alpha, focus/CTA glow at 0.3 alpha, and the `accent-flare` gradient (54°, `#ff5b00` → `#b64100`). The Judge.me reviews widget is merchant-configured to `#fe5b00` — a one-digit drift from the theme orange that should be treated as the same brand color (and ideally reconciled).
- **Secondary red `#dd1d1d`:** the alternate action color, applied through section color schemes — featured-collection quick-add buttons, newsletter CTAs, and the wave section-divider shape. Always paired with white labels.
- **Scoped purple `#6d388b`:** a single collection-list CTA override (`--hightlight-color`); real but one-context — don't generalize it.
- **Functional alphas:** borders and dividers are never new hues; they are the scheme foreground at fixed opacities (0.1 badges/cards, 0.15 pickers, 0.55 inputs/pills), with black scrims at 0.3 over media.

Deliberately excluded from the token set: inline payment-network SVG artwork in the footer (Visa blue `#0071ce`, Mastercard red `#eb001b` / yellow `#f79e1b` / orange `#ff5f00` — note that last one is Mastercard's orange, *not* the brand `#ff5b00`) and Judge.me's internal library grays (`#eeeeee`, `#dddddd`, `#333333`, `#cccccc`), which are third-party widget defaults rather than brand decisions.

## Typography

One family, two weights, everywhere: Poppins 400 for body, Poppins 700 for headings, buttons, prices, and promo labels (600 appears on icon-links; 300/500 only inside third-party widgets). Self-hosted via Shopify's font CDN with `sans-serif` fallback.

- **Scale basis:** `html { font-size: 62.5% }` with `--font-body-scale: 1.0`, so 1rem = 10px. All sizes below are theme-verbatim rem values.
- **Headings** (`--font-heading-*`): weight 700, line-height 1.3, letter-spacing 0.06rem. Sizes step up at 750px (h1 2.25→3rem; display `.h0` 3.25→4.25→4.5rem across the three breakpoint tiers).
- **Body:** 1.5rem / 1.8 line-height / 0.06rem tracking — generous leading that keeps dense commerce copy airy.
- **Labels:** buttons and prices run 1.6rem / 700 / 0.1rem tracking; micro-captions run 1rem / 0.13rem tracking, uppercase.
- **Signature pattern:** `title-with-highlight` — headlines split into two tones, e.g. "**Best Value** Kits" with the leading phrase in `rgb(var(--accent-color))` orange and the remainder in near-black. Reproduce this for hero and section headings.

## Layout & Spacing

A centered 1200px column (`--page-width: 120rem`) on full-bleed section bands. The rhythm is half-rem (5px) steps — 1rem, 1.5rem, 2rem, 3rem, 4rem, 5rem dominate the captured padding/margin/gap values.

- **Grid:** product/collection grids gap at 20px desktop / 15px mobile (`--grid-*-spacing`; one section group widens to 40/20).
- **Sections:** `--spacing-sections: 0px` — bands sit flush against each other. Separation comes from background-color changes and wavy dividers, not margin.
- **Breakpoints:** 749px max-mobile, 750px tablet, 990px desktop (the canonical Dawn trio; 107/69/21 media-query occurrences).
- **Density:** buttons are large tap targets (49px), cards center-aligned (`--*-card-text-alignment: center`), content blocks breathe via internal padding rather than outer margins.

## Elevation & Depth

Depth is soft and photographic, never hard-edged. Shadows are black at low alpha, tuned per component through settings variables:

- **Product cards:** `0.2rem 0.6rem 1rem rgba(0,0,0,0.1)` — a tight grounded lift.
- **Collection/blog cards:** `1rem 1rem 3.5rem rgba(0,0,0,0.05)` — a wide ambient float.
- **Popups:** `10px 12px 20px rgba(0,0,0,0.1)` on a 22px-radius panel; drawers keep a whisper `0 4px 5px` at 0 opacity by default.
- **The orange glow:** `@keyframes glowing` pulses `box-shadow: 0 0 3px #ff5b004d` out to `0 0 15px` and back, applied as `animation: glowing 1.5s infinite`; the `.glowing` element pairs the halo with a 2px solid black border and black label — elevation used as attention, unique to this brand. Use it sparingly, on one primary CTA per view.
- **Focus rings:** Dawn's double-ring pattern — `0 0 0 0.3rem` in the scheme background plus `0 0 0.5rem 0.4rem` foreground at 0.3 alpha — so focus survives on any band color.
- **Media:** hover shine sweeps use `rgba(255,255,255,0.4)` gradients; image overlays scrim at `rgba(0,0,0,0.3)`.

## Shapes

The shape language is soft-industrial: rounded enough to feel cushioned (it's a comfort product), square enough to stay sporty.

- **Controls:** 6px — buttons, inputs, badges (with 7–8px outset companions for focus offsets).
- **Media & cards:** 10–12px — product imagery, product/blog cards (collection cards 10px).
- **Overlays:** 22–24px — popups and text-boxes get the roundest treatment.
- **Pills & circles:** 40px variant pills; perfect circles for color swatches, slider arrows, and the "Limited Edition" sticker badge.
- **Dividers:** full-width wave/slant shapes between bands (rendered in black, white, or secondary red) — the signature transition device.
- **Buttons carry a visible 2px border** (`--buttons-border-width: 2`) even when solid, drawn as a box-shadow ring.

## Components

### Buttons

Solid primary buttons are brand orange with white 1.6rem/700 labels; promo-scheme sections (featured collections, newsletter) swap the fill to secondary red; the footer inverts to white-on-near-black. Secondary buttons are transparent with a 2px ring and orange labels (`--color-base-outline-button-labels`). All variants: 49px tall, `0 3rem` padding, 6px radius, 0.1rem letter-spacing. Reserve the animated glow for the single highest-intent CTA.

### Cards

Product cards are white, 12px-radius, center-aligned, with the tight grounded shadow — and their imagery does the brand work (orange seamless backgrounds). Collection cards lay white bold titles with arrow glyphs over a bottom gradient scrim on the photo. Sale pricing pairs an orange 700-weight price with a struck-through compare-at price in foreground at 0.9 alpha, one size step down.

### Inputs & Pills

Fields use floating labels (1.6rem, 0.1rem tracking) inside 6px-radius, 49px-tall boxes bordered by foreground at 0.55 alpha, sharpening to full opacity on hover. On dark bands (newsletter), the same anatomy renders as a thin light outline on black. Variant selectors are 40px-radius pills; color swatches are borderless circles that gain a 0.5-alpha ring when selected.

### Bands & Ticker

The announcement bar is a black marquee of bold uppercase micro-messages with emoji separators. Feature bands alternate white → plum `#2e2a39` → black/`#121212`, always with white foreground and scheme-appropriate button recolors, joined by wave dividers. The newsletter band sits on black directly above the `#121212` footer, which closes with the orange logo chip, white link columns, and outlined pill selectors for country/language.
