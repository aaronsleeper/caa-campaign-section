# FPO Image Prompts — CAA SB 54 Section

Generation prompts for **For-Placement-Only** imagery across the SB 54 campaign section. FPO only — every final image ships rights-free or licensed through CAA Communications (`internalcomms@circularaction.org`).

## How to run these

1. Copy the **Persistent context** block once.
2. Copy the **one numbered prompt** for the slot you're generating.
3. Paste both into Gemini together (context first, then the prompt).

Do **not** paste the whole file — pasting all the context plus layout notes made Gemini bake the page's chrome (corner blocks, edge arcs) into the image. The context block below is the trimmed, image-safe version.

## Imagery-mode strategy (CAA Visual Designer, 2026-05-24)

- **Primary modes: Community Photography + Packaging-as-Circular-Art.** This is an operator-facing education microsite — interest holders need to see real work, real people, and their materials as commodities. These modes carry the section.
- **Abstract Circular Motion is an accent, not a hero.** Use it for section dividers, a quiet background band behind a heading, or a hero's secondary panel — never as a standalone primary hero. It's connective tissue, not the headline act.
- **Unity Spark on photos lives in CSS, never in the image.** Generated brand-art (packaging still lifes, pure abstract) may embody the Spark internally; photographs get any circular crop / arc framing from the page (clip-path / mask / SVG overlay) so it never slices a subject. When the Spark appears it is CAA's interlocking-arches mark, not a generic spirograph.

## Source of truth

- **On-page descriptions** are canonical in the `.astro` sources (the `fpo__desc` spans). This file caches them per slot and owns the *generation prompts*. If a description changes, edit the `.astro` file first, then re-derive the prompt.
- **Brand visual language** is canonical in `Knowledge/Projects/Change Craft/CAA/Live Site Style Audit.md` — the live `circularactionalliance.org` extraction, which **supersedes Visual Standards v1** for anything visual (per Aaron, 2026-05-24). The palette below is the live-site palette, not the v1 hexes in this repo's `CLAUDE.md`.

---

## Persistent context — copy this first, every time

```
Brand image system for the Circular Action Alliance (CAA) SB 54 campaign. Every image follows these rules:

PALETTE: deep Source Navy #031D2D, Trusted Teal #196D80 (primary), warm Action Gold #FFD364, optional sparing green #3DE87A, clean white. Gold is the warm accent and may be used freely — but it must be the soft live-site gold #FFD364, NEVER a saturated amber/marigold (#FFB81C). Brand colors fill 95–100% of the composition.

MOTIF — the Unity Spark: a four-fold radial pinwheel of interlocking curved arches (overlapping crescent forms in rotational symmetry, spiraling from a center). It is a geometric brand mark, never a literal sun or flower. Use it ONLY in abstract/graphic images. NEVER paint arcs, swirls, circular crops, or pinwheel shapes on top of a photograph — photographs stay clean and full-bleed; any circular framing is added later in CSS by the page, not by the image.

COMMODITIES: recyclable materials always read as valuable commodities — clean, sorted, organized, intentional. Never as trash, litter, dirt, spillage, or mess.

FRAME: the image fills the full frame edge-to-edge. No border blocks, framing panels, or corner color-blocks — the webpage supplies its own chrome.

CLEAN: no text, words, letters, logos, watermarks, or decorative sparkles/stars anywhere in the image.

STYLE: even, optimistic, professional lighting; modern, flat, brand-forward art direction; generous negative space; constructive partner tone, not corporate stock cliché.

NEGATIVE PROMPT: trash, garbage, litter, dirty, messy, waste pile, spillage, text, words, letters, logo, watermark, sparkle, star, border, frame, distorted hands, cluttered.
```

---

## Prompts — paste one below the context

### 1 · Hub hero panel A — `src/pages/index.astro:18`

Packaging as Circular Art · **Aspect 3:4** (narrow side-by-side panel)
**REGEN** — expert reassigned from abstract to packaging-art, to partner with panel B. (Don't give a meaningless spirograph half the most important viewport on the site.)

```
A clean, organized arrangement of recovered recyclable materials shot from above on a deep navy ground — sorted clear plastics, aluminum cans, paper fiber — presented as valuable commodities in a tidy, intentional composition. Materials look pristine, like a product display. Soft even lighting, a single soft gold #FFD364 accent. Aspect ratio 3:4.
```

### 2 · Hub hero panel B — `src/pages/index.astro:22` — ✅ KEEP

Packaging as Circular Art · **Aspect 3:4** (narrow side-by-side panel)
Expert verdict: best image in the set, on-thesis. Regen only if pairing with a new panel 1 demands a matched ground.

```
A clean, organized arrangement of recovered recyclable materials — clear glass cullet, baled paper fiber, sorted plastic pellets, aluminum ingots — presented as valuable commodities in a tidy, intentional composition on a trusted teal ground. Materials look pristine, like a product display. Soft even lighting, a single warm gold accent. Aspect ratio 3:4.
```

### 3 · Hub "who this is for" split — `src/pages/index.astro:63`

Community Photography · **Aspect 16:9**
**REPLACE-MODE** — expert moved this off abstract. The slot routes audiences (jurisdictions, haulers, MRFs, Tribal staff); it should show those people, not a spirograph. (Alternative: a calm teal/navy live-site-style color block — decide in layout.)

```
Clean, full-bleed documentary-style photograph (no graphic shapes or arcs overlaid): a small group of recycling-system operators — a jurisdiction coordinator, a hauler in hi-vis, an MRF worker — standing together on-site at a clean facility, approachable and capable. Sorted recyclable commodities visible nearby. Teal and navy environmental tones, warm even light, institutional and grounded. Aspect ratio 16:9.
```

### 4 · What's Changing (M1) — `src/pages/whats-changing.astro:90`

Community Photography · **Aspect 16:9**

```
Clean, full-bleed documentary-style photograph (no graphic shapes or arcs overlaid): recycling-program staff and local operators at work in a clean, well-lit facility, purposeful and engaged, handling sorted recyclable materials that look like valuable commodities. Teal and navy environmental tones, warm natural light, optimistic and dignified. People as collaborators. Aspect ratio 16:9.
```

### 5 · Roles & Responsibilities (M2) — `src/pages/roles-and-responsibilities.astro:30`

Community Photography · **Aspect 16:9**

```
Clean, full-bleed documentary-style photograph (no graphic shapes or arcs overlaid): a jurisdiction coordinator and a hauler operator in friendly conversation on-site at a clean, organized recycling facility — two roles collaborating as partners. Sorted recyclable materials visible as valuable commodities in the background. Teal and navy environmental tones, warm even light, respectful and constructive. Aspect ratio 16:9.
```

### 6 · Reimbursement gateway (M3) — `src/pages/reimbursement/index.astro:18` — ✅ KEEP

Packaging as Circular Art · **Aspect 16:9**
Expert verdict: right mode for a gateway hero, on-brand. Optional micro-nit: make the green flecks read as ground pellet/material, not confetti.

```
A bold still-life of covered-material categories — beverage cartons, clean bottles, paper fiber, plastic film — composed into a precise circular layout, like a designed product flat-lay. Materials are pristine, sorted, reframed as valuable commodities. Trusted teal ground with navy depth and a single warm gold accent. Crisp studio lighting, brand-forward art direction. Aspect ratio 16:9.
```

### 7 · Collection systems (M3b) — `src/pages/reimbursement/collection.astro:29`

Community Photography / Abstract Motion · **Aspect 16:9**

```
Clean, full-bleed documentary-style photograph (no graphic shapes or arcs overlaid): an organized recycling collection route — a tidy fleet of recycling collection carts or a clean recycling truck on a residential street, purposeful and well-maintained, covered materials collected cleanly with no spillage. Teal and navy tones, bright optimistic daylight. Orderly and professional. Aspect ratio 16:9.
```

### 8 · Local programs (M3a) — `src/pages/reimbursement/local-programs.astro:29`

Community Photography · **Aspect 16:9**

```
Clean, full-bleed documentary-style photograph (no graphic shapes or arcs overlaid): a local recycling outreach event or curbside drop-off where residents engage with a recycling program — clean labeled bins, organized sorted materials, volunteers in teal vests. People shown as active collaborators, not subjects. Neutral, operational daylight (avoid golden-hour glow or sentimental campaign mood). Teal and navy environmental accents. Aspect ratio 16:9.
```

### 9 · Processing — abstract (M3c) — `src/pages/reimbursement/processing.astro:28`

Abstract Circular Motion (accent — the one abstract worth keeping) · **Aspect 16:9**
Expert: tighten toward "material flowing to end markets" — show commodities resolving into the loop, not a generic swoosh.

```
Abstract conceptual graphic: small clean recovered materials (pellets, flakes, fiber) at the edges resolving into smooth interlocking ribbon-loops that flow in a continuous closed circuit — recovered material moving through processing into viable end markets. Trusted teal #196D80 ribbons over a deep navy #031D2D ground, one soft gold #FFD364 accent loop. Sense of motion, flow, and closed-loop continuity; flat vector art direction, generous negative space. Aspect ratio 16:9.

> Regen note (2026-05-24): the first cut came back on a WHITE ground that bled into the page white. Navy ground specified above fixes contrast + matches the rest of the set. A CSS containment edge (`.fpo--filled` border + shadow) is also in place as a guardrail for any light-ground image.
```

### 10 · Processing — circular art (M3c) — `src/pages/reimbursement/processing.astro:53`

Packaging as Circular Art · **Aspect 16:9**
**GENERATE** — not yet made; expert prioritized this (the missing packaging-art piece) over re-running abstracts.

```
A bold, organized still-life of neatly stacked bales of clean recovered commodities — baled PET, crushed aluminum, baled paper fiber — arranged into a precise circular composition like a designed product flat-lay, presented as valuable industrial material, precise and orderly. Trusted teal #196D80 ground with navy #031D2D depth, crisp directional lighting, a single soft gold #FFD364 accent. Reads as valuable commodity, never as waste. Aspect ratio 16:9.
```

### 11 · Share image (Open Graph / Twitter) — `src/layouts/BaseLayout.astro:11`

Packaging as Circular Art · **Aspect 1.91:1** (target 1200×630 — Open Graph / Twitter `summary_large_image` standard)
**GENERATE** — currently filled by `public/fpo/3.png` (the operator-group documentary photo) as a placeholder. Save the final asset to `public/fpo/share.png` and update `DEFAULT_OG_IMAGE` in `src/layouts/BaseLayout.astro` to match — keeps slot 3's photo intact for its in-page use.

This is the section-wide default surfacing whenever any SB 54 page is shared (Slack, LinkedIn, iMessage, Teams). It needs to scan as the campaign at thumbnail size — one strong centered focal point, brand-forward palette, generous breathing room so platform crops don't kill the composition. Per the imagery-mode strategy, packaging-art is the right mode here — a single documentary photo doesn't read as "the campaign" the way a brand-forward circular composition does.

```
A bold, brand-forward still-life of clean recovered recyclable materials — sorted aluminum, clear plastic pellets, baled paper fiber, crushed glass cullet — composed into a single tight circular flat-lay at the center of the frame, like a designed product display. Materials are pristine, organized, intentional, reframed as valuable commodities. Trusted teal #196D80 ground with deep Source Navy #031D2D shadow at the edges, a single soft Action Gold #FFD364 accent within the composition. Crisp even studio lighting, flat modern art direction, generous negative space around the central composition so it reads cleanly at small thumbnail sizes and survives off-center cropping on social platforms. Aspect ratio 1.91:1.
```
