# Ecom Star: Amazon Overall #1 Affiliate Video System

Ecom Star duplicates the complete Build Star project and adds a category-independent, single-product affiliate-video workflow. Every midnight it checks Amazon’s overall Best Sellers list, selects only the visible #1 product, creates an original vertical marketing video, and publishes it after rights, factual, safety, and platform checks pass. Amazon’s public ordering is sales-based evidence, but it is not a disclosure of exact unit sales.

Repository: https://github.com/henrynkoh/ecom_star

[![Open Ecom Star Landing Page](https://img.shields.io/badge/OPEN-LANDING_PAGE-238636?style=for-the-badge&logo=githubpages&logoColor=white)](https://henrynkoh.github.io/ecom_star/)

## Daily Ecom Star Routine

At 12:00 AM America/Los_Angeles every day:

1. Inspect Amazon’s overall Best Sellers page and record the visible #1 product, rank, ASIN, timestamp, and source URL.
2. Select **only #1 overall**, regardless of industry or category. Do not substitute #2. If #1 is ineligible, unsafe, unavailable, recalled, or lacks verifiably permitted media, stop that day and report the reason.
3. Use the affiliate tracking tag `buildsmartpic-20`. Never claim exact sales volume unless Amazon explicitly displays it.
4. Use as many useful product visuals as the video needs, but only when affiliate, manufacturer, or other reuse permission is verified. Do not copy an Amazon listing or advertisement wholesale, and do not use customer review media.
5. Write original narration, captions, hooks, and calls to action from verified product facts.
6. Create one 20–45 second, 1080 × 1920 vertical video customized to that single product.
7. Include the exact disclosure: `As an Amazon Associate I earn from qualifying purchases.`
8. Mark paid promotion, answer the AI/synthetic-content setting truthfully, and mark the video not made for kids.
9. Upload Public as soon as copyright, factual, safety, and platform checks pass.
10. Log the evidence, affiliate URL, media-rights basis, output files, public video URL, and outcome.

## Single-Product Video Strategy

Use a product-specific structure rather than the construction workflow format:

- **0–2 seconds:** pattern-interrupt hook identifying it as Amazon’s #1 overall seller at the recorded check time
- **2–6 seconds:** clear product identity and strongest permitted hero visual
- **6–16 seconds:** the buyer problem or use case, without unsupported claims
- **16–28 seconds:** 2–4 verified features shown with varied permitted images, close-ups, diagrams, or original graphics
- **28–36 seconds:** who it is for, limitations, compatibility, and a safety note when relevant
- **36–45 seconds:** concise affiliate call to action and visible disclosure

Adapt pacing, tone, colors, typography, proof points, and safety language to the selected product’s market. Avoid repetitive templates that obscure what the product actually is.

See [automation/DAILY_WORKFLOW.md](automation/DAILY_WORKFLOW.md) for the operating specification.

## Highlights

- 15 construction workflow pages, from site preparation through final punch list
- 69 material lines with quantity, price, labor-hour, and supplier fields
- 180 Amazon product picks organized by construction step
- Affiliate campaign page and CSV export
- 60-video browser-based Shorts Studio
- Optional Python rendering and YouTube upload pipeline
- Plain HTML, CSS, and JavaScript with no framework or build step

## Quick Start

```bash
git clone https://github.com/henrynkoh/ecom_star.git
cd ecom_star
python3 -m http.server 8000
```

Open http://localhost:8000.

Read next:

- [5-minute Quick Start](docs/QUICKSTART.md)
- [Step-by-step Tutorial](docs/TUTORIAL.md)
- [Complete Manual](docs/MANUAL.md)
- [Marketing Kit](marketing/README.md)

## Project Structure

```text
ecom_star/
├── index.html
├── step-01.html ... step-15.html
├── affiliate.html
├── shorts.html
├── data.js
├── app.js
├── styles.css
├── shorts-data.js
├── pipeline/
│   ├── run_pipeline.py
│   └── shorts.json
├── docs/
│   ├── QUICKSTART.md
│   ├── TUTORIAL.md
│   └── MANUAL.md
└── marketing/
    ├── README.md
    ├── facebook.md
    ├── instagram.md
    ├── threads.md
    ├── blogger.md
    ├── naver-blog.md
    ├── tistory.md
    ├── wordpress.md
    ├── newsletter.md
    └── email.md
```

## Main Pages

| Page | Purpose |
|---|---|
| `index.html` | Main hub, workflow, materials, tools, costs, and labor |
| `step-01.html` to `step-15.html` | Detailed page for each construction step |
| `affiliate.html` | Amazon affiliate campaign and CSV export |
| `shorts.html` | Preview and browser rendering interface for 60 Shorts |

The website depends on `data.js`, `app.js`, `styles.css`, and `shorts-data.js`.

## Customize the Amazon Associates Tag

The current tag is `buildsmartpic-20`. Replace it in:

- `data.js`
- `shorts-data.js`
- `pipeline/shorts.json`

Check for remaining occurrences:

```bash
grep -rn "buildsmartpic-20" .
```

You can also override the tag for a pipeline run with `--tag`.

## YouTube Shorts Pipeline

The pipeline uses the macOS `say` command for narration.

### Requirements

- macOS
- Python 3
- ffmpeg
- Pillow
- requests
- google-api-python-client
- google-auth-oauthlib

```bash
brew install ffmpeg
python3 -m venv pipeline/.venv
source pipeline/.venv/bin/activate
pip install Pillow requests google-api-python-client google-auth-oauthlib
```

Render one test Short:

```bash
python3 pipeline/run_pipeline.py \
  --tag buildsmartpic-20 \
  --render \
  --only s01-m-1
```

For YouTube uploads, place the OAuth Desktop App file at `pipeline/client_secret.json`. The script stores authorization at `pipeline/token.json`. Never commit either file.

```bash
python3 pipeline/run_pipeline.py \
  --tag buildsmartpic-20 \
  --upload \
  --per-day 6 \
  --privacy private
```

Uploaded videos default to private. Review each video in YouTube Studio before publishing.

## Disclosures and Safety

- Clearly disclose Amazon affiliate links. Suggested wording: "As an Amazon Associate I earn from qualifying purchases."
- Product prices, ratings, availability, and rankings can change. Verify before publishing or purchasing.
- Construction quantities and labor figures are planning estimates, not bids or engineering documents.
- Follow local building codes, permit requirements, manufacturer instructions, and job-site safety practices.
- Consult licensed professionals when required.

## Credential Safety

Never commit credentials or authorization tokens. Recommended `.gitignore` entries:

```gitignore
pipeline/client_secret.json
pipeline/token.json
pipeline/state.json
pipeline/out/
*.pickle
```

If a credential is exposed, revoke it immediately, generate a replacement, and remove the exposed value from Git history.

## License

No license has been specified. Add a `LICENSE` file before allowing reuse or redistribution.
