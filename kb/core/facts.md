# Facts — every claim that may appear in outbound material
<!-- Never add a metric without user confirmation. Unconfirmed = marked UNCONFIRMED. -->
<!-- Source: master-cv.md (synthesized from 19 submitted/draft CV variants) -->
<!-- Confirmed metrics sourced from DRIVE-DATA.md / customer quotes per prior KB session. -->

## Employment timeline
- Senior Product Manager at Oqton: Feb 2025 – Present
- Product Manager, Simulation Suite at Oqton: Feb 2022 – Feb 2025
  <!-- Date conflict resolved in master-cv.md: some sources show "Mar 2022" start; sources consistently favour Feb 2022; followed sources. -->
- Software QA Team Lead at 3D Systems: Jan 2017 – Feb 2022
- Software QA Engineer, Founding Team at 3D Systems: 2015 – Jan 2017
  <!-- Exact start month not stated in any source; only year "2015" confirmed. One prior KB entry showed "Mar 2015" — treat as UNCONFIRMED until user verifies. -->
- Software QA Engineer at Cimatron: 2012 – 2015
  <!-- No month-level dates found in any source. -->
  <!-- Role conflict resolved: task brief referenced "Cimatron — QA Team Lead" but no source supports that. The QA Team Lead role is at 3D Systems, not Cimatron. Followed sources. -->

## Products owned (Oqton)

### AMVero
- What it is: A real-time AI monitoring platform for industrial additive manufacturing (LPBF). Uses computer vision, anomaly detection, and an autonomous decision engine to detect defects mid-build and determine whether a live production run continues or stops.
- Scope: Machine-agnostic, cross-vendor; deployed on Cloud (SaaS on AWS) and On-Premise; serves aerospace, defense, medical, and automotive enterprise customers; ITAR and SOC 2 compliant.
- Version: Commercial release v26.1.1, early 2026 — CONFIRMED (user confirmed 2026-05-26)
- Core technical capabilities (confirmed 2026-05-26; use in 3D printing company variants only — too technical for general CVs):
  - Generates an "As Built Part" 3D digital twin by aggregating part contours in real-time during the build
  - Detects named anomaly types mid-build: spatter, recoater hopping, recoater lines, warpage, short feed — each tagged critical or moderate severity
  - 3D Volume Aggregation module: combines related critical detections into multiple 3D volumes for contextual assessment by machine operators
  - Generates a complete build summary report per build for audit/traceability requirements
- Role: First PM for the product; owned from initial concept through enterprise launch; personally curated AI training data using Label Studio; authored smart alerting features; led customer discovery and prototype validation; stayed close through deployment.
- Defensible specifics:
  - "Signed 5 enterprise customers within 5 months of release, including Thales, Baker Hughes, 3D Systems, ELOS Medtech, and Rolls-Royce" — CONFIRMED (user confirmed 2026-05-26; Rolls-Royce is the 5th named customer)
  - "Beehive" — ruled out; Rolls-Royce is the confirmed 5th customer
  - "98% reduction in manual data review time" — all Oqton variants (marked universal in master-cv.md) — CONFIRMED (per DRIVE-DATA.md, Baker Hughes)
  - "~$150,000 in annual labor savings per machine" — all Oqton variants (marked universal) — UNCONFIRMED (calculation baseline not verified in master-cv.md; sourced from DRIVE-DATA.md in prior session)
  - "98% faster root cause analysis" — sourced from DRIVE-DATA.md in prior session — UNCONFIRMED in master-cv.md; user to verify before use in outbound
  - "~50% machine time recovery per rejected part" — sourced from DRIVE-DATA.md in prior session — UNCONFIRMED in master-cv.md; user to verify
  - "136 hours saved per year per printer" (Baker Hughes) — sourced from DRIVE-DATA.md in prior session — UNCONFIRMED in master-cv.md; user to verify
  - "18% reduction in scrap costs" (Baker Hughes) — sourced from DRIVE-DATA.md in prior session — UNCONFIRMED in master-cv.md; user to verify
  - "90% accuracy" for the real-time AI-based defect detection model — sources: AIPM, Unframe, SaaS, NICE, EnterpriseAI, Wiliot, Elbit, SysAid, Stratasys — CONFIRMED (per DRIVE-DATA.md)
  - "over $100k" value per live production run (context: what the decision engine decides to continue or stop) — multiple submitted variants — UNCONFIRMED

### Predictive Simulation Suite
- What it is: Three physics-based simulation modules (thermo-mechanical, thermal, and mechanical) integrated into 3DXpert, enabling engineers in medical, aerospace, and defense to validate designs digitally before committing to expensive production runs.
- Scope: Enterprise B2B SaaS product line; built on a third-party physics simulation engine shaped into domain-specific workflow modules; serves aerospace, defense, energy, and medical manufacturers.
- Role: Sole PM; owned strategy, roadmap, requirements, and GTM across all three modules; led cross-functional team.
- Defensible specifics:
  - "Cross-functional team of 11 (5 engineers, 2 designers, 2 sales, 2 application engineers)" — sources: Elbit, Stratasys — UNCONFIRMED
  - "Beta validation with 2 enterprise customers" — sources: AIPM, Autodesk, Unframe, NICE, SaaS, EnterpriseAI, Wiliot, Elbit, SysAid, Stratasys — UNCONFIRMED
  - "Published 2 whitepapers following beta completion" — same sources as above — UNCONFIRMED
  - "Pricing model redesign: flat per-machine license to credit-based; entry cost reduced from $30,000 to $2,500 for a standard 5-machine fleet" — source: Stratasys variant only — UNCONFIRMED
  - Visual scripting turning "multi-step configurations into single-click operations" (qualitative UX outcome) — multiple sources — UNCONFIRMED
  - Simulation validation (Heat Exchanger): 430mm x 260mm part (1,900 cm³ volume, 0.7mm walls, 3.58 m² surface area), 2.9M mechanical elements (8h15m run), 6.7M thermal elements across 30-hour print — sourced from DRIVE-DATA.md in prior session — UNCONFIRMED in master-cv.md; user to verify
  - Simulation validation (Knauf): Beta thermo-mechanical validation for 100mm x 140mm x 100mm specimen in 316L (heated to 470°C); distortion reduced from 0.7mm to <0.1mm (near 100% compensation) — sourced from DRIVE-DATA.md in prior session — UNCONFIRMED in master-cv.md; user to verify
  - Simulation validation (Emerson): 20+ hour build; thermal simulation predicted 390°C heating and 720µm shrinkage; compensated to <150µm maximum deviation (80% overall reduction) — sourced from DRIVE-DATA.md in prior session — UNCONFIRMED in master-cv.md; user to verify

### Internal RAG portal
- What it is: A self-serve internal knowledge portal for sales, marketing, operations, and application engineers; implemented as a RAG pipeline on a locally hosted LLM (Ollama) connected to live product documentation.
- Scope: Internal tool at Oqton; reduces dependency on PM and engineering team for technical product questions.
- Role: Built and deployed by Michael personally; classified as an Oqton work bullet (under Senior PM role), not a side project.
- Defensible specifics:
  - "~30% reduction in PM dependency on the engineering team" — sources: NICE, Autodesk, General, Unframe, Wiliot, EnterpriseAI, Medison, Portfolio, XTEND, SysAid — UNCONFIRMED (measurement method not described in any source)

## Tools and protocols
- Label Studio: Personal curation of AMVero training data across multiple machine types and vendors, working with data science teams — source: General, NICE__draft, Wiliot, Defense, Portfolio, XTEND, Stratasys, SysAid
- Ollama: Local LLM host for the internal RAG portal; also used in personal AI setup — source: multiple submitted variants; Skills table; AI Projects section
- OPC-UA: Real-time telemetry and image-transfer protocol; data integration requirements defined for machine-to-platform transfer across customer environments — source: Elbit; Skills table
- MQTT: Real-time telemetry protocol, same context as OPC-UA — source: Elbit; Skills table
- Figma / FigJam: Design and prototyping; "Figma Make" specifically used to generate prototypes from specs and context prompts — source: Autodesk, NICE__draft, Unframe, EnterpriseAI, Medison, SaaS, SysAid; Skills table
- Claude Code: Used in personal multi-agent PM workspace and for rapid prototyping — source: Skills table; AIPM__submitted bench bullets; user confirmed 2026-05-26
- OpenClaw: Multi-agent orchestration tool used in daily PM workflow — source: Skills table; AI Projects section; AIPM__submitted bench bullets; user confirmed 2026-05-26
- MiniMax: AI model provider (not a tool); used as a cost-effective model backend for agentic tasks within the multi-agent workflow, with routing to other models when needed — CONFIRMED (user confirmed 2026-05-26); does not belong in CV skills or tools sections
- Jira: Backlog management, sprint planning, integrated into AI workspace — source: multiple variants; Skills table
- SQL: Listed in Skills table — source: Skills table only; no specific use-case described in active bullets
- 3DXpert: Enterprise CAD/CAM platform the Simulation Suite is integrated into — source: Simulation Suite role description
- Cimatron (software): QA experience testing CAD/CAM manufacturing software (toolpaths, 3D modeling features, CNC machine integrations) — source: Cimatron role bullet; Skills table

## Metrics extracted (user to confirm each)
| Claim | Source (in master-cv.md) | Status |
|-------|--------------------------|--------|
| 5 enterprise customers within 5 months of AMVero release | Multiple submitted variants (NICE, AIPM, Autodesk, EnterpriseAI, Medison, SaaS, General, Defense, Stratasys, SysAid) | CONFIRMED (per DRIVE-DATA.md) |
| Named customers: Thales, Baker Hughes, 3D Systems, ELOS Medtech, Rolls-Royce | Same as above + user confirmed Rolls-Royce 2026-05-26 | CONFIRMED |
| Rolls-Royce as fifth named customer | User confirmed 2026-05-26 | CONFIRMED |
| 98% reduction in manual data review time | All Oqton variants (marked universal) | CONFIRMED (per DRIVE-DATA.md, Baker Hughes) |
| ~$150,000 annual labor savings per machine | All Oqton variants (marked universal) | UNCONFIRMED — calculation baseline unclear |
| 98% faster root cause analysis | DRIVE-DATA.md (prior session) | UNCONFIRMED in master-cv.md — user to verify |
| ~50% machine time recovery per rejected part | DRIVE-DATA.md (prior session) | UNCONFIRMED in master-cv.md — user to verify |
| 136 hours saved per year per printer (Baker Hughes) | DRIVE-DATA.md (prior session) | UNCONFIRMED in master-cv.md — user to verify |
| 18% reduction in scrap costs (Baker Hughes) | DRIVE-DATA.md (prior session) | UNCONFIRMED in master-cv.md — user to verify |
| 90% AI model accuracy (defect detection) | AIPM, Unframe, SaaS, NICE, EnterpriseAI, Wiliot, Elbit, SysAid, Stratasys | CONFIRMED (per DRIVE-DATA.md) |
| Production run value "over $100k" | Multiple submitted variants | UNCONFIRMED |
| ~30% reduction in PM dependency on engineering team (RAG portal) | NICE, Autodesk, General, Unframe, Wiliot, EnterpriseAI, Medison, Portfolio, XTEND, SysAid | UNCONFIRMED |
| Cross-functional team of 11 (5 engineers, 2 designers, 2 sales, 2 application engineers) | Elbit, Stratasys | UNCONFIRMED |
| Beta validation with 2 enterprise customers (Simulation Suite) | AIPM, Autodesk, Unframe, NICE, SaaS, EnterpriseAI, Wiliot, Elbit, SysAid, Stratasys | UNCONFIRMED |
| 2 whitepapers published after beta (Simulation Suite) | Same as above | UNCONFIRMED |
| Pricing model entry cost: $30,000 to $2,500 for standard 5-machine fleet | Stratasys variant only | UNCONFIRMED |
| QA team size: 4 QA Engineers at 3D Systems (Team Lead role) | AIPM, SaaS bench bullets | CONFIRMED (per DRIVE-DATA.md) |
| Simulation validation — Heat Exchanger (430mm x 260mm, 2.9M elements, etc.) | DRIVE-DATA.md (prior session) | UNCONFIRMED in master-cv.md — user to verify before outbound use |
| Simulation validation — Knauf (distortion 0.7mm to <0.1mm, 316L, 470°C) | DRIVE-DATA.md (prior session) | UNCONFIRMED in master-cv.md — user to verify before outbound use |
| Simulation validation — Emerson (390°C, 720µm, <150µm, 80% reduction) | DRIVE-DATA.md (prior session) | UNCONFIRMED in master-cv.md — user to verify before outbound use |
| "6+ years in enterprise B2B software" (summary claim) | AIPM__submitted summary | UNCONFIRMED — timeline check: PM tenure Feb 2022 to present = ~4 years; total career from 2012 = ~14 years; framing needs user sign-off |

## Education
- B.Sc., Mechanical Engineering, Ben-Gurion University of the Negev, Beer Sheva, Israel, 2008–2012
  <!-- Institution and dates confirmed: present in all variants per master-cv.md. No TODO needed. -->

## Languages
- Hebrew: Native
- English: Professional
- Russian: Fluent — CONFIRMED (user confirmed 2026-05-26; NICE__submitted "Native" was an error)
