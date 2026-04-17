# CAA Campaign Section

Local static prototype for the SB 54 interest-holder campaign section on `circularactionalliance.org`. Serves as spec artifact + portable reference for whoever ports to Squarespace.

## Source of truth

All IA, UX, and copy decisions live in `Stack Overflowed/Projects/Change Craft/CAA/`:
- `IA and UX Recommendation.md` — approved IA, page templates, gateway pattern, CTAs, navigation, terminology
- `Design Brief.md` — colors, typography, logo rules, imagery style
- `Creative Brief - Interest Holder Materials 4-10-26.md` — per-module content (objectives, audiences, key messages, user journeys)
- `Questions for Brandon.md` — open external questions (don't assume answers)

## Brand rules (from Design Brief)

### Colors
```css
--caa-teal: #218CA5;       /* Trusted Teal — primary */
--caa-navy: #0B3647;       /* Source Navy — primary */
--caa-yellow: #FFB81C;     /* Action Yellow — accent ONLY (CTAs, highlights) */
--caa-ink: #242424;         /* Body text */
--caa-paper: #FFFFFF;       /* Background */
```

Core + white space = 95–100% of any composition. Action Yellow on exactly one element per card/section (the CTA). Secondary palette (data viz only): `#08518F`, `#E06940`, `#B5A8BF`, `#7ABE96`, `#D8E04D`, `#9DE5DD`.

### Typography
- **Body:** Avenir Next LT Pro (Book, Medium, Heavy, Black). Not a Google Font — licensing pending (see Questions for Brandon). **Fallback:** `"Nunito Sans", system-ui, sans-serif` — flagged as non-brand-compliant.
- **Display/headlines:** Montserrat (Google Fonts). Headlines only — never body. Montserrat is approved for comms team and agencies.
- **Hierarchy:** Headline ~200–250% of body, Subhead ~120–140%, Body 16px preferred (14px minimum).
- **Line length:** 45–75 characters.
- Do not introduce additional fonts.

### Logo
- One logo per page. Prefer corner placement.
- Occupy no more than 1/3 live-area width.
- Clear space = height of the "C" in the logo.
- Source vector: `../Stack Overflowed/Projects/Change Craft/CAA/CAA-logo-page-vector.svg` (needs isolation in Illustrator/Figma).

### Imagery
- Packaging as Circular Art / Community Photography / Abstract circular forms.
- Recyclables are **valuable commodities, never trash** — items must look clean, organized.
- All images rights-free or licensed through CAA Communications.

## Site structure

```
/california/sb54/                        ← Hub
    /whats-changing/                     ← Module 1: What SB 54 Means for You
    /roles-and-responsibilities/         ← Module 2: Roles and Responsibilities Under SB 54
    /reimbursement/                      ← Module 3: Reimbursement for Covered Costs (gateway)
        /local-programs/                 ← 3a: Local Programs
        /collection/                     ← 3b: Collection Systems
        /processing/                     ← 3c: Processing and End Markets
    /questions/                          ← Questions (tag-filtered, dual-surface)
```

## Three page templates

1. **Hub** — campaign name, value prop, 3 module cards, footer (Questions link, contact)
2. **Module page** (1, 2, 3a, 3b, 3c) — Hero (H1 + one-liner), "Why this matters," key messages, deck embed, video, FAQ accordion, stacked CTA block, prev/next nav
3. **Gateway** (Module 3 only) — Hero, 3 tri-cards with audience tags + CTAs, soft egress link. No stacked CTA block.

## Navigation

GOV.UK step-by-step simplified:
- Desktop: sticky left-column list (Hub → M1 → M2 → M3 with 3a/3b/3c indented), current page highlighted in Trusted Teal
- Mobile: top "In this section" accordion
- Prev/next buttons at page bottom
- No completion checkmarks (sub-modules are parallel, not sequential)

## Stack

- Astro (static site generator)
- CSS custom properties for design tokens
- Montserrat via Google Fonts; Avenir Next fallback to Nunito Sans until licensing resolves
- No JS frameworks — vanilla JS only where needed (Questions page tag filters, nav accordion)
- Deploy to Netlify or Vercel for preview — not publicly indexed until CAA approves

## Language conventions

- "Interest holders" — not "stakeholders" (CAA's term; use in body copy, not URLs or navigation)
- Recyclables are "valuable commodities, never trash"
- Producers are collaborators, not offenders
- No hedging: avoid "may," "might," "could," "important to note"
- Confident and grounded, not promotional
- Inline-gloss on first use: CMC, "new or additional," Covered Costs
- Tooltip on first use: E&O, JPA, PRO, end markets
- Every dollar amount, date, or statutory citation needs `[VERIFY]` in draft

## Do not

- Use haven-ui components or tokens — this is a separate brand system
- Commit Avenir Next LT Pro font files (licensing unresolved)
- Deploy to a publicly indexed URL without CAA approval
- Edit files in `Stack Overflowed/Projects/Change Craft/CAA/` from this project — those are source-of-truth docs
