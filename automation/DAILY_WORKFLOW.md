# Ecom Star Daily Workflow

## Purpose

Produce one original, category-independent Amazon affiliate video every day for the first product visibly carrying a #1 rank in page order on Amazon’s Any Department Best Sellers page at the midnight check. Use verifiable facts, permitted media, clear commercial disclosure, and product-specific safety language.

## Schedule

- Start: 12:00 AM midnight
- Time zone: America/Los_Angeles
- Cadence: daily
- Affiliate tracking ID: `buildsmartpic-20`
- Source list: Amazon Best Sellers, Any Department; select the first visible category #1 in page order as the cross-category proxy
- Source URL: `https://www.amazon.com/gp/bestsellers/`
- Destination channel: Build Smart Tools & Materials (`@BuildSmartPicks`) unless the user later designates another channel
- Publish state: Public only after all gates pass

## Meaning of “number one by sales volume”

Amazon describes Best Sellers as popular products based on sales and updates the page frequently. However, the Any Department page shows separate category lists and does not publish one cross-department overall #1. Ecom Star therefore uses the **first visible product carrying a #1 rank in page order** as a transparent, repeatable cross-category proxy.

Record:

- Timestamp and America/Los_Angeles time zone
- Page heading proving the view is Any Department
- The first category heading shown, its position in page order, and the visible #1 rank
- Product title, ASIN, price as observed, and detail URL
- Rating, review count, and any visible “bought in past month” bucket, quoted exactly
- Screenshot or captured page evidence

Never infer or invent a precise unit-sales number. Never call the selected item Amazon’s true overall sales champion. Describe it accurately as the first #1 bestseller shown on Amazon’s Any Department page and name its actual category and check time.

## Exactly one product

Select only the first visible #1-ranked product in page order on the Any Department page. Do not replace it with #2 or a different category’s #1. If #1 fails any eligibility gate, log a blocked run for that day and do not publish a substitute product. The same product may be featured on consecutive days if it remains #1, but the script, hook, and creative treatment should not misrepresent newness.

## Eligibility gates

The #1 product must:

- Have a stable product identity or ASIN and a valid affiliate destination
- Be available when checked
- Be legally and platform-appropriate to promote
- Have no known active recall or serious credible counterfeit/safety warning found in a current check
- Not require prohibited medical, financial, legal, age-restricted, or regulated claims
- Have enough verifiable facts for an accurate original video
- Have sufficient media with a verified usage basis

If any gate fails, do not bypass it. Record the reason and notify the user.

## Media rights

Use as many distinct visuals as improve the video, but every asset must have a documented usage basis. Preferred sources:

1. Amazon Product Advertising API or SiteStripe Product Advertising Content when the account and registered Site use permit it
2. Manufacturer press kits, affiliate assets, or product media carrying explicit reuse permission
3. Commercially licensed or Creative Commons media whose terms allow the intended use
4. Original photos, footage, diagrams, backgrounds, icons, animation, and typography created for Ecom Star

Do not copy an Amazon advertisement, listing layout, video, or description wholesale. Do not use customer review photos, videos, or text. Do not remove watermarks or imply manufacturer endorsement. Product titles and short factual specifications may be quoted as needed for identification, but marketing narration and captions must be original.

## Fact gathering

Verify important facts from the live Amazon listing and preferably the manufacturer or authoritative source. Record source URLs. Clearly separate specifications from opinions. Avoid unsupported claims about:

- Performance, durability, quality, or results
- Health, medical, environmental, or safety benefits
- Certifications, compatibility, or regulatory compliance
- Price duration, inventory, discounts, or future availability
- “Best,” “guaranteed,” or universal suitability

Use category-specific cautions. Examples include PPE and manufacturer instructions for tools, allergy and ingredient cautions for consumables, compatibility checks for electronics, age guidance for children’s products, and professional advice for regulated or high-risk products.

## Customized video strategy

The video must be tailored to the product rather than forced into a construction template.

### Recommended 20–45 second structure

- **0–2 seconds:** high-clarity hook naming the actual category and #1 rank at the recorded check time
- **2–6 seconds:** product name, category context, and strongest permitted hero visual
- **6–16 seconds:** the practical need, problem, or desire the product addresses
- **16–28 seconds:** 2–4 verified features demonstrated with varied permitted visuals or original diagrams
- **28–36 seconds:** likely buyer fit, compatibility, limitations, and relevant safety note
- **36–45 seconds:** concise call to action, affiliate relationship, and current-price caveat

Customize tone and creative direction by market:

- Everyday consumable: fast, practical, replenishment-oriented
- Electronics: clean, feature-led, compatibility-focused
- Beauty or personal care: restrained, non-medical, ingredient-aware
- Home product: problem/solution and space/use visualization
- Toy or family product: age guidance and safe-use context
- Tool or equipment: demonstration logic, PPE, and manufacturer instructions

## Technical video specification

- Format: vertical 9:16
- Resolution: 1080 × 1920
- Target duration: 20–45 seconds
- Narration: original and fact-checked
- Captions: burned in and proofread
- Visuals: varied permitted product assets plus original motion, backgrounds, layouts, callouts, and diagrams
- Audio: original or properly licensed only
- Final frame: product name, affiliate call to action, and disclosure cue

## Required disclosure

Include this exact sentence in the description above or adjacent to the affiliate link:

> As an Amazon Associate I earn from qualifying purchases.

The commercial relationship must also be clear in the video or opening description. Use YouTube’s paid-promotion declaration.

## YouTube upload checklist

Before publishing, verify:

- Signed-in channel is **Build Smart Tools & Materials** (`@BuildSmartPicks`) unless a new channel has been explicitly designated
- Title and description identify the correct product and ASIN
- Any #1 claim names the actual category and includes the observed check date or time context
- Affiliate link uses `buildsmartpic-20`
- Required Amazon Associates disclosure is present
- Paid promotion is marked
- AI/synthetic-content setting is answered truthfully
- Audience is **No, it is not made for kids** unless a platform rule requires different handling; do not target children
- Visibility is **Public**
- Copyright checks show no blocking issue
- Product-specific safety, compatibility, or usage caveat is present when relevant

If the active channel is wrong, media rights are unclear, facts conflict, upload limits apply, or checks show an issue, do not publish. Preserve a private draft when possible and report the smallest next step.

## Daily log

Record:

- Date and start/finish time
- Selected first-displayed category #1 product, actual category, ASIN, page-order evidence, and source URL
- Eligibility and recall/safety check result
- Affiliate URL
- Media sources and usage basis
- Factual sources
- Script, description, and creative strategy
- Rendered file path
- YouTube video ID and public URL
- Visibility and setting confirmations
- Errors, blocks, or unresolved checks

Never commit OAuth credentials, API secrets, browser cookies, or YouTube tokens to this repository.

## REA + Six Sigma execution layer

Use [REA_SIX_SIGMA.md](REA_SIX_SIGMA.md) for every run. The benchmark analysis at [../research/BENCHMARK_REA.md](../research/BENCHMARK_REA.md) provides general communication hypotheses only; never copy its creative expression.

### Define

Create a run charter containing the selected product, actual category and ranking context, ASIN, target viewer, buyer decision, authorized sources, media boundaries, required caveats, single call to action, and stop conditions.

### Measure

Before scripting, count objective claims, supported claims, assets, approved assets, unresolved contradictions, selected Voice of Customer questions, and answered questions. After production, record duration, distinct visuals, caption checks, rework cycles, and production time.

Calculate and log:

- Evidence coverage = supported objective claims / objective claims
- Media-rights coverage = approved assets / assets used
- Voice of Customer coverage = answered priority questions / selected priority questions
- First-pass result = passed without correction or required rework

Unavailable measurements must be marked unavailable, never estimated.

### Analyze

For every contradiction, blocked gate, or rework event, record the cause. Apply Five Whys to critical or repeated defects. Use a weekly Pareto review to identify the small number of defect categories producing most delays or corrections. Treat benchmark success as a hypothesis source, not proof of causation.

### Improve

Use an original treatment that applies the principles of a clear promise, observable proof, useful sequence, compliance, integrity, and one next action. Change one major creative variable at a time when practical. Put limitations, safety, and disclosure before the final call to action.

### Control

Require all gates in REA_SIX_SIGMA.md. Critical defects have zero tolerance. Evidence coverage, media-rights coverage, required disclosure, product-to-ASIN matching, and post-publication verification must each be 100%. Reopen the public video and verify playback, metadata, disclosure, affiliate URL, product match, and visibility.

## Independent challenge

Before upload, a verifier other than the creative-design role must attempt to disprove every material claim, detect product/ASIN mismatch, identify missing buyer limitations, confirm asset permissions, and check whether the creative is too similar to a benchmark. The run is blocked until material findings are resolved.

## Voice of Customer loop

Use public questions and comments only as evidence of buyer information needs. Do not treat them as factual product evidence. Classify questions into buyer fit, compatibility, limitations, safety, price/availability, included items, and alternatives. Select the highest-priority unanswered questions for the next improvement cycle.
