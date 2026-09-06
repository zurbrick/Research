# Notion Workspace Reorganization — Phase 3 Change Log and Link-Integrity Check

Date: 2026-09-05 · Executor: MAX · Every batch ran only after a printed dry run and Don's "go". Nothing was deleted. No content was replaced; every content write was an insert (top or bottom) or a title/icon property change.

## 1. Change log

| Batch | Action | Count | Result |
|---|---|---|---|
| 0 | Created 🗄️ Archive (3d2eb501d42c819e9b6de62a5fde4c92) with NOW / WORK / LIFE / KNOWLEDGE / PROJECTS sub-pages, and 🚩 TeamLogic (Migrating) (3d2eb501d42c81bcbb8fdf41d5df533b) under Command Center | 7 creates | Verified. Six titles corrected to the icon-outside-title convention; the rename of the TeamLogic holding page was denied, so its title keeps the emoji |
| 1 | LIFE / KNOWLEDGE / PROJECTS consolidation: Health & Fitness → W-005; Trading → W-054; Properties Hub, W-036, W-037 → W-025; People → W-001; W-041 → W-057; Household Management Hub, Travel, Side Hustle → Command Center; Records Retention, PiMan, W-008, Shared Context Packet, W-019, W-020, W-021, W-042, W-059 → W-063. Renames: Household Management Hub → 🚗 Vehicles & Household; blank-titled hub → 💼 Sales Development | 19 moves, 2 renames | Verified by fetching all six target parents and the four moved pages |
| 2 | Sixteen TeamLogic pages and databases → 🚩 TeamLogic (Migrating), including W-015 and W-016 extracted from the root Work Hub | 16 moves | Verified; a baseline Sales Pipeline row still resolves its Contact relation and its last-edited time is unchanged |
| 3 | Archived with callout: W-018, Rebuild Checklist, four HISTORICAL pages, W-002, W-003, W-006, W-007, Archive (Zye Cleanup), Zye's Brain, 08-27 review, Life Ops, Claude Memory Archive, Cruise, Life Scorecard. Moved without callout: Business Insights [SUPERSEDED] DB, Agent Audits DB | 17 callouts, 19 moves | Verified on all four Archive sub-pages; Zye's Brain read back with callout above its existing banners |
| 4 | Archived with callout: three RiverHouse blanks, Branford Ag (+ Glamping Domes), Lot 5, Lots 5/6/7, Side Businesses Operating Map, Quick Start Guide, TL Operating Map, Observability Sprint, TL Work Hub shell. Moved without callout: Docs, Daily Health Log, Strategy Library, Properties, Vendors & Contractors, Insurance Policies, Zemple Hub databases. Appended a Current State block to Properties Hub | 12 callouts, 19 moves, 1 append | Verified on three Archive sub-pages and Properties Hub |
| 5 | W-001: Corrections section appended (Orbit retired; People roster location; Memory Archive moved) | 1 append | Read back |
| 6 | Wiki Index: dated notes appended to 12 entry lines; W-065, W-066, W-067, W-068 added; W-011, W-027, W-028 marked RETIRED; reorganization log appended | 1 update_content (15 edits), 1 append | Read back |
| 7 | Metadata blocks inserted at the top of 34 live pages in the W-010 format | 34 inserts | Read back on W-063 and W-024 |
| 8 | Phase 4: 📐 Workspace Rules page created under Command Center; Wiki Index entry appended | 1 create, 1 append | See phase4 section below |

Totals: 8 creates, 73 moves, 2 renames, 29 archive callouts, 38 other inserts, 0 replacements, 0 deletions.

## 2. Link-integrity check

State legend: repointed · left intentionally (ID link survives or target archived with successor named) · unresolved (needs Don).

| Linking page | Target | Link type | State |
|---|---|---|---|
| Command Center nav | Life Ops, Life Scorecard, W-002, OpenClaw, Orbit, Hermes, Work Pipeline, Work Context, TeamLogic IT, SecureAI Docs (404), Client KB (404) | body link | unresolved: Don pastes the replacement nav text (Workspace Rules page, toggle at bottom) |
| Command Center bottom sections | Client KB, SecureAI Docs, Knowledge DBs | body link | unresolved: removed by the same paste |
| Wiki Index | every W-page | index entry | left intentionally: entries survive moves; archived and retired entries carry dated notes |
| Wiki Index | W-065 to W-068, Archive, TeamLogic holding page, Workspace Rules | index entry | repointed (new entries appended) |
| W-001 | Orbit W-007, W-003 | body link | left intentionally, with a Corrections line appended stating both are archived |
| W-001 | 👥 People | child page | repointed (People is now a child; Corrections line links it) |
| W-063 | W-019, W-020, W-021, Shared Context Packet, Canon Registry, HISTORICAL W-063 | body link | left intentionally: targets are now children or archived with successor |
| W-021 | W-005, W-004, W-001, W-054, Contacts, Inbox, Health Check-ins | body link | left intentionally: ID links; W-004 now under the TL holding page |
| W-020 ADR-003 | Hermes read-only claim | body text | unresolved: content edit for Don; noted in W-020 metadata block |
| W-050 | Reading & Resources (trashed) | body link | unresolved: proposed repoint to Business Insights, not approved yet |
| Life Scorecard (archived) | Properties Hub, Financial Accounts, Health Check-ins | body link | left intentionally |
| Lots 5/6/7 (archived) | Lot 5 (archived) | body link | left intentionally |
| Health Dashboard (archived with Zye's Brain) | W-005 | body link | left intentionally |
| Vehicles & Household | Properties, Vendors, Insurance DBs (archived); Equipment, Maintenance, Home Projects (404) | mention / body link | left intentionally: archived targets still resolve; the three 404s predate this work and are noted in the page's metadata block |
| Sales Pipeline ↔ Contacts | relation | relation property | left intentionally; verified on one row after Batch 2 |
| Financial Accounts ↔ Trading Ideas | relation | relation property | not touched |
| Canon Registry | 33 targets | url property | unresolved for Don: add 🗄️ Archived status; flip Zye's Brain, Work Hub, Brain Contacts, Life Scorecard, W-002 rows; fix Cold Outreach Page URL to 7746e9da82704554baeb09f7321cd5a0 |
| Scheduled task (monthly flood) | Flood & Crest page | task target | left intentionally: Don confirmed no task writes into the moved subtree; page ID unchanged |

## 3. Read this first, per domain

| Domain | Read first | Then |
|---|---|---|
| Everything | 🔗 Shared Context Packet, then 🧠 Memory Operating System W-063 | 📐 Workspace Rules for placement and hygiene; Canon Registry for source status |
| Personal / identity | 📋 Personal Context W-001 (Corrections section at the bottom is newest) | 👥 People (child of W-001) |
| Health | ❤️ Health Context W-005 canonical answers block | W-049 latest A1c, W-064 medication reconciliation worksheet; 💪 Health & Fitness W-024 for supplements DB and clinician prep; medication questions go to Dr. Patel |
| Money / trading | 💰 Money W-054 | 💼 Financial Accounts W-060, 💡 Trading Ideas W-061, 🧭 State Reconciliation (under Trading) for the current book |
| RiverHouse / DMZ | 🏡 RiverHouse W-025 | 🏡 Property Reference W-036 (Tier 3), 🛎️ Guest Guide W-037, 🏠 Properties Hub (Current State block pending Don), 🌊 Flood & Crest reference |
| Ventures | 🏕️ Side Businesses W-057 | 🛶 River Watch W-041, 🧪 Prompt Lab W-051, 🧪 Zemple Polsia W-052, 🚀 Side Hustle W-067 |
| Agent stack | 🧠 W-063 authority matrix | ⏰ Scheduled Task Registry W-042, 🖥️ PiMan W-065, ⚙️ Hermes W-008 (flagged stale), 🗄️ Records Retention W-068 |
| TeamLogic | 🚩 TeamLogic (Migrating) callout, then stop | 🚚 Migration Manifest W-044 on the Teams account |
| Knowledge | 📑 Wiki Index | Business Insights (live DB), Process Library, Technical Documentation, Lessons Learned |
| Anything old | 🗄️ Archive › area sub-page | Read the callout first; the successor is named there |

## 4. Phase 4

📐 Workspace Rules page created under Command Center (3d2eb501d42c819faa35f6810335876a). It covers placement per domain, the archive rule and callout format, the inbound-link search rule, the 90-day staleness procedure, the required metadata block, hub-summary rewriting on change, the never-delete rule, and the A1/A2 authority split, and it carries the Command Center replacement text in a toggle for Don to paste.

Recommended recurring task (recommendation only, not created): "Monthly staleness and link-integrity check", first Sunday of each month, folded into the existing Sunday lint in W-042. Steps are section 4 of the Rules page. Output is Inbox rows only; no moves without Don's approval.

## 5. Open for Don

1. Paste the Command Center replacement text (toggle at the bottom of the Workspace Rules page).
2. Canon Registry: add 🗄️ Archived status, flip the five archived rows, fix the Cold Outreach Page URL, add rows for Archive, TeamLogic (Migrating), and Workspace Rules if he wants them tracked.
3. Fill the Properties Hub Current State block and mark the Tracker RECONCILE notes.
4. Rewrite ⚙️ Hermes W-008.
5. Complete the W-004 review.
6. Decide whether Workspace Rules gets W-069.
7. Approve or decline the W-050 repoint (Reading & Resources → Business Insights).
8. Add the monthly staleness task to W-042 if he wants it.

## 6. Addendum — Command Center nav edit (Don's request, 2026-09-05 17:27 UTC)

Don asked MAX to apply item 1 of the open list directly. Applied with update_content (search-and-replace on exact section text), never replace_content:

- WORK, LIFE, KNOWLEDGE, PROJECTS nav sections rewritten; a 🗄️ Archive nav section added; the Sales Development line removed from the Shared section (it now lives under the TeamLogic holding page); the two 404 links (SecureAI Documentation, Client Knowledge Base) replaced by one unlinked pointer to the Teams account.
- The stale November 2025 bottom half was not deleted. It was moved unedited into a collapsed toggle under a SUPERSEDED 2026-09-05 callout, honoring the never-delete rule. Don can delete the toggle in the UI if he wants it gone.
- **Incident:** after the edit, the read-back showed the orange "Second Brain Reorg stopped at Phase 1" banner missing from the top of the page. No edit targeted it; the update tool appears to have dropped the first block on re-render. MAX re-inserted the banner with its exact original text and read the page back again. Lesson for the Rules page: after any update_content on a page whose first block is a callout, read back the first block explicitly.

## 7. Addendum — Canon Registry and Properties Hub (Don's request, 2026-09-05 17:35 UTC)

- **Canon Registry schema:** one option added to Status, 🗄️ Archived (gray). All eight existing options were re-declared with their original colors and kept their original option IDs. A 33-row Status snapshot was taken before the change and re-queried after: every row matched except the four intended flips.
- **Rows flipped to 🗄️ Archived:** 🧠 Zye's Brain (+ subtree), 🏨 TeamLogicIT - Work Hub, 📇 Brain Contacts DB, 🗄️ Archive (Zye Cleanup Mar 16). Page URL filled on the Work Hub and Brain Contacts rows, which had none. Life Scorecard and W-002 have no Registry rows, so there was nothing to flip.
- **Cold Outreach Log DB row:** Page URL corrected from the Sales Development hub page to the database itself (7746e9da82704554baeb09f7321cd5a0).
- **Properties Hub:** the three placeholder checkboxes were replaced (update_content, exact match) with the Current State that Don confirmed: the STR Portfolio Tracker is the source of truth; Lot 5 mobile home long-term rental live; Lot 6 three A-frames planned (one VISTA 3, two VISTA 1) replacing the dome plan; Lot 7 Guest House live, Octagon launching, Airstream and Basecamp 20X coming soon. Read back with the metadata block intact.
- **STR Portfolio Tracker:** the two Lot 7 rows carrying RECONCILE notes (Airstream, Basecamp 20X) had a dated RESOLVED line appended to their existing Notes text; no other property changed.

## 8. Addendum — 👥 People overwritten by Perplexity (2026-09-05 21:37 UTC)

Don shared a Perplexity-prepared "W-001 Gap Fill" document. On reading 👥 People, MAX found the page body already replaced with those blocks at 21:37 UTC. Don confirmed Perplexity made the write. Perplexity's authority row (Shared Context Packet, matrix v1.2) is append-to-Inbox only and forbids Tier 2 exposure; the pass also read Google Contacts. No Inbox delta had been logged.

Handling: content retained (never delete). MAX inserted a provenance callout and a metadata block (rag_tier 3, because the page carries two insurance policy numbers) at the top of 👥 People, appended a Corrections line to W-001, and posted an Inbox [CORRECTION] row naming the breach, the evidence, and the three content flags (possible Ryan Frye duplicate, unconfirmed Borasch line, Dawn Graff employer conflict). The Assessments block from the document, which carried a decision filter missing "Compliance", was not on the page. Recommendation to Don: restrict the Perplexity Notion integration to read-only or the Inbox database at the integration level; a matrix row cannot stop a tool that holds write scope.
- **Follow-up (Don's rulings, same evening):** Ryan on the vendor line is Ryan Frye (W-041); Matthew Borasch is not Don's advisor; Dawn Graff's employer is Velera (PSCU rebranded in 2024). Each line on 👥 People was amended by append, the provenance callout's open-flags sentence was updated, and the Inbox row was appended. Don chose to strike the two Progressive policy numbers himself; the page stays rag_tier 3 until he does.
- **Policy numbers:** Don authorized MAX to remove the two Progressive policy numbers from the Insurance line on 👥 People (one update_content edit; carrier and vehicle names kept; pointer to the Vehicles DB added). Page metadata dropped to rag_tier 2. Read back.
- **Matrix v1.3 (Don-approved 2026-09-05):** Perplexity's row widened from append-to-Inbox only to bounded A1 append on 👥 People and on pages Don names per task, Inbox delta required, no moves, archives, schema, renames, permissions, or Tier 3. Updated on both the Shared Context Packet (version stamp, summary table, change log) and W-063 (metadata, matrix heading, row). No other row changed.
- **Patty Zurbrick pointer on W-025:** Don declined; the fact stays on 👥 People only.
- **Matrix v1.4 (Don-approved 2026-09-05):** ChatGPT / Codex row added on W-063 and the Shared Context Packet. Don's ruling was "authority to audit, reconcile, and make changes"; MAX wrote it with the same A1/A2 gate that binds every editor (A1 alone; A2 with Don's explicit approval; never replace content; Inbox delta and read-back on every write; defers to Claude MAX, whom Don confirmed as top authority in Notion). Inbox Source uses the existing "ChatGPT/Codex" option. Bootstrap blocks delivered to Don for Grok Bot (Canon + Wags) and ChatGPT, each under 5,000 characters. Don was told MAX advised against an unbounded grant and can widen the row if he wants ChatGPT exempt from A2 approval.

## 9. Addendum — search-path hardening (Don's "go", 2026-09-05 23:00 UTC)

MAX tested the workspace two ways: as an agent following the bootstrap (packet, Registry, canonical page) and as an agent that searches first. The routed path returned current, non-contradictory answers. The search path still surfaced the old medication regimen on four live health pages, ranked archived Branford plan pages above the Properties Hub, and returned a July Technical Documentation row that still calls Orbit the project tracker. Don approved two fixes:

- **Canon Registry:** four rows added (👥 People, 🏠 Properties Hub + STR Portfolio Tracker, 📐 Workspace Rules, 🗄️ Archive with Status 🗄️ Archived and a Go-instead pointer). The W-025 row's Page URL repointed from the Side Businesses hub to the RiverHouse page.
- **Health pages:** a one-line dated note appended to the bottom of W-045 Annual Lab Panel, W-049 April lab page, W-064 Medication Reconciliation, and the endocrinology note under the Mounjaro Titration Log, each stating that medications named on the page are historical and routing to W-005 and Dr. Patel. No existing text changed. Don granted this as a narrow exception to the no-edit rule on Health Context children.

Still open for Don: the July Technical Documentation row naming Orbit (TeamLogic-scope row; flagged, not edited), bootstrap paste into ChatGPT, Grok Bot, and Perplexity, Perplexity integration scoping.
- **Retry note:** the first pass of the four health-page appends returned success for all four, but fresh reads showed only W-064 changed; W-045, W-049, and the endocrinology note were untouched with their original last-edited times. The three were re-issued and each read back with the note at the bottom and nothing else changed. Lesson recorded for the Workspace Rules: a write is not done until the read-back shows it, and a cached fetch (an "as of" date older than the write) is not a read-back.
- **Preference saved (Don, 2026-09-05):** "Ask questions one at a time, never batched" appended to W-001 Corrections and read back.
- **QuantConnect reconciliation:** the W-001 read-back revealed two ChatGPT/Codex writes made today without Inbox deltas: a trading-platform correction inserted in the Money & trading section, and a "ChatGPT operating preferences adopted" block under Corrections. Don confirmed the trading correction (TradeStation and Schwab; no QuantConnect). MAX appended a dated Corrections line to W-054 Money (which still listed QuantConnect plus IB) and to W-001, and posted an Inbox [CORRECTION] row marked Done that also notes the missing ChatGPT deltas for the Sunday lint.

## 10. Post-reorganization review and Batch A (2026-09-06)

Don closed PR #6 unmerged on 2026-09-06 and chose to keep this branch as the record; a pointer callout was added to the bottom of 📐 Workspace Rules naming the branch and the three files. He then asked for a read-only review of every folder and page under Command Center: does its location make sense, and should it be moved, updated, or archived.

**Review scope.** Command Center and every direct child, the five Archive sub-pages, 🚩 TeamLogic (Migrating), every hub (W-001, W-005, W-024, W-054, W-057, W-025, W-063 and its children), the venture pages, the Wiki Index, the Steward Log, the 2026-09-06 weekly review, and all 38 Canon Registry rows. Not read: every archived page body, every database row, and the full PiMan page (head only).

**Findings (structure holds; no rethink).** Move: W-065 PiMan from W-063 to Command Center (PROJECTS); the five weekly review pages into a new 🗓️ Weekly Reviews holder page; the 🔄 Momentum ETF Trades database and the RedTeam Stress Test page to Archive › LIFE. Archive candidates for Don: 🧪 Prompt Lab W-051 (parked 84 days), ✈️ Travel (empty), Zemple.ai W-052 and Side Hustle W-067 (decide by their 90-day dates), two untitled databases in the Archive to be titled. Update: W-001 body contradicts its own appended corrections (rebuild to v3.2); W-054 snapshot 102 days old; W-024 body is the 2025 template; 🚗 Vehicles & Household body describes archived and non-existent databases; W-063 title still says v1.0; W-058 still reads week 0; W-042 Registry row behind the live comparison; about twenty titles carry the emoji twice. Batches proposed: A small dated notes, B moves and archives, C renames, D rewrites.

**Batch A (Don's "go", 2026-09-06 16:46 UTC), nine writes, all read back:**
1. 💰 Money W-054: SUPERSEDED callout inserted above Recent Trades and Watch Items.
2. 🚗 Vehicles & Household: SUPERSEDED callout inserted above the template text.
3. 🧠 W-063: Corrections section appended (Friday sweep and health tracker are local tasks, not account routines).
4. 💰 Trading: metadata block and Current State callout inserted at the top.
5. 📑 Wiki Index: header count 64 → 65 (68 issued, 3 retired). The only in-place text edit.
6. 🏤 Command Center: surface-rule callout line updated; first-block banner confirmed intact.
7. Registry ⏰ Scheduled Task Registry row: Verified through 2026-09-06, Review due 2026-09-13, Notes appended.
8. Registry 📑 Wiki Index row: Notes appended with the current count.
9. Registry: new row 🚗 Vehicles DB (Tier 2, ⚠️ Partial, contents unverified).

Inbox [CORRECTION] row posted, Status Done. Nothing moved, renamed, replaced, or deleted.
