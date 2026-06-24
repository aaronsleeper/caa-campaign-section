# AI Imagery POV Compliance — Tier Audit + Disclosure Component Spec

Cross-references Brandon Tate's AI Imagery POV (Change Craft → CAA, June 2026) against the FPO imagery currently shipping in this prototype, and specs the production-ready disclosure pattern for Tier 2 imagery that survives Larine sign-off.

**Sources:**
- POV markdown: `/tmp/caa-pov.md` (extracted from `CAA_CC AI Imagery POV (June 2026).docx`)
- Quick reference: `/tmp/caa-quickref.md`
- Generation prompts: [IMAGE-PROMPTS.md](IMAGE-PROMPTS.md)
- Prior generation history: [`~/.claude/plans/caa-sb54-fpo-images.md`](../../.claude/plans/caa-sb54-fpo-images.md)

## Tier classification — current FPO slots

Per the POV's three-tier framework (Green internal / Yellow stylized-public / Red real-people/places/facilities):

| Slot | File | Mode | POV tier | Path forward |
|---|---|---|---|---|
| 1 | `index.astro` (hero A) | Packaging-as-Circular-Art | **Tier 2 YELLOW** | Regen on approved platform + AI-disclosure badge + Larine batch sign-off |
| 2 | `index.astro` (hero B) | Packaging-as-Circular-Art | **Tier 2 YELLOW** | Same — KEEP current pending Vertex-AI regen if it differentiates |
| 3 | `index.astro` (hub split) | Community Photography | **Tier 3 RED** | Commission California-based community photographer per POV §"Where Change Craft recommends retaining human creators" |
| 4 | `whats-changing.astro` | Community Photography | **Tier 3 RED** | Commission facility photography |
| 5 | `roles-and-responsibilities.astro` (video placeholder) | Community Photography | **Tier 3 RED** | Replace with video OR commission photography; current FPO is interim |
| 6 | `reimbursement/index.astro` | Packaging-as-Circular-Art | **Tier 2 YELLOW** | Regen on approved platform + disclosure |
| 7 | `reimbursement/collection.astro` | Community Photography | **Tier 3 RED** | Commission collection-route photography |
| 8 | `reimbursement/local-programs.astro` | Abstract overlay pattern | **Tier 2 YELLOW** | Regen on approved platform + disclosure |
| 9 | `reimbursement/processing.astro` (abstract) | Abstract circular | **Tier 2 YELLOW** | Regen on approved platform + disclosure |
| 10 | `reimbursement/processing.astro` (packaging) | Packaging-as-Circular-Art | **Tier 2 YELLOW** | Regen on approved platform + disclosure |

**Classification source-of-truth:** POV explicitly designates as Tier 3 RED any "depiction of California communities affected by plastic pollution," "recycling facilities, sorting lines, or material recovery operations," and any "documentary-style" photographic framing. The five Community Photography slots match all three criteria.

## Friday-draft handling (interim build state)

The Tier 3 slots carry a `.fpo__pov-flag` corner badge ("Tier 3 · Commission") rendered atop the figure. This is **build-review-only** signal — it marks each slot as POV-non-compliant for the next builder's eye. Remove when commissioned replacement lands.

Tier 2 slots remain unflagged in the current draft because:
- They are POV-compliant in shape (stylized, not documentary)
- They still require **regeneration on an approved platform** (Adobe Firefly Pro, Google Vertex AI / Imagen 4, or OpenAI Enterprise — current Gemini consumer-tier outputs don't qualify) before they can go live as Tier 2
- Once regenerated + Larine-signed, they get the production `.fpo__ai-disclosure` badge per spec below

## Production AI disclosure component spec (`.fpo__ai-disclosure`)

For Tier 2 imagery that survives Larine sign-off — visible disclosure per POV §"The Five Non-Negotiables" requirement 3.

### Visual

- Small corner chip in bottom-right of the image
- Navy ground (rgba(3,29,45,0.78)) + gold text (#FFD364) — brand-aligned, distinct from defect/warning patterns
- Backdrop blur softens against busy image content
- ~12px font (text-xs), Montserrat, 600 weight

### Markup

```html
<figure class="fpo fpo--filled">
  <img src="..." alt="<describes the image content>" />
  <span class="fpo__ai-disclosure" 
        aria-label="Illustration · AI-assisted on Vertex AI · brand direction: Aaron Sleeper">
    Illustration · AI-assisted
  </span>
</figure>
```

### Content guidance

- **Visible chip text** (short form, ≤4 words): `Illustration · AI-assisted`
- **Aria-label** (full attribution): `Illustration · AI-assisted on <platform> · brand direction: <human name>`
- Per the POV's "Roles and accountability" section, the human-direction attribution lives in the aria-label, not the visible text, to avoid layout intrusion. Aria-label content is canonical for screen readers and machine readers (e.g., search-index disclosure crawlers per SB 942 latent provenance).

### Squarespace portability

- The chip is CSS + a single `<span>` — works inside Squarespace Code Block or HTML-embed blocks
- Squarespace's native Image Block does NOT support nested elements; Tier 2 imagery must ship via Code Block / paste-mode HTML
- Track in the Squarespace build spec ([SQUARESPACE-BUILD-SPEC.md](SQUARESPACE-BUILD-SPEC.md)) as a follow-up

### Non-component obligations (POV's other Tier 2 requirements)

The visible chip is the visible-disclosure piece. The other Tier 2 non-negotiables happen outside the component:
- **C2PA / SynthID provenance metadata:** preserved in image file at generation time on approved platforms (do not strip)
- **Named CAA executive sign-off:** documented per image batch (Larine + CC creative director per POV §"Roles and accountability")
- **Generation logs:** retained per POV §"Output security" (prompts, model version, timestamp, approver)

## POV-non-compliance build flag (`.fpo__pov-flag`) — operator notes

For builders/reviewers reading the prototype:

- The red "Tier 3 · Commission" badge marks any slot the POV classifies as RED
- It is **not a final asset state** — it signals "this needs commissioned-human replacement before launch"
- Remove the `<span class="fpo__pov-flag">` when the slot ships with commissioned imagery
- The badge has `z-index: 2` so it sits above the Unity Spark framing overlay; bright red `#B22222` is intentionally outside the CAA palette to avoid being mistaken for brand chrome

## Open questions tracked separately

- **Account access for Tier 2 regen** — Vertex AI / Imagen 4 access lives with Change Craft per Brandon's POV adoption; Aaron's outstanding ask in the 2026-06-24 Slack reply
- **Commissioning brief for Tier 3 slots** — separate workstream; not in this doc's scope
- **POV citation verification** — one citation error found by factuality reviewer (FTC Endorsement Guides Part 255 / Sept 2024 — should be Part 465 / Oct 21, 2024 OR Part 255 / July 26, 2023); Aaron drafting heads-up to Brandon

## Owner

Aaron Sleeper · CAA SB 54 campaign section build
Last updated: 2026-06-24
