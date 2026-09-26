# Sources inventory — US people-search / data-broker opt-out directories

Generated for skill update. **No personal PII.** Licenses noted for attribution compliance (Optery & Yael are CC BY-NC-SA 4.0; Eraser is MIT).

## 1. Optery — `optery/optery-data-brokers-directory`

| Field | Value |
|-------|-------|
| URL | https://github.com/optery/optery-data-brokers-directory |
| Primary data | `data/data-brokers.csv`, `data/data-brokers.json`, `data/data-brokers.md` |
| Total entries | **956** |
| People Search Site | **386** |
| Phone Directory | 37 |
| Profile Data Broker | 46 |
| Marketing | 285 |
| B2B Lead Generation | 127 |
| Business Search | 72 |
| With `opt_out_url` | **509** / 956 |
| Fields | id, title, website, opt_out_url, opt_out_guide_url, opt_out_guide_video_url, email, description, type, optery_support_tier, is_expanded_reach |
| Optery support tiers | Core (366), Custom Removals (318), Extended (176), Ultimate (96) |
| License | **CC BY-NC-SA 4.0** (Optery, Inc.) — attribution + non-commercial + share-alike required |
| Notes | Largest structured directory; many state-arrest / court-record clones share InfoTracer opt-out URLs. "Custom Removals" = Optery product tier, not necessarily "no free opt-out". |

## 2. Eraser — `digisamroc/eraser` (upstream `eraser-privacy/eraser`)

| Field | Value |
|-------|-------|
| URL | https://github.com/digisamroc/eraser (module `github.com/eraser-privacy/eraser`) |
| Primary data | `data/brokers.yaml` |
| Total entries | **764** |
| people-search | **25** |
| background-check | **6** |
| marketing | **733** |
| Regions | us (751), global (13) |
| Fields | id, name, email, website, opt_out_url, region, category |
| License | **MIT** |
| Notes | Go app that emails CCPA/GDPR-style removal requests. Marketing-heavy list (733). People-search list is small but high-signal (Spokeo, BeenVerified, Whitepages, Intelius, TPS, FPS, etc.). |

## 3. Yael Writes — Big Ass Data Broker Opt-Out List (BADBOOL)

| Field | Value |
|-------|-------|
| URLs | https://github.com/yaelwrites/Big-Ass-Data-Broker-Opt-Out-List and https://github.com/yaelwrites/big-ass-data-broker-opt-out-list (same content) |
| Primary data | `README.md` (markdown list; no CSV/JSON) |
| Brokerish entries parsed | **48** (plus guidance sections excluded) |
| Priority markers | 💐 crucial (~12), ☠ high priority (~6), 💰 charges money, 📞 phone required, 🎫 driver's license |
| License | **CC BY-NC-SA 4.0** |
| Last noted update in README | August 27, 2026 |
| Notes | Best curated *priority* signal and procedural quirks. Mentions CA DROP portal; for **Florida / non-CA** prefer **universal free suppression** paths, not CA-only DROP. Documents PeopleConnect ownership graph (Intelius family) and BeenVerified→PeopleSmart/PeopleLooker. |

## Cross-source usage for this catalog

- **Priority / quirks:** Yael 💐/☠ + project Session A/B status
- **Breadth + opt-out URLs:** Optery people-search / phone / profile
- **Emailable broker contacts + compact PS list:** Eraser YAML
- **Aggressive de-dupe:** normalized domain + brand-family aliases (PeopleConnect, BeenVerified, Whitepages/411, Spokeo mirrors, InfoTracer clones)
