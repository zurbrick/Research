# Notion Workspace Audit — Phase 1 (read-only)

Workspace: Zurbrick · Audit date: 2026-09-05 · Auditor: MAX (Claude), acting as canonical editor per W-063 authority matrix (A1 scope only; no writes made).

Page URL convention: every ID below resolves at `https://www.notion.so/<id>`. Dates are Notion `page_last_edited_at`. Tier 2/3 specifics (health values, medication names, policy numbers, guest and client names, family data) are deliberately not reproduced here; the audit points at where they live.

## 0. Scope, method, and what could not be read

Method: fetched Command Center and walked every child; fetched each root-level private page and its subtree; listed private and shared pages and teamspaces; queried every reachable database via SQL; ran empty-query and keyword searches sorted by last-edited and created to catch orphans; read the Canon Registry (33 rows) and reconciled its statuses against what was found.

Not readable by this integration (reported, not guessed):

| Item | ID | Evidence |
|---|---|---|
| 🏢 Client Knowledge Base | 2a3eb501d42c812ba458c6379a9bac62 | 404 object_not_found; Registry 🔴 Inaccessible; belongs on Teams account |
| 🤖 SecureAI Documentation | 2a3eb501d42c81d8b3dce8a6413c0181 | 404; Registry 🔴 Inaccessible; belongs on Teams account |
| Equipment & Appliances DB | 4c7cd78f6ca84ad0aee63ddcf17b636b | 404; linked from Household Management Hub |
| Maintenance Log DB (Household) | 64f4269bdea845b9988bf8c40f9306c9 | 404; linked from Household Management Hub |
| Home Projects DB | 50f08fa161084dd0b5fc56c5c6912f3d | 404; linked from Household Management Hub |
| Personal Advisors DB | 2710f52f35ba4384a7a1e327f92fec8c | 404; linked from Life Ops › Operating Map |
| Teamspaces EmberLogicAI, rTrading, TLIT, Zemple | — | all in trash |
| 🎯 Projects DB, 📚 Reading & Resources | — | trashed 2026-08-10 per Registry; still referenced by W-050 |
| W-011 Karpathy Gist, W-027 Jesse Sethi, W-028 Mirza Baig | — | Wiki Index entries with no locatable page (search returns only W-010 and the two 1:1 templates) |
| 🖥️ PiMan audit body | 3bdeb501d42c81cd9d3fc2cbdccd6c46 | page is 68k chars; only head/tail read |
| Shared-with-me list | — | empty |

Rubric: CURRENT · STALE-BUT-TRUE · OUTDATED · DUPLICATE (survivor named) · EMPTY-JUNK. Confidence is given for every OUTDATED and DUPLICATE call; high only when the page itself carries the evidence.

## 1. Audit table by domain

### 1a. Governance / Agent OS (parent: Command Center unless noted)

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| 🏤 Command Center | 2a3eb501d42c81959e01d32d00f15642 | workspace root | 2026-09-05 | context/hub | CURRENT (partially stale body) | high | Top nav is current; bottom sections "SecureAI Practice", "Client Intelligence", "Core Databases", "Additional Knowledge Areas", "Usage Guidelines" still describe the Nov-2025 Work Hub / Knowledge Base structure |
| 📑 Wiki Index | 348eb501d42c81ae912ec5574f22a29f | Command Center | 2026-09-05 | wiki index | CURRENT | — | 64 W-IDs; three entries dangle (W-011, W-027, W-028) |
| 🗺️ Canon Registry (DB) | 1ddfe754f4364c2e8fd64b30a30843c3 | Command Center | 2026-09-05 | database | CURRENT | — | 33 rows; two reviews overdue (W-004 due 08-22, W-042 due 08-30); Cold Outreach row URL points to hub page not DB |
| 🧠 Memory Operating System W-063 | 3b8eb501d42c8100ae36ef4683c8a822 | Command Center | 2026-09-04 | context | CURRENT | — | Front door; authority matrix; four rules |
| 🔗 Shared Context Packet | 3d1eb501d42c81d5b53ff1f036dfb392 | Command Center | 2026-09-04 | context | CURRENT | — | Protocol v1.0, matrix v1.2 |
| 🧭 RAG Retrieval Map W-021 | 3aceb501d42c8169b711db26ec3780b3 | Command Center | 2026-09-05 | wiki | CURRENT | — | Routing rules |
| 🔐 RAG Access Classification W-019 | 325eb501d42c8173b944ebb445d52eb7 | Command Center | 2026-08-24 | wiki | CURRENT | — | Boundary contract dated 2026-08-23 |
| 📜 LLM Wiki Schema Constitution W-020 | 348eb501d42c81299a77ecfc0c5f9a98 | Command Center | 2026-08-24 | wiki | CURRENT (one stale ADR) | — | ADR-003 still says Hermes is read-only; contradicted by W-063 |
| 💡 LLM Wiki Pattern W-010 | 348eb501d42c8165862dc4280bc37c1c | Command Center | 2026-04-20 | wiki | STALE-BUT-TRUE | — | Reference; has frontmatter |
| 📋 Strategic Framework W-022 | 2a3eb501d42c81518e23dcac0fad6d6d | Command Center | 2025-11-06 | wiki | STALE-BUT-TRUE | — | Generic reference, no dated claims |
| AEBOP W-023 | 312eb501d42c81188645d323c60298a6 | Command Center | 2026-02-25 | wiki | STALE-BUT-TRUE | — | References Zye as operator; principles still valid |
| 🧭 Second Brain Reorg — Execution Plan W-018 | 34ceb501d42c8183a7c7cca046045f81 | Command Center | 2026-08-18 | project | OUTDATED (decision record) | high | Carries SUPERSEDED banner; Don stopped it 2026-08-18: "Phase 1 is the final state… Phases 2 and 3 will not be built" |
| 🧭 Notion Rebuild Execution Checklist | 32ceb501d42c817fbb1cd8bd2cf52bfd | Command Center | 2026-03-23 | project | OUTDATED | high | Describes March scaffolding already built or abandoned; no W-ID; superseded by W-018 then by the 08-18 stop |
| 🧹 Daily Notion Steward Log | 3c8eb501d42c81629b94c1f4d4e5c076 | Command Center | 2026-09-05 | log | CURRENT | — | Written daily by Hermes steward |
| ⏰ Scheduled Task Registry W-042 | 3aeeb501d42c8144aa6be8a26ed9ca16 | Command Center | 2026-08-26 | wiki | STALE-BUT-TRUE (review overdue) | — | Registry ⚠️ Needs Review since 08-30 |
| 🗂️ Capture System W-043 | 3aeeb501d42c8170b74ae3f90fa34933 | Command Center | 2026-08-02 | wiki | CURRENT | — | — |
| 🧪 Rule Audit W-059 | 3b6eb501d42c81d4bbdad68542fa6258 | Command Center | 2026-08-08 | note/decision | STALE-BUT-TRUE | — | Decision record |
| Weekly Review 2026-08-09 | 3b7eb501d42c811cbe8ac2ef100eabfa | Command Center | 2026-08-09 | note | STALE-BUT-TRUE | — | Historical |
| Weekly Review 2026-08-16 | 3beeb501d42c81da898bec6f5f0f1833 | Command Center | 2026-08-16 | note | STALE-BUT-TRUE | — | Historical |
| Weekly Review 2026-08-23 | 3c5eb501d42c812d8074f838ca5f515e | Command Center | 2026-08-23 | note | STALE-BUT-TRUE | — | Historical |
| 📆 Weekly Review 2026-08-27 | 3c9eb501d42c81aaa9bbf96b2f1e2cea | Command Center | 2026-08-27 | template | EMPTY-JUNK | high | Canon-generated template, never filled; 08-30 review diffs against 08-23 and ignores it |
| Weekly Review 2026-08-30 | 3cceb501d42c8139a63cc718d47d7cfe | Command Center | 2026-08-30 | note | CURRENT | — | Latest review |
| 🗄️ HISTORICAL W-019 / W-020 / W-021 / W-063 (4 pages) | 3c6eb501d42c81a0889cf8116384efe1 · 3c6eb501d42c812d846be8f24efdf099 · 3c6eb501d42c81ef9e8bfb8f080b76eb · 3c7eb501d42c81809dbbc751653cab39 | Command Center | 2026-08-24/25 | note | STALE-BUT-TRUE (archive material) | — | Self-labelled historical snapshots; sit at same level as their live counterparts; still carry the W-IDs in their titles |
| 🚀 Active Projects & Priorities W-002 | 347eb501d42c81f3b3dedf45eb3d17bf | Command Center | 2026-08-02 | context | OUTDATED | high | Own banner says stale 105 days; lists P-303 complete while sprint page says in progress |
| 🗄️ Records Retention Rule | 3b7eb501d42c81939c0cc80d3099a255 | W-002 | 2026-08-09 | wiki (rule) | CURRENT (misparented) | — | Durable rule filed under a stale project page |
| 🖥️ PiMan audit | 3bdeb501d42c81cd9d3fc2cbdccd6c46 | W-002 | 2026-08-16 | project | CURRENT (misparented) | — | Live agent-stack project; no W-ID; body not fully read |
| 🏗️ Agent Architecture ZyeOS W-003 | 347eb501d42c81268fc5eec41440bdd9 | Command Center | 2026-07-18 | wiki | OUTDATED | high | DEPRECATED banner on page |
| ⚙️ OpenClaw W-006 | 348eb501d42c81cfbf68f80d6bcf8625 | Command Center | 2026-04-20 | wiki | OUTDATED | high | DEPRECATED banner on page |
| ⚙️ Orbit W-007 | 348eb501d42c8137a6cac584a426e7a3 | Command Center | 2026-04-20 | wiki | OUTDATED | medium | Describes ~/.openclaw paths and an OpenClaw connection; OpenClaw is retired, yet W-001 still lists Orbit as a live tool. Inference, not on-page evidence |
| ⚙️ Hermes W-008 | 348eb501d42c81878887f4179263d88a | Command Center | 2026-04-20 | wiki | OUTDATED | medium-high | Says v0.8.0 and "read-only wiki consumer (no Notion MCP)"; Hermes now writes Inbox and steward log daily per W-063 and the log itself |
| Agent Audits (DB) | f5076ce74fdb46db9ac8e60ff181eba5 | Command Center | 2026-04 | database | STALE-BUT-TRUE | — | 9 April-2026 audit rows for OpenClaw/Hermes; history |
| 🗄️ Archive (Zye Cleanup Mar 16) | 325eb501d42c8185b415c9fb7b29b8a3 | Command Center | 2026-03 | container | EMPTY-JUNK | high | Empty shell; Registry ⛔ Poison |
| 🧠 Zye's Brain | 312eb501d42c819c880cd1f51b81d1a7 | Command Center | 2026-08-18 | context (legacy) | OUTDATED | high | Registry ⛔ Poison; Feb-2026 health snapshot with superseded values |
| ├ Daily Briefing Feb 25 | 312eb501d42c813389e7f04d9d3a4d0f | Zye's Brain | 2026-02 | note | OUTDATED | high | Dated daily brief |
| ├ Agent Guardrails | 312eb501d42c81d2add1fea3c1b7d739 | Zye's Brain | 2026-02 | wiki | OUTDATED | high | Zye-era; superseded by W-063 rules |
| ├ Anthropic Blog | 312eb501d42c813391f4d2b9885255db | Zye's Brain | 2026-02 | note | STALE-BUT-TRUE | — | Reference clip |
| ├ 📦 Archive › Zye — AI Chief of Staff | 315eb501d42c81e78ed7f2f371e82ce7 › 2a3eb501d42c806f961bd87df3c7bc02 | Zye's Brain | 2025-11 | note | OUTDATED | high | Zye retired (W-003 deprecated) |
| ├ 🎯 Projects › 🗂️ Migrate Off Notion | 315eb501d42c81c1906ede23316af73e › 338eb501d42c81bf8041d0679b5c5e27 | Zye's Brain | 2026-04-24 | project | OUTDATED | high | P-300 marked DEPRECATED 2026-04-24 on page |
| ├ 📚 Resources › Buffett prompts | 315eb501d42c813ca179d4d11e2575da › 312eb501d42c81dea4e2d7d6c3384ec0 | Zye's Brain | 2026-02 | note | STALE-BUT-TRUE | — | Reference |
| ├ 🤖 Agent Architecture | 315eb501d42c81c78c5ccb46a64b2f1e | Zye's Brain | 2026-02 | wiki | OUTDATED | high | Superseded by W-003 which is itself deprecated |
| ├ 👥 People | 315eb501d42c81ebb5fbec1f67e5a416 | Zye's Brain | 2026-02 | context | STALE-BUT-TRUE (Tier 2) | — | Only personal roster in the workspace (family and friends); W-001 says this roster is missing |
| ├ 💪 Health Dashboard | 315eb501d42c81d4b98ae2bab1c248b1 | Zye's Brain | 2026-02 | context | OUTDATED | high | Feb-2026 values superseded by W-005/W-049 |
| ├ Situational Awareness | 31aeb501d42c810cb7e4eaab98d6e27b | Zye's Brain | 2026-03 | note | OUTDATED | high | Dated situational snapshot |
| ├ 📇 Contacts (Deprecated) DB | 32beb501d42c815cb921d56a37f45e4b | Zye's Brain | 2026-03 | database | EMPTY-JUNK | high | 0 rows; Registry ⛔ Poison; title says Deprecated |
| ├ Canonical Contacts Decision | 32ceb501d42c81b68e2be6d504fb8043 | Zye's Brain | 2026-03 | note/decision | STALE-BUT-TRUE | — | Decision record naming the live Contacts DB |
| ├ 🏠 Properties Hub | 315eb501d42c81349badce4bc49a7de2 | Zye's Brain | 2026-05-04 | hub | STALE-BUT-TRUE (Tier 2) | — | Live property content inside the poison subtree; booking callouts name guests |

### 1b. Personal / Identity

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| 📋 Don Zurbrick — Personal Context W-001 | 347eb501d42c81af93f6d19a87a51d89 | Command Center | 2026-08-16 | context | CURRENT | — | Still lists Orbit as live and says the people roster is missing |
| 🗄️ Claude Memory Archive | 3baeb501d42c8172be3cce61aa89a483 | W-001 | 2026-08-12 | note (legacy export) | STALE (Tier 2) | — | Legacy export carrying a superseded medication line; archive candidate |
| 🏆 Life Scorecard W-056 | 325eb501d42c813bb5cbed907e9a96e9 | Command Center | 2026-04-04 | context | OUTDATED | high | Last refresh April; refresh cron dead; lists guest names |
| 📆 Life Ops | 32ceb501d42c8132a226cc81a00969b3 | Command Center | 2026-03-23 | container | EMPTY-JUNK | high | Four blank children (Health, Household, Travel, Personal Finance: 32ceb501d42c816fa324e9557e1e37a1 · 32ceb501d42c81e293efed0ff1f591dc · 32ceb501d42c813a9d68d7e5f9f0d471 · 32ceb501d42c81a196b1c3327411fc81) plus Operating Map 32ceb501d42c81b59fb7f8953873a12e linking a 404 DB |

### 1c. Health (untouchable content: Health Context, Supplements & Medications, Health Check-in rows)

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| ❤️ Health Context W-005 | 347eb501d42c8190ad2fe6c45b848087 | Command Center | 2026-08-10 | context | CURRENT (banner) / frozen tables | — | Registry ⚠️ Partial; meds and conditions tables frozen 2026-04-19 marked DO NOT CITE; canonical answers current |
| ├ Lab result W-049 | 34aeb501d42c810eb26de80ade87c0ae | W-005 | 2026-04-22 | note | CURRENT (latest value) | — | Newest lab value on file |
| ├ D-Dimer follow-up W-047 | 396eb501d42c81e89641c197868e099d | W-005 | 2026-07-07 | note | STALE-BUT-TRUE | — | — |
| ├ MRI W-048 | 3a4eb501d42c810f9a74c2788195f4a5 | W-005 | 2026-08-05 | note | CURRENT | — | — |
| ├ 🗄️ ARCHIVED Core-8 W-046 | 3aeeb501d42c81a9b64ff4de8ee632ce | W-005 | 2026-08 | note | STALE-BUT-TRUE | — | Already self-archived in place |
| ├ 🩸 Annual Lab Panel W-045 | 3aeeb501d42c81a38d54ec45ffff1a53 | W-005 | 2026-08 | wiki | CURRENT (one stale line) | — | Repeats the superseded medication line |
| ├ 💊 Medication Reconciliation W-064 | 3b8eb501d42c811598e0e74bdecabadf | W-005 | 2026-08-11 | note | CURRENT | — | — |
| 💪 Health & Fitness W-024 | 2a3eb501d42c81738076c88d695742b3 | workspace root | 2026-08-23 | hub | CURRENT (thin) | — | Second health hub at root, separate from W-005 |
| ├ 💊 Supplements & Medications DB | 797f026229c04fe5aa115a394bd1d2d0 | Health & Fitness | 2026-08-23 | database | CURRENT (untouchable) | — | 22 rows, 20 Pending Review |
| ├ 💉 Mounjaro Titration Log (DB row) + 2 children | 348eb501d42c810988e7e950969904a1 › 34aeb501d42c810cad13f352ee4823bb · 34aeb501d42c8136bb61cb371570bd12 | Supplements DB | 2026-08-23 | note misfiled as row | STALE-BUT-TRUE (misfiled) | — | Blank properties; narrative note living as a DB row; untouchable content, parent placement only for Don |
| ├ Docs DB | 1cfeb501d42c80f19780cc449583b9b3 | Health & Fitness | 2026 | database | EMPTY-JUNK | high | 0 rows; named as orphan in a Feb Inbox item |
| ├ 🩺 Clinician Prep W-062 | 383eb501d42c81ae9230e033df548572 | Health & Fitness | 2026-09-01 | wiki | CURRENT (one stale line in §5) | — | §5 repeats the superseded medication line |
| ├ 🩹 Daily Health Log (Med Ramp) DB | 01ff71c479e540b292fe5e37655c0383 | Health & Fitness | 2026-06-19 | database | EMPTY-JUNK | medium | 1 row; duplicates Health Check-ins purpose; no later use |
| ├ 🥦 F. prausnitzii list | 38deb501d42c81b2875deafeb495e102 | Health & Fitness | 2026-06-28 | note | STALE-BUT-TRUE | — | — |
| ├ 🩺 Cardiology Prep | 3b8eb501d42c81cbbdfef4f035c5f645 | Health & Fitness | 2026-08-11 | note | CURRENT | — | No W-ID |
| 🩺 Health Check-ins DB | 2b201f6381ba4cb6a9c9145dbfa2da52 | Command Center | 2026-09-04 | database | CURRENT (untouchable rows) | — | 46 rows; not linked from Command Center nav; Registry 🕳️ Gap |

### 1d. Trading / Money

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| 💰 Money W-054 | 312eb501d42c8107b735d6b60385b76c | Command Center | 2026-05-27 | context | CURRENT (partial staleness) | — | Registry ✅; still carries a Zye-era "7AM weekday review" line and a Feb-2026 "Recent Trades" section |
| ├ 💼 Financial Accounts DB W-060 | aabc29f1f8ac4bad9d517ff57dcb9592 | Money | 2026 | database | CURRENT | — | 6 rows; TradeStation row 36deb501d42c814f9e92edafa31f7b76 body and properties disagree on holding |
| ├ 💡 Trading Ideas & Theses DB W-061 | aefb823e39004e9aa48d855d6a8acef8 | Money | 2026 | database | CURRENT | — | 10 rows incl. Sector Momentum Rotation (Archived) 36deb501d42c813b82ddf0f3ade251cf and Roth ladder W-053 36deb501d42c8197876ef985efeceefa |
| 💰 Household Budget W-058 | 3b1eb501d42c8116a897e799e049f1b7 | Command Center | 2026-08-03 | context | CURRENT | — | — |
| 💰 Trading (root page) | 2a3eb501d42c80b4939fc9b9f7a50477 | workspace root | 2025-11-06 | container | STALE-BUT-TRUE | — | Near-empty container; children below |
| ├ Strategy Library DB | 1d9eb501d42c806eb534c0df0e8cfbf2 | Trading | 2025 | database | EMPTY-JUNK | high | 0 rows |
| ├ 🔄 Momentum ETF Trades DB | 9fe1ed205d0d46cf985f4c03d61375af | Trading | 2026 | database | STALE-BUT-TRUE (untouchable rows) | — | 3 rows, all Closed; this is the Trade Journal analogue |
| ├ 🧪 Contrarian AI-Backbone v2 | 381eb501d42c81409975e3a7c6e0cfbd | Trading | 2026-06-16 | note (research) | STALE-BUT-TRUE | — | — |
| ├ 🔴 RedTeam Stress Test | 390eb501d42c813bab4efa63d57a4b97 | Trading | 2026-07-01 | note | STALE-BUT-TRUE | — | — |
| ├ 🧭 State Reconciliation | 3c5eb501d42c81aebb44de51e69cf48c | Trading | 2026-08-23 | note | CURRENT | — | Newest statement of book state |

### 1e. DMZ Adventures / RiverHouse / Property (content split across three parents)

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| 🏕️ Side Businesses W-057 | 32ceb501d42c81cba54bef43ed424df1 | Command Center | 2026-03-23 | hub | STALE-BUT-TRUE (thin) | — | Container |
| ├ Operating Map | 32ceb501d42c8183a6ccd836a97cdec4 | Side Businesses | 2026-03 | note | OUTDATED | high | Links only to 404 databases |
| ├ 🛶 DMZ Adventures W-026 | 32ceb501d42c81b69356d6ff63e2ce2e | Side Businesses | 2026-03 | hub | EMPTY-JUNK (container) | high | Blank body; only child is RiverHouse |
| ├ 🏡 RiverHouse W-025 | 32ceb501d42c81b18749c58415d0a9a4 | DMZ Adventures | 2026-03 | hub | STALE-BUT-TRUE (thin) | — | Registry ⚠️ Partial |
| ├ Operations · Guests & Hosting · Compliance & Tax | 32ceb501d42c81f9a76cee912836dbee · 32ceb501d42c81d1bf17ff543ed2cd92 · 32ceb501d42c81c28e54fd0d03e5c1d4 | RiverHouse | 2026-03 | note | EMPTY-JUNK | high | Blank scaffolding |
| ├ Financials | 32ceb501d42c8155bcfbd48e0881de9c | RiverHouse | 2026-09-05 | note | STALE-BUT-TRUE | — | Verification-status note only |
| ├ Vendors & Maintenance › 🔧 Maintenance Log W-039 | 32ceb501d42c81a99f4ee49efe822368 › 38deb501d42c8187be24e04e60637902 | RiverHouse | 2026-06-28 | wiki | STALE-BUT-TRUE | — | — |
| ├ Vendors & Maintenance › 🚜 Equipment & Tools W-040 | 391eb501d42c8100b907ef1d1cbf24db | RiverHouse | 2026-07-02 | wiki | STALE-BUT-TRUE | — | — |
| 🏠 Household Management Hub | 2abeb501d42c8103a723df88843feeac | workspace root | 2026-03-23 | hub | STALE-BUT-TRUE (boilerplate) | — | Template text; three linked DBs 404; Vehicles DB live |
| ├ 🏡 RiverHouse — Property Reference W-036 | 3aeeb501d42c8102aa93da6a3af3f4c9 | Household Hub | 2026-08-15 | wiki | CURRENT (Tier 2/3 content) | — | Contains an insurance policy number |
| ├ 🔨 Punch List W-038 | 3b0eb501d42c819cb81fef92a7310f6a | W-036 | 2026-08-02 | wiki | CURRENT | — | — |
| ├ 🛎️ Guest Guide W-037 | 3aeeb501d42c81e58b2ae9b6c2396f35 | Household Hub | 2026-07-31 | wiki | CURRENT | — | — |
| ├ Properties DB · Vendors & Contractors DB · Insurance Policies DB | 24b07faee5014df8afcc9283f390ae48 · 1f922235893544bf8ab75fcddbc36cbf · 793484afd61b43109d716d6f3bdd6521 | Household Hub | 2026 | database | EMPTY-JUNK | high | 0 rows each |
| ├ 🚗 Vehicles DB | 46025ded3376426f8dd8f99616d0d3fc | Household Hub | 2026-09-05 | database | CURRENT | — | 18 rows populated 09-02 to 09-05 |
| 🛶 River Watch Property Stewardship W-041 | 390eb501d42c819ea67cdcb5228f42c0 | workspace root | 2026-07-01 | project | STALE-BUT-TRUE | — | Terms pending |
| 🏠 Properties Hub (in Zye's Brain) | 315eb501d42c81349badce4bc49a7de2 | Zye's Brain | 2026-05-04 | hub | STALE-BUT-TRUE (Tier 2) | — | See 1a; children below |
| ├ 🏕️ Santa Fe River Base Camp — Lot 5 | 34ceb501d42c81ed81efc362c2bf73f9 | Properties Hub | 2026-04-24 | project | OUTDATED (partially) | medium | Describes a 12-unit plan on Lot 5; the newer Tracker (06-25) records a different unit type and lot; Don has not reconciled |
| ├ 📦 [ARCHIVED] Branford Lot 5/6/7 Ag | 34feb501d42c812988a2f268ab42ff41 | Properties Hub | 2026-04-27 | project | OUTDATED (self-archived) | high | Title says ARCHIVED |
| ├ Glamping Domes (5) | 38aeb501d42c81df8c02e49ca0a8aa11 | Archived Ag page | 2026 | note | EMPTY-JUNK | high | Blank |
| ├ 🏡 Branford Lots 5/6/7 — STR Portfolio Build | 34feb501d42c81ff93b8e32ec3e4b63d | Properties Hub | 2026-04-27 | project | OUTDATED (partially) | medium | Self-declared "single source of truth" but the Tracker (06-25) changes unit type; unreconciled |
| ├ 🌊 Santa Fe River Flood & Crest Reference | 37feb501d42c8178a1bbd6e96ae7bfdf | Properties Hub | 2026-09-02 | wiki | CURRENT | — | Fed by a live monthly task; sits inside the poison subtree |
| ├ STR Portfolio Tracker DB | 756f9c26bdf64cf78bd63e3b64fce6d0 | Properties Hub | 2026-06-25 | database | CURRENT (newest) | — | 8 rows; notes say RECONCILE |

### 1f. TeamLogic IT / SecureAI (pending migration to Teams account; flagged, not enriched)

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| 🏢 Work Context W-004 | 347eb501d42c819cb5e1ec5ca30e4d92 | Command Center | 2026-08-15 | context | STALE-BUT-TRUE (review overdue) | — | Title carries [NEEDS REVIEW]; Registry review due 08-22 |
| ├ 1:1 templates (2) | 34feb501d42c81699bcef31e20ee9e45 · 34feb501d42c81faacc6ee78aa457618 | W-004 | 2026-04-27 | template | STALE-BUT-TRUE | — | Wiki Index W-027/W-028 point here though they are templates, not person pages |
| 🏢 TeamLogic IT W-009 | 348eb501d42c816d9a6af23db12d4b73 | Command Center | 2026-04-20 | wiki | STALE-BUT-TRUE | — | Has frontmatter |
| 🚀 150-Day Plan W-013 | 37feb501d42c81f9b3fdea402750f875 | Command Center | 2026 | project | STALE-BUT-TRUE | — | — |
| 🖥️ Private AI Hosting W-014 | 3a5eb501d42c81c6b0aac0d731c32299 | Command Center | 2026-07-22 | wiki | STALE-BUT-TRUE | — | — |
| ⚙️ Hatz W-029 · Autotask W-030 · Rewst W-031 | 3adeb501d42c814394d1e80f273f52d1 · 3adeb501d42c8109a283fa999dc25437 · 3adeb501d42c81d2a5dbc75ff5823078 | Command Center | 2026-07-30 | wiki | STALE-BUT-TRUE | — | Tool pages |
| ⚙️ HubSpot W-032 | 3adeb501d42c8184b962f5f6dc8c14f8 | Command Center | 2026-07-30 | wiki | CURRENT (decision) | — | NOT IN USE decision 2026-07-30 |
| 🏢 Client account page W-033 | 3adeb501d42c8113af8dca74c6f80951 | Command Center | 2026-08-07 | wiki | STALE-BUT-TRUE (TL client data, flag) | — | Contains client call logs with named attendees; belongs on Teams |
| 👤 Person pages W-034, W-035 | 3adeb501d42c81… (see Wiki Index) | Command Center | 2026-07-30 | wiki | STALE-BUT-TRUE (TL employee data, flag) | — | Employee records; belong on Teams |
| 🚚 Migration Manifest W-044 | 3adeb501d42c81228c5fdaa1214afa21 | Command Center | 2026-07-30 | project | CURRENT | — | The migration plan itself |
| 💼 Work Pipeline | 325eb501d42c811797def5d315a757b0 | Command Center | 2026-03-31 | context | OUTDATED (untouchable) | high | Dead cron; names Hatz tenants; content untouchable per constraints |
| (untitled) Sales Development hub W-012 | 365eb501d42c810a8319f53e669f932e | Command Center | 2026 | hub | STALE-BUT-TRUE (title blank) | — | Registry Cold Outreach row points here by mistake |
| ├ 💼 Sales Pipeline DB | ee056126ff8341a4a179dd8ee29ccd40 | W-012 | 2026 | database | STALE-BUT-TRUE (🚚 Migrating; PII) | — | 57 rows; relation to Contacts |
| ├ 📨 Cold Outreach Log DB | 7746e9da82704554baeb09f7321cd5a0 | W-012 | 2026 | database | STALE-BUT-TRUE (🚚 Migrating) | — | 9 rows |
| ├ 📊 Sales Development Dashboard | 365eb501d42c81558336ed7039fbbd55 | W-012 | 2026-08-10 | context | STALE-BUT-TRUE (PII) | — | Names prospects; ICP wording differs from W-004/W-009 |
| 🏨 TeamLogicIT — Work Hub | 2a3eb501d42c81d1b3edf32cd4b9c176 | workspace root | 2026-03-23 | hub | OUTDATED | high | Registry ⛔ Poison; competes with Command Center |
| ├ 📖 Quick Start Guide | 2a3eb501d42c8171b9d1ec05815b3793 | Work Hub | 2025-11-06 | wiki | OUTDATED | high | Dated Nov 2025; references pages that no longer exist |
| ├ 🐻 TechBear Brand Guide W-015 | 2a3eb501d42c81cd9809d12dc987537a | Work Hub | 2025-11-06 | wiki | STALE-BUT-TRUE | — | — |
| ├ ✍️ Content Lab W-016 | 312eb501d42c81b6be38fabf61ec6eeb | Work Hub | 2026-05-04 | hub | STALE-BUT-TRUE | — | ~20 LinkedIn draft children (07-23 to 08-13); 📊 LinkedIn Draft Log DB e601e9ef2f5d46a59d2fb7bee1d28958 (15 rows); 🛠️ Runbook W-017 356eb501d42c813e9b0de9b8a331d9a5; ⚙️ Task Spec v2.0 3adeb501d42c81e78329ecc29d004da6; still mentions the cancelled HubSpot migration |
| ├ Operating Map | 32ceb501d42c81deaa8ee2668104168e | Work Hub | 2026-03 | note | OUTDATED | high | March-2026 OpenClaw cron statistics |
| ├ 🔭 Observability Sprint | 340eb501d42c81b1b179e3b7f788689d | Work Hub | 2026-04-12 | project | OUTDATED | high | Still "In Progress" with unchecked phases; W-002 records P-303 complete |

### 1g. Ventures

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| 🚀 Side Hustle — Interview Pitch Sites | 384eb501d42c8161b0d9da9648a84fbe | workspace root | 2026-06-19 | project | STALE-BUT-TRUE | — | Not in Wiki Index; no W-ID |
| 🧪 Prompt Lab W-051 | 37feb501d42c81cfbb9bd8b440c076c3 | Command Center | 2026-06-14 | project | STALE-BUT-TRUE | — | Parked |
| 🧪 Zemple.ai Polsia W-052 | 3aaeb501d42c8168aaffe832fbb5be30 | Command Center | 2026-07-27 | project | STALE-BUT-TRUE | — | Own metadata style |
| Zemple Hub DB | 1d9eb501d42c80afbef2d31c3014720a | workspace root | 2025-04-18 | database | EMPTY-JUNK | high | 0 rows |

### 1h. Knowledge databases and Contacts

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| 📊 Business Insights (live) | f5b827cf3e614e79800230794e2d8918 | Command Center | 2026 | database | CURRENT | — | 8 rows; one TL-scope row |
| 📊 Business Insights Database [SUPERSEDED] | 7f1bedc856a947889fc51f9913a25fe9 | Command Center | 2026 | database | DUPLICATE → survivor f5b827cf… | high | is_archived true; title says SUPERSEDED; 5 rows |
| Process Library | 5e891a539953433a961f409f60ed2037 | Command Center | 2026 | database | STALE-BUT-TRUE | — | 6 rows; W-050 Notion Knowledge Capture 3aceb501d42c8143b9f5f8d5674915ba routes to trashed Reading & Resources |
| Technical Documentation | 20a68cce4a144ad59a7979854da5fa99 | Command Center | 2026 | database | STALE-BUT-TRUE | — | 8 rows |
| Lessons Learned | d8f93946f63d4b65996aa8c67f48d823 | Command Center | 2026 | database | STALE-BUT-TRUE | — | 23 rows |
| 📇 Contacts DB | 32beb501d42c81cfa5a5e3c562c39add | Command Center | 2026 | database | CURRENT (untouchable) | — | 41 rows; relation to Sales Pipeline; Registry ⚠️ Partial |
| 📥 Inbox DB | 312eb501d42c8148b14bccb54f979c37 | Command Center | 2026-09 | database | CURRENT | — | 44 rows: 7 New, 3 Processing, 22 Done, 12 Archived |

### 1i. Travel, root-level and system items

| Title | ID | Parent | Edited | Type | Status | Conf | Reasoning |
|---|---|---|---|---|---|---|---|
| ✈️ Travel | 2a3eb501d42c815e8525ced423e5ca78 | workspace root | 2026-04-27 | hub | STALE-BUT-TRUE | — | — |
| 🛳️ Mediterranean Cruise + 9 day pages + 🧳 Travel Agent Review | 2a4eb501d42c81e88cf6e41c6a206f03 · 347eb501d42c81ccaa0ee0011855a247 | Travel | 2026-06-01 | project | OUTDATED (completed; Tier 3 booking data) | high | Trip completed; page holds booking numbers and access keys |
| Instructions (morning-brief agent) | 3a1eb501d42c824bbd0b012274cb7044 | workspace root (not in private list) | 2026-03-22 | template/instructions | CURRENT | — | Drives the Notion AI morning brief |
| 🌻 Morning briefs hub DB | d1feb501d42c83ae802081efab4fbb22 | Instructions | 2026-09-04 | database | CURRENT | — | 115 daily rows; open Inbox [DECISION] on its navigation; contains mail links |
| AI meeting notes | 259eb501d42c828c9e228195c36aa41c | workspace root | 2025-11-06 | system collection | CURRENT (system) | — | Notion-managed meeting-notes collection, not a user database; leave |

## 2. Contradictions (same subject, different claims)

| # | Subject | Page A (claim) | Page B (claim) | Current | Evidence |
|---|---|---|---|---|---|
| 1 | Medication regimen | W-005 frozen meds table 347eb501d42c8190ad2fe6c45b848087; W-045 3aeeb501d42c81a38d54ec45ffff1a53; W-062 §5 383eb501d42c81ae9230e033df548572; Claude Memory Archive 3baeb501d42c8172be3cce61aa89a483; Mounjaro log 348eb501d42c810988e7e950969904a1 (older regimen line) | W-005 canonical answers + W-063 3b8eb501d42c8100ae36ef4683c8a822 (no list exists; delivery and TRT form changed 2026-02-24) | W-005 banner; route to Dr. Patel | W-005 banner dated 2026-04-19 marks its own tables DO NOT CITE; W-063 rule "never reconstruct med list" |
| 2 | Latest A1c | Zye's Brain 312eb501d42c819c880cd1f51b81d1a7 and Health Dashboard 315eb501d42c81d4b98ae2bab1c248b1 (Feb-2026 value) | W-005 / W-049 34aeb501d42c810eb26de80ade87c0ae (April value) | W-049 | Later dated lab page |
| 3 | Momentum ETF book | TradeStation row 36deb501d42c814f9e92edafa31f7b76 body and Money "Recent Trades" 312eb501d42c8107b735d6b60385b76c (book live) | Sector Momentum Rotation (Archived) 36deb501d42c813b82ddf0f3ade251cf and State Reconciliation 3c5eb501d42c81aebb44de51e69cf48c (archived 2026-05-27) | Archived | Reconciliation dated 08-23; row's own properties say the newer holding |
| 4 | Branford build plan | Base Camp Lot 5 34ceb501d42c81ed81efc362c2bf73f9 (12 units, Lot 5) vs Lots 5/6/7 Build 34feb501d42c81ff93b8e32ec3e4b63d (5 domes, Lot 6) vs STR Portfolio Tracker 756f9c26bdf64cf78bd63e3b64fce6d0 (A-frames replace domes) | — | Tracker is newest (06-25) but unreconciled | Tracker notes say RECONCILE; flag for Don |
| 5 | Hermes capability | W-008 348eb501d42c81878887f4179263d88a and W-020 ADR-003 (read-only, no Notion MCP) | W-063 matrix and Steward Log 3c8eb501d42c81629b94c1f4d4e5c076 (writes daily) | W-063 | Log entries exist |
| 6 | Orbit status | W-007 348eb501d42c8137a6cac584a426e7a3 (connected to OpenClaw) | W-001 347eb501d42c81af93f6d19a87a51d89 (Orbit live) with W-006 (OpenClaw deprecated) | Unclear | No page states Orbit's current state; flag for Don |
| 7 | HubSpot migration | Sales Dev hub 365eb501d42c810a8319f53e669f932e and Content Lab 312eb501d42c81b6be38fabf61ec6eeb (migration July 2026) | W-032 3adeb501d42c8184b962f5f6dc8c14f8 and W-001 (cancelled 2026-07-30) | Cancelled | Decision dated on W-032 |
| 8 | LinkedIn follower count | W-004 / W-009 (older figure) | Content Lab / Runbook 356eb501d42c813e9b0de9b8a331d9a5 (05-04 figure) | Runbook | Later date; cosmetic |
| 9 | Project P-303 Observability | W-002 347eb501d42c81f3b3dedf45eb3d17bf (COMPLETE) | Observability Sprint 340eb501d42c81b1b179e3b7f788689d (In Progress) | W-002 likely | W-002 is later dated but stale itself; flag |
| 10 | Personal people roster | W-001 (roster missing) | Zye's Brain › People 315eb501d42c81ebb5fbec1f67e5a416 (roster exists, Tier 2) | Neither fully | Roster exists but sits in a poison subtree |
| 11 | Workspace structure | Command Center bottom sections (Work Hub / Knowledge Base, Nov 2025) | Command Center top nav and W-018 stop decision (five areas) | Top nav | Don's 08-18 decision |
| 12 | Weekly review chain | 08-27 template 3c9eb501d42c81aaa9bbf96b2f1e2cea | 08-30 review 3cceb501d42c8139a63cc718d47d7cfe diffs against 08-23 | 08-30 | 08-27 is empty |
| 13 | ICP employee band | Sales Dev hub (20–200) | W-004 / W-009 (20–250) | Unknown | Flag for Don; TL positioning, low stakes here |

## 3. Link map (source → target → link type)

Index entries
- Wiki Index → every W-001…W-064 page → index entry (W-011, W-027, W-028 unresolved)
- Canon Registry rows → 33 pages/DBs → index entry via Page URL property (Cold Outreach row → wrong target 365eb501d42c810a8319f53e669f932e)
- Command Center top nav → W-063, W-001, W-004, W-005, W-054, W-057, Wiki Index, Registry, Inbox, Contacts → body link
- Command Center bottom sections → TL Work Hub, Client KB (404), SecureAI Docs (404), Knowledge DBs → body link (stale)
- Instructions → Morning briefs hub DB → body link

Body links and mentions
- W-063 → W-019, W-020, W-021, Shared Context Packet, Wiki Index, Registry → body link
- W-021 → W-005, W-004, W-001, W-054, Contacts, Inbox, Health Check-ins → body link (routing table)
- W-019 → W-005, W-036, Financial Accounts, Sales Pipeline, Contacts → mention (tier examples)
- W-001 → W-005, W-004, W-054, W-007 (Orbit), W-003 → body link
- W-005 → W-045…W-049, W-064, Supplements DB, Health Check-ins → body link
- W-062 → W-005, W-045, Supplements DB → body link
- W-002 → Observability Sprint, PiMan, Records Retention → body link / child
- W-018 → Command Center, W-002, W-019, W-020 → body link
- W-050 → Process Library, Reading & Resources (trashed) → body link (dangling)
- Money W-054 → Financial Accounts DB, Trading Ideas DB, State Reconciliation → body link
- Life Scorecard W-056 → Properties Hub, Financial Accounts, Health Check-ins → body link
- Household Management Hub → Equipment & Appliances (404), Maintenance Log (404), Home Projects (404), Vehicles DB, W-036, W-037 → body link
- Life Ops › Operating Map → Personal Advisors DB (404) → body link
- Side Businesses › Operating Map → 404 databases → body link
- RiverHouse W-025 → Operations, Guests, Compliance, Financials, Vendors → child pages
- Properties Hub → Lot 5, Lots 5/6/7, Archived Ag, Flood Reference, STR Tracker → child pages; Lots 5/6/7 → Lot 5 → body link
- TL Work Hub → Quick Start, Brand Guide, Content Lab, Operating Map, Observability Sprint → child pages; Quick Start → nonexistent pages → body link (dangling)
- Sales Dev hub W-012 → Sales Pipeline, Cold Outreach, Dashboard → child; Dashboard → Sales Pipeline rows → mention
- Zye's Brain → all children listed in 1a → child pages; Health Dashboard → W-005 → body link
- Migration Manifest W-044 → W-033, W-034, W-035, Sales Pipeline, Cold Outreach, Work Pipeline → body link
- Steward Log → Inbox rows → mention
- Morning briefs rows → Inbox, Health Check-ins, Calendar/mail links → mention

Relation properties (never edited by me; listed for Don)
- Sales Pipeline DB ↔ Contacts DB → relation property (57 rows)
- Canon Registry → Page URL (url property, not relation)
- Financial Accounts ↔ Trading Ideas → relation (Roth ladder row references account rows)

## 4. Ten worst problems

1. Live property content trapped inside the ⛔ Poison subtree. Properties Hub, the Flood reference fed monthly, the STR Tracker, and the only personal people roster all live under Zye's Brain, so an agent obeying the poison flag misses them and an agent ignoring it ingests superseded health values.
2. Three unreconciled Branford build plans (contradiction 4) with no page marked current.
3. Superseded medication line repeated in five places (contradiction 1) despite the W-005 banner; W-062 is the most dangerous because it is the clinician-facing page edited four days ago.
4. RiverHouse content split across three parents (Side Businesses subtree, Household Management Hub, Properties Hub) with blank scaffolding under W-025 and the real pages elsewhere.
5. Agent-stack wiki (W-003, W-006, W-007, W-008) is deprecated or describes retired tooling while W-001 and W-020 ADR-003 still cite it as live.
6. Competing hubs at workspace root: TeamLogicIT Work Hub (Poison), Health & Fitness, Trading, Travel, Household Management Hub, plus two Health entry points (W-005 and W-024) and an Instructions page not in the sidebar.
7. Canon Registry drift: two overdue reviews, a wrong Page URL on the Cold Outreach row, three Wiki Index entries with no page, and W-050 routing to a trashed database.
8. Command Center's bottom half still describes the November-2025 structure and links two 404 pages.
9. Fourteen empty or blank items (Life Ops and its four children, DMZ/RiverHouse scaffolding, Docs, Strategy Library, Zemple Hub, Properties, Vendors, Insurance, Brain Contacts, 08-27 review, Glamping Domes) that pad search results.
10. Tier 2/3 data sitting in ordinary pages: policy number in W-036, booking numbers and access keys in the Cruise page, guest names in Properties Hub and Life Scorecard, TL client and employee pages W-033 to W-035 and Work Pipeline still on this account pending the W-044 migration.

## 5. Note for Phase 2

Don's 2026-08-18 decision on W-018 states the five-area structure is final and no further phases will be built. Any Phase 2 taxonomy proposal must work inside that decision (consolidation under existing areas, one Archive page, registry and index hygiene) rather than propose a new tree. Phase 2 is not started; awaiting Don's review of this audit.
