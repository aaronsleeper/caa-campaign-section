# CAA SB 54 — Squarespace Native Build Spec

Per-page build instructions for the SB 54 interest-holder section on circularactionalliance.org. Pages are built using **Squarespace 7.1 native blocks** (no Code Block paste) so they inherit the live site's Site Styles, typography, and component patterns by default.

This document is the spec; the Astro prototype at `aaronsleeper.github.io/caa-campaign-section/` is the visual reference for what each page should communicate. Where our custom layouts wouldn't reproduce as native blocks, this spec degrades to Squarespace's native equivalents that match patterns already used on the live CAA site.

---

## Cover note — for Brandon + Larine

Hi Larine, thanks for getting the 5 blank pages up so quickly — and for the clear ask on building these natively. Agreed. The spec below switches us from the code-paste approach to a per-page native-block build that inherits your existing Site Styles and component patterns. It will read more "of the site" than our paste would have, which is what we both want.

A few things to confirm before you start building:

**The 8 pages we need.** You've created 5; we need 3 more for the Reimbursement sub-pages. Final list and URL slugs:

- SB 54 in California *(this becomes the section landing)* → URL slug: `sb54`
- What SB 54 Means for You → URL slug: `whats-changing`
- Roles and Responsibilities Under SB 54 → URL slug: `roles-and-responsibilities`
- Reimbursement for Covered Costs *(gateway)* → URL slug: `reimbursement`
- Local Programs *(sub-page of Reimbursement)* → URL slug: `local-programs`
- Collection Systems *(sub-page of Reimbursement)* → URL slug: `collection`
- Processing and End Markets *(sub-page of Reimbursement)* → URL slug: `processing`
- Questions → URL slug: `questions`

The intended full URL pattern is `/california/sb54/<slug>/` for the top-level pages and `/california/sb54/reimbursement/<slug>/` for the three Reimbursement sub-pages. If your template's nesting model needs us to flatten some of those, just let us know what's possible and we'll adjust — the structure matters more than the exact path.

**One nav-structure decision for you.** Two ways the section can appear in the main menu under California, both fine:

- **Option A (dropdown):** Move all 5 top-level pages into an SB 54 folder under California in your Pages panel. The folder name becomes the dropdown label, and the 5 pages show as menu items inside it. (The 3 Reimbursement sub-pages don't appear in the menu — visitors reach them from cards on the Reimbursement page.)
- **Option B (single entry):** Keep the pages where they are, set the SB 54 landing page as the only one that appears in the main nav, and let visitors navigate to the others from the landing page itself. Simpler structurally, leans more on in-page wayfinding.

Recommend Option A if your template supports folders cleanly; Option B if folder creation under California turns out to be fiddly.

**What's still pending and will land as we go.** Video URLs (Emily's recordings), FAQ confirmations (a few items still in review with Tony and Ashley), and a couple of CTA destinations (eligibility checklist downloads, working-group request forms). The spec marks these as `[PENDING: …]` so you can build the page structure now and we drop the final content in as it lands.

**How block instructions read.** Each page below has a list of sections from top to bottom. Each section names the Squarespace block(s) to use, what content goes in them, and any settings (background color, alignment) that matter. Where we want a specific live-site treatment (the gold-highlighted section heading, the gold-dot timeline, the teal stat band), I've called out the pattern by name from your existing site so you can reuse what's already there.

Holler if anything's unclear or doesn't translate cleanly to your template — happy to adjust block-by-block.

— Aaron

---

## Live-site patterns referenced in this spec

These are devices already in use on the live CAA site that several pages below reuse. Pulled from the public site audit; should already be available in your component vocabulary.

- **Gold-highlighted section heading** — H2 with a gold underline/marker treatment (used on every content page on the live site)
- **Teal "Key Goals" band** — full-width teal band with eyebrow text + 3-stat grid (used on the California page)
- **Gold-dot milestone timeline** — horizontal timeline with large gold dots, dates, and short labels (used on the California page)
- **Circular teal line-icon grid** — 3-column grid with thin circular teal icons + heading + short text (used on the About "Strategic Operating Principles")
- **Image-top card grid** — 3-column grid, image at top of each card, label + headline + text + CTA link (used on the Newsroom Blog and Home)
- **Two-column FAQ accordion** — label/subtext column + accordion column with thin rules and `+` affordance (used on the California FAQ)
- **Gold pill button** — full-radius gold-fill button with navy text, capitalized (used site-wide on the "Producer Registration" CTA — this is your `sqs-button-element--primary`)

When the spec says "use the live site's [pattern name]," that's what's being referenced.

---

## Page 1 — SB 54 in California *(section landing)*

**Page Title:** SB 54 in California
**Navigation Title:** Overview *(if Option A folder)* / SB 54 in California *(if Option B single entry)*
**URL Slug:** `sb54` *(or set as the folder's index page)*

This is the section's landing page. It introduces SB 54 at a glance, points visitors into the three modules, names the campaign's goals, and ends with the CAA inquiry-form CTA.

**Blocks, top to bottom:**

1. **Hero — Text block.** Heading: `SB 54 in California` (Squarespace's H1 styling). Below the heading, body paragraph: *"California is taking on one of its most ambitious recycling and packaging challenges yet. SB 54 is one of the most comprehensive and far-reaching packaging responsibility laws in the U.S., creating a producer-funded system to support recycling, composting, and waste management improvements across the state."*

2. **Video Block.** Centered, prominent. `[PENDING: video URL from Emily]`. Use a placeholder image until the video lands.

3. **Section heading — Text block.** H2: `Start with the topic that's most relevant to where you are right now`. Apply the live site's gold-highlighted heading treatment.

4. **Three module cards — Image-top card grid (live site's Newsroom/Home pattern).** Three cards, equal weight:
   - **Card 1.** Image: [PENDING — pick from the imagery library; circular-art or community-photo treatment]. Eyebrow/label: `Module 1`. Headline: `What SB 54 Means for You`. Body: *"Learn what is changing under SB 54, what stays the same, and what to expect as implementation moves forward."* Button: `Start here →` linking to `/california/sb54/whats-changing/`.
   - **Card 2.** Image: [PENDING]. Eyebrow: `Module 2`. Headline: `Roles and Responsibilities`. Body: *"Understand who does what under SB 54, how responsibilities are shared, and where your organization fits."* Button: `Find your role →` linking to `/california/sb54/roles-and-responsibilities/`.
   - **Card 3.** Image: [PENDING]. Eyebrow: `Module 3 (Coming Soon)`. Headline: `Reimbursement for Covered Costs`. Body: *"Learn how reimbursement works, what costs may be eligible, and how to prepare for future funding opportunities."* Button: `See reimbursement overview →` linking to `/california/sb54/reimbursement/`.

5. **Goals band — reuse the live site's teal "Key Goals" band.** Eyebrow text: `By January 1, 2032:`. Title above the stats: `Goals of SB 54`. Three stats (the checkmark + text pattern):
   - **25%** — reduction in single-use plastic packaging
   - **65%** — recycling rate
   - **100%** — of packaging recyclable or compostable

6. **Split image + text — Two-column section.** Left column: image (recycling-system operators on-site — coordinator, hauler, MRF worker). Right column: paragraph *"Whether you're already involved in this work or just beginning to learn about SB 54, this site is here to help you understand what is changing, where you fit, and how to access available support and funding."*

7. **CTA — Text block + Button block.** Body text: *"If you haven't connected with CAA yet, complete the CAA California Recycling & Reuse System Inquiry Form. Knowing a bit more about your organization helps CAA point you to the best next steps."* Then a gold pill button: `Complete the inquiry form →` linking to `https://www.surveymonkey.com/r/2M3GMYV` (opens in new tab). Below the button, smaller body text: *"You can also [sign up to receive CAA updates via our newsletter](https://circularactionalliance.org/newsletter-subscription)."*

---

## Page 2 — What SB 54 Means for You *(Module 1)*

**Page Title:** What SB 54 Means for You
**Navigation Title:** What's Changing
**URL Slug:** `whats-changing`

The first module. Establishes what SB 54 is, why it exists, what's changing and what isn't, and where the law sits in the larger statutory landscape.

**Blocks, top to bottom:**

1. **Hero — Text block.** H1: `What SB 54 Means for You`. Intro paragraph below: *"California has some of the most dedicated recycling programs in the country. Jurisdictions, haulers, and local operators have been doing this work for years. SB 54 is designed to support and strengthen those efforts through additional funding, coordination, and statewide alignment."*

2. **Video Block.** `[PENDING: video URL from Emily]`. Placeholder image until ready.

3. **Goals band — reuse the live site's teal "Key Goals" band** (same as on the landing page; this reinforces the targets in context). Eyebrow: `By January 1, 2032:`. Title: `Goals of SB 54`. Three stats: **25%** reduction in single-use plastic packaging, **65%** recycling rate for single-use plastic packaging, **100%** of packaging recyclable or compostable.

4. **Timeline — reuse the live site's gold-dot milestone timeline.** Section heading: `How SB 54 unfolds`. Four milestones:
   - **2022** — SB 54 is signed into law in California.
   - **2024–2025** — CalRecycle publishes and updates the Covered Material Categories (CMC) list.
   - **Late 2026 / Early 2027** — Pending CalRecycle approval of the program plan, implementation roll out begins.
   - **By 2032** — Statewide reduction, recycling, and recyclability targets come due.

5. **Section heading + intro — Text block.** H2: `Find out what SB 54 means for your work` (gold-highlighted treatment). Paragraph below: *"SB 54 brings changes to how the recycling system is funded and what is expected of it. The questions below cover what is changing, what stays the same, and how different organizations may be affected. Start here."*

6. **FAQ — Accordion block.** Nine items, in order:
   - **What is SB 54, in simple terms?** *SB 54 is the Plastic Pollution Prevention and Packaging Producer Responsibility Act. It creates a new, producer-funded system to manage packaging and food serviceware, along with improving recycling and composting efforts across California. Producers take on an active role in funding system improvements while local governments continue to operate existing programs.*
   - **What issue is SB 54 trying to address?** *California's recycling system faces real challenges. Operational and capacity gaps exist across the state, recycling outcomes vary by community, and local programs have historically carried most of the responsibility. SB 54 is designed to improve how packaging is managed, strengthen recycling performance, and create a more consistent and coordinated system statewide.*
   - **What is Extended Producer Responsibility, or EPR?** *EPR is a policy approach that shifts the cost of managing packaging from local governments and taxpayers to the companies that make and sell it. Under EPR, producers pay fees that fund collection, processing, education and outreach, infrastructure improvements, and end market development.*
   - **What is actually changing?** *Funding is shifting from primarily local sources to a producer-funded model. Responsibility is more clearly shared across producers, jurisdictions, and service providers. And statewide standards for recycling and reporting are being established for the first time.*
   - **What is NOT changing?** *Local programs stay local. Jurisdictions, haulers, and recyclers remain responsible for day-to-day operations. Existing laws like SB 1383 still apply. SB 54 supports and strengthens what is already in place.*
   - **What are Covered Material Categories, or CMCs?** *CMCs are the standardized classifications of packaging covered under SB 54. They define what must meet recyclability or compostability standards and what gets tracked and reported. CalRecycle defines and updates the CMC list annually.*
   - **How does SB 54 connect to existing laws?** *SB 54 builds on SB 1383, which focuses on organics and composting; SB 343, which defines recyclable materials; and AB 1201, which sets labeling requirements for compostable products. Together these laws address the full arc of how materials are designed, labeled, collected, and recovered.*
   - **When does implementation begin?** *Pending approval of the program plan by CalRecycle by December 27, 2026, CAA will begin implementation in January 2027.*
   - **Will this increase costs for local governments or ratepayers?** *No. CAA is responsible for covering all new and additional costs related to statewide SB 54 implementation.*

7. **CTA — Section with teal background, Text block + Button block.** H2: `What to do next`. Body: *"Tell us how you fit into SB 54. Your answers help CAA share relevant information, funding opportunities, and updates with organizations across California."* Gold pill button: `Share how you fit in →` linking to `https://www.surveymonkey.com/r/2M3GMYV` (new tab).

---

## Page 3 — Roles and Responsibilities Under SB 54 *(Module 2)*

**Page Title:** Roles and Responsibilities Under SB 54
**Navigation Title:** Roles and Responsibilities
**URL Slug:** `roles-and-responsibilities`

The second module. Names who's responsible for what — CAA, CalRecycle, producers, and local partners — and reassures readers that local decision-making stays local.

**Blocks, top to bottom:**

1. **Hero — Text block.** H1: `Roles and Responsibilities Under SB 54`. Intro: *"SB 54 builds on work that is already happening across California. The people and organizations involved today remain central to making the system work. What changes is how that work is connected, funded, and supported."*

2. **Video Block.** `[PENDING: video URL from Emily]`. Placeholder image until ready.

3. **Section heading + intro — Text block.** H2: `Find where you fit under SB 54` (gold-highlighted treatment). Paragraph: *"SB 54 involves many organizations with different responsibilities. The questions below explain how the system is structured, who does what, and how the pieces fit together."*

4. **FAQ — Accordion block.** Six items, in order:
   - **What is CAA responsible for?** *CAA implements and manages the statewide SB 54 program on behalf of producers. That includes managing producer registration and reporting, distributing funding to support local programs and system improvements, coordinating with jurisdictions and haulers, and providing guidance and technical assistance. CAA coordinates and supports the system. It does not replace local programs or regulate the industry.*
   - **What is the difference between CAA and CalRecycle?** *CalRecycle sets the rules, approves the program plan, and enforces compliance. CAA implements the program within that framework. For policy or regulatory questions, contact CalRecycle. For funding, implementation, or coordination questions, contact CAA.*
   - **What are producers responsible for?** *Producers register with CAA, report packaging data, fund system improvements, and redesign packaging to meet recyclability, compostability, and source reduction targets.*
   - **What is my organization responsible for?** *Local jurisdictions and service providers are responsible for including all materials on CalRecycle's CMC list in their collection and recycling programs. Depending on your role, that may involve running local outreach programs, managing collection routes, or sorting and processing covered materials. Funding is available to support new and additional work tied to those responsibilities.*
   - **Will SB 54 change who makes local decisions?** *No. Local partners continue making day-to-day program decisions. SB 54 creates statewide standards and coordination, but it does not replace local decision-making.*
   - **Who manages the Plastic Pollution Mitigation Fund?** *CAA collects PPMF fees from producers and remits them to the California Department of Tax and Fee Administration. CalEPA and other state entities oversee how those funds are allocated and used.*

5. **CTA — Section with teal background, Text block + Button block.** H2: `What to do next`. Body: *"Tell us how you fit into SB 54. Your answers help CAA share relevant information, funding opportunities, and updates with organizations across California."* Gold pill button: `Share how you fit in →` linking to `https://www.surveymonkey.com/r/2M3GMYV` (new tab).

---

## Page 4 — Reimbursement for Covered Costs *(Module 3 gateway)*

**Page Title:** Reimbursement for Covered Costs
**Navigation Title:** Reimbursement
**URL Slug:** `reimbursement`

The Module 3 gateway. Routes visitors to one of three audience-specific sub-pages (Local Programs, Collection Systems, Processing and End Markets) based on where they fit in the system. The full reimbursement program is still in development; the page acknowledges that and points to the inquiry form for now.

**Blocks, top to bottom:**

1. **Hero — Text block.** H1: `Reimbursement for Covered Costs`. Intro: *"SB 54 comes with real funding. CAA's reimbursement programs cover eligible new and additional costs from January 1, 2023 forward, using 2022 as the cost baseline — so the work you were already doing before SB 54 is not displaced, it's supported."*

2. **Image Block.** Brand image: covered-material categories arranged as a clean circular still life — valuable commodities. `[PENDING: image asset]`.

3. **Three audience-routing cards — Image-top card grid (live site's pattern), or three side-by-side button blocks if the card pattern is heavy.** Each card represents one path forward:
   - **Card 1.** Eyebrow: `For local recycling programs`. Headline: `Local Programs`. Body: *"Public education, outreach, contamination reduction, and program administration — what local jurisdictions and community-based organizations deliver."* Button: `See local programs →` linking to `/california/sb54/reimbursement/local-programs/`.
   - **Card 2.** Eyebrow: `For collection operators`. Headline: `Collection Systems`. Body: *"Expanded service, equipment upgrades, route improvements, and new drop-off locations — what jurisdictions and haulers deliver together."* Button: `See collection systems →` linking to `/california/sb54/reimbursement/collection/`.
   - **Card 3.** Eyebrow: `For processors and end-market operators`. Headline: `Processing and End Markets`. Body: *"Sorting upgrades, contamination reduction, capacity expansion, and end-market development — what MRFs, processors, and end-market operators deliver."* Button: `See processing and end markets →` linking to `/california/sb54/reimbursement/processing/`.

4. **Holding-state band — Section with teal background, Text block + Button block.** This is the "coming soon" treatment for the broader reimbursement program detail:
   - H2: `Reimbursement details are coming soon`
   - Paragraph: *"CAA is developing reimbursement programs to support eligible activities under SB 54. Information about eligibility, covered costs, and reimbursement opportunities for different parts of the system will be published here as it becomes available."*
   - Paragraph: *"In the meantime, tell us how you fit into SB 54 so CAA can share relevant updates with your organization."*
   - Gold pill button: `Share how you fit in →` linking to `https://www.surveymonkey.com/r/2M3GMYV` (new tab).

*Note: the gateway page intentionally does not include the per-audience CTA block at the bottom; the three sub-pages own those.*

---

## Page 5 — Local Programs *(Module 3a)*

**Page Title:** Local Programs
**Navigation Title:** *(not in main nav — reached from the Reimbursement gateway card)*
**URL Slug:** `local-programs`
**Intended full URL:** `/california/sb54/reimbursement/local-programs/`

The first reimbursement sub-page. For jurisdictions, Tribal governments, community-based organizations, and service providers running local recycling and outreach programs.

**Blocks, top to bottom:**

1. **Hero — Text block.** H1: `Local Programs`. Intro: *"If you run a local recycling program, coordinate community outreach, or help residents understand how to participate, a lot of what you do is now eligible for reimbursement under SB 54. This is a meaningful opportunity to expand what your program can do with funding behind it."*

2. **Video Block.** `[PENDING: video URL from Emily]`. Placeholder image until ready.

3. **Split image + text — Two-column section.** Left column: image (a local recycling outreach event — residents engaging with a program). Right column: H2 `Why this matters to you` (gold-highlighted) + paragraph *"SB 54 reimburses eligible new and additional costs for local program implementation along with education and outreach. That includes jurisdictions, Tribal governments, community-based organizations, and service providers delivering work tied directly to SB 54 requirements."*

4. **Callout — Quote block (or styled emphasis paragraph).** Text: *"Funding covers new and additional work only — the activities you take on to meet SB 54, beyond what your program was already doing."*

5. **Key messages — reuse the live site's circular teal line-icon grid pattern (3-column, repeated rows).** Section heading: `Key messages`. Six items:
   - Eligible activities include public education campaigns, contamination reduction efforts, community outreach and translation services, program administration, and support for reuse and refill programs at the local level.
   - Funding covers new and additional work only. If the activity exists to meet SB 54 requirements and goes beyond what your program was doing before 2023, it qualifies.
   - Multiple types of organizations can apply directly, including jurisdictions, Tribal governments, community-based organizations, and service providers. There is a pathway to funding if your organization is delivering eligible work.
   - Programs must support recovery of Covered Material Categories (CMCs). Outreach should help residents understand what covered materials are and how to handle them correctly.
   - Applications go through CAA's online portal and require a plan for activities, outcomes, and measurement. Reporting on actual results is required after funding is received.
   - Equity is a required consideration. Programs must improve access, engage underserved communities, and avoid placing additional burdens on areas already impacted by environmental harm.

   *(If the icon-grid pattern needs an icon per row, pick a thin circular teal line icon per item — outreach, funding/dollar, hands, recycle, document, balance. If exact icons aren't on hand, use the same generic Unity Spark variant across all six and we'll iterate later.)*

6. **Section heading + FAQ — Accordion block.** H2: `Questions` (gold-highlighted). Four items:
   - **What does new or additional mean?** *It means work that goes beyond what your program was already doing before 2023. If it exists to meet SB 54 requirements, it qualifies. If it was already in place, it does not.*
   - **Can community-based organizations apply directly?** *Yes. CBOs, environmental justice partners, and others implementing eligible work can apply directly or partner with jurisdictions to access funding together.*
   - **How are funded programs evaluated?** *Programs should outline expected outcomes like increased recycling, reduced contamination, and improved community understanding, along with a plan to measure progress. Reporting on actual results after funding is received is required.*
   - **How does equity factor in?** *Equity is built into the program, not added on. Programs must improve access, engage underserved communities, and avoid placing additional burdens on areas already impacted by environmental harm.*

7. **CTA — Section with teal background, three side-by-side card-like content blocks.** H2: `What to do next`. Three audience-tagged paths:
   - **For staffed jurisdictions.** *Start a funding conversation with CAA* — `[PENDING: calendar link or intake form URL]`.
   - **For all audiences.** *Download the eligibility checklist* — `[PENDING: checklist PDF link]`.
   - **Stay ready.** *Request a working group invitation* — `[PENDING: working-group request form URL]`. Tribal government office hours, small-jurisdiction working group, or regional agency roundtable.

---

## Page 6 — Collection Systems *(Module 3b)*

**Page Title:** Collection Systems
**Navigation Title:** *(not in main nav — reached from the Reimbursement gateway card)*
**URL Slug:** `collection`
**Intended full URL:** `/california/sb54/reimbursement/collection/`

The second reimbursement sub-page. For jurisdictions designing collection systems and haulers operating them.

**Blocks, top to bottom:**

1. **Hero — Text block.** H1: `Collection Systems`. Intro: *"Improving how covered materials get collected is one of the most direct ways to hit SB 54's recovery targets. If you oversee collection systems, manage routes, or coordinate service delivery, funding is available to support the improvements it takes to get there."*

2. **Video Block.** `[PENDING: video URL from Emily]`. Placeholder image until ready.

3. **Split image + text — Two-column section (image on left this time, alternating with sibling sub-pages).** Left column: image (organized recycling collection route — carts and collection truck). Right column: H2 `Why this matters to you` (gold-highlighted) + paragraph *"Collection system improvements are a core funding category under SB 54. Whether you design the system or operate it on the ground, there are reimbursement opportunities tied to the incremental work of expanding and improving collection of covered materials."*

4. **Callout — Quote block (or styled emphasis paragraph).** Text: *"Only the incremental costs tied to SB 54 qualify — existing services and baseline operations are not reimbursable."*

5. **Key messages — reuse the live site's circular teal line-icon grid pattern (3-column).** Section heading: `Key messages`. Six items:
   - Eligible improvements include expanded service to multifamily and underserved areas, new or upgraded carts, bins, and vehicles, route adjustments to improve CMC capture, and new drop-off or depot locations.
   - Improvements must be tied to covered material categories, or CMCs. The goal is better capture rates, less contamination at the point of collection, and cleaner material reaching processing facilities.
   - Only incremental costs tied to SB 54 qualify. Existing services and baseline operations are not reimbursable.
   - Collection improvements require coordination between those who design the system and those who operate it. Funding must align with existing service agreements and contracts, so early coordination is essential.
   - Reimbursement is tied to documented outcomes including increased tons collected, expanded service coverage, and improved capture rates.
   - Rural areas and communities with access gaps are explicitly addressed. Additional transportation costs and service expansion in hard-to-reach areas are eligible.

6. **Section heading + FAQ — Accordion block.** H2: `Questions` (gold-highlighted). Four items:
   - **What types of collection improvements are eligible?** *Service expansion to multifamily buildings, public spaces, and underserved areas; equipment including carts, bins, and vehicles; route and service changes tied to CMCs; and new drop-off locations or depots.*
   - **Who leads, the hauler or the jurisdiction?** *Both. Those who design and oversee the system set service requirements. Those who operate it implement the changes. Funding must align with existing franchise agreements, so early coordination between these roles is important.*
   - **How is reimbursement evaluated and paid?** *Based on documented outcomes. Tons collected, service coverage expansion, and capture rate improvements all factor in. Cost models and actual data are both used to evaluate what is reasonable.*
   - **What about reuse and refill collection?** *Operators managing the collection and return of covered materials through reuse and refill models are part of the collection system under SB 54 and are eligible for the same funding considerations.*

7. **CTA — Section with teal background, three side-by-side card-like content blocks.** H2: `What to do next`:
   - **For jurisdictions and local program operators.** *Share your collection improvement concepts with CAA* — structured form for early planning and budgeting. This is a planning conversation, not an application. `[PENDING: form URL]`.
   - **For haulers walking into franchise conversations.** *Download the jurisdiction-hauler coordination brief* — `[PENDING: brief PDF link]`.
   - **Stay ready.** *Request a working group invitation* — `[PENDING: working-group form URL]`. Small-jurisdiction working group, regional agency roundtable.

---

## Page 7 — Processing and End Markets *(Module 3c)*

**Page Title:** Processing and End Markets
**Navigation Title:** *(not in main nav — reached from the Reimbursement gateway card)*
**URL Slug:** `processing`
**Intended full URL:** `/california/sb54/reimbursement/processing/`

The third reimbursement sub-page. For MRFs, processors, composting facilities, transfer stations, and end-market operators.

**Blocks, top to bottom:**

1. **Hero — Text block.** H1: `Processing and End Markets`. Intro: *"Better sorting. Cleaner materials. Stronger end markets. Processing is where covered materials are either recovered or lost. SB 54 invests in making the system deliver all the way through, and that investment flows directly to the facilities and operators doing that work."*

2. **Video Block.** `[PENDING: video URL from Emily]`. Placeholder image until ready.

3. **Split image + text — Two-column section (image on right this time).** Left column: H2 `Why this matters to you` (gold-highlighted) + paragraph *"If you operate a processing facility, manage material recovery, or develop end markets for recyclables, there are reimbursement opportunities tied to the improvements that strengthen system performance and increase recovery of covered material categories."* Right column: image (dynamic looping forms suggesting material flowing through to viable end markets).

4. **Key messages — reuse the live site's circular teal line-icon grid pattern (3-column, repeated rows).** Section heading: `Key messages`. Seven items:
   - Eligible investments must be tied to CMCs. Sorting upgrades, contamination reduction systems, capacity expansion, and end market development all qualify when they demonstrably improve recovery and material quality.
   - New and additional investments only. Existing operations and baseline costs are not reimbursable.
   - Reimbursement is typically structured per ton of covered materials processed or improved. Projects must show higher recovery, better material quality, or stronger end market alignment.
   - If your facility handles both covered and non-covered materials, only the portion tied to covered materials is eligible. CAA uses actual data and cost benchmarks to evaluate proportionate costs.
   - Processing does not have to happen in California to qualify, provided outcomes align with SB 54 performance and reporting requirements.
   - Incentive funding is available for innovation. Hard-to-recycle materials, contamination reduction breakthroughs, and end market development in low-demand areas are all areas where additional support may be available.
   - Environmental justice considerations apply. Facilities must assess and work to mitigate community impacts and demonstrate meaningful engagement.

5. **Image Block.** Second brand image: baled clean commodities arranged in concentric circles — valuable material, not waste. `[PENDING: image asset]`.

6. **Section heading + FAQ — Accordion block.** H2: `Questions` (gold-highlighted). Three items:
   - **What types of processing investments are eligible?** *Sorting and processing equipment, contamination reduction systems, capacity expansion, efficiency improvements, and end market development, all when tied to covered material categories. Only technologies that meet SB 54's definition of recycling are eligible. Disposal-based or energy-generation technologies are excluded.*
   - **Can out-of-state facilities participate?** *Yes. Facilities processing California covered materials can participate regardless of location, provided investments and outcomes align with SB 54 requirements for recovery, quality, and reporting.*
   - **How are end markets supported?** *Developing end markets for covered materials is one of CAA's highest priorities. CAA does not expect anyone to collect or process materials without a viable end market, and is committed to providing updated information on new end markets as they become available. Funding can also support end market development and innovation directly.*

7. **CTA — Section with teal background, three side-by-side card-like content blocks.** H2: `What to do next`:
   - **For MRFs, processors, composting, transfer stations.** *Start a facility investment conversation with CAA* — `[PENDING: form/calendar URL]`.
   - **For facilities handling mixed material streams.** *Download the CMC eligibility worksheet* — `[PENDING: worksheet PDF link]`.
   - **Stay ready.** *Request a working group invitation* — `[PENDING: working-group form URL]`. Regional agency roundtable, processor working group.

---

## Page 8 — Questions *(consolidated FAQ index)*

**Page Title:** Questions
**Navigation Title:** Questions
**URL Slug:** `questions`

The section's consolidated question index. Surfaces all questions from across the modules, grouped by module so visitors who don't know which module they need can scan the whole catalog. Use the live site's two-column FAQ layout (label-and-subtext column on the left, accordion on the right).

**Blocks, top to bottom:**

1. **Hero — Text block.** H1: `Questions`. Intro: *"All the questions covered across the SB 54 section, in one place. Use the section headings to jump to the topic you're looking for, or open each question to see the answer."*

2. **Module 1 group — reuse the live site's two-column FAQ accordion pattern.** Left column label: `What SB 54 Means for You`. Subtext: *"The law in simple terms — what is changing, what is not, and how SB 54 fits with existing law."* Right column: accordion with all nine Module 1 FAQ items (copy from Page 2 above).

3. **Module 2 group — same pattern.** Left column label: `Roles and Responsibilities`. Subtext: *"Who is responsible for what — CAA, CalRecycle, producers, and local partners."* Right column: accordion with all six Module 2 FAQ items (copy from Page 3 above).

4. **Module 3a group — same pattern.** Left column label: `Local Programs`. Subtext: *"Funding for local recycling programs, outreach, and community-based work."* Right column: accordion with all four Module 3a FAQ items (copy from Page 5 above).

5. **Module 3b group — same pattern.** Left column label: `Collection Systems`. Subtext: *"Funding for service expansion, equipment, route improvements, and drop-off locations."* Right column: accordion with all four Module 3b FAQ items (copy from Page 6 above).

6. **Module 3c group — same pattern.** Left column label: `Processing and End Markets`. Subtext: *"Funding for sorting, contamination reduction, capacity expansion, and end-market development."* Right column: accordion with all three Module 3c FAQ items (copy from Page 7 above).

7. **CTA — Section with teal background, Text block + Button block.** H2: `Don't see your question?`. Body: *"Tell us how you fit into SB 54 and we'll share relevant updates and answer questions specific to your organization."* Gold pill button: `Share how you fit in →` linking to `https://www.surveymonkey.com/r/2M3GMYV` (new tab).

---

## Open items — to land as we go

These will arrive over the coming days and weeks. The page structures are built to accept them without rebuilds.

- **Video URLs** — Emily is recording one explainer per module (4 total: Module 1, Module 2, Module 3 gateway, plus the overview video being positioned as Option 2 / unlinked landing per the recent thread). Drop into the marked `[PENDING: video URL]` slots as they land.
- **FAQ confirmations** — most FAQ content here is from the May 18 Copy Deck. A small number of items may shift after Tony's video script pass and Ashley's per-module FAQ review.
- **CTA destinations** — eligibility checklist PDFs, working-group request form URLs, intake/calendar links for funding conversations. Several of these are CAA-side asset decisions; we'll fill the destinations as CAA confirms them.
- **Imagery** — circular-art and community-photography selections per module. Will provide image briefs and final selections; the FPO placeholders in the prototype name the intended treatment.
- **Time-sensitive claims (`[VERIFY]`)** — dates, statutes, and dollar figures cited above were sourced from the Copy Deck; if CAA's primary-source verification surfaces an updated value, we update the spec and the live pages together.
