# Session plan — free listing suppression (blank template)

**No personal PII.** Batches sized **8–12** sites (auto lane first; park Needs-you items to end of batch). Prefer email/form verify over phone; never pay for removal products. Digests at batch end, not per site.

**Residency example:** for Florida / most non-CA residents, use universal free suppression forms; do **not** rely on CA-only DROP as the primary path. Ask residency first (CA → CCPA/DROP may apply; EU → GDPR). Copy this file per project and fill Status as you go — do not write live progress back into the shared skill.

## Autonomy (how batches run)

1. **Auto lane first** — form + CAPTCHA + inbox confirms the agent can finish alone.
2. **Needs you last** — phone-only verify, ID upload, failed CAPTCHA/Cloudflare after retries, send-or-discard drafts, identity ambiguity.
3. **Batch size** — 8–12 sites; merge Session D+E (and F into T2) when running without check-ins.
4. **Quiet mid-batch** — one start note, one end digest; interrupt only for expiring confirms / hard blockers.
5. **Between batches** — if user said keep going, start the next planned session after the digest until they pause.

## Tier-1 sessions

### Session A
_Whitepages + Spokeo + BeenVerified + PeopleConnect network._
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| Whitepages (411.com) | `whitepages.com` | https://www.whitepages.com/suppression-requests | Not started |
| Spokeo | `spokeo.com` | https://www.spokeo.com/optout | Not started |
| BeenVerified (PeopleSmart / PeopleLooker) | `beenverified.com` | https://www.beenverified.com/app/optout/search | Not started |
| PeopleConnect (Intelius / Instant Checkmate / TruthFinder / ZabaSearch / AnyWho) | `peopleconnect.us` | https://suppression.peopleconnect.us/login | Not started |

### Session B
_TruePeopleSearch + FastPeopleSearch + That's Them + FamilyTreeNow._
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| TruePeopleSearch | `truepeoplesearch.com` | https://www.truepeoplesearch.com/removal | Not started |
| FastPeopleSearch | `fastpeoplesearch.com` | https://www.fastpeoplesearch.com/optout | Not started |
| That's Them | `thatsthem.com` | https://thatsthem.com/optout | Not started |
| FamilyTreeNow | `familytreenow.com` | https://www.familytreenow.com/optout | Not started |

### Session C
_PeopleFinders + SmartBackgroundChecks + MyLife + USPhonebook._
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| PeopleFinders | `peoplefinders.com` | https://www.peoplefinders.com/opt-out | Not started |
| SmartBackgroundChecks | `smartbackgroundchecks.com` | https://www.smartbackgroundchecks.com/optout | Not started |
| MyLife | `mylife.com` | https://www.mylife.com/privacyrequest | Not started |
| USPhoneBook | `usphonebook.com` | https://www.usphonebook.com/opt-out | Not started |

### Session D+E
_Auto lane first. InfoTracer often covers many state-arrest / court-record clones — do InfoTracer once, then spot-check clones only if still in SERPs._
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| Radaris | `radaris.com` | https://radaris.com/control-privacy | Not started |
| Nuwber | `nuwber.com` | https://nuwber.com/removal/link | Not started |
| CheckPeople | `checkpeople.com` | https://checkpeople.com/opt-out | Not started |
| CyberBackgroundChecks | `cyberbackgroundchecks.com` | https://www.cyberbackgroundchecks.com/removal | Not started |
| InfoTracer | `infotracer.com` | https://infotracer.com/optout/ | Not started |
| SearchPeopleFree | `searchpeoplefree.com` | https://www.searchpeoplefree.com/opt-out | Not started |
| USA People Search | `usa-people-search.com` | https://www.usa-people-search.com/removal | Not started |
| PeopleSearchNow | `peoplesearchnow.com` | https://www.peoplesearchnow.com/opt-out | Not started |

### Session F
_Finish Tier-1 leftovers; pull first T2 sites from Session G if capacity remains._
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| AdvancedBackgroundChecks | `advancedbackgroundchecks.com` | https://www.advancedbackgroundchecks.com/opt-out | Not started |
| Veripages | `veripages.com` | https://veripages.com/inner/control-privacy | Not started |
| Clustal | `clustal.org` | https://www.clustal.org/privacy-control | Not started |
| PrivateEye | `privateeye.com` | https://www.privateeye.com/removal | Not started |

## Tier-2 follow-on sessions (other people-search)

Seeded from `master-catalog.csv` (`priority_tier=T2`), ~8 sites per session. Collapse parent-network siblings when the catalog says so. Status starts as `Not started` for every fresh project.

### Session G
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| 411.info | `411.info` | https://411.info/manage/ | Not started |
| Adstra (American List Counsel) | `adstradata.com` | https://privacyportal.onetrust.com/webform/3d2d5e0c-bd98-46b8-906c-ede68a6f6a80/f54a1b10-bb5d-4c99-9521-3e08dc527583 | Not started |
| AlarmsCalifornia | `alarmscalifornia.org` | http://www.alarmscalifornia.org/about | Not started |
| Amedisys, Inc. | `amedisys.com` | https://cdn.amedisys.com/userfiles/CCPA%20Request%20Form.pdf | Not started |
| AmericaPhonebook | `americaphonebook.com` | http://www.americaphonebook.com/contact.php | Not started |
| Areacode-Lookup | `areacode-lookup.com` | https://www.areacode-lookup.com/optout | Not started |
| ArrestWarrant.org | `arrestwarrant.org` | https://ms.arrestwarrant.org/InfoPayOpt-OutNew.pdf | Not started |
| AtData | `atdata.com` | https://instantdata.atdata.com/optout | Not started |

### Session H
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| Background Hawk | `backgroundhawk.com` | https://www.truthfinder.com/opt-out/v2/submit/ | Not started |
| BackgroundCheckers | `backgroundcheckers.net` | https://www.backgroundcheckers.net/api/helper/optOutLight/search | Not started |
| California Criminal Records Search | `californiacriminalrecords.org` | https://californiacriminalrecords.org/contact | Not started |
| CallApp Software Ltd. | `callapp.com` | https://callapp.com/support/can-i-wipe-my-information-from-callapp-2 | Not started |
| CallerCenter.com | `callercenter.com` | https://www.callercenter.com/remove_name.htm | Not started |
| CallerSmart | `callersmart.com` | https://www.callersmart.com/data | Not started |
| Centeda | `centeda.com` | https://centeda.com/ng/control/privacy | Not started |
| Checksecrets | `checksecrets.com` | https://www.checksecrets.com/api/helper/optOutLight/search | Not started |

### Session I
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| City-Data.com | `city-data.com` | https://www.city-data.com/delrequest/form.php | Not started |
| Clustermaps.NET | `clustermaps.net` | https://clustermaps.net/opt-out/ | Not started |
| ClustrMaps | `clustrmaps.com` | https://clustrmaps.com/bl/opt-out | Not started |
| CocoFinder | `cocofinder.net` | https://cocofinder.net/remove-my-info | Not started |
| ConfidentialPhoneLookup | `confidentialphonelookup.com` | https://www.confidentialphonelookup.com/removals/ | Not started |
| ContractorsCalifornia.org | `contractorscalifornia.org` | http://www.contractorscalifornia.org/about#contact | Not started |
| CorporationWiki | `corporationwiki.com` | https://www.corporationwiki.com/profiles/public | Not started |
| CourtCaseFinder | `courtcasefinder.com` | https://courtcasefinder.com/optout | Not started |

### Session J
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| CourtRec.com | `courtrec.com` | https://dashboard.courtrec.com/opt-out | Not started |
| Criminal.com | `criminal.com` | https://www.truthfinder.com/opt-out/v2/submit/ | Not started |
| CriminalDataCheck | `criminaldatacheck.com` | https://www.intelius.com/privacy-center | Not started |
| CriminalRecords.com | `criminalrecords.com` | https://www.intelius.com/privacy-center | Not started |
| CriminalRegistry.org | `criminalregistry.org` | https://criminalregistry.org/remove.php?fn=&ln= | Not started |
| Data Trust | `thedatatrust.com` | https://thedatatrust.com/do-not-sell-my-personal-information/ | Not started |
| DentistsCalifornia.org | `dentistscalifornia.org` | http://www.dentistscalifornia.org/about#contact | Not started |
| DexKnows.com | `dexknows.com` | https://privacyportal-cdn.onetrust.com/dsarwebform/dd6500c7-03cb-45b0-8bed-97ece55a892d/cfcefb69-41db-4aee-bd00-c702df72ee0f.html | Not started |

### Session K
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| DOBsearch.com | `dobsearch.com` | https://www.dobsearch.com/people-finder/block-record-request.php | Not started |
| Drunk Drivers | `drunkdrivers.org` | https://drunkdrivers.org/remove-my-info/ | Not started |
| EasyBackgroundChecks | `easybackgroundchecks.com` | https://www.intelius.com/suppression-center/ | Not started |
| Fandom, Inc. | `fandom.com` | https://itlaw.fandom.com/wiki/Opt-out | Not started |
| FastBackgroundCheck | `fastbackgroundcheck.com` | https://www.fastbackgroundcheck.com/optout | Not started |
| FindPeopleFast.net | `findpeoplefast.net` | https://findpeoplefast.net/company/remove-my-info | Not started |
| FireArmsCalifornia.org | `firearmscalifornia.org` | http://www.firearmscalifornia.org/about#contact | Not started |
| First Advantage Corporation | `fadv.com` | https://fadv.com/privacy-center/non-us-residents/your-rights/ | Not started |

### Session L
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| First Beat Media | `phonelookup.com` | https://www.phonelookup.com/opt | Not started |
| Florida Residents | `floridaresidentsdirectory.com` | https://www.floridaresidentsdirectory.com/opt-out | Not started |
| Florida Voter Directory | `floridavoterdirectory.com` | https://www.floridavoterdirectory.com/opt-out | Not started |
| FloridaParcels.com | `floridaparcels.com` | https://floridaparcels.com/redaction/ | Not started |
| Foller.me | `foller.me` | https://www.foller.me/do-not-sell | Not started |
| FreeBackgroundCheck.org | `freebackgroundcheck.org` | https://new-members.freebackgroundcheck.org/removeMyData/ | Not started |
| FreeBackgroundChecks.com | `freebackgroundchecks.com` | https://freebackgroundchecks.com/optout/ | Not started |
| FreePeopleSearch | `freepeoplesearch.com` | https://freepeoplesearch.com/opt-out | Not started |

### Session M
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| FreePhoneTracer | `freephonetracer.com` | https://www.beenverified.com/app/optout/search | Not started |
| Glad I Know | `gladiknow.com` | https://gladiknow.com/opt-out | Not started |
| GovernmentRegistry.org | `governmentregistry.org` | https://www.governmentregistry.org/opt-out | Not started |
| Houston Association of REALTORS® | `har.com` | https://www.har.com/question/27460_how-can-i-opt-out-of-the-zillow-listing | Not started |
| HudwayGlass | `hudwayglass.com` | https://hudwayglass.com/page/privacy | Not started |
| IDCrawl | `idcrawl.com` | https://www.idcrawl.com/remove-my-information | Not started |
| IDnotify | `idnotify.com` | https://portal.idnotify.com/privacy-policy | Not started |
| IDStrong | `idstrong.com` | https://www.idstrong.com/optout/ | Not started |

### Session N
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| IDTrue | `idtrue.com` | https://www.idtrue.com/optout | Not started |
| Illinois Prison Talk | `illinoisprisontalk.org` | https://illinoisprisontalk.org/remove-my-info.php | Not started |
| Information.com | `information.com` | https://information.com/opt-out | Not started |
| InmatesSearcher | `inmatessearcher.com` | https://www.inmatessearcher.com/api/helper/optOutLight/search | Not started |
| InstantCheckSpy | `instantcheckspy.com` | https://www.truthfinder.com/privacy-center | Not started |
| IPQualityScore LLC | `ipqualityscore.com` | https://www.ipqualityscore.com/domain-reputation/optout.networkadvertising.org | Not started |
| Kids Live Safe | `kidslivesafe.com` | https://www.kidslivesafe.com/help-center/privacy-requests | Not started |
| LENSO AI SPÓŁKA AKCYJNA | `lenso.ai` | https://lenso.ai/en/opt-out | Not started |

### Session O
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| Men Stopping Violence | `menstoppingviolence.org` | https://www.menstoppingviolence.org/privacy/ | Not started |
| Michigan Residents | `michiganresidentdatabase.com` | https://www.michiganresidentdatabase.com/opt-out | Not started |
| MineralHolders | `mineralholders.com` | https://www.mineralholders.com/opt-out | Not started |
| Mississippi People Records | `mississippipeoplerecords.org` | https://mississippipeoplerecords.org/privacy-policy | Not started |
| MoneyBot5000 | `moneybot5000.com` | https://www.moneybot5000.com/svc/optout/search/optouts | Not started |
| MUGSHOTLOOK | `mugshotlook.com` | https://www.mugshotlook.com/api/helper/optOutLight/search | Not started |
| National Public Data | `nationalpublicdata.com` | https://nationalpublicdata.com/optout.html | Not started |
| Native American Netroots | `nativeamericannetroots.net` | https://nativeamericannetroots.net/diary/51 | Not started |

### Session P
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| Neighbor.Report | `neighbor.report` | https://neighbor.report/remove | Not started |
| NeighborWho | `neighborwho.com` | https://neighborwho.com/remove | Not started |
| NJPropertyRecords | `njpropertyrecords.com` | https://njpropertyrecords.com/redaction | Not started |
| North Carolina Residents | `northcarolinaresidentdatabase.com` | https://northcarolinaresidentdatabase.com/opt-out | Not started |
| NorthCarolinaPublicRecords.org | `northcarolinapublicrecords.org` | https://www.truthfinder.com/opt-out/v2/submit/ | Not started |
| NotariesCalifornia.com | `notariescalifornia.com` | http://www.notariescalifornia.com/about | Not started |
| NumberGuru | `numberguru.com` | https://www.numberguru.com/svc/optout/search/optouts/search_person_result | Not started |
| NumLooker | `numlooker.com` | https://numlooker.com/remove-my-info | Not started |

### Session Q
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| NumLookup | `numlookup.com` | https://www.numlookup.com/opt_out | Not started |
| OfficialUSA | `officialusa.com` | https://www.officialusa.com/opt-out/ | Not started |
| Ohio Residents | `ohioresidentdatabase.com` | https://www.ohioresidentdatabase.com/opt-out | Not started |
| OpenDataUSA | `opendatausa.com` | https://opendatausa.com/optout | Not started |
| OpenPeopleSearch | `openpeoplesearch.com` | https://openpeoplesearch.com/Consumer | Not started |
| OpenPublicRecords | `open-public-records.com` | https://www.open-public-records.com/records_removal.htm | Not started |
| Ownerly | `ownerly.com` | https://www.beenverified.com/svc/optout/search/comprehensive_optouts | Not started |
| PeopleByName | `peoplebyname.com` | http://www.peoplebyname.com/remove.php | Not started |

### Session R
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| PeopleFind.com | `peoplefind.com` | https://www.intelius.com/privacy-center | Not started |
| PeopleFinder | `peoplefinder.com` | https://suppression.peopleconnect.us/login | Not started |
| PeopleFinder.Info | `peoplefinder.info` | https://peoplefinder.info/optout | Not started |
| PeopleSearch | `peoplesearch.com` | https://www.whitepages.com/privacy/ccpa | Not started |
| PeopleSearch123 | `peoplesearch123.com` | https://www.peoplesearch123.com/api/helper/optOutLight/search | Not started |
| PeopleSearcher | `peoplesearcher.com` | https://www.peoplesearcher.com/api/helper/optOutLight/search | Not started |
| PeopleSearchUSA | `peoplesearchusa.org` | https://www.peoplesearchusa.org/api/helper/optOutLight/search | Not started |
| PeopleWhiz.com | `peoplewhiz.com` | https://www.peoplewhiz.com/optout | Not started |

### Session S
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| peoplewhizr.com | `peoplewhizr.com` | https://www.peoplewhizr.com/optout | Not started |
| PeopleWin | `peoplewin.com` | https://peoplewin.com/privacy/control | Not started |
| PersonSearchers | `personsearchers.com` | https://www.personsearchers.com/api/helper/optOutLight/search | Not started |
| Persopo.com | `persopo.com` | http://info.persopo.com/opt-out.html | Not started |
| PhoneBooks.com | `phonebooks.com` | https://www.phonebooks.com/opt-out | Not started |
| PhoneNumberInfo.us | `phonenumberinfo.us` | https://phonenumberinfo.us/contact.php | Not started |
| PhoneNumbers.org | `phonenumbers.org` | https://phonenumbers.org/optout/ | Not started |
| Pipl | `pipl.com` | https://pipl.com/personal-information-removal-request | Not started |

### Session T
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| PrivateNumberChecker.com | `privatenumberchecker.com` | https://www.privatenumberchecker.com/removal-request/ | Not started |
| PrivateRecords | `privaterecords.net` | https://www.privaterecords.net/api/helper/optOutLight/search | Not started |
| PrivateReports | `privatereports.com` | https://www.privatereports.com/api/helper/optOutLight/search | Not started |
| PropertyChecker.com | `propertychecker.com` | https://propertychecker.com/optout | Not started |
| PropertyIQ | `propertyiq.com` | https://www.propertyiq.com/opt-out/address-search | Not started |
| PropertyReach | `propertyreach.com` | https://www.propertyreach.com/privacy-rights | Not started |
| PropertyRecord.com | `propertyrecord.com` | https://dashboard.propertyrecord.com/opt-out | Not started |
| PropertyRecs | `propertyrecs.com` | https://dashboard.propertyrecs.com/opt-out | Not started |

### Session U
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| PropertyRecs | `dashboard.propertyrecs.com` | https://dashboard.propertyrecs.com/opt-out | Not started |
| Public Data Check | `publicdatacheck.com` | https://www.publicdatacheck.com/help-center/privacy-requests | Not started |
| Public Information Services | `publicinfoservices.com` | https://www.publicinfoservices.com/help-center/privacy-requests | Not started |
| Public Libraries | `publiclibraries.com` | https://www.truthfinder.com/opt-out/v2/submit/ | Not started |
| Public Record Reports | `publicrecordreports.com` | https://www.publicrecordreports.com/help-center/privacy-requests | Not started |
| PublicDataUSA | `publicdatausa.com` | https://publicdatausa.com/optout | Not started |
| PublicRecordCenter.com | `publicrecordcenter.com` | https://www.publicrecordcenter.com/remove.html | Not started |
| PublicRecords.com | `publicrecords.com` | https://suppression.peopleconnect.us/login | Not started |

### Session V
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| PublicRecords.us | `publicrecords.us` | https://dashboard.publicrecords.us/opt-out | Not started |
| PublicRecordsNow | `publicrecordsnow.com` | https://www.publicrecordsnow.com/static/view/optout/ | Not started |
| PublicSearcher | `publicsearcher.com` | https://www.publicsearcher.com/api/helper/optOutLight/search | Not started |
| Quick Public Records | `quickpublicrecords.com` | https://www.quickpublicrecords.com/help-center/privacy-requests | Not started |
| Rain Street | `rain-street.org` | https://rain-street.org/page/contact | Not started |
| RealPeopleSearch | `realpeoplesearch.com` | https://realpeoplesearch.com/about/remove-my-info | Not started |
| Realtyhop.com | `realtyhop.com` | https://www.realtyhop.com/resources/realtyhop-redaction-request-system/ | Not started |
| RecordsFinder | `recordsfinder.com` | https://recordsfinder.com/optout/ | Not started |

### Session W
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| RecordsPage | `recordspage.org` | https://www.truthfinder.com/opt-out/v2/submit/ | Not started |
| RecordsQuarry | `recordsquarry.com` | https://www.truthfinder.com/opt-out/v2/submit/ | Not started |
| Redfin Corporation | `redfin.com` | https://support.redfin.com/hc/en-us/articles/38493151019419-How-do-I-remove-my-home-from-Redfin | Not started |
| Rehold | `rehold.com` | https://rehold.com/control/privacy | Not started |
| Reveal Phone Owner | `revealphoneowner.com` | https://www.revealphoneowner.com/data-removal/ | Not started |
| Reverseaustralia | `reverseaustralia.com` | https://www.reverseaustralia.com/privacy.php | Not started |
| ReversePhone | `reversephone.com` | https://www.reversephone.com/svc/optout/search/optouts | Not started |
| ReversePhoneLookup | `reversephonelookup.com` | https://www.intelius.com/privacy-center | Not started |

### Session X
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| RhodeIslandPeopleRecords.org | `rhodeislandpeoplerecords.org` | https://rhodeislandpeoplerecords.org/opt-out | Not started |
| SageStream, LLC | `sagestreamllc.com` | https://www.sagestreamllc.com/opt-out-opt-in/index.html | Not started |
| Salary.com, LLC | `salary.com` | https://www.salary.com/legal/privacy-controls/ | Not started |
| Scribd, Inc. | `scribd.com` | https://www.scribd.com/document/253240908/Opt-Out-Form | Not started |
| SealedRecords | `sealedrecords.net` | https://www.sealedrecords.net/api/helper/optOutLight/search | Not started |
| Search Quarry | `searchquarry.com` | https://members.searchquarry.com/terms?tab=optout | Not started |
| SearchMobileNumber.com | `searchmobilenumber.com` | https://searchmobilenumber.com/privacy-policy | Not started |
| SearchPublicRecords.com | `searchpublicrecords.com` | https://www.searchpublicrecords.com/help-center/privacy-requests | Not started |

### Session Y
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| SearchSystems Public Records | `publicrecords.searchsystems.net` | https://publicrecords.searchsystems.net/opt-out.php | Not started |
| SearchUSAPeople | `searchusapeople.com` | https://www.searchusapeople.com/data-removal-request/ | Not started |
| Searqle | `searqle.com` | https://searqle.com/opt-out-information/ | Not started |
| Secretinfo | `secretinfo.org` | https://www.secretinfo.org/api/helper/optOutLight/search | Not started |
| SeekHD | `seekhd.com` | https://www.seekhd.com/optout | Not started |
| SheriffsDepartment.net | `sheriffsdepartment.net` | https://www.truthfinder.com/opt-out/v2/submit/ | Not started |
| SimpleContacts | `simplecontacts.com` | https://www.simplecontacts.com/opt-out | Not started |
| Snoopstation | `snoopstation.com` | https://www.intelius.com/privacy-center | Not started |

### Session Z
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| SocialCatfish | `socialcatfish.com` | https://socialcatfish.com/opt-out/ | Not started |
| SouthCarolinaPublicRecords.com | `southcarolinapublicrecords.com` | https://www.truthfinder.com/opt-out/v2/submit/ | Not started |
| SpyDialer | `spydialer.com` | https://spydialer.com/Consumers/ | Not started |
| StateRecords.org | `staterecords.org` | https://staterecords.org/optout | Not started |
| Subsplash | `subsplash.com` | https://www.subsplash.com/legal/privacy | Not started |
| Sync.ME | `sync.me` | https://sync.me/unsubscribe/ | Not started |
| TeamUnify, LLC | `teamunify.com` | https://www.teamunify.com/team/mdest/page/safe-sport/photo-opt-out | Not started |
| Telephone Directories | `telephonedirectories.us` | https://www.telephonedirectories.us/Edit_Records | Not started |

### Session AA
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| TexasWarrantRoundup.org | `texaswarrantroundup.org` | https://texaswarrantroundup.org/InfoPayOpt-OutNew.pdf | Not started |
| The Bump | `thebump.com` | https://support.thebump.com/hc/en-us/articles/34980593049748-How-Can-I-Remove-My-Registry-From-The-Bump | Not started |
| The Dots Global Limited | `the-dots.com` | https://the-dots.com/users/sophia-woodleigh-200258 | Not started |
| ThePublicIndex | `thepublicindex.org` | https://thepublicindex.org/optout | Not started |
| Torre Labs, Inc. | `torre.ai` | https://torre.ai/en/terms | Not started |
| Trulia, LLC | `trulia.com` | https://support.trulia.com/hc/en-us/articles/221366928-How-do-I-remove-my-agent-s-listing-of-my-home | Not started |
| TruthRecord | `truthrecord.org` | https://www.truthrecord.org/api/helper/optOutLight/search | Not started |
| TruthViewer | `truthviewer.com` | https://www.truthviewer.com/api/helper/optOutLight/search | Not started |

### Session AB
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| uFind.name | `ufind.name` | https://ufind.name/opt-out | Not started |
| Unite 4Heritage | `unite4heritage.org` | https://www.unite4heritage.org/opt-out | Not started |
| Unmask | `unmask.com` | https://unmask.com/opt-out/ | Not started |
| USA Public Data Search | `usa-official.com` | https://usa-official.com/optout | Not started |
| USATrace | `usatrace.com` | https://www.usatrace.com/contact-us/ | Not started |
| User-Searcher | `user-searcher.com` | https://blog.user-searcher.com/policy | Not started |
| VerifyRecords | `verifyrecords.com` | https://members.verifyrecords.com/customer/opt-out | Not started |
| VoterRecords.com | `voterrecords.com` | https://voterrecords.com/faq | Not started |

### Session AC
| Site | Domain | Opt-out URL | Status |
|------|--------|-------------|--------|
| WebMD Health Corp. | `webmd.com` | https://www.webmd.com/about-webmd-policies/about-ccpa-do-not-sell | Not started |
| WeInform | `weinform.org` | https://www.weinform.org/api/helper/optOutLight/search | Not started |
| Wyty | `wyty.com` | https://www.wyty.com/remove/ | Not started |
| X-Ray Contact | `x-ray.contact` | https://x-ray.contact/blog/x-ray-contact-privacy-policy-update-account-deletion/ | Not started |
| Yellow Pages Directory Inc. | `yellowpagesdirectory.com` | https://www.yellowpagesdirectory.com/support.php | Not started |
| ZipRecruiter, Inc. | `ziprecruiter.com` | https://www.ziprecruiter.com/ccpa-opt-out | Not started |
| Zlookup | `zlookup.com` | https://www.zlookup.com/opt_out | Not started |
| ZoomInfo | `privacyrights.org` | https://privacyrequest.zoominfo.com/remove/verify | Not started |

## Lower-priority buckets (not sessionized tightly)

- **T3_CLONE:** InfoTracer/Spokeo/PeopleConnect mirrors — suppress parent first; only chase clones if they still rank.

- **T3_OTHER:** genealogy (Ancestry/FamilySearch/Archives), face-search (PimEyes/Facecheck), weak opt-out URLs.

- **T4_MARKETING:** adtech/marketing brokers (Acxiom, Epsilon, etc.) — after people-SERP work; universal opt-out only.

- **T4_B2B:** LexisNexis Risk, Checkr, GoodHire, Sterling, HireRight, ZoomInfo — employment/credit B2B; different workflow.

- **SKIP:** Searchbug, SpyFly (paid/charged removal) and paid reputation services — **never pay**.

## Next session list (site names only)

**Session A:** Whitepages, Spokeo, BeenVerified, PeopleConnect

