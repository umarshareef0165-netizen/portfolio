# Portfolio Site — Umar Shareef (One Who Codes 2026)

Single-page portfolio for **One Who Codes 2026 — A Portfolio Challenge**
(Acadable, via Unstop). Deadline: **Sun Nov 15, 2026, 10:29 AM PT**.

## What it is

- `index.html` — the whole site in one file: inline CSS + a tiny inline script.
  **Zero dependencies, zero external requests** (no web fonts, no images, no
  analytics). Inline SVG icons only. That makes it fast (1 request total) and
  impossible to break by a third-party outage.
- Showcases the 6 verified projects from `../PORTFOLIO.md` (AgriYield Advisor
  ⭐ featured, FrankenLedger, Receipt-to-Ledger, PayPerPrompt, Scholarship
  Hunter Agent, HireReady Agent), each with live demo link, public repo link,
  demo video, one-line description, tech stack, and evidence line.
- Headline, bio, skills, and contact links are copied verbatim from
  `../PORTFOLIO.md`. Nothing is invented: no user counts, revenue, or prizes.

## Local preview

```bash
cd ~/workspace/one-who-codes-2026/portfolio-site
python3 -m http.server 8137
# open http://localhost:8137/
```

## Deploy to Vercel (next step — NOT done by this build)

### Option A — Vercel CLI (fastest, no repo needed)

```bash
cd ~/workspace/one-who-codes-2026/portfolio-site
npm i -g vercel        # once, if the CLI is not installed
vercel                 # follow the prompts; accept the detected settings
vercel --prod          # production deploy — note the live URL it prints
```

No build command, no framework preset, no environment variables.
Output is the folder itself (`index.html` at the root).

### Option B — Vercel dashboard + GitHub

1. Create a new public GitHub repo (e.g. `umarshareef0165-netizen/portfolio`)
   and push the contents of this folder to it.
2. In the Vercel dashboard: **Add New → Project → Import** the repo.
3. Framework preset: **Other**. Build command: *(empty)*. Output directory:
   *(repo root)*. Deploy.
4. Note the live `*.vercel.app` URL.

### After deploy (required before the Unstop submit)

1. Open the live URL and confirm all 6 projects, bio, skills, and links render.
2. Claim the ONEWHO name **`umarshareef`** at https://isonewho.codes/
   (GitHub sign-in) and connect the deployed portfolio URL to it →
   `umarshareef.isonewho.codes`.
3. In the ONEWHO dashboard, add an application named **Unstop** → this creates
   `umarshareef.isonewho.codes/a/unstop`.
4. Submit on Unstop before **Sun Nov 15, 10:29 AM PT**: paste the
   `/a/unstop` link (NOT the bare address) + the featured repo
   `https://github.com/umarshareef0165-netizen/agriyield-advisor`.
   Needs Umar's final approval first. Leave the site unchanged until results
   are announced (Nov 18).

## Verification performed (Nov 12, 2026)

- HTML well-formedness checked with Python `html.parser` (tag balance, no
  unclosed elements).
- Every live link and repo link in the page checked with `curl` (HTTP 200
  required; Render free-tier apps allowed a long cold-start timeout).
- Page served locally and fetched: all 6 project names, the headline, the
  bio, all 12 skills, and the GitHub/LinkedIn/X links confirmed present.
- Grep checks: no `lorem` / `TODO` / `placeholder` / `FIXME` / `example.com`
  text; no external asset requests (only anchor links to the verified URLs).

See `BUILD-VERIFICATION.md` for the full check log (if present).
