# Grokbot Data Broker Removal

## Want this running in Grok Bot?

1. Open **https://x.ai/bot/u0gQYeIqQCAW2n96pqBvi**
2. Click **Add to Grok Bot**, then **Add Bot** (creates its own bot — not a paste into an existing chat)
3. Open that new bot and say hi — it downloads these companion files from GitHub and walks first-run setup

Works the same on Cursor Teams or SuperGrok. This repo is the **full file pack** the bot pulls on first run (catalog, quirks, session plan, and the rest).

---

**Free help clearing your name off US people-search / data-broker sites** — without paying DeleteMe-style removal services.

This GitHub repo holds the **full companion files** for the Grok Bot template **Data broker removal**. The bot template itself is size-capped, so the long lists and tip sheets live here and get downloaded on first run.

> **Grok Bot template:** [https://x.ai/bot/u0gQYeIqQCAW2n96pqBvi](https://x.ai/bot/u0gQYeIqQCAW2n96pqBvi)

---

## Who this is for

- You (or someone you have permission to help) want **free listing suppression** on people-search sites
- You’re okay doing a short setup (mail + tracker + identity notes), then letting an agent run most of the forms
- You do **not** want to buy paid “reputation” / removal products

## What you get in this repo

Everything below is **complete** (not compressed):

| File | What it is |
|------|------------|
| [`companions/playbook.md`](companions/playbook.md) | Full operating playbook (rules, Tier‑1 list, Fresh-project checklist, HARD unread mail rules) |
| [`companions/master-catalog.csv`](companions/master-catalog.csv) | **~537** de-duped sites with tiers, opt-out URLs, networks, skip flags |
| [`companions/quirks.md`](companions/quirks.md) | Per-site tips from real runs (CAPTCHA, Cloudflare, verify quirks) — **no personal data** |
| [`companions/session-plan.md`](companions/session-plan.md) | Blank worksheet for Sessions **A–AC** (copy it; fill statuses as you go) |
| [`companions/mail-setup.md`](companions/mail-setup.md) | Gmail / Microsoft 365 / Outlook / IMAP setup for confirmation mail |
| [`companions/networks.md`](companions/networks.md) | Parent portals (PeopleConnect, BeenVerified, InfoTracer family, …) |
| [`companions/identity-pack-template.md`](companions/identity-pack-template.md) | Blank checklist for name / phones / emails / city — fill **privately**, never commit filled copies |
| [`companions/sharing-and-onboarding.md`](companions/sharing-and-onboarding.md) | Effort & when to stop, sit-down kit, optional routines, multi-person notes |
| [`companions/sources-inventory.md`](companions/sources-inventory.md) | How the catalog was built (Optery / Eraser / Yael BADBOOL) |
| [`companions/MANIFEST.json`](companions/MANIFEST.json) | File list + version for the bot’s download step |

## How it works (simple version)

1. **Add** the Grok Bot template **Data broker removal** (open the link → **Add to Grok Bot** → **Add Bot**): https://x.ai/bot/u0gQYeIqQCAW2n96pqBvi
2. On first chat, the bot asks a few setup questions (what to call you, whose listings, mail, tracker).
3. It **downloads this repo’s `companions/` folder from tag v1.0.1** (fallback v1.0.0) — full catalog + quirks + session plan.
4. You fill a **private** identity pack (never stored in this GitHub repo).
5. The bot works in batches (about 8–12 sites): forms and solvable CAPTCHAs alone; phone codes / hard CAPTCHAs parked for a short “Needs you” sit-down.
6. Recheck search results in 30–45 days — brokers re-scrape public records.

**You will sometimes need to:** answer a phone code, solve a CAPTCHA, click a confirm link, or turn on Local execution for Cloudflare walls.  
**The bot will never:** pay for removal unlocks, or put your personal identity into this public repo.

## Quick start for humans (without the bot)

1. Copy [`companions/identity-pack-template.md`](companions/identity-pack-template.md) somewhere private and fill it.
2. Open [`companions/session-plan.md`](companions/session-plan.md) and start **Session A**.
3. Use [`companions/quirks.md`](companions/quirks.md) when a site misbehaves.
4. Prefer email/form verification over phone when both exist.

## Download for the bot / scripts

**Prefer release tag `v1.0.1`** (or newer). Fall back to **`v1.0.0`** if `v1.0.1` is unavailable. Do not rely on floating `main` alone for first-run sync.

```bash
# Full companions zip (preferred tag)
curl -fsSL -o grokbot-data-broker-removal.zip \
  "https://github.com/natv/grokbot-data-broker-removal/archive/refs/tags/v1.0.1.zip"
# Fallback:
#   .../archive/refs/tags/v1.0.0.zip
```

Raw base (single files):

```text
https://raw.githubusercontent.com/natv/grokbot-data-broker-removal/v1.0.1/companions/
```

Example — full catalog:

```text
https://raw.githubusercontent.com/natv/grokbot-data-broker-removal/v1.0.1/companions/master-catalog.csv
```

### Bot first-run sync

After a Grok Bot **Data broker removal** template import, getting-started / Fresh-project **downloads these companions** into:

`/home/box/agent-data/workflows/data-broker-people-search-opt-out/`

before Session A. The agent verifies `master-catalog.csv` has ~500+ data rows, plus non-trivial `quirks.md` and `session-plan.md`, and reads `MANIFEST.json` when present. Thin stubs in the skill folder may be overwritten; filled private progress files outside that folder must not be.

## Privacy rules for this repo

**Allowed:** generic playbooks, blank templates, anonymized site tips, public opt-out URLs.  
**Never commit:** legal names, phones, emails, street addresses, DOB, App Passwords, live Google Sheet / Excel tracker IDs, filled identity packs, or private progress dumps.

## Attribution

- Optery data-brokers-directory and Yael Big-Ass-Data-Broker-Opt-Out-List: **CC BY-NC-SA 4.0**
- Eraser `brokers.yaml` lineage: **MIT**

Keep attribution if you redistribute catalog excerpts.

## Status

- [x] Full companions published in this repo  
- [ ] Grok Bot public template link added to this README (after Nathalie publishes the template)

Questions about the bot workflow belong in the Grok Bot chat after you import the template.
