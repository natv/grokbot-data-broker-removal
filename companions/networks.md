# Network groupings

Suppress once at the parent portal when possible; spot-check siblings in SERPs.


Suppress once at the parent portal when possible; spot-check siblings in SERPs.

### PeopleConnect
- Canonical: https://suppression.peopleconnect.us/
- Brands often covered: Intelius, Instant Checkmate, TruthFinder, US Search, AnyWho, ZabaSearch, Addresses.com, PeopleLookup, and related skins. Classmates / reverse reports may still need a separate check.

### BeenVerified
- Canonical: https://www.beenverified.com/app/optout/search
- Related: PeopleSmart, PeopleLooker (and sometimes Bumper). One free people-search opt-out per email is common — extra records → email support.

### Whitepages
- Canonical: https://www.whitepages.com/suppression-requests
- Also: 411.com (same suppression family).

### Spokeo
- **Quirk:** Self-serve form can send a confirm email whose `http://spokeo.com/opt_out/verify?...` link returns HTTP 400; rewriting to `https://www.spokeo.com/...` may land on `/optout` with “Invalid email address.” Prefer Zendesk listing-URL confirmation path if verify fails; do not loop the same token.
- Canonical: https://www.spokeo.com/optout
- Mirrors (e.g. FreePeopleDirectory) often point at the same opt-out.

### PeopleFinders ↔ SmartBackgroundChecks
- Do **both** if both rank. Some guides say SBC may clear PeopleFinders; verify SERPs rather than assuming.

### InfoTracer family
- Canonical: https://infotracer.com/optout/
- Many state arrest / court / resident-directory clones reuse this opt-out. Do InfoTracer first; only chase clones that still appear in search.
