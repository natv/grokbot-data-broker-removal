---
name: Data broker people-search opt-out
description: >-
  Use when removing a person's listings from US people-search / data-broker
  sites; running Eraser (drumandbytes) with Gmail or Microsoft 365/Outlook;
  teaching a Grok Bot newcomer the Tier-1 live handoff vs park-for-later
  Needs-you flow; sharing/onboarding this skill (identity pack, effort tiers,
  sit-down kit, handoff, routines, multi-person); retrying failures; or clearing
  Cloudflare blocks with Local execution (traffic through the user's computer).
---
Generic process for **free listing suppression** on US people-search / data-broker sites. **Do not put subject PII in this skill** — pull name, phones, emails, address, and DOB from the user or the agent's private notes for that person.

Companion files in this skill folder (travel with the skill when shared):
- `master-catalog.csv` — **537** de-duped rows (tiers, opt-out URLs, networks, skip flags)
- `sources-inventory.md` — how Optery / Eraser / Yael BADBOOL were merged
- `session-plan.md` — blank multi-session batch template (seed statuses as `Not started`)
- `quirks.md` — per-site mechanism tips from live runs (no subject PII)
- `mail-setup.md` — Gmail / Microsoft 365 / Outlook / other IMAP for Eraser (App Passwords, manual-send fallback, unread preserve)
- `networks.md` — parent-network portals and sibling brands
- `identity-pack-template.md` — blank private identity-pack checklist (never fill in the skill folder)
- `sharing-and-onboarding.md` — identity pack, effort/stop, export hygiene, sit-down kit, handoff, standing routines, multi-person

**When companions are missing or incomplete after a Grok Bot template import:** the agent **MUST** download the full companions from the public GitHub release tag **v1.0.1** (fallback **v1.0.0**) into this skill folder **before Session A**. Prefer the tagged zip or raw files — do not rely on floating `main` alone.

- Zip: `https://github.com/natv/grokbot-data-broker-removal/archive/refs/tags/v1.0.1.zip` (fallback: `…/tags/v1.0.0.zip`)
- Raw base: `https://raw.githubusercontent.com/natv/grokbot-data-broker-removal/v1.0.1/companions/` (fallback: `…/v1.0.0/companions/`)
- Sync at least: `master-catalog.csv`, `quirks.md`, `session-plan.md`, `mail-setup.md`, `networks.md`, `identity-pack-template.md`, `sharing-and-onboarding.md`, `sources-inventory.md`; optionally refresh playbook from `playbook.md` if the embedded skill body is thinner than the GitHub playbook.
- Overwrite thin stubs in this skill folder only. **Never** overwrite a filled private progress file, identity pack, or tracker outside this folder.
- See **Fresh-project checklist** step **Sync companions from GitHub**.

**Directory attribution:** Optery data-brokers-directory and Yael Big-Ass-Data-Broker-Opt-Out-List are **CC BY-NC-SA 4.0**; Eraser `brokers.yaml` is **MIT**. Keep attribution if you redistribute catalog excerpts.

## What to expect (tell the human up front)

This skill is written so an agent can run most of the work. The **human still participates** — say that clearly at the start of a fresh project, especially if they are new to Grok Bot.

**You (the human) will sometimes need to:**
- Answer a **robot phone call** or enter an on-screen code (some Tier‑1 sites only verify by phone).
- Solve a **CAPTCHA** or Cloudflare puzzle the agent cannot finish after a few tries.
- Click a confirm / IDV link on your phone if the inbox is not connected to the agent.
- Upload a government ID only when a site requires it (optional; many people skip those sites).
- Flip **Local execution** on later so a Cloudflare‑blocked batch can retry through your own network (see below).

**The agent will:**
- Do listing search, free forms, solvable CAPTCHAs, and inbox confirm links on its own.
- Install / use **two browsers** on its computer (Chrome + **Firefox ESR**) and swap when one hits a spinner or bot wall.
- Prefer email/form verify over phone when both exist.
- Never pay for removal products.
- Ask how they want progress **tracked** (Sheets, Excel/OneDrive, or agent-only local) before Session A.
- Keep a running **Needs you** list and a separate **Cloudflare / egress** list instead of stopping the whole project on every blocker.
- Prepare a **Needs-you sit-down digest** before calling the human over; respect effort tiers (Tier‑1 first; finishing all ~537 rows is not required).
- Offer optional standing routines after onboarding (inbox watch, SERP recheck, Eraser resend) — create only if the user says yes.

## Onboarding & sharing (see companion)

Full text for identity pack, effort/when to stop, multi-person projects, Needs-you sit-down kit, export hygiene, how to install/share, and optional standing routines lives in **`sharing-and-onboarding.md`**. Blank fields: **`identity-pack-template.md`**. Follow that companion during Fresh-project checklist steps that mention identity pack, export hygiene, sit-down kit, or routines.

## Legal / residency

Ask the subject's **residency / primary jurisdiction** before choosing templates or portals.

- **Most US non-CA residents** (e.g. Florida, Texas, New York, and similar): use each site's **universal free listing suppression**, not California DROP / Delete Act portals as the primary path. Florida is a common example of non-CA, not the only audience.
- **California residents:** CCPA / CPRA paths and DROP may apply in addition to universal suppression; Eraser template `ccpa` is appropriate when the subject qualifies.
- **EU / UK residents:** prefer Eraser template `gdpr` and follow Eraser `EU-NOTES.md`; local DSAR wording may differ from US free-suppression forms.
- Opt-out ≠ removal from county / court / voter originals that brokers re-scrape. Recheck in 30–45 days, then ~twice yearly.

## HARD — preserve confirmation-inbox unread (do not “read” the user’s mail)

Checking the confirmation mailbox for broker replies **must not** clear the user’s unread/bold state on unrelated (or even related) messages. Apply this to **any** connected confirmation inbox (Gmail connector, Outlook / Microsoft 365 connector, or Eraser IMAP).

1. **Prefer** metadata / search / snippets for triage (`search_threads`, `METADATA_ONLY`, Outlook search, IMAP ENVELOPE/FLAGS without body). Only fetch a full body when you need a confirm link or exact wording.
2. **Before** a body fetch, note whether the message is unread. **After** the fetch, if it was unread and the connector marked it read, immediately restore unread (Gmail: `update_message_labels` with `addLabelIds: ["UNREAD"]`; Outlook / M365: use whatever mark-unread the connector exposes).
3. **Eraser IMAP:** `FetchRecentEmails` must use `BodySectionName{Peek: true}` (BODY.PEEK) so monitor does not set `\Seen` on every message in the date window. Rebuild `~/.local/bin/eraser` after pulling upstream if the patch is lost. Stock Eraser without Peek marks the whole recent INBOX read.
4. Never bulk-open or scan the whole INBOX “just to look.” Scope searches to broker/privacy subjects, known senders, or Eraser-known domains.
5. Archiving handled broker mail is fine; that is intentional. Clearing UNREAD on mail you only inspected is not.

## Tracker setup (ask before Session A)

**Ask how they want progress tracked** — do not assume Google Sheets. Use a short question (widget when available) with real options:

1. **Google Sheets** — agent creates/updates a spreadsheet via the Sheets connector. Best when they already live in Google.
2. **Excel in Microsoft 365 / OneDrive** — same columns in a workbook they can open in the browser or desktop Excel; agent updates via the Microsoft / OneDrive path when connected.
3. **Agent-only (on my computer)** — a local `progress.md` (and/or a working copy of `master-catalog.csv`) on the agent computer. No extra account setup. Fine for a solo run; remind them confirmation state lives with the agent unless they export later.
4. **Something else they name** — e.g. Notion database (same columns; export CSV for the agent periodically). Only offer if they ask, or as a custom option.

Recommended columns (workflow + inventory — same idea as a Notion broker DB), whatever tool they pick:

| Column | Purpose |
|--------|---------|
| Priority | Tier + rank from `master-catalog.csv` |
| Site | Canonical name |
| Opt-out URL | Free suppression / privacy URL |
| Listing URL(s) | Profile URLs found for this subject |
| Status | see vocabulary below |
| Submitted | Timestamp |
| Confirm clicked | Timestamp |
| Verified gone | Timestamp |
| Recheck due | Date |
| Notes | Quirks, ticket IDs — **no SSN/DL images** |
| Category | e.g. people-search, marketing, B2B (from catalog) |
| Parent network | PeopleConnect, BeenVerified, InfoTracer, etc. |
| BADBOOL priority | `crucial` / `high` / `unknown` (Yael triage signal) |
| Sources | Which directories listed it: Optery / Eraser / Yael |
| Method | `form` / `email` / `phone` (primary path used) |
| Opt-out email | Privacy/support address when email path exists (Eraser overlays help) |

Also useful views/filters: Needs you (later), Retry later, Cloudflare / egress.

Skip a separate Optery ID column unless you keep syncing to Optery’s CSV. Prefer one **Sources** text field over separate “BADBOOL match” / “In Eraser list” checkboxes.

Seed the tracker from `master-catalog.csv` (at least all **T1** rows, then T2 as you reach them). Backfill Category, Parent network, BADBOOL priority, Sources, Method, and Opt-out email from the catalog (+ Eraser emails when present). Collapse network siblings to one parent row when the portal covers them.

Do **not** hard-code a live tracker URL into this skill — each project gets its own sheet/workbook/local files.

## Operating rules

1. Prefer **email or web-form verification** over phone when both exist (even if slower). Phone only if it is the sole path.
2. Attempt CAPTCHAs **2–3 times** via the desktop agent before handoff. If Chrome hits an endless Cloudflare spinner with nothing to click, retry in **Firefox ESR** (or another browser engine). Keep **both browsers installed** on the agent computer so swapping is one step, not a mid-batch install.
3. **Never pay** for removal / reputation products (DeleteMe-style upsells, Searchbug paid unlocks, SpyFly paid paths, premium "protection" upsells).
4. Search for a listing **before** submitting extra PII; only send data the broker already shows.
5. Draft-only for any email sent as the user unless they asked to send.
6. After each live run, append new quirks to `quirks.md` (mechanism tips only — no subject PII).
7. **Retry failures:** transient errors (timeouts, 5xx, "try again later", email verifier down, voucher expired) → log `Blocked` / note the cause, then **retry later** in a dedicated retry pass (same day or next session). Do not burn the human's attention on a failure the agent can reattempt alone.
8. **Cloudflare / bot-wall accumulation:** when a site still blocks after Chrome + Firefox tries, do **not** stop the project. Mark it on a **Cloudflare / egress** list (site + URL + what failed) and continue the auto lane. Later, run a focused pass with [Local execution](grokbot://app/v1/settings?id=local-execution) enabled (traffic through the human's own computer) — see **Cloudflare / local-execution pass** below.

## Autonomy & batching (minimize user check-ins)

**Batch size:** default **8–12 sites** per work session (Tier‑1 can still be ~8; Tier‑2 long-tail **10–12**). Collapse parent-network siblings into one portal pass when the catalog says so.

### Human interaction — two lanes (important)

Assume the human is **not** sitting at the desk for every site. Split Needs‑you by priority:

1. **Tier‑1 Needs‑you — knock out early (with the human).**  
   For the highest‑impact people‑search sites (Whitepages, Spokeo, BeenVerified, PeopleConnect, TruePeopleSearch, FastPeopleSearch, That's Them, FamilyTreeNow, PeopleFinders, SmartBackgroundChecks, and similar top‑of‑table rows), if the path needs a **phone call**, a **CAPTCHA the agent cannot solve**, or another live human action, **pause and ask the human now** (or at the start of that Tier‑1 batch). Clear those while attention is available. Do not bury Tier‑1 phone gates at the bottom of a long park list.

2. **Everything else Needs‑you — log for a later sit‑down.**  
   For Tier‑2+ (and any non‑critical leftovers), when something needs the human, **record it and keep going**. Tracker status + a short **Needs you (later)** queue: site, why (phone / CAPTCHA / ID upload / SSO / decision), link or ticket ID, and what the human should do. At the end of a batch (or when the auto lane is drained), offer one digest and ask when they want a **Needs‑you sit‑down** session. Do not interrupt mid‑batch for these unless a confirm link is about to expire and only they can click it.

**Needs you** includes: phone/robot verification only path; government ID upload; payment/paywall (skip — never pay); CAPTCHA/Cloudflare failed after 2–3 tries + Firefox (also add to Cloudflare / egress list when the wall is network/bot related); SSO/login only the user can do; a decision (appeal wording, which listing, send vs discard an email draft); ambiguous identity matches.

### Order inside a batch

1. **Auto lane (do first):** listing search + free form + CAPTCHA the agent can solve + confirmation links the agent can open from the connected inbox. No payment, no ID upload, no phone call, no box handoff.
2. **Tier‑1 live handoffs:** if a Tier‑1 site needs the human right now, ask once, finish that site, then return to the auto lane.
3. **Park lane:** non‑Tier‑1 Needs‑you → log only; finish the auto lane before any sit‑down.
4. **Retry lane (same or next session):** reattempt earlier transient failures without the human when possible.
5. **Cloudflare / local-execution pass (scheduled):** when the Cloudflare / egress list has enough entries (or the human is free), ask them to enable Local execution temporarily and clear that list in one focused run.

**While waiting on email confirms:** do not idle the batch. Keep submitting other auto-lane sites. Click confirm/IDV links **promptly** when mail arrives (many vouchers expire ≤24h).

**Check-in cadence (default):**
- **Project start:** set expectations (phone/CAPTCHA/Firefox/Local execution) in plain language — especially for Grok Bot newcomers.
- **Start of batch:** one short note naming the batch (e.g. Session D, N sites) — then work quietly.
- **End of batch (or end of day):** one digest — Submitted / Confirm clicked / No listing / Blocked / Needs you (Tier‑1 done vs later) / Cloudflare queued / Retries due, with ticket IDs and next recheck dates. No per-site play-by-play unless something is blocked on the user.
- **Interrupt mid-batch only when:** a **Tier‑1** live handoff is required; a confirm link will expire soon and the inbox isn’t connected; payment/ID is required to finish a path they already chose; or a real blocker stops the whole batch.
- **Email drafts:** queue them and present at the end of the batch (or when the user is already in chat), not one-by-one mid-run unless the user asked to send ASAP.
- **Standing permission:** if the user says to keep running sessions without asking between batches, continue into the next planned session after the digest until they say pause / stop at session N / only do Tier‑1. Still interrupt for Tier‑1 phone/CAPTCHA handoffs unless they explicitly said to park those too.

**Tracker:** update after each site (or at least before the next site) so a crash never loses state. Status vocabulary stays authoritative. Keep Notes fields for `retry_after`, `cloudflare_egress`, and `needs_you_later` when useful.

### Cloudflare / local-execution pass

Grok Bot can send the agent computer's browser traffic **through the human's own network** via [Local execution](grokbot://app/v1/settings?id=local-execution) (the slider that routes network traffic through their computer). Many Cloudflare / datacenter bot walls clear on residential egress.

**How to use it:**
1. While running normal batches, **accumulate** sites that stay blocked after Chrome + Firefox attempts. Do not ask for Local execution on every single failure.
2. When the list is worth a focused session (or the human offers), ask them to **turn Local execution on temporarily**, confirm it is on, then retry only the Cloudflare / egress queue.
3. After that pass, ask them to **turn Local execution off** again (default stays on the agent computer's network).
4. Update the tracker: cleared → `Submitted` / `Confirm clicked` / etc.; still blocked → leave on the list with a fresh note.

## Eraser-first hybrid (recommended for large catalogs)

Manual browser sessions burn agent usage. For **email-addressable** brokers, prefer **[Eraser](https://github.com/drumandbytes/eraser)** (MIT; maintained fork of digisamroc/eraser): it emails 700+ brokers, tracks history, and surfaces leftovers in `pipeline`. The agent (or you) only handles what Eraser cannot finish alone.

### Recommended flow

1. Install Eraser on the agent computer (or your machine): release binary, Homebrew cask, or `go install github.com/drumandbytes/eraser/cmd/eraser@latest` / build from source.
2. `eraser init` **or** write `~/.eraser/config.yaml` from `config.example.yaml`. Put **subject PII only in that private config** — never in this skill, never in git, never in chat.
3. **Ask which confirmation + send mailbox** the user wants (Gmail vs Microsoft 365 / Outlook vs other IMAP) — see **Mail provider setup** below — then configure Eraser send + monitor **or** fall back to manual send / connector drafts.
4. Template from residency: **`generic`** for most US non-CA residents; `ccpa` if CA resident; `gdpr` for EU (see Eraser `EU-NOTES.md`).
5. Exclude noise: `excluded_categories: [requires-id]` (never upload government ID via automation). Optionally exclude brokers already completed via form portals.
6. Send: `eraser send --dry-run` first, then `eraser send`. Optional filters: `--list verified`, `--region us`, `--category people-search`.
7. Follow-up: enable inbox monitor when IMAP/App Password available → `eraser monitor` / `eraser confirm` for click-links → `eraser pipeline` for forms still needing a human or desktop agent (`eraser fill` needs Chrome/Chromium). **Must use BODY.PEEK** (see HARD — preserve confirmation-inbox unread); stock Eraser `FetchRecentEmails` without Peek marks the whole recent INBOX read.
8. **Tracker sync:** after each send day, merge Eraser `status` / `export` into the project tracker (Sheets / Notion / Excel / local). Method = `email` for Eraser sends; keep form quirks for portal work.
9. Agent role after Eraser: process **pipeline leftovers** + high-SERP people-search forms (auto lane first, Needs-you last). Do not re-email brokers Eraser already marked sent unless `pipeline` / bounce cleanup says so.
10. Recheck SERPs in 30–45 days; re-run Eraser every 60–90 days (brokers re-scrape).

### Mail provider setup (ask before configuring Eraser)

Ask which mailbox will send opt-outs and receive confirmations **before** configuring Eraser. Full Gmail / Microsoft 365 / Outlook / other IMAP steps (App Passwords, SMTP AUTH, manual-send fallback, HARD unread restore) live in companion **`mail-setup.md`**.

Short version: prefer App Password + IMAP BODY.PEEK when available; if the org blocks SMTP AUTH / basic auth, use `options.send_mode: manual` and connector drafts / search instead of `eraser monitor`.

### Inbox hygiene (after Eraser sends)

Broker replies can flood the confirmation inbox. Default cleanup after the agent has acted:

1. **Confirm / verify links:** click via Eraser `confirm` or the desktop agent; update tracker / Eraser status.
2. **Then archive** the handled message (or thread) — prefer **archive** over trash so nothing important is lost. Do **not** leave duplicates and “we got your request” acks sitting in the inbox.
3. **Safe to archive after handling:** confirmation-link mails, auto-acks (“request received”), duplicate copies of the same broker reply, marketing upsells attached to an opt-out thread.
4. **Do not auto-trash** unless the user asked for delete. Skip archiving if the thread still needs a user decision (ID upload, phone verify, ambiguous identity).
5. Optional: apply a mailbox label such as `Eraser` / `DataBroker-OptOut` before archive so history stays searchable (create the label in the user’s mailbox; do not hard-code provider label IDs).
6. Run a periodic inbox pass (`eraser monitor` and/or connector search for recent broker/privacy subjects) during active send weeks; quiet if nothing new.
7. **Unread:** `eraser monitor` must Peek (see HARD section). Connector body reads must restore unread when the message was unread before the fetch.

### Security notes for skill sharers

- `~/.eraser/config.yaml` holds PII + credentials — agent computer only; do not share the config when exporting the skill.
- Prefer a **dedicated send/confirmation mailbox** for opt-out traffic if the user wants separation from their main inbox.
- Eraser is not legal advice; compliance varies by broker and jurisdiction.
- Never put subject name, phones, emails, street address, DOB, ticket IDs for a live person, or live tracker URLs into this skill file.

### Attribution

Eraser broker data is **MIT**. Optery / Yael directories remain **CC BY-NC-SA 4.0** when you redistribute catalog excerpts from this skill folder.

## Network groupings

Suppress once at the parent portal when possible; spot-check siblings in SERPs. Parent portals and brand lists (PeopleConnect, BeenVerified, Whitepages, Spokeo, PeopleFinders↔SBC, InfoTracer) live in companion **`networks.md`**.

## Prioritized catalog (Tier 1 — hit these first)

Highest SERP / people-search impact. Full machine list: `master-catalog.csv`.

| Rank | Site | Opt-out |
|------|------|---------|
| 1 | Whitepages (411.com) | https://www.whitepages.com/suppression-requests |
| 2 | Spokeo | https://www.spokeo.com/optout |
| 3 | BeenVerified (+ PeopleSmart / PeopleLooker) | https://www.beenverified.com/app/optout/search |
| 4 | PeopleConnect network | https://suppression.peopleconnect.us/ |
| 5 | TruePeopleSearch | https://www.truepeoplesearch.com/removal |
| 6 | FastPeopleSearch | https://www.fastpeoplesearch.com/removal |
| 7 | That's Them | https://thatsthem.com/optout |
| 8 | FamilyTreeNow | https://www.familytreenow.com/optout |
| 9 | PeopleFinders | https://www.peoplefinders.com/opt-out |
| 10 | SmartBackgroundChecks | https://www.smartbackgroundchecks.com/optout |
| 11 | MyLife | https://www.mylife.com/privacyrequest |
| 12 | USPhonebook | https://www.usphonebook.com/opt-out/ |
| 13 | Radaris | https://radaris.com/control-privacy |
| 14 | Nuwber | https://nuwber.com/removal/link |
| 15 | CheckPeople | https://checkpeople.com/opt-out |
| 16 | CyberBackgroundChecks | https://www.cyberbackgroundchecks.com/removal |
| 17 | InfoTracer | https://infotracer.com/optout/ |
| 18 | SearchPeopleFree | https://www.searchpeoplefree.com/opt-out |
| 19 | USA People Search | https://www.usa-people-search.com/removal |
| 20 | PeopleSearchNow | https://www.peoplesearchnow.com/opt-out |
| 21 | AdvancedBackgroundChecks | https://www.advancedbackgroundchecks.com/opt-out |
| 22 | Veripages | https://veripages.com/inner/control-privacy |
| 23 | Clustal | https://www.clustal.org/privacy-control |
| 24 | PrivateEye | https://www.privateeye.com/removal |

### Other tiers (from `master-catalog.csv`)

| Tier | ~Count | How to use |
|------|-------:|------------|
| T2 | 184 | Other people-search with free opt-out when URL known — Session G+ |
| T3_CLONE | 119 | InfoTracer / mirror skins — parent first |
| T3_OTHER | 136 | Genealogy, face-search, weak/unknown opt-out |
| T4_MARKETING | 66+ | Adtech samples — after people-SERP work |
| T4_B2B | 6 | LexisNexis Risk, Checkr, GoodHire, etc. — different workflow |
| SKIP | Searchbug, SpyFly, DeleteMe/Incogni/Kanary/Optery paid products | Never pay |

## Multi-session plan (recommended order)

Use **8–12** sites per batch and merge adjacent sessions when running autonomously. Full tables live in `session-plan.md` (blank template — all statuses `Not started` until a project starts). Do not record personal progress in this skill.

**Session A:** Whitepages → Spokeo → BeenVerified → PeopleConnect  
**Session B:** TruePeopleSearch → FastPeopleSearch → That's Them → FamilyTreeNow  
**Session C:** PeopleFinders → SmartBackgroundChecks → MyLife → USPhonebook  
**Session D+E (~8):** Radaris → Nuwber → CheckPeople → CyberBackgroundChecks → InfoTracer → SearchPeopleFree → USA People Search → PeopleSearchNow  
**Session F (+ first T2 if capacity):** AdvancedBackgroundChecks → Veripages → Clustal → PrivateEye → (+ NeighborWho / Centeda / … from `session-plan.md` as room allows)  
**Session G+:** Tier-2 batches of **10–12** from `session-plan.md` / `master-catalog.csv` (`priority_tier=T2`)

Inside each batch: run **auto lane first**; handle **Tier‑1 Needs‑you** with the human when they come up; park other Needs‑you for a later sit‑down. After each batch: update tracker, process confirmation inbox, one digest, schedule retries / rechecks.

## Per-site playbook

Site-by-site mechanism tips (Whitepages through Sessions D–AA+) live in companion **`quirks.md`** — expanded from live runs; keep appending new mechanism tips after each session (placeholders only, no subject PII).

## Execution loop

**Default when Eraser is available:** run Eraser send/monitor/pipeline first (see above), sync tracker, then only open the browser for pipeline leftovers and Tier-1 SERP portals not covered by email.

**Per site (browser / form path):**

1. Search subject (name variants + city + each phone + email).
2. Collect every matching **listing/profile URL**.
3. Submit opt-out for each required unit (URL / record / phone as site demands).
4. Watch confirmation inbox; click confirm links promptly.
5. Update tracker: Status, timestamps, Notes, Method, Opt-out email as needed.
6. Append new quirks to `quirks.md` (no subject PII).
7. After batch: spot-check search; schedule recheck 30–45 days.

## Status vocabulary

`Not started` | `Searching` | `Submitted` | `Awaiting confirm` | `Awaiting appeal reply` | `Confirm clicked` | `Verified gone` | `Blocked` | `Retry later` | `Needs you (Tier-1)` | `Needs you (later)` | `Cloudflare / egress` | `No listing found` | `Skip (paid)`

## Fresh-project checklist (onboarding)

1. **Set expectations** (especially if they are new to Grok Bot): some sites need a live phone code or CAPTCHA; the agent uses Chrome + Firefox; Tier‑1 handoffs happen early; other Needs‑you items wait for a sit‑down; Cloudflare blocks are batched for a Local execution pass; finishing all ~537 catalog rows is not required (see **Effort & when to stop** in `sharing-and-onboarding.md`).
2. **Sync companions from GitHub** (required after a thin Grok Bot template import; skip only if companions are already complete beside this skill):
   1. Check whether `master-catalog.csv` exists in this skill folder and has **~500+** data rows (not a stub).
   2. If missing or thin: download the release zip **or** `curl` each companion from the raw tag URLs into this skill folder. Prefer tag **v1.0.1**, fall back to **v1.0.0**. Zip: `https://github.com/natv/grokbot-data-broker-removal/archive/refs/tags/v1.0.1.zip` (or `…/v1.0.0.zip`). Raw base: `https://raw.githubusercontent.com/natv/grokbot-data-broker-removal/v1.0.1/companions/` (or `…/v1.0.0/companions/`). Files to sync: `master-catalog.csv`, `quirks.md`, `session-plan.md`, `mail-setup.md`, `networks.md`, `identity-pack-template.md`, `sharing-and-onboarding.md`, `sources-inventory.md`; optionally overwrite a thinner embedded playbook from `playbook.md`. Overwrite thin stubs here only — **never** overwrite filled private progress / identity / tracker files outside this folder.
   3. Verify `master-catalog.csv`, `quirks.md`, and `session-plan.md` are present and non-trivial (catalog ~500+ rows; quirks and session-plan are multi-KB docs, not pointers).
   4. Read `MANIFEST.json` version / `download_tag` when present (expect `v1.0.1` or newer; `v1.0.0` is an acceptable fallback).
   5. Keep attribution: Optery / Yael **CC BY-NC-SA 4.0**; Eraser **MIT**.
3. Collect the subject **identity pack privately** — copy blank fields from **`identity-pack-template.md`** into private notes (name variants, phones, emails, city/state, street/DOB only if forms need them). Never fill the template inside this skill folder; never commit filled values that will be shared.
4. Ask **residency** → choose Eraser template `generic` / `ccpa` / `gdpr` and whether CA DROP portals apply.
5. Ask **mail provider** → Gmail vs Microsoft 365 / Outlook vs other IMAP → configure Eraser send + monitor **or** `options.send_mode: manual` + connector drafts / search.
6. Install Eraser (release binary / Homebrew / `go install` or build from source). If building for IMAP monitor, ensure BODY.PEEK patch is present; rebuild `~/.local/bin/eraser` after upstream pulls if Peek is lost.
7. Ensure the agent computer has **Firefox ESR** (or another second browser) installed alongside Chrome before Session A.
8. **Ask tracker preference** (Google Sheets / Excel in Microsoft 365–OneDrive / agent-only on my computer / other they name). Create that tracker; seed from `master-catalog.csv` T1+; backfill inventory columns; collapse network siblings; add Needs you (later), Retry later, and Cloudflare / egress views if useful. Do not paste a live tracker URL into this skill. If **multi-person / family**, one tracker (or Subject column + separate confirm emails) per person — see `sharing-and-onboarding.md`.
9. `eraser send --dry-run` → `eraser send` under the daily cap → sync Eraser status into the tracker.
10. Process `pipeline` leftovers and Tier‑1 SERP forms with **auto-lane batching** (8–12 sites); **Tier‑1 Needs‑you with the human early** (use the **Needs-you sit-down kit** in `sharing-and-onboarding.md`); park other Needs‑you for a later sit‑down; one digest per batch.
11. Run a **retry pass** for transient failures; when the Cloudflare list is ready, ask for a temporary [Local execution](grokbot://app/v1/settings?id=local-execution) pass, then turn it back off.
12. Recheck SERPs in **30–45 days**; re-run Eraser every **60–90 days** (brokers re-scrape). Never buy removal products; prefer email/form verify; CAPTCHA 2–3× then handoff; Firefox if Cloudflare spinner; exclude `requires-id`.
13. **Export hygiene reminder:** if this skill will be shared later, keep filled packs, App Passwords, live tracker IDs, and progress dumps out of the folder (see **Sharing this skill** in `sharing-and-onboarding.md`).
14. **Offer optional standing routines** after onboarding (inbox watch, SERP recheck, Eraser resend) — create only if the user says yes (see **Optional standing routines** in `sharing-and-onboarding.md`).
