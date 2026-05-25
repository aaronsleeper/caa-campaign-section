# FPO Image Prompts — CAA SB 54 Section

Generation prompts for **For-Placement-Only** imagery across the SB 54 campaign section. Run each prompt through Gemini (Imagen / "Nano Banana") to produce a placeholder. FPO only — every final image ships rights-free or licensed through CAA Communications (`internalcomms@circularaction.org`).

## Source of truth

- **On-page descriptions** are canonical in the `.astro` sources (the `fpo__desc` spans). This file caches them for convenience and owns the *generation prompts*. If a description changes, edit the `.astro` file first, then re-derive the prompt here.
- **Brand visual language** is canonical in `Knowledge/Projects/Change Craft/CAA/Live Site Style Audit.md` — the live `circularactionalliance.org` extraction, which **supersedes Visual Standards v1** for anything visual (per Aaron, 2026-05-24). The prompts below use the live-site palette, not the v1 hexes in this repo's `CLAUDE.md`.

## Brand palette (live site — use in every prompt)

| Role | Name | Hex | Use |
|---|---|---|---|
| Navy | Source Navy | `#031D2D` | Dominant ground, deep blocks |
| Teal | Trusted Teal | `#196D80` | Primary brand color, blocks, motion |
| Gold | Action Gold | `#FFD364` | Accent only — one focal moment per image |
| Green | — | `#3DE87A` | Sparing accent, optional |
| Paper | White | `#FFFFFF` | Whitespace, clean ground |

## Unity Spark motif

The brand signature: a **four-fold radial pinwheel of interlocking curved arches** (rotational symmetry, like overlapping crescent petals spiraling out from a center). Represents Producers / States / Communities connecting. May appear as a semi-transparent overlay, a crop frame ("circular crop"), or layered abstract arcs. It is a *geometric brand mark*, never a literal sun/flower.

## Global rules baked into every prompt

- Recyclables read as **valuable commodities** — clean, organized, sorted, on a neutral or brand-color ground. Never as trash, litter, mess, or dirty waste.
- **No text, no words, no logos, no watermarks** in the generated image (logo is placed separately on the page; Gemini garbles text).
- Brand palette dominates 95–100% of the composition; gold is a single accent moment.
- Even, optimistic, professional lighting; constructive partner tone, not corporate stock cliché.
- **Negative prompt** (append where the tool supports it): `trash, garbage, litter, dirty, messy, waste pile, text, words, letters, logo, watermark, distorted hands, cluttered`

## Reusable style suffix

Append this to any prompt if you want to tighten brand fidelity:

> Color palette restricted to deep navy `#031D2D`, trusted teal `#196D80`, warm gold `#FFD364` accent, and clean white; generous negative space; modern, optimistic, professional; flat brand-forward art direction echoing a four-fold radial pinwheel of interlocking arches; no text or logos.

---

## Slots

### 1 · Hub hero panel A — `src/pages/index.astro:18`

- **Mode:** Abstract Circular Motion · **Aspect:** ~3:4 / flexible panel (side-by-side hero block)
- **On-page desc:** Abstract Circular Motion — layered Unity Spark arcs in teal & navy.

> Abstract brand graphic: layered, semi-transparent interlocking curved arches arranged in four-fold radial symmetry — a pinwheel of crescent forms spiraling from a center, suggesting a system coming together. Deep navy `#031D2D` ground with trusted teal `#196D80` arcs, a single warm gold `#FFD364` highlight arc. Flat vector style, smooth gradients, generous negative space, no literal objects. No text, no logos.

### 2 · Hub hero panel B — `src/pages/index.astro:22`

- **Mode:** Packaging as Circular Art · **Aspect:** ~3:4 / flexible panel
- **On-page desc:** California system — clean recovered material as valuable commodity.

> A clean, organized arrangement of recovered recyclable materials — clear glass, baled paper fiber, sorted plastics, aluminum — presented as valuable commodities in a tidy, bold composition on a trusted teal `#196D80` ground. Materials look pristine and intentional, like a product display, not waste. Soft even lighting, brand-forward, a single warm gold `#FFD364` accent. No text, no logos, nothing dirty.

### 3 · Hub cover image — `src/pages/index.astro:63`

- **Mode:** Abstract Circular Motion · **Aspect:** 16:9
- **On-page desc:** Abstract Circular Motion: layered, semi-transparent Unity Spark arcs in teal and navy — a system coming together. No literal objects; the brand signature as the cover image.

> A wide hero cover graphic built entirely from the brand signature: large, layered, semi-transparent interlocking curved arches in four-fold radial symmetry — overlapping crescent petals spiraling outward, conveying motion, depth, and connection. Deep navy `#031D2D` and trusted teal `#196D80` arcs over a clean ground, one warm gold `#FFD364` accent arc. Purely abstract, no literal objects, generous negative space, flat vector art direction. No text, no logos.

### 4 · What's Changing (M1) — `src/pages/whats-changing.astro:90`

- **Mode:** Community Photography · **Aspect:** 16:9
- **On-page desc:** Community photography: recycling-program staff or local operators at work, clean and purposeful, framed within a circular crop that echoes the Unity Spark. Recyclables shown as valuable commodities, never as trash.

> Documentary-style community photograph: recycling-program staff and local operators at work in a clean, well-lit facility, purposeful and engaged, handling sorted recyclable materials that look like valuable commodities. Composition framed within a soft circular crop echoing a radial pinwheel motif. Trusted teal `#196D80` and navy `#031D2D` tones in the environment, warm natural light, optimistic and dignified. People as collaborators. No trash, no mess, no text, no logos.

### 5 · Roles & Responsibilities (M2) — `src/pages/roles-and-responsibilities.astro:30`

- **Mode:** Community Photography · **Aspect:** 16:9
- **On-page desc:** Community photography: a jurisdiction coordinator and a hauler operator in conversation on-site — every role working together. Clean facility, organized materials, circular crop echoing the Unity Spark.

> Documentary-style community photograph: a jurisdiction coordinator and a hauler operator in friendly conversation on-site at a clean, organized recycling facility — two roles collaborating as partners. Sorted recyclable materials visible as valuable commodities in the background. Soft circular crop echoing a radial pinwheel motif; trusted teal and navy environmental tones, warm even light, respectful and constructive. No trash, no clutter, no text, no logos.

### 6 · Reimbursement gateway (M3) — `src/pages/reimbursement/index.astro:18`

- **Mode:** Packaging as Circular Art · **Aspect:** 16:9
- **On-page desc:** Circular Art: covered-material categories (cartons, bottles, fiber, film) arranged as a clean circular still life — valuable commodities, not trash.

> A bold still-life arrangement of covered-material categories — beverage cartons, clean bottles, paper fiber, plastic film — composed into a precise circular layout, like a designed product flat-lay. Materials are pristine, sorted, and reframed as valuable commodities. Trusted teal `#196D80` ground with navy `#031D2D` depth and a single warm gold `#FFD364` accent. Crisp studio lighting, brand-forward art direction. No trash, no dirt, no text, no logos.

### 7 · Collection systems (M3b) — `src/pages/reimbursement/collection.astro:29`

- **Mode:** Community Photography / Abstract Motion · **Aspect:** 16:9
- **On-page desc:** Community photography or abstract motion: a collection route or cart fleet, organized and purposeful — covered materials collected cleanly. Circular crop echoing the Unity Spark.

> Documentary-style photograph of an organized recycling collection route: a tidy fleet of collection carts or a clean collection truck on a residential street, purposeful and well-maintained, covered materials collected cleanly with no spillage. Soft circular crop echoing a radial pinwheel motif; trusted teal and navy tones, bright optimistic daylight. Orderly and professional. No trash on the ground, no mess, no text, no logos.

### 8 · Local programs (M3a) — `src/pages/reimbursement/local-programs.astro:29`

- **Mode:** Community Photography · **Aspect:** 16:9
- **On-page desc:** Community photography: a local outreach event or curbside drop-off — residents engaging with a recycling program, clean bins, organized materials. People as collaborators, not subjects.

> Documentary-style community photograph: a local recycling outreach event or curbside drop-off where residents engage warmly with a recycling program — clean labeled bins, organized sorted materials, friendly volunteers. People shown as active collaborators, not subjects. Trusted teal and navy environmental accents, warm natural light, welcoming and community-driven. No trash piles, no clutter, no text, no logos.

### 9 · Processing — abstract (M3c) — `src/pages/reimbursement/processing.astro:28`

- **Mode:** Abstract Circular Motion · **Aspect:** 16:9
- **On-page desc:** Abstract Circular Motion: dynamic looping forms suggesting material flowing through to viable end markets — conceptual, brand-palette, no literal facility shot needed.

> Abstract conceptual graphic: dynamic looping ribbon-like forms flowing in a continuous circuit, suggesting recovered material moving through processing into viable end markets. Built from smooth interlocking arcs in trusted teal `#196D80` and navy `#031D2D` over a clean ground, with one warm gold `#FFD364` accent loop. Sense of motion, flow, and closed-loop continuity; flat vector art direction, generous negative space. No literal facility, no objects, no text, no logos.

### 10 · Processing — circular art (M3c) — `src/pages/reimbursement/processing.astro:53`

- **Mode:** Packaging as Circular Art · **Aspect:** 16:9
- **On-page desc:** Circular Art: a MRF sorting line or baled clean commodities arranged as a bold, organized composition — recyclables as valuable material, never as waste. Brand-palette ground.

> A bold, organized composition of a materials recovery facility sorting line or neatly stacked bales of clean recovered commodities — sorted plastics, fiber, and metal presented as valuable industrial material, precise and orderly. Brand-palette ground in trusted teal `#196D80` and navy `#031D2D`, crisp directional lighting, a single warm gold `#FFD364` accent. Reads as valuable commodity, never as waste. No trash, no grime, no text, no logos.
