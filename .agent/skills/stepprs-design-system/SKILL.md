---
name: stepprs-design-system
description: Frontend design skill for this Shopify theme workspace. Use whenever styling, theming, or building storefront UI — any change to colors, typography, spacing, components, sections, CSS, or Liquid that affects visual appearance. Enforces the Stepprs design system defined in DESIGN.md at the repo root.
---

# Stepprs Design System — Frontend Skill

`DESIGN.md` at the repo root is the single source of truth. Its YAML tokens are normative;
its prose sections explain application; its `#` comments carry provenance. This skill is the
working summary — when in doubt, open DESIGN.md.

## Core doctrine

1. **Settings before CSS.** Express tokens through `config/settings_data.json` (within
   `settings_schema.json`'s vocabulary) first. Only what settings cannot express goes in
   `assets/stepprs-theme.css` — the one and only custom CSS file. Never scatter overrides.
2. **Never touch the published theme.** Edit and push only the unpublished dev copy
   (`--theme <DEV_THEME_ID>` on every push). `shopify theme publish` is human-only.
3. **Tokens transfer, brand assets don't.** Never introduce Stepprs' logo, photography,
   copy, or name. This store keeps its own identity; only the abstracted system applies.
4. **Rem basis:** DESIGN.md rems assume a 10px root. If this theme's root differs, use the
   px equivalents below.
5. **Low-confidence tokens** (`#f3f3f3`, `#b64100`, `#7b7b7b`) must be visually verified on
   the dev preview before building on them.

## Token cheat sheet (px-resolved)

**Color roles**
| Role | Value | Use |
|---|---|---|
| surface | `#ffffff` | default canvas |
| surface-container | `#f3f3f3` | subdued bands (verify live) |
| inverse-surface | `#2e2a39` | plum feature bands, white ink |
| inverse-surface-dim | `#121212` | footer |
| on-surface | `#000000` | headlines, root ink, black bands |
| on-surface-variant | `#2e2a39` | body ink in content sections |
| primary | `#ff5b00` | THE brand accent: links (0.85a), active nav, sale prices, solid CTAs, heading highlights, glow |
| on-primary | `#ffffff` | labels on orange |
| secondary | `#dd1d1d` | promo-scheme buttons, divider shapes; white labels |
| scrim | `rgba(0,0,0,.3)` | media overlays |
| borders | foreground @ 0.1 (badges/cards) · 0.15 (pickers) · 0.55 (inputs/pills) | never new hues |
| gradient accent | `linear-gradient(54deg, #ff5b00 14%, #b64100 85%)` | accent flares |

One dominant chromatic: orange does all accent work on a monochrome stage. Red is the only
sanctioned alternate, applied per-scheme. No new hues.

**Typography** — Poppins only (Shopify font library), fallback `sans-serif`.
| Token | Size (desktop / mobile) | Weight | LH | Tracking |
|---|---|---|---|---|
| display | 45px / 32.5px | 700 | 1.3 | 0.6px |
| h1 | 30px / 22.5px | 700 | 1.3 | 0.6px |
| h2 | 24px / 20px | 700 | 1.3 | 0.6px |
| h3 | 18px / 17px | 700 | 1.3 | 0.6px |
| body | 15px | 400 | 1.8 | 0.6px |
| body-sm | 14px | 400 | 1.8 | 0.6px |
| button/price label | 16px | 700 | 1.2 | 1px |
| caps caption | 10px, uppercase | 400 | 1.2 | 1.3px |

**Shape & space**
- Radii: 6px controls (buttons/inputs/badges) · 10–12px cards/media · 22–24px popups ·
  40px pills · 50% swatches/circular arrows
- Buttons: 49px min-height, ~30px x-padding, visible 2px ring even when solid
- Rhythm: 5px half-steps (10/15/20/30/40/50 dominate) · grid gaps 20px desktop / 15px mobile
- Page width 1200px · sections sit flush (0 gap) — separation via band color changes and
  wave dividers, not margin
- Breakpoints: 749px / 750px / 990px

**Depth**
- Product cards: `0.2rem 0.6rem 1rem rgba(0,0,0,.1)` (2px 6px 10px)
- Collection/blog cards: `1rem 1rem 3.5rem rgba(0,0,0,.05)` (10px 10px 35px)
- Popups: `10px 12px 20px rgba(0,0,0,.1)` on 22px radius

## Signature effects (canonical CSS for assets/stepprs-theme.css)

```css
/* Two-tone heading — lead phrase pops orange inside a dark headline */
.title-highlight { color: #ff5b00; }

/* Animated CTA glow — exactly ONE primary CTA per view (theme-verbatim).
   Source pairs the halo with a 2px black border + black label on the glowing element. */
@keyframes glowing {
  0%   { box-shadow: 0 0 3px #ff5b004d; }
  50%  { box-shadow: 0 0 15px #ff5b004d; }
  100% { box-shadow: 0 0 3px #ff5b004d; }
}
.glowing { animation: glowing 1.5s infinite; color: #000; border: 2px solid #000; }

/* Double focus ring — survives on any band color */
:focus-visible {
  outline: none;
  box-shadow: 0 0 0 0.3rem rgb(var(--color-background)),
              0 0 0.5rem 0.4rem rgba(var(--color-foreground), 0.3);
}
```

## Component quick rules

- **Sale price:** orange, 700; compare-at struck through, foreground @ 0.9a, one size down.
- **Announcement bar:** black band, bold uppercase white micro-text, 1px tracking.
- **Cards:** white, rounded, centered text, tight grounded shadow; imagery does the brand
  work — never tint or filter product photos toward orange in CSS.
- **Dark bands:** white → `#2e2a39` → `#121212`/black alternation, white foreground,
  scheme-recolored buttons, wave dividers between bands.
- **Accepted deviation:** white-on-orange CTAs measure ~3.1:1 — authentic to the source
  system. Do not "fix" silently; do not make anything else fall below 4.5:1.

## Verify before done

Run `shopify theme dev --theme <DEV_THEME_ID>`, browser-check home / collection / product /
cart at 1440px and 390px, screenshot to Artifacts, and confirm changed surfaces against this
sheet. Any token that can't be applied natively: note it and where you handled it instead.
