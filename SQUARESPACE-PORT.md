# Squarespace port mapping

Two parts:
- **Part 1 — Full-section inherit-readiness** (below): how the whole 7-page Astro build is wired to inherit live Site Styles. The durable reference.
- **Part 2 — Temp landing mapping** (further down): the original single-page `paste-to-squarespace.html` notes. Delete once that page is pasted and approved.

---

## Part 1 — Full-section inherit-readiness (2026-05-24)

The Astro source is wired so the *same* CSS works two ways: standalone (GitHub Pages preview) it uses fallback values; pasted into Squarespace it inherits the live Site Styles. This fixes the "stale styles" root cause — when CAA evolves their site, the section follows.

### Verified live token mapping (primary source)

Pulled from the live `site.css` / `custom.css` on 2026-05-24 (not inferred). Each fallback triple equals our prior hex, so the standalone preview is unchanged:

| Our token | Live Squarespace token | Live value | Hex equiv |
|---|---|---|---|
| `--caa-teal` | `--darkAccent-hsl` | `191.07,67.32%,30%` | `#196D80` |
| `--caa-navy` / `--caa-ink` | `--black-hsl` | `202.86,87.5%,9.41%` | `#031D2D` |
| `--caa-yellow` | `--accent-hsl` | `42.97,100%,69.61%` | `#FFD364` |
| `--caa-green` | `--lightAccent-hsl` | `141.4,78.8%,57.45%` | `#3DE87A` |
| `--caa-paper` | `--white-hsl` | `0,0%,100%` | `#FFFFFF` |
| `--font-body` | `--body-font-font-family` | `"DM Sans"` | — |
| `--font-display` | `--heading-font-font-family` | `"DM Sans"` | — |

Heading sizes (unitless, fluid `calc()` on the live site): h1 `2.6`, h2 `2.3`, h3 `1.8`, h4 `1`. We do **not** wire these — see below.

### The dual-mode pattern

`src/styles/tokens.css` defines colors as `hsla(var(--<token>, <fallback-triple>), 1)` and fonts as `var(--<token>, "DM Sans"), system-ui, sans-serif`. In Squarespace the `:root` token resolves (inherits live Site Styles); standalone the fallback activates. No per-element rewrites — every page picks it up through the existing `var(--caa-*)` / `var(--font-*)` usage.

What's wired vs not:
- ✅ **Font family** — inherits via `--body/heading-font-font-family`.
- ✅ **Brand colors** — inherit via the HSL tokens above (incl. the `rgba()` brand-tint literals in `global.css`, now `hsla(var(--token, …), α)`).
- ❌ **Heading font-size** — kept on our rem scale. The live site sizes headings with a 3-breakpoint fluid `calc()`; a flat `* 1rem` override would be worse. Minor, intentional divergence.

### Native heading highlight

The live `custom.css` styles `h1 em` (teal bar `#218ca5`) and `h1 strong` / `h3 strong` (yellow bar `#ffd364`) **globally with `!important`**. So:
- Markup uses `<h1>…<em>SB&nbsp;54</em>…</h1>` on the three "SB 54" titles (hub, whats-changing, roles). In Squarespace the site's `!important` rule paints the bar.
- `global.css` carries a non-`!important` fallback copy of those exact gradients so the bar also renders standalone. Site `!important` wins in-context; fallback wins standalone.
- The hand-built `h2::after` gold bar is kept for section headings (our device; the live site doesn't auto-bar h2).
- Module pages take the highlight via the optional `titleHtml` prop on `ModuleLayout`.

### Buttons

`.card__cta` anchors carry `sqs-block-button-element sqs-block-button-element--medium sqs-button-element--primary` in addition to `.card__cta`. The markup is port-ready; standalone, our `.card__cta` CSS styles the pill. **At paste time, strip the `.card__cta` button CSS** so the site's button styling inherits (matches `paste-to-squarespace.html`).

### Generating a paste artifact from a page

The Astro build IS the standalone preview. To produce a Squarespace paste for a page (as was done for the temp landing):
1. Wrap content under a `.caa-sb54` (or page-specific) wrapper so custom CSS can't leak into the host site.
2. Strip the `@import` DM Sans webfont (BaseLayout) — the site serves DM Sans via Site Styles.
3. Strip our `.card__cta` button CSS — let the site button inherit.
4. Keep: layout, spacing, custom containers (bands, cards, timeline, FPO), brand-accent borders. The token wiring already inherits the rest.

Leak-prevention (success criterion "scoped under a wrapper") is enforced at this paste-generation step; the global element rules in `global.css` are the standalone preview layer and do not travel.

### Still to verify

Token *names* are confirmed present on the live site. The end-to-end "paste auto-inherits" check requires pasting into the CAA Squarespace CMS (needs CAA access) — do this when porting each page.

---

## Part 2 — Temp landing mapping

Working doc for porting `src/pages/temp/index.astro` to circularactionalliance.org as an unpublished page. Captures the class taxonomy and CSS-token mapping inferred from the live site (May 2026). Delete once the page is pasted and approved.

## What I learned from the live site

### Squarespace 7.1 design system on this site

- Site uses **Fluid Engine** (their grid system); content blocks live inside `.fluid-engine` containers, each block wrapped in `.fe-block` with a unique ID class
- Typography is driven by **CSS custom properties on `:root`** — `--heading-font-font-family`, `--heading-1-size-value`, `--body-font-font-family`, etc. Set via Site Styles editor; compiled into `site.css`
- All headings use `font-size: calc(var(--heading-N-size-value) * 1rem)` — fluid scaling already wired
- Color tokens are HSL triples: `--accent-hsl`, `--black-hsl`, etc., consumed via `hsla(var(--token-hsl), 1)`

### Brand colors already on the site

These show up in their `custom.css` overrides (so they're applied, not inherited from defaults):

- **`#218ca5` — Trusted Teal** (matches our `--caa-teal` exactly). Used for: nav active/hover, `<h1><em>` highlight, header link hover
- **`#ffd364` — soft yellow** (different from our `#FFB81C`). Used for: `<h1><strong>` highlight bar
- Section-tinted yellows/oranges for hero accents: `#f99a53`, `#dd9e10`, `#4686fb`, `#852133`, `#33773a`, `#8f8cb7`

The custom.css uses `!important` heavily, so these overrides will apply to our pasted content too.

### Decorative typographic patterns (theirs, free for us to use)

- `<h1><em>text</em></h1>` → text gets a Trusted Teal underline highlight bar
- `<h1><strong>text</strong></h1>` → text gets a yellow underline highlight bar

Examples on /california: `<h1><em>California</em></h1>`, `<h1><strong>FAQ</strong></h1>`. We can lean on these for our hero treatments.

### Font (updated 2026-05-08)

Avenir Next LT Pro is now licensed via Adobe Fonts. Family name (all weights):

```css
font-family: avenirnext-lt-pro-ultlight, sans-serif;
```

Weights and styles:

| Weight | font-weight | font-style |
|---|---|---|
| Regular | 400 | normal |
| Italic | 400 | italic |
| Medium | 500 | normal |
| Medium Italic | 500 | italic |
| Bold | 800 | normal |
| Bold Italic | 800 | italic |
| Heavy | 900 | normal |
| Heavy Italic | 900 | italic |

**Precondition for our paste to render correctly**: the Adobe Fonts kit needs to be loaded on circularactionalliance.org AND Squarespace's Site Styles → Fonts → Heading + Paragraph need to be set to this family. Otherwise our content inherits whatever the site currently uses (Helvetica fallbacks based on what's in `site.css`).

If that config isn't done yet, we have two choices:
- **Wait** for that config to land (cleanest — single source of truth)
- **Belt-and-suspenders** — set `font-family: avenirnext-lt-pro-ultlight, sans-serif` on a wrapper class in our pasted CSS so it shows the right font even if Squarespace fallback is wrong, but this assumes the kit JS is loaded on the page (which it would be once the kit is added site-wide via Code Injection per the Adobe Fonts → Squarespace tutorial)

### Button taxonomy (Squarespace 7.1)

Found two class patterns in use:

```html
<!-- Standard button block -->
<a class="sqs-block-button-element sqs-block-button-element--medium sqs-button-element--primary" href="...">Sign Up</a>

<!-- List-item button (inside list sections) -->
<a class="list-item-content__button sqs-block-button-element sqs-block-button-element--medium sqs-button-element--primary" href="...">Read the press release</a>
```

Variants:

- **Size**: `--small` | `--medium` | `--large` (suffix on `sqs-block-button-element--`)
- **Style**: `--primary` | `--secondary` | `--tertiary` (suffix on `sqs-button-element--`)

For our CTAs, default to: `sqs-block-button-element sqs-block-button-element--medium sqs-button-element--primary`. Wrap in their container if we want centered alignment (`<div class="sqs-block-button-container--center">`).

## Mapping: ours → theirs

| Our element | Their pattern | Notes |
|---|---|---|
| Custom `<h1>` with brand-token color | Plain `<h1>` (optionally `<h1><em>` for teal underline) | Inherits site heading font + size |
| Custom `<h2>`/`<h3>` | Plain `<h2>`/`<h3>` | Inherits |
| Body `<p>` with custom color | Plain `<p>` | Inherits |
| Inline link `<a>` with custom color | Plain `<a>` | Inherits site link color (already teal-adjacent) |
| Our CTA buttons (custom CSS) | `<a class="sqs-block-button-element sqs-block-button-element--medium sqs-button-element--primary">` | Inherits site button styling |
| Our `<ul>`/`<ol>` | Plain | Inherits |
| Our `<strong>`/`<em>` inside `<h1>` | Same — used intentionally for teal/yellow highlights | Decorative pattern from their custom.css |

## What we strip from our CSS

Going through `src/pages/temp/index.astro`:

- ❌ All `font-family` declarations (let inherit)
- ❌ All `font-size` declarations on headings + body (let inherit fluid scaling)
- ❌ All `font-weight` declarations on tags Squarespace styles (h1-h6, p, button)
- ❌ All `color` declarations on body text and links (let inherit)
- ❌ All `--caa-teal`, `--caa-yellow`, `--caa-navy`, `--caa-ink`, `--caa-paper` token usage on text/buttons
- ❌ Our custom button classes (replace markup with Squarespace classes)
- ❌ Anything with `!important` on these properties

## What we keep

- ✅ Layout CSS — flexbox/grid, our specific section structure
- ✅ Spacing — margins, padding, gaps unique to this page's IA
- ✅ Card/panel containers (their visual treatment isn't in the site CSS by default)
- ✅ Scoped under a wrapper class like `.caa-temp-landing` so our rules don't leak into the rest of the page
- ✅ Any iconography/SVG assets

## Open questions for you

1. **Font kit timing**: is Adobe Fonts already configured on the CAA Squarespace site, or is that work in flight? Affects whether we wait or include belt-and-suspenders font-family on our wrapper.
2. **Decorative highlights**: want me to use `<h1><em>` for the page title to get the teal highlight bar, matching the /california page treatment? It's site-native and on-brand.
3. **Wrapper class name**: I'll scope our layout CSS under `.caa-sb54-landing` to avoid bleeding into the rest of the page. OK or prefer something else?

## Risks

- **Brand override leakage**: their custom.css uses `!important` on `<h1><strong>`/`<h1><em>` highlights — if we use those tags incidentally elsewhere in our content, they'll get unintended highlight bars. Audit our content for accidental usage.
- **Block ID collision**: their custom.css targets specific block IDs (`#block-...`). Won't affect us since we won't use those IDs.
- **Code Block stripping**: Squarespace's Code Block has been known to strip certain script tags or modify `<style>` placement. Our build will inline `<style>` in the body, which works in Code Blocks — but if Squarespace strips it, we move it to page Header Code Injection.
- **Site Styles divergence**: if Site Styles → Fonts isn't configured to Avenir Next yet, the page will look right *eventually* (when that config lands) but wrong now. Coordinate the paste with the font config.
