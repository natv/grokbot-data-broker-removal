# Grokbot Data Broker Removal

**Free help clearing your name off US people-search / data-broker sites** — without paying DeleteMe-style removal services.

This GitHub repo holds the **full companion files** for the Grok Bot template **Data broker removal**. The bot template itself is size-capped, so the long lists and tip sheets live here and get downloaded on first run.

> **Grok Bot template link:** _coming soon — added here right after the public template is published._

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

1. **Install** the Grok Bot template **Data broker removal** (link above, once published).
2. On first chat, the bot asks a few setup questions (what to call you, whose listings, mail, tracker).
3. It **downloads this repo’s `companions/` folder** (full catalog + quirks + session plan).
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

Prefer a **release tag** when one exists (example `v1.0.0`):

```bash
# Full repo zip (main branch)
curl -fsSL -o grokbot-data-broker-removal.zip \
  "https://github.com/natv/grokbot-data-broker-removal/archive/refs/heads/main.zip"
```

Single file (catalog):

```text
https://raw.githubusercontent.com/natv/grokbot-data-broker-removal/main/companions/master-catalog.csv
```

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
