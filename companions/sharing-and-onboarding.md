# Sharing & onboarding (companion)

These sections travel with the skill. Keep subject PII out of this file.

## Identity pack (private)

Subject PII never belongs in this skill folder. For each person, copy **`identity-pack-template.md`** into **private** notes (or keep the filled answers only in chat / a private file outside the skill). Fill blank fields there: legal name + variants, phones, emails (which is the confirmation inbox), city/state (+ prior cities if relevant), street / DOB only when a form requires them, residency for Eraser (`generic` / `ccpa` / `gdpr`), and verify-path notes (email over phone; which devices can take OTP).

Never commit filled values into the skill folder. Never paste a filled pack into chat if avoidable. See **Multi-person / family projects** when more than one subject is in scope.

## Effort & when to stop

- **Tier‑1** (~24 high-SERP people-search rows): highest impact. Expect most of the human phone / CAPTCHA time here. Clear these first.
- **Tier‑2** long-tail: diminishing returns. Batch **10–12**. Stop when SERP for the subject’s name + city is clean enough for their goal — not when the catalog is empty.
- **T3 clones:** parent portal first (InfoTracer and similar). Skip clones unless they still appear in SERPs.
- **T4 marketing / B2B:** optional; different workflow. Do after people-SERP work if at all.
- **SKIP paid products always** (DeleteMe-style, Searchbug paid unlocks, etc.).
- Finishing all **~537** catalog rows is **not** required for a successful project.

## Multi-person / family projects

- One **identity pack** + one **tracker** (or local progress file) **per subject**.
- Do not mix family members in one sheet without a **Subject** column and separate confirmation emails if needed.
- **Eraser:** separate config profile / subject block per person if the tool supports it; never reuse one person’s confirmations for another.
- If attention is limited, run **Tier‑1 for person A** before starting person B.

## Needs-you sit-down kit

Before calling the human over, prepare **one digest** (not a drip of interrupts):

1. **Ranked queue** — Tier‑1 first, then parked later items.
2. **Site + why** — phone / CAPTCHA / ID upload / OTP / device verify / decision.
3. **Direct link or ticket path** — no subject PII in examples or skill notes.
4. **Code / OTP still valid?** — note expire time if known; skip items that already expired and need a resubmit first.
5. **Which browser / tab** — Chrome vs Firefox; is [Local execution](grokbot://app/v1/settings?id=local-execution) on or off for this pass?
6. **Exact ask in one sentence** — e.g. “Enter the 4-digit code on screen”, “Solve the image CAPTCHA”, “Click Verify on your phone”.

**After the sit-down:** update the tracker; archive handled confirmation mail; note what remains on Needs you (later) or Cloudflare / egress.

## Sharing this skill (export hygiene)

**DO share:** `SKILL.md` + all companions in this folder — `master-catalog.csv`, `quirks.md`, blank `session-plan.md`, `mail-setup.md`, `networks.md`, `sources-inventory.md`, blank `identity-pack-template.md`.

**NEVER share:**
- Filled identity packs
- `~/.eraser/config.yaml` (PII + credentials)
- App Passwords or mailbox secrets
- Live tracker URLs / spreadsheet IDs
- Private progress files (`*PROGRESS*`, broker-verify notes with PII)
- Confirmation-inbox dumps
- Screenshots with visible PII

**Before export:** grep the skill folder for emails, phone numbers, sheet IDs, and real names. If anything subject-specific is present, remove it or move it to private notes outside the folder.

## How to install / share (Grok Bot)

**Preferred public distribution:** publish / import the **Grok Bot template** **Data broker removal**, with full companions hosted in the public GitHub repo [natv/grokbot-data-broker-removal](https://github.com/natv/grokbot-data-broker-removal) at release tag **v1.0.1** (fallback **v1.0.0**). The template stays size-safe; the long catalog / quirks / session-plan live on GitHub.

- **After a template import:** Fresh-project / getting-started **downloads companions from GitHub** (zip or raw tag URLs) into the skill folder `/home/box/agent-data/workflows/data-broker-people-search-opt-out/` before Session A. See the playbook step **Sync companions from GitHub**.
- **Whole skill folder share** still works when companions already travel with `SKILL.md` (catalog, quirks, blank session-plan, mail-setup, networks, sources-inventory, blank identity-pack-template) — skip the download if files are already complete (~500+ catalog rows).
- If unsure of the exact share UI wording: keep skill + companions in the **same folder** when sharing locally; the recipient agent should **Read this SKILL** and follow the **Fresh-project checklist**.
- **After install:** sync companions if needed → run Fresh-project checklist; ask tracker preference + mail provider; install **Firefox ESR** + **Eraser** on the agent computer.
- Point them at [Local execution](grokbot://app/v1/settings?id=local-execution) **only when** the Cloudflare / egress list is ready for a focused pass.
- Keep wording generic — do not invent UI paths beyond known `grokbot://` links, the public GitHub tag URLs, and “skill folder / companions travel with share.”

## Optional standing routines (offer after onboarding)

Offer to create these — **do not auto-create** without asking. When the user says yes, create via the routines skill with a quiet-if-nothing posture where noted.

1. **Confirmation-inbox watch** (e.g. every 2h daytime)  
   - **Trigger idea:** weekday daytime cadence while sends are active.  
   - **Routine should:** Peek / unread-safe triage of the confirmation inbox; notify on confirm links or Tier‑1 needs; **quiet if nothing**.  
   - Archive handled mail after acting.

2. **SERP recheck ~30–45 days after Tier‑1 batch**  
   - **Trigger idea:** one-shot or recurring ~monthly after the first Tier‑1 wave.  
   - **Routine should:** spot-check top people-search results for the subject’s name + city; update tracker statuses / recheck dates; notify only if listings reappeared or action is needed.

3. **Eraser resend every 60–90 days**  
   - **Trigger idea:** quarterly-ish while the project is still “keep clean.”  
   - **Routine should:** `eraser send --dry-run` then send under the daily cap; sync tracker; **quiet if nothing new** beyond a short “resend done” note.
