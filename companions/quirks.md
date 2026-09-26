# Quirks & per-site playbook

Mechanism tips from live runs. Placeholders only — no subject PII.

Update **`quirks.md`** after each session. Mechanism tips only — use placeholders (`the subject`, `/people/{slug}/…`, `subject phone`, `confirmation inbox`).

## Cross-cutting patterns

- **TrustArc portals** (InfoTracer, Search Quarry, StateRecords, ThePublicIndex, RecordsFinder, PropertyChecker, CourtCaseFinder, …): one Right-to-Delete / opt-out submit; watch confirmation inbox; many clones collapse to the same parent — suppress parent first, spot-check SERPs only.
- **OneTrust / Ketch identity verify:** email “Verify My Identity” links often fail (Identity Not Verified / 400–403) from the agent computer. Prefer the **subject’s own device/browser**; timed windows (~15 min) are common — resubmit the portal for a fresh link rather than reusing a dead one.
- **Scalable help-center privacy** (Kids Live Safe, Public Data Check, Public Information Services, Quick/Public Record Reports, SearchPublicRecords, …): SMS/email OTP codes expire; if submit fails after code entry (CF/Turnstile/form error), **restart the whole form** for a fresh code — do not burn an expired OTP.
- **Image CAPTCHA → Needs-you lane:** USA People Search, PeopleSearchNow, SpyDialer, USATrace, Zlookup, IDCrawl (reCAPTCHA image), AdvancedBackgroundChecks (reCAPTCHA fail after retries). Park; do not burn retries mid-batch.
- **Non-CA / FL-style statutory refuse:** SearchPeopleFree, FastPeopleSearch, Glad I Know / GovernmentRegistry (FL missing from state selector), Data Trust, Foller.me (CA-only). Prefer a **courtesy / voluntary suppression** ask citing the listing URL; do not spam form retries after “no applicable state privacy law.”
- **Parent network first:** InfoTracer, PeopleConnect, Spokeo, BeenVerified, Whitepages — skip or park clones once parent is submitted (rate-limit / redirect loops are common on clones).
- **Court-order / Atlas-style domain transfer:** Radaris, Centeda, Rehold, Rain Street, Telephone Directories — free form gone; skip (no free path).
- **Cloudflare parks:** accumulate after Chrome + Firefox fails; run a focused [Local execution](grokbot://app/v1/settings?id=local-execution) pass later (see skill — do not duplicate that playbook here).
- **Archive / Eraser:** if Eraser already acked a site, treat as covered; only reopen browser for pipeline leftovers or SERP leftovers.
- **SKIP paid:** Searchbug, SpyFly, paid reputation products — never pay for removal.

### Whitepages
- Needs **exact listing URL** first. Fast path: robot phone call + on-screen 4-digit code (changes on retry).
- No email verify on the automated tool. Fallback: email privacyrequest@ / support@ with name + listing URL.
- **Quirks:** Middle-name variants on listings; carrier spam filters often reject the robot call (2–3 retries); site may say up to 24h to clear; extra name searches can hit bot walls — stick to known listing URL.

### Spokeo
- Exact profile URL + email confirmation. One submission per profile URL.
- **Quirks:** Form may rate-limit ("limit the frequency of automated privacy requests") → email privacy@spokeo.com; confirm link required; ignore identity-theft upsells. HTTPS rewrite of verify links often still fails — prefer Zendesk / listing-URL path (see Network groupings).

### BeenVerified (+ siblings)
- Search → select record → email verification. Free.
- **Quirks:** Opt-out URL often redirects to `/svc/optout/search/`; hCaptcha can look solved but submit still errors → escalate by email to privacy@ + support@; one people-search record per email historically; check PeopleSmart / PeopleLooker; records may show middle initial. Ticket auto-ack only is common before human reply; still retry free form under residential egress before assuming email path is final.

### PeopleConnect network
- Email gate → Suppression Center. One suppression often covers Intelius / Instant Checkmate / TruthFinder / US Search background reports.
- **Quirks:** Reverse phone/address/email and Classmates may still show — re-check brands. Interactive Suppression Center + email gate in desktop browser — do not rely on curl alone. Prefer a fresh tab if another OneTrust portal tab is mid-OTP.

### TruePeopleSearch / FastPeopleSearch / That's Them / FamilyTreeNow
- Free, highly indexed. Email confirm + CAPTCHA / Cloudflare common. **Per listing.**
- **Quirks:**
  - **TruePeopleSearch:** Name + city and phones can return zero matches even when other brokers list the person. Phone reverse can surface unrelated people — exclude by name. Brief Cloudflare may clear without a puzzle. Mark `No listing found` and move on; recheck later.
  - **FastPeopleSearch:** Homepage may 429 while profile URLs still load. Flow: profile → removal → verify email (~24h) → `/optout/removal` with ticket → success (claimed ≤3 days). Follow-up email may **refuse** states without a comprehensive privacy law they apply (common for many non-CA residents). Appeal via https://www.fastpeoplesearch.com/privacy-rights (reply-to does **not** start appeal). Prefer a **courtesy / voluntary suppression** ask citing the listing URL over a weak statutory claim. GPC/cookies ≠ listing removal.
  - **That's Them:** `/optout`. Turnstile can stick — retry after Success. Confirmation email often within 72h. Name vs phone reverse cities can differ — opt out matching listings.
  - **FamilyTreeNow:** Cloudflare endless spinner with **no puzzle** possible. Try alternate browser (Firefox if Chrome failed) before parking as Blocked. Ticketed IDV form may claim removal in ≤3 days.

### PeopleFinders / SmartBackgroundChecks
- Opt-out on one does **not** reliably clear the other. Do both if listed.
- PeopleFinders `/opt-out` can 404 — use Help Center if needed.
- **Quirks:** Confirmation IDV link can show **Opt-out Voucher Expired** if delayed or double-used — resubmit opt-out for a fresh ticket and complete the ID form promptly (≤24h). SmartBackgroundChecks may 403 under Chrome Cloudflare; Firefox often works. FamilyTreeNow IDV submit can return “We were unable to process your request at this time” after a live CAPTCHA — park and retry / fresh Complete-your link; do not pay. Email confirm link then voucher-redeem success page; removal often claimed “shortly” / ~72h after click.

### GB Group / GBG (OneTrust)
- Portal: `privacyportal-uk.onetrust.com` JWT links — Eraser often blocks the redirect; open in desktop. “Needs Attention” often hits access-code gate (email OTP, 15 min) to the confirmation inbox.
- **Residency gate:** GBG may only process residents of listed eligible states. If the subject’s state is recorded as ineligible, close as Blocked; do not misrepresent residency.

### MyLife / USPhonebook
- MyLife: privacy request form at `/privacyrequest`; avoid membership upsells; ID upload only if unavoidable (redact ID#). Email verifier can fail mid-form (“Failed to send verification mail… server is down”) — retry later or use on-page privacy email if shown. When verifier works, Jotform email from noreply@jotform.com carries a one-time code (valid ~24h). Form also requires **birth year** before submit — keep DOB out of shared skills; pull from the subject’s private identity pack. Fallback email: membersupport@mylife.com (ticket ack e.g. MCC-*).
- USPhonebook: submit at `/opt-out` or `/removal`, then **email** with a second IDV form link (`/removal/validate-record-info?…&ticketid=…`). Complete promptly (≤24h) or regenerate. Success often claims removal ≤72h. One phone field per pass is common. Confirmation can return HTTP 200 and redirect to a process-wrong-info endpoint; Eraser may still record success.

---

## Sessions D–F (Tier-1 remainder)

### Radaris
- Free opt-out often **unavailable** after court-order / Atlas Data Privacy domain transfer.
- Skip free-form path; do not chase dead `/control-privacy` flows. Same pattern seen on Centeda / Rehold / Rain Street / Telephone Directories.

### Nuwber
- `/removal/link` frequently **ERR_CONNECTION_CLOSED** or tunnel fail even after retries.
- Park for Local-execution / later retry; do not burn the batch on it.

### CheckPeople
- Opt-out sends a verification email. Site may say a **verification request already exists** while the confirm message is delayed or missing in the confirmation inbox.
- Wait / search inbox (incl. spam) before resubmitting; duplicate submits rarely help.

### CyberBackgroundChecks
- Flow: removal request → email with second form (`/removal/optoutrequest/{id}/…`) that includes **reCAPTCHA**.
- Ticket / form link typically expires in **~24h** — complete promptly or resubmit for a fresh ticket.
- reCAPTCHA can block agent submit → Needs-you lane.

### InfoTracer (+ clones)
- TrustArc opt-out at `infotracer.com/optout/`. **Do parent first** — covers many state-arrest / court / resident-directory clones.
- Clones hitting the same portal may show **“page requested too many times”** rate-limit (e.g. SearchUSAPeople) — park clone; parent submission is enough unless SERP still ranks a unique listing.
- See `networks.md` InfoTracer family.

### SearchPeopleFree
- Common **non-CA / FL-style refuse**: “Privacy Request Processed” but no applicable state privacy law they apply.
- Do **not** spam form retries after refuse; prefer courtesy ask or park. Re-attempt tickets are usually not worth it.

### USA People Search / PeopleSearchNow
- Free removal forms commonly blocked by **image CAPTCHA** → Needs-you.
- Park mid-batch; complete when the human is available.

### AdvancedBackgroundChecks
- `/opt-out` reCAPTCHA often fails after multiple retries → Needs-you.
- Do not loop CAPTCHA mid-batch.

### Veripages
- `/inner/control-privacy` returns a **tracking id**; then await confirm email to the confirmation inbox.
- Complete confirm promptly when it arrives.

### Clustal
- `/privacy-control` — confirm link works; submission can be archived under Eraser once acked.
- Treat as done when confirm + Eraser ack both present.

### PrivateEye
- `/removal` often **404** — no free path. Mark N/A; do not invent alternate paid flows.

---

## Tier-2 / Sessions G–AA+

### NeighborWho
- `/remove` → await **verify email**; confirm completes the opt-out.
- Watch confirmation inbox (incl. spam).

### Centeda / Rehold / Rain Street / Telephone Directories
- Court-order domain transfer — free form gone. **Skip** (same class as Radaris).

### IDTrue / ClustrMaps / Neighbor.Report / OfficialUSA / PeopleFinder.Info
- Frequent **ERR_CONNECTION_CLOSED** / unreachable. Park for later / Local execution.

### National Public Data
- Catalog form URL may **404** — fall back to email `support@` with listing details.
- Prefer email path when form is dead.

### Unmask
- Opt-out may 403 from agent egress; when reachable: verify email → then **DOB + legal name** on the confirm page.
- “**No matching record**” after verify often means done (nothing to remove) — close as no listing / complete, not failure.
- Prefer confirm click from subject’s familiar inbox if agent path is blocked.

### PrivateRecords / Checksecrets / BackgroundCheckers / MUGSHOTLOOK / PeopleSearch123 / PeopleSearcher / PublicSearcher / SealedRecords / Secretinfo / TruthRecord / TruthViewer / WeInform / PersonSearchers / PrivateReports
- Shared **optOutLight/search** pattern: Turnstile or Cloudflare “Verifying” / “Processing” stuck after 2–3 tries.
- TruthRecord / SealedRecords: Turnstile can pass while **search Processing** still sticks.
- Accumulate as Cloudflare parks; Local-execution pass later. Some are Eraser / Revcontent pipeline leftovers — check Eraser ack before burning browser time.

### PropertyRecs / PropertyRecord.com / PublicRecords.us
- Dashboard opt-out can return **Success: Information Removed** or already-removed for subject phones — verify and close.

### PeopleByName
- May surface **multiple records** — submit each; await email.

### City-Data
- `/delrequest/form.php` — submitted then **email confirm**. Watch confirmation inbox.

### Adstra (American List Counsel) / ICE–Black Knight (OneTrust)
- OneTrust webforms: CAPTCHA on submit commonly Needs-you even when fields are filled.
- Prefer subject device if agent CAPTCHA fails repeatedly.

### AmericaPhonebook / Areacode-Lookup / CallApp / ConfidentialPhoneLookup / PhoneNumberInfo / SeekHD / Reveal Phone Owner
- Phone-centric removals: submit **each subject phone** (and email when asked). Contact-form path is common when dedicated opt-out is weak.
- CallerCenter: may no longer store names — N/A if stated.

### CourtCaseFinder / PropertyChecker / Search Quarry / StateRecords / ThePublicIndex / RecordsFinder
- **TrustArc** Right-to-Delete / members opt-out. Submit once; under-review / success confirmation is normal.
- Keep Report / request id in tracker (generic), not in shared quirks with PII.

### Data Trust / Glad I Know / GovernmentRegistry / Foller.me
- Jurisdiction / state-selector gaps (FL missing) or **CA-only** email paths. Park or courtesy ask; do not misrepresent residency.

### FastBackgroundCheck
- Ticketed opt-out; claimed removal often **≤3 days**. Complete email/ticket steps promptly.

### Florida Residents Directory / Florida Voter Directory / FloridaParcels
- Resident-directory family: listing URLs look like `/person/{id}/{slug}` or `/property/…`.
- CF verify can fail HTTP 400 on some siblings while others accept; treat each domain separately.
- Voter / parcel removals often claim **24–72h**.

### DexKnows
- OneTrust Delete Data; may contact confirmation inbox with no request id shown — still track as submitted.

### FreeBackgroundCheck.org / FreeBackgroundChecks.com / FreePeopleSearch
- Dead forms (404 / fax-mail only), TruthFinder redirects, or Cloudflare blocks. Search for listing before investing; skip paid.

### IDCrawl
- Listing path often `/ {slug} / {state}`. **reCAPTCHA image** → Needs-you.

### IDnotify (Experian)
- Consumer-privacy portal with **timed KBA** (sale/share/sensitive/ads + delete). Needs-you — human must answer knowledge questions within the timer.
- Do not start KBA until the subject is present.

### Illinois Prison Talk / Michigan Residents / Mississippi People Records / Ohio Residents / North Carolina Residents
- State-scoped directories: empty V-index / no-match search → **no listing**.
- Mississippi privacy/homepage **404** → N/A. NC variants may be CF 403 or expired domain parking pages.

### Lenso.ai
- Face-search opt-out requires **face-image upload**. Needs-you if no usable photo in the identity pack; do not scrape social photos without consent.

### Information.com
- Opt-out → Mandrill-style **verify email**. Link can fail or land on a **generic page** (especially from agent browser).
- Retry from confirmation inbox on the subject’s device; do not paste live verify URLs with email/name query params into shared notes.

### InmatesSearcher
- optOutLight path; confirm email sent after submit — complete confirm.

### Kids Live Safe / Public Data Check / Public Information Services / Quick Public Records / Public Record Reports / SearchPublicRecords
- Scalable-style **help-center privacy**: OTP (email/SMS) then select data / submit.
- Codes expire; CF 403 / Turnstile / form error after code entry → **restart form** for a fresh code (OTP alone is not reusable).
- Kids Live Safe can reach verification-complete; siblings often Needs-you on the post-OTP step.

### NumLooker / NumLookup / NumberGuru
- NumLooker: FAQ/support **email-only**; CF may block address fetch → Needs-you draft.
- NumLookup: after CAPTCHA may ask for a **different device** → Needs-you.
- NumberGuru: CF 403 park.

### OpenPeopleSearch
- `/Consumer` flow can land on `/Consumer/Confirmed` — treat as submitted success.

### OpenPublicRecords
- Form may **reject fields** even with no listing — park; do not force bad data.

### PeopleWhiz
- Request may be received, but confirm URL often **redirects to generic `/optout`** (no ID step) or hits CF 403.
- Some flows later ask ID upload — redact ID# if unavoidable; park if confirm is broken and retry later / subject device.

### PeopleWin
- Opt-out redirects to **Spokeo** parent — covered if Spokeo already handled.

### Persopo / User-Searcher
- Weak or missing web form → **email support** (`support@…` / `admin@…`) with opt-out request + listing context.
- Draft for human send when agent cannot mail from the confirmation identity.

### PhoneBooks.com / PrivateNumberChecker / RealPeopleSearch / PropertyReach / North Carolina Residents / VoterRecords / ReversePhone / SocialCatfish / Wyty / Unite4Heritage / MoneyBot5000
- Recurring **Cloudflare 403 / Verifying stuck**. Accumulate; Local-execution pass.

### PhoneNumbers.org / PublicRecordCenter / RhodeIslandPeopleRecords / Searqle / Realtyhop / OpenDataUSA / X-Ray Contact
- Opt-out or root **404** / unrelated redirect → **N/A**. Do not invent paths.

### SageStream / LexisNexis Risk
- Consumer opt-request portal (CAPTCHA often auto); then **email confirmation** (“Email Confirmation request sent”).
- Under review after confirm is normal; no ID upload on the happy path observed.

### SearchMobileNumber
- **Email-only** removal — no web form. Needs-you draft to the privacy contact.

### Searchbug / Spytox / SpyFly
- Spytox unreachable; Searchbug Access Denied / **paid** → **SKIP**. Never pay.

### SearchSystems
- Not a data broker (index / privacy page only) → **N/A**; no opt-out form.

### SpyDialer
- `/Consumers/` image CAPTCHA → Needs-you.

### Sync.ME
- `/unsubscribe/` — submit **each subject phone**; processing often **~24h**.

### USATrace / VerifyRecords / Zlookup
- Image CAPTCHA or “verifying” stuck → Needs-you. Listings may appear under nearby cities — match carefully before submit.

### Yellow Pages Directory / uFind / MineralHolders / CocoFinder / IDStrong / AlarmsCalifornia / etc.
- Search empty → **no listing**; close and recheck later if SERP changes.

### Cotality / Online Privacy Portal (CoreLogic family)
- FL / similar: **opt-out of sale/sharing** available; full deletion often **not** offered for that residency — do not claim deletion rights the portal denies.
- Ketch-style **Verify My Identity** email (~**15-min** window). Agent computer frequently gets **Identity Not Verified** (400/403) immediately — not merely expiry.
- **Works from the subject’s own phone/browser** in practice. Resubmit portal for a fresh link if the first fails; keep request id in the private tracker only.
- Fallback: reply on the privacy-thread contact if device verify still fails.

### ICE / Black Knight (Collateral Analytics) OneTrust
- Form can be fully filled while **CAPTCHA blocks submit** → Needs-you.
- Same OneTrust CAPTCHA pattern as Adstra.

---

## Quick reference — park / skip classes

| Class | Action |
|-------|--------|
| Court-order / Atlas transfer | Skip free form |
| Cloudflare Verifying / 403 after Chrome+Firefox | Accumulate → Local execution |
| Image / hard reCAPTCHA | Needs-you lane |
| Non-CA statutory refuse | Courtesy ask or park; no spam retries |
| Parent already submitted | Park clone unless unique SERP hit |
| Opt-out 404 / not a broker | N/A |
| Paid removal product | SKIP — never pay |
| Eraser already acked | Archive; browser only for leftovers |
