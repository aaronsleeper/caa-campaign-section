# FPO Image Prompts — CAA SB 54 Section

Generation prompts for **For-Placement-Only** imagery across the SB 54 campaign section. FPO only — every final image ships rights-free or licensed through CAA Communications (`internalcomms@circularaction.org`).

## How to run these

1. Copy the **Persistent context** block once.
2. Copy the **one numbered prompt** for the slot you're generating.
3. Paste both into Gemini together (context first, then the prompt).

Do **not** paste the whole file — pasting all the context plus layout notes made Gemini bake the page's chrome (corner blocks, edge arcs) into the image. The context block below is the trimmed, image-safe version.

## Source of truth

- **On-page descriptions** are canonical in the `.astro` sources (the `fpo__desc` spans). This file caches them per slot and owns the *generation prompts*. If a description changes, edit the `.astro` file first, then re-derive the prompt.
- **Brand visual language** is canonical in `Knowledge/Projects/Change Craft/CAA/Live Site Style Audit.md` — the live `circularactionalliance.org` extraction, which **supersedes Visual Standards v1** for anything visual (per Aaron, 2026-05-24). The palette below is the live-site palette, not the v1 hexes in this repo's `CLAUDE.md`.

---

## Persistent context — copy this first, every time

```
Brand image system for the Circular Action Alliance (CAA) SB 54 campaign. Every image follows these rules:

PALETTE: deep Source Navy #031D2D, Trusted Teal #196D80 (primary), warm Action Gold #FFD364 (accent only — exactly one focal moment), optional sparing green #3DE87A, clean white. Brand colors fill 95–100% of the composition.

MOTIF — the Unity Spark: a four-fold radial pinwheel of interlocking curved arches (overlapping crescent forms in rotational symmetry, spiraling from a center). May appear as a semi-transparent overlay or as a soft circular crop. It is a geometric brand mark, never a literal sun or flower.

COMMODITIES: recyclable materials always read as valuable commodities — clean, sorted, organized, intentional. Never as trash, litter, dirt, spillage, or mess.

FRAME: the image fills the full frame edge-to-edge. No border blocks, framing panels, or corner color-blocks — the webpage supplies its own chrome.

CLEAN: no text, words, letters, logos, watermarks, or decorative sparkles/stars anywhere in the image.

STYLE: even, optimistic, professional lighting; modern, flat, brand-forward art direction; generous negative space; constructive partner tone, not corporate stock cliché.

NEGATIVE PROMPT: trash, garbage, litter, dirty, messy, waste pile, spillage, text, words, letters, logo, watermark, sparkle, star, border, frame, distorted hands, cluttered.
```

---

## Prompts — paste one below the context

### 1 · Hub hero panel A — `src/pages/index.astro:18`

Abstract Circular Motion · **Aspect 3:4** (narrow side-by-side panel)

```
Layered, semi-transparent interlocking curved arches in four-fold radial symmetry — a pinwheel of crescent forms spiraling from a center, suggesting a system coming together. Deep navy ground, trusted teal arcs, a single warm gold highlight arc. Flat vector style, smooth gradients, purely abstract with no literal objects. Aspect ratio 3:4.
```

### 2 · Hub hero panel B — `src/pages/index.astro:22`

Packaging as Circular Art · **Aspect 3:4** (narrow side-by-side panel)

```
A clean, organized arrangement of recovered recyclable materials — clear glass cullet, baled paper fiber, sorted plastic pellets, aluminum ingots — presented as valuable commodities in a tidy, intentional composition on a trusted teal ground. Materials look pristine, like a product display. Soft even lighting, a single warm gold accent. Aspect ratio 3:4.
```

### 3 · Hub cover image — `src/pages/index.astro:63`

Abstract Circular Motion · **Aspect 16:9**

```
A wide hero cover built entirely from the brand signature: large, layered, semi-transparent interlocking curved arches in four-fold radial symmetry — overlapping crescent petals spiraling outward, conveying motion, depth, and connection. Deep navy and trusted teal arcs over a clean ground, one warm gold accent arc. Purely abstract, no literal objects, generous negative space. Aspect ratio 16:9.
```

### 4 · What's Changing (M1) — `src/pages/whats-changing.astro:90`

Community Photography · **Aspect 16:9**

```
Documentary-style photograph: recycling-program staff and local operators at work in a clean, well-lit facility, purposeful and engaged, handling sorted recyclable materials that look like valuable commodities. Composition framed within a soft circular crop echoing the radial pinwheel motif. Teal and navy environmental tones, warm natural light, optimistic and dignified. People as collaborators. Aspect ratio 16:9.
```

### 5 · Roles & Responsibilities (M2) — `src/pages/roles-and-responsibilities.astro:30`

Community Photography · **Aspect 16:9**

```
Documentary-style photograph: a jurisdiction coordinator and a hauler operator in friendly conversation on-site at a clean, organized recycling facility — two roles collaborating as partners. Sorted recyclable materials visible as valuable commodities in the background. Soft circular crop echoing the radial pinwheel motif; teal and navy environmental tones, warm even light, respectful and constructive. Aspect ratio 16:9.
```

### 6 · Reimbursement gateway (M3) — `src/pages/reimbursement/index.astro:18`

Packaging as Circular Art · **Aspect 16:9**

```
A bold still-life of covered-material categories — beverage cartons, clean bottles, paper fiber, plastic film — composed into a precise circular layout, like a designed product flat-lay. Materials are pristine, sorted, reframed as valuable commodities. Trusted teal ground with navy depth and a single warm gold accent. Crisp studio lighting, brand-forward art direction. Aspect ratio 16:9.
```

### 7 · Collection systems (M3b) — `src/pages/reimbursement/collection.astro:29`

Community Photography / Abstract Motion · **Aspect 16:9**

```
Documentary-style photograph of an organized recycling collection route: a tidy fleet of collection carts or a clean collection truck on a residential street, purposeful and well-maintained, covered materials collected cleanly with no spillage. Soft circular crop echoing the radial pinwheel motif; teal and navy tones, bright optimistic daylight. Orderly and professional. Aspect ratio 16:9.
```

### 8 · Local programs (M3a) — `src/pages/reimbursement/local-programs.astro:29`

Community Photography · **Aspect 16:9**

```
Documentary-style photograph: a local recycling outreach event or curbside drop-off where residents engage warmly with a recycling program — clean labeled bins, organized sorted materials, friendly volunteers. People shown as active collaborators, not subjects. Teal and navy environmental accents, warm natural light, welcoming and community-driven. Aspect ratio 16:9.
```

### 9 · Processing — abstract (M3c) — `src/pages/reimbursement/processing.astro:28`

Abstract Circular Motion · **Aspect 16:9**

```
Abstract conceptual graphic: dynamic looping ribbon-like forms flowing in a continuous circuit, suggesting recovered material moving through processing into viable end markets. Built from smooth interlocking arcs in trusted teal and navy over a clean ground, with one warm gold accent loop. Sense of motion, flow, and closed-loop continuity; flat vector art direction, generous negative space. No literal facility. Aspect ratio 16:9.
```

### 10 · Processing — circular art (M3c) — `src/pages/reimbursement/processing.astro:53`

Packaging as Circular Art · **Aspect 16:9**

```
A bold, organized composition of a materials recovery facility sorting line or neatly stacked bales of clean recovered commodities — sorted plastics, fiber, and metal presented as valuable industrial material, precise and orderly. Brand-palette ground in trusted teal and navy, crisp directional lighting, a single warm gold accent. Reads as valuable commodity, never as waste. Aspect ratio 16:9.
```
