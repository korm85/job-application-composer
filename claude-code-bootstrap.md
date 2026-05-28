# Job Search KB — Claude Code Bootstrap Brief

You are setting up a personal knowledge base (KB) for Michael Korenevsky's job search. This file is your operating manual. Read it fully before doing anything.

The source assets already exist in Google Drive. The Google Drive MCP is connected. Pull source content directly from Drive rather than asking the user to paste anything. File and folder IDs are listed in §3.

---

## 1. Who the user is (context for tone and framing, not for invention)

- Michael Korenevsky, Product Manager based in Israel
- B.Sc. Mechanical Engineering
- ~7 years in QA (QA Engineer → QA Team Lead at 3D Systems and Cimatron)
- Transitioned into PM at Oqton, working on:
  - **AMVero**: real-time AI-based defect detection for industrial 3D printing; cross-vendor/cross-machine; he personally curated training data via Label Studio with the data science team
  - **Predictive Simulation Suite**: integrated into 3DXpert; three physics-based modules for medical, aerospace, defense; visual scripting was prioritized from direct customer feedback; designed for workflow reuse
  - Internal RAG portal for application engineers and support staff using a locally hosted LLM (Ollama)
- Targeting: PM and Technical Product Owner roles at SaaS companies; interest in agentic AI and enterprise software

---

## 2. Build the following folder structure on the local filesystem

```
/kb
  /core
    master-cv.md
    facts.md
    voice-and-rules.md
    target-roles.md
    decisions-log.md
  /cv-variants
    (one file per existing variant — see §3 for source mapping)
  /output-specs
    cv-format.md
    cv-assembly.md
    two-page-discipline.md
    render-check.md
  /linkedin
    profile.md
    experience-section.md
  /outreach
    dm-cold.md
    dm-warm.md
    dm-post-interview.md
    email-templates.md
  /templates
    job-input.md
  /enhancement
    promotion-queue.md
    promotion-log.md
    retro-checklist.md
  /tracking
    applications-log.md
    /active/
    /archive/
  /_source-cache
    (raw exports from Drive, for diff/reference — see §3.7)
  README.md
  KB-MANIFEST.md
```

---

## 3. Source assets in Google Drive — pull these directly

Use the Google Drive MCP tools (`read_file_content` for Google Docs, `download_file_content` for PDFs, `read_file_content` for Sheets) to fetch source content. Do NOT ask the user to paste.

### 3.1 Umbrella folder
- **Job Search Artifacts**: `1s7_SZNU8dINhZAGHgAfHKbkY0K2XTExA`

### 3.2 CV variants — load these as source for `master-cv.md` and `/cv-variants/`

**Approach:** for every company subfolder under "Job Search Artifacts", list its contents (`Google Drive:search_files` with `parentId = '<folder-id>'`), take the file with the newest `modifiedTime` as the submitted variant for that company, and cache older same-folder versions as prior drafts of that same application. Loose files in My Drive root with descriptive names (e.g., `CV_Elbit_Technical_PO.md`) are pre-rename drafts that may not have been submitted; treat them as additional source bullets and ask the user to confirm which were actually sent.

**Company subfolders to scan:**
- Resume SaaS: `1OHEVjSGcusIodOdGKDgRfUmYfkJMMv5f` → variant identity: SaaS (broad)
- Resume AI Unframe: `1FGr1hKOOJaURc_O9IMbT5bzPYOlhQAtG` → Unframe
- Resume NiCE: `1Tmihna4a3B1oqaGQfL1lsYQG558lU9Cg` → NICE
- Resume Autodesk: `13wIMSNvkHVEggk5Z8mDDdEL5VG2rru7S` → Autodesk
- Resume AI PM: `1xol08YZ2PB_Fs51TLt-AjFojAKwyGTC1` → AI PM (broad archetype)

**Known files already identified (use these directly, but still scan parent folders for any not listed):**

Submitted variants (titled "Michael Korenevsky Resume" / "Michael Korenevsky CV", identified by parent folder):
- `1ib0Hk7qrNFKxlo67-7lTXhiqDSKNgCxA24xT_0wd6_I` → Autodesk
- `1BKMKrDl_TQ0ca6qP3lpeiDBvImVeoHca8za1hChZS-E` → Unframe
- `1DqWa2jJsqtEe5MSQmCCK1C2U5Qqg2Cf5oZ7p3j9L8FI` → AI PM
- `1xEXl4XVuXCfx0ZfUnQ8tUW8tiZaGvfQ2` (PDF) → SaaS (broad)
- `1RH_pfayahI1BBTL5WyueFj3PM7fSSe19` (PDF) → SaaS
- `1T0dkjovjj7MnI5w-bADzcL0mAjDuHvgI` (PDF) → AI PM
- `1pqKP1EgZ-CfwS7ezLgOtfgt5HzMVcIKG` (PDF) → Wiliot (parent folder `1MaLr_8i4NDbNz8kQ0vWuK1nfNaiMBq_u` — list this folder to confirm)
- `1JSYTI07l3cSo-ZFNZGcYigwaJOwJHATbJEuruE32Jp0` → in root, latest among "Michael Korenevsky CV" titles in root — treat as general unless user identifies a target

Descriptively-named drafts in My Drive root (may or may not have been submitted — confirm with user):
- `1RHPagSbqPkM1XW1z2FbEX0DEr3EJ4HeGmamdtewamX4` — Michael_Korenevsky_CV_XTEND.md (latest, 2026-05-25) → XTEND
- `1UcZbtLBHpPhpI9hBeUg-_28W1nhPCo30xM-aVzeBTZY` — CV_Enterprise_AI_Startup.md → Enterprise AI Startup archetype
- `1x9D2jX87QXcnbmnoX4D2IrlxCty40fvhXaxcTSULMdw` — CV_Elbit_Technical_PO.md → Elbit
- `1JP0QRIU1ntNE9DEq3Hp7Hj1svBY_E34lyxJxdOwFm8U` — Michael_Korenevsky_CV_SysAid.md → SysAid
- `1mudNS1VMR2SUyVoZeScLaVx5w2_2FN1rXA0JUb_hwBg` — Michael_Korenevsky_CV_Defense.md → Defense archetype
- `1vU1AhNr7KJ0zu_A_w-70Df7lo9lIYpm0PPHPq3D6mz8` — Michael_Korenevsky_CV_Medison.md → Medison
- `1xI8ZqPtUo46-wlqj6UM5KuY2pGNqyTZAsAjqWloRBCY` — Michael_Korenevsky_CV_Bagira.md → Bagira
- `1TTig_RJmlJRO_hE82YpWQJdfrDdGMd6USte8PwLjGVw` — Michael_Korenevsky_CV_Windward_v2.md → Windward
- `1lbPupUpBwSxuhgy3deDYpYZzX8OKtBLz1HrCqE_aZUY` — Michael_Korenevsky_CV_Portfolio.md → Portfolio
- `1ERQtX7Vf0UEqqExc__r7WBpP2tvAuInVAKWhFYkVC8s` — CV_Stratasys_Sr_PM → Stratasys
- `11F269-ei9APP37W0ie4CjZiBJGQFLDCKImIqF4mOdyk` — Michael Korenevsky CyberSecurity → CyberSecurity archetype

For each descriptively-named draft, check whether a same-folder "Michael Korenevsky Resume"-titled successor exists with a later `modifiedTime`. If yes, the descriptive draft is a pre-submission version; cache it but build `/cv-variants/[company].md` from the renamed submitted version. If no, ask the user to confirm whether the descriptive draft was submitted.

**Important — interpreting the CV file lifecycle:**

The user's per-application workflow is:
1. Draft the CV in markdown with a descriptive filename (e.g., `CV_Elbit_Technical_PO.md`, `Michael_Korenevsky_CV_Medison.md`).
2. Before sending, rename to the standardized title "Michael Korenevsky Resume" or "Michael Korenevsky CV".
3. Apply Google Docs formatting (0.5" margins, 11pt body, single spacing, headings 12–13pt with 10pt before / 2pt after, 0.25" bullet indent) and adjust to fit two pages.
4. Export to PDF.
5. Submit the PDF.

This means the descriptive markdown draft, the renamed Google Doc, and the resulting PDF are the **same content at three lifecycle stages of one application** — not three independent variants. They should be ingested as one variant per company.

**Ingestion rule:**
- For each application, prefer the source with the latest editorial content. That is typically the renamed "Michael Korenevsky Resume" Google Doc or PDF in the company subfolder, since formatting cleanup at stage 3 sometimes also includes last-minute text edits.
- The descriptive markdown draft in My Drive root is the same application's earlier stage — useful as a sanity check and for retrieving any bullets that may have been trimmed for two-page fit (these belong in the Bench).
- Use parent folder name as the company identifier (e.g., Unframe folder → variant identity is Unframe; AI PM folder → AI PM archetype).
- If a descriptive draft exists in My Drive root without a matching renamed/PDF copy in any subfolder, ask the user whether it was submitted or abandoned.

**Action on ingestion:**
1. For each company subfolder under "Job Search Artifacts", read the latest "Michael Korenevsky Resume/CV" file (Doc or PDF) — this is the submitted version.
2. Find the corresponding descriptive draft in My Drive root by content match (e.g., a draft mentioning Elbit-specific framing matches the Elbit folder's submitted file).
3. Compare the two: any bullet present in the draft but missing from the submitted version was trimmed for two-page fit → add to **Bench** in `master-cv.md` with a note: "trimmed from [company] for two-page fit on [date]".
4. Cache both stages in `/_source-cache/` with names like `Elbit__draft__1x9D2j.md` and `Elbit__submitted__<id>.md` for traceability.
5. Build one `/cv-variants/[company].md` per application using the submitted version's content.

In the handoff summary, produce a mapping table per application: `[company] → [draft Drive ID] → [submitted Drive ID(s)] → [bullets trimmed for fit, if any]`. The user verifies this mapping before the KB is treated as operational.

### 3.3 LinkedIn content
- `1-Izu6EO5Ob1hXZ77Gj3cbiXL6KqJi24hUW14oooVw5I` — LinkedIn_Profile.md → `/linkedin/profile.md`
- `1jkNWEh8i58CZOT3503FaVt1zSeIG9E61rIBGPhFN7dc` — LinkedIn Experience (latest, 2026-04-16) → `/linkedin/experience-section.md`
- `1z11LzVjKWKSI16AEFrEwns7gYtLzGvZ6pJ3jhykanPc` — LinkedIn Experience (earlier; load only if newer is incomplete)

### 3.4 Cover letters and outreach (source material for `/outreach/`)
- `148_ncZHtJcyO5m70tXO8djIdzjuE22GtPuWa4V9NMHI` — Cover Letter Medison
- `1TKUv32XPSEENQ_Ht_mif0wFMvjBd1kzLmzbFSp0hq1k` — Cover Letter Oriient
- `1FI_oFVC-T_sVPHRwaG232yMC-q24hvIPRIer6_Knzlg` — Cover Letter (Windward)

Extract patterns from these into the `/outreach/` templates rather than copying verbatim. Then ask the user to confirm or supply LinkedIn DM examples (which may not be in Drive yet).

### 3.5 Interview prep (reference material — do not copy into KB, just catalog)
- `1wBuIKAxeEmcydY2Uf7FAfdKiGgi20YdJ77itDOZpmYg` — Master Pitch & Interview Prep SysAid
- `1o2Aqgv5CjpgfMAoRuCne-Qscsi3GmCSbAhVem3tFKxM` — Master Pitch V2
- `1NAsSwmR-Wu_Ynh3GPsR9URI22jJ1DeKFPwNQOSA-ygY` — SysAid HR Interview Prep
- `1uF-DoveY5XNiB553hrnjZltKmt4y07K6yoo2icyPllk` — Interview Flashcards

Record these in `KB-MANIFEST.md`. When an application moves to `/active/`, surface these as candidates for interview prep.

### 3.6 Existing tracking
- `1GIDsGPatT6By3IaYay5h_RFIV0JsXE3SklL8n5Q3Y2g` — Job Search Tracker (Sheets). Read and seed `tracking/applications-log.md` with any entries found.

### 3.7 Caching policy
For every Drive file you read, save the extracted markdown to `/kb/_source-cache/` with a filename matching the Drive title plus the Drive ID suffix (e.g., `Michael_Korenevsky_CV_XTEND__1RHPagSb.md`). Add a header line in each cached file with the Drive ID, modifiedTime, and fetch time. Do not re-fetch on subsequent sessions unless the user asks to refresh.

---

## 4. Operating principles (these govern everything)

### 4.1 Never invent
- No metric, number, percentage, customer count, timeline, or claim may appear in any output unless it is in `facts.md`.
- If a metric appears in a source CV but its origin is unclear, surface it as a candidate for `facts.md` and ask the user to confirm before using it elsewhere.
- Do not estimate, round, or infer.

### 4.2 Never silently cut
- If a CV variant overflows two pages, do NOT cut content to make it fit.
- Stop, report the overflow, diagnose the cause, and propose 2–4 ranked options with tradeoffs.
- Wait for approval before any cut that removes a claim, metric, bullet, or substantively rewords a bullet.
- Mechanical compression (whitespace, punctuation per voice rules) is allowed without approval.
- After approved cuts, append to the variant's `change-log` section.

### 4.3 Defensibility test
- Every bullet must be something the user can defend in an interview.
- If a bullet uses a buzzword, vague claim, or framing without concrete grounding, flag it.

### 4.4 Voice
- Plain, specific, defensible language.
- No em dashes — use colons or commas.
- No buzzword stacking ("synergistic", "leveraged", "spearheaded", "best-in-class", "cutting-edge", etc.).
- No "Senior" in tagline or summary; "Senior" appears only in the Experience section for the latest Oqton role.
- No QA-to-PM career narrative in the summary.

### 4.5 Output format
- All CV outputs are `.md` by default.
- `.docx` only when explicitly requested.

### 4.6 Don't over-tailor
- Do not echo job description language verbatim unless it genuinely matches the user's experience.
- Adjust existing bullets to fit; do not add new bullets just to match a JD theme.
- Hard ceiling: 6 bullets per role for general CVs; 7 only for technical-depth variants (NICE-style) where each bullet is independently defensible.

---

## 5. Content to populate

### 5.1 `README.md` — operating model for future sessions
Include: purpose, folder map, generation order (§6), outreach order (§7), enhancement loop (§8), tracking model (§9), "do not" list summarizing §4.

### 5.2 `core/master-cv.md` — built by extracting from Drive

Build the master by processing the variants in §3.2:

1. **Treat each application as one variant, not three.** The descriptive markdown draft, the renamed Google Doc, and the submitted PDF for any single application are stages of the same content. Use the submitted version (Doc or PDF in the company subfolder) as the canonical phrasing for that application. Use the descriptive draft as the source for **Bench** bullets that were trimmed for two-page fit.

2. **Identify every unique bullet across all applications.** Across companies (Unframe, NICE, Autodesk, Elbit, Medison, SysAid, etc.), collect every distinct bullet.

3. **Deduplicate near-identical bullets.** When the same bullet appears in multiple applications with slightly different phrasing, keep the strongest version. Flag close calls for user choice in the handoff.

4. **Tag each bullet with archetype fit:** `[PLG]` `[Agentic]` `[Enterprise]` `[TechPO]` (one bullet may carry multiple tags). Use the application's company/folder as a starting signal: Unframe → `[Agentic]`, NICE → `[Enterprise]`, Elbit → `[TechPO]`, AI PM folder → `[Agentic]`, etc. Confirm tags with user during handoff.

5. **Group under:** Oqton (Senior PM), Oqton (PM if applicable), Cimatron, 3D Systems, Education, Bench.

6. **For QA roles, reduce to one bullet per role** — pick the strongest across all applications, move the rest to Bench.

7. **Preserve every distinct summary variant as a candidate**, tagged by archetype, with source noted.

8. **Bench rules:**
   - Bullets that appear in a descriptive draft but were cut from that application's submitted version → Bench, tagged "trimmed for fit, [company], [date]"
   - QA bullets not selected as the single per-role representative → Bench
   - Bullets that appeared in only one application and weren't reused → Bench, tagged with their original company

9. **For each bullet in the master, record the source application(s)** and whether the source phrasing came from the submitted version or a draft. This becomes important for the enhancement loop and for understanding which framings have been "battle-tested" in actual submissions.

Output schema:
```
# Master CV — source of truth

## Header
- Name, tagline (no "Senior"), contact, short LinkedIn URL

## Summary candidates
### [Archetype tag] — [short label]
[2–3 line summary]
[source: variant filename]

## Experience

### Oqton — Senior Product Manager
- [bullet text] [tags] [source]
...

### Cimatron — QA Team Lead
- [one bullet] [source]

### 3D Systems
- [one bullet per role] [source]

## Education

## Bench
- [bullets considered but not in any active variant, with source]
```

### 5.3 `core/facts.md`

Initial schema:
```
# Facts — every claim that may appear in outbound material

## Employment timeline
- [role, company, start–end]

## Products owned (Oqton)
### AMVero
- What it is: real-time AI-based defect detection for industrial 3D printing
- Scope: cross-vendor, cross-machine type
- Role: PM; personally curated training data via Label Studio with data science team
- Defensible specifics:
  - [TODO — pending user confirmation of any specific metrics from variants]

### Predictive Simulation Suite
- What it is: physics-based predictive simulation integrated into 3DXpert
- Modules: three (medical, aerospace, defense)
- Role: PM; visual scripting prioritized from direct customer feedback; designed for workflow reuse
- Defensible specifics:
  - [TODO]

### Internal RAG portal
- What it is: internal portal for application engineers and support staff
- Stack: locally hosted LLM (Ollama)
- Role: built the portal
- Defensible specifics:
  - [TODO]

## Tools and protocols
- Label Studio: training data curation
- Ollama: locally hosted LLM
- OPC-UA: [TODO — confirm depth of use]
- MQTT: [TODO — confirm depth of use]

## Metrics extracted from existing variants (TODO — user to confirm each)
<!-- Every number, percentage, count, or timeline found in variants. -->
<!-- Format: "claim → source variant filename → status (confirmed / unconfirmed)" -->

## Education
- B.Sc. Mechanical Engineering — [TODO institution, year]
```

After populating, list every TODO and every unconfirmed metric in the handoff summary.

### 5.4 `core/voice-and-rules.md`
Encode §4.4 plus:
- Bullet discipline: 6 max per role general; 7 max technical-depth variants only
- QA roles: 1 bullet each
- No "Side Projects" section; RAG portal is an Oqton bullet
- LinkedIn URL: short form
- Signal engineering depth where relevant ("physics-based")
- Banned vague phrases: maintain a list, starting with "measurable impact on customer efficiency"
- Summary: 2–3 lines, no QA-to-PM narrative, no "Senior" label

### 5.5 `core/target-roles.md`
Archetypes with tone shifts and recommended master-CV bullet tags:
- **PLG/SaaS PM** — customer feedback loops, iteration speed, usage signal
- **Agentic AI PM** — LLM workflows, data curation, evals, internal RAG portal
- **Enterprise PM** — cross-functional, integration complexity, regulated industries, long sales cycles
- **Technical Product Owner** — protocol depth (OPC-UA, MQTT), engineering collaboration, physics-based simulation

For each, document tone shift, recommended bullet tags, and what NOT to emphasize.

### 5.6 `core/decisions-log.md`
Seed: "Hardware/systems-focused roles: ruled out as poor fit." Append as the user shares more.

### 5.7 `cv-variants/*.md`
For each Drive variant, create a corresponding file. Each contains:
- Header noting source Drive ID and target archetype
- The assembled CV under current voice rules
- A `change-log` section (empty initially)

Naming: `[company-or-archetype].md` (e.g., `unframe.md`, `elbit-technical-po.md`).

### 5.8 `output-specs/cv-format.md`

Document the user's actual output pipeline:

**Pipeline:**
1. Generate the CV in markdown (`.md`) under current voice and content rules.
2. The user imports the markdown into Google Docs.
3. The user applies these Google Docs formatting defaults:
   - Page: 0.5" margins all sides; US Letter default (A4 alternative)
   - Body: 11pt, single line spacing, 0pt before/after on paragraphs and bullets
   - Section headings (H2): 12–13pt, bold, 10pt before / 2pt after
   - Bullet indent: 0.25" left, hanging
   - Bullet character: spec one and use consistently
   - Name block: name 18pt, tagline 11pt, contact line 10–11pt single line
   - Contact separators: pick one (`  •  ` or ` | `)
   - Dates: right-aligned, "Mon YYYY – Mon YYYY" / "Mon YYYY – Present"
   - Section order: Summary → Experience → Education → Skills (Skills only if it adds signal)
   - No horizontal rules, no color, no icons, no photo
   - Font: spec one (recommend Calibri or Source Sans 3)
4. The user adjusts to fit exactly two pages (any cuts at this stage must go through the propose-and-approve loop in §4.2; do not silently cut).
5. Export to PDF.
6. Submit the PDF.

**What this means for the markdown output:**
- The markdown is sized for two pages after applying the Docs defaults above. Estimate roughly: ~6 bullets per role × 4 roles + summary + education ≈ two pages at 11pt single-spacing.
- The render-check in `render-check.md` validates the markdown is two-page-realistic, not that the markdown itself is two pages (markdown rendering is irrelevant).
- The final two-page validation happens in Google Docs by the user — but Claude Code's job is to produce markdown that fits without forcing cuts at the Docs stage.

### 5.9 `output-specs/cv-assembly.md`
Document the build order from §6.

### 5.10 `output-specs/two-page-discipline.md`
Document §4.2 in full, including hard prohibitions (no font shrink below 11pt, no margin reduction below 0.5", no line spacing below single) and the propose-options output format.

### 5.11 `output-specs/render-check.md`
Pre-finalization checklist (Claude Code runs against the markdown before declaring it done):
- Two-page realism check: bullet count and summary length within the budget that fits two pages at the Google Docs defaults in `cv-format.md` (rough guide: max ~6 bullets per recent role, ~1 per QA role, 2–3 line summary)
- Every metric traceable to `facts.md`
- Bullet count per role within limit (6 default, 7 only for technical-depth variants)
- No em dashes
- No banned buzzwords
- Contact line uses short LinkedIn URL
- Section heading hierarchy is consistent (H1 for name, H2 for sections, H3 for roles)
- Markdown saved (or `.docx` only if explicitly requested)
- Change-log appended if any cuts were made
- Note in the output reminding the user: "Final two-page validation happens in Google Docs after applying formatting defaults. If overflow occurs there, invoke the propose-and-approve loop before cutting anything."

### 5.12 `linkedin/profile.md` and `linkedin/experience-section.md`
Pull from Drive IDs in §3.3. Apply voice rules and flag any drift between LinkedIn content and master-CV bullets for review.

### 5.13 `outreach/dm-cold.md`, `dm-warm.md`, `dm-post-interview.md`, `email-templates.md`
Extract patterns from the cover letters in §3.4. Each file documents:
- When to use this template (relationship depth, situation)
- Structural template (placeholders for company specifics)
- 1–2 worked examples
- The calibrated ask appropriate for this depth

### 5.14 `templates/job-input.md`
```
# Job input

- Company:
- Role title:
- Source:
- Contact name (if any):
- Relationship depth (none / weak / warm / strong):
- Deadline (if any):
- JD (paste full text below):

---

[JD text]
```

### 5.15 `enhancement/retro-checklist.md`, `promotion-queue.md`, `promotion-log.md`
Per §8.

### 5.16 `KB-MANIFEST.md`
Append-only inventory of every Drive file read during setup. Per entry:
- Drive ID
- Drive title
- modifiedTime at fetch
- Local cache path in `/_source-cache/`
- KB destination file(s)
- Notes (duplicate, stale, partial, etc.)

This is the audit trail.

### 5.17 `tracking/applications-log.md`
Top: pipeline snapshot. Body: table with columns `| Date | Company | Role | Variant | Source | Status | Last update |`.

Status vocabulary: `applied`, `acknowledged`, `screen-scheduled`, `screen-done`, `interview-scheduled`, `interview-done`, `offer`, `rejected`, `ghosted`, `withdrawn`, `on-hold`.

Seed from the Job Search Tracker Sheet (§3.6) if it has entries.

---

## 6. Order of operations: generating a tailored CV

1. Read `facts.md`, `voice-and-rules.md`, `target-roles.md`, `decisions-log.md`.
2. Identify role archetype from JD; confirm with user if ambiguous.
3. Select summary candidate from `master-cv.md` matching archetype.
4. Select bullets by matching archetype tags; enforce bullet count limits.
5. Compress QA roles to one bullet each.
6. Apply `voice-and-rules.md`.
7. Validate every metric against `facts.md`. If missing, ask the user.
8. Apply `cv-format.md` structure (see §12.3 for the required markdown layout).
9. Run `render-check.md`.
10. Save markdown to `/cv-variants/[company].md`.
11. Generate `.docx` via pandoc using `reference.docx` (§12.4).
12. Run validation page-count check via LibreOffice headless (§12.5).
13. If validation PDF is exactly two pages: report success and paths to user.
14. If validation PDF overflows: invoke `two-page-discipline.md` (propose, don't cut). Do not generate a final docx until cuts are approved.
15. Create entry in `applications-log.md`.
16. Run `retro-checklist.md`; add candidates to `promotion-queue.md`.

---

## 7. Order of operations: outreach

1. Ask: relationship depth.
2. Pull base template from matching `/outreach/` file.
3. Tailor with company specifics from `job-input.md`.
4. Apply voice rules.
5. Calibrate the ask to relationship depth.
6. Present for approval before sending.

---

## 8. Enhancement loop

After each application generated AND after each interview:
1. Run `retro-checklist.md`.
2. Add promotion candidates to `promotion-queue.md`.
3. Do not auto-merge into `master-cv.md`; wait for batched review.
4. On approval, update `master-cv.md` and log in `promotion-log.md`.

---

## 9. Application tracking

- Every generated variant creates a row in `applications-log.md`.
- The user updates status in natural language.
- On status change to `screen-scheduled` or beyond, prompt to promote to `/active/[company]-[role].md` (default yes).
- `/active/` files hold: JD, variant link, outreach history, interview prep, debriefs, follow-up drafts.
- On close, move to `/archive/` with a short retro at the top.
- Auto-flag `ghosted` after 3 weeks of silence.
- On `interview-done`, `rejected`, or `offer`, trigger the retro checklist.

---

## 10. What to do right now (execution sequence)

1. Create the folder structure in §2.
2. Verify the PDF pipeline toolchain (§12.1): confirm `pandoc` and `libreoffice` are installed; install via apt if not.
3. Set up `reference.docx` (§12.2): generate the default, present the manual customization instructions to the user, and confirm when the styled `reference.docx` is in place. This is a one-time setup step.
4. Use the Google Drive MCP to fetch each source asset in §3. Cache raw exports to `/kb/_source-cache/` (§3.7) and log every fetch to `KB-MANIFEST.md` (§5.16).
5. Populate all files specified in §5.
6. After population, produce a handoff summary covering:
   - Folder tree created
   - Toolchain verification result (pandoc version, libreoffice version, reference.docx status)
   - Files populated vs. files needing user input
   - Full list of TODOs in `facts.md` (every unconfirmed metric pulled from variants, with source)
   - Application mapping table per §3.2 (company → draft Drive ID → submitted Drive ID(s) → trimmed bullets sent to Bench)
   - Any near-duplicate bullets across applications where you had to pick the strongest phrasing — list them so the user can review
   - Any Drive files you skipped and why
   - Any ambiguities that block the KB from being operational

7. Do NOT generate any tailored CV, docx, PDF, or outreach output until the user reviews the handoff summary and confirms.

---

## 11. Tooling notes for Claude Code

- For Google Docs (`application/vnd.google-apps.document`): use `read_file_content` to get natural-language markdown.
- For PDFs (`application/pdf`): use `download_file_content` then extract text.
- For Sheets (`application/vnd.google-apps.spreadsheet`): use `read_file_content`.
- Batch reads; don't re-fetch files already in `_source-cache` unless the user asks to refresh.
- If a Drive file fails to fetch, log it in `KB-MANIFEST.md` with the error and continue. Surface the list at handoff.

---

## 12. PDF generation pipeline (Path B: markdown → docx → user-finalized PDF)

The user is on Ubuntu 26.04. Final outputs are PDF files submitted to employers. The pipeline:

1. Claude Code generates the tailored CV as markdown in `/cv-variants/[company].md`.
2. Claude Code uses `pandoc` with a reference docx template to produce `[company]-cv.docx`.
3. The user opens the `.docx` in Google Docs (preserves styles cleanly), performs a quick visual check, and exports to PDF.
4. The PDF is what gets submitted.

### 12.1 One-time environment setup

On first run, Claude Code must verify the toolchain:

```bash
# Verify pandoc is installed (Ubuntu 26.04 ships pandoc 3.7.x in universe)
pandoc --version || sudo apt-get update && sudo apt-get install -y pandoc
```

If `pandoc` is missing, install it. No LaTeX or TeXLive needed — we are generating docx, not PDF directly via pandoc.

### 12.2 Reference docx template

Create `/kb/output-specs/reference.docx` — this is the style template pandoc uses for all generated docx files. To create it on first run:

```bash
# Generate a default reference doc, then we will modify it
pandoc --print-default-data-file reference.docx > /kb/output-specs/reference.docx
```

Then Claude Code must modify the styles inside `reference.docx` to match the user's formatting defaults from `cv-format.md`. The reliable way to do this without manipulating XML directly is:

1. Open the generated `reference.docx` in LibreOffice or Google Docs.
2. Modify the named styles to match:
   - **Normal**: Calibri 11pt, single line spacing, 0pt before/after
   - **Heading 1**: Calibri 18pt bold (used for name)
   - **Heading 2**: Calibri 12pt bold, 10pt before / 2pt after (used for section headers like "Experience")
   - **Heading 3**: Calibri 11pt bold (used for role titles)
   - **List Paragraph**: Calibri 11pt, 0.25" left indent, hanging indent
3. Set page margins to 0.5" all sides under Page Setup.
4. Save and re-place in `/kb/output-specs/reference.docx`.

Claude Code should present these instructions to the user as a one-time setup step and confirm when `reference.docx` is in place before any docx generation.

### 12.3 Markdown structure requirements (so pandoc maps cleanly to styles)

Generated CV markdown must follow this structure:

```markdown
# Michael Korenevsky

Product Manager | [contact line]

## Summary

[2–3 lines of summary text]

## Experience

### Oqton — Senior Product Manager
*Mar 2022 – Present*

- Bullet text
- Bullet text

### Oqton — Product Manager
*Date range*

- Bullet text

### Cimatron — QA Team Lead
*Date range*

- Single bullet for QA role

## Education

- B.Sc. Mechanical Engineering, [institution], [year]
```

Date ranges use italics (single asterisks) on their own line under the role header. This avoids needing right-aligned tabs, which don't survive markdown-to-docx well.

### 12.4 Conversion command

```bash
pandoc /kb/cv-variants/[company].md \
  --reference-doc=/kb/output-specs/reference.docx \
  --output=/kb/cv-variants/[company]-cv.docx
```

Run from the CV variant filename. Output goes alongside the source markdown.

### 12.5 Post-conversion validation

After generating the docx, run a page-count sanity check using LibreOffice in headless mode (which is pre-installed on Ubuntu desktop; install with `sudo apt-get install -y libreoffice` if missing):

```bash
# Convert docx to PDF to verify page count without manual Docs round-trip
libreoffice --headless --convert-to pdf --outdir /tmp /kb/cv-variants/[company]-cv.docx
# Use pdfinfo to count pages
pdfinfo /tmp/[company]-cv.pdf | grep "^Pages:"
```

If page count is exactly 2: proceed.
If page count is 1: usually fine, but note for the user — they may want to add content from `master-cv.md` Bench.
If page count is 3 or more: STOP. Do not produce a final output. Invoke the propose-and-approve loop from `two-page-discipline.md` and present overflow options to the user.

The `libreoffice --headless` PDF is **only for validation**, not for submission. The submitted PDF is the one the user generates from Google Docs in step 3 of §12 (because Google Docs is what the user uses and trusts for final visual QA).

### 12.6 Filename convention

For the docx output, name it `Michael Korenevsky Resume.docx` to match the user's submission convention. Store it in `/kb/cv-variants/[company]/` (create a subfolder per company if generating both md and docx) — but make the docx easy to find for upload. Suggested layout:

```
/cv-variants/
  unframe.md
  unframe/
    Michael Korenevsky Resume.docx
    Michael Korenevsky Resume.pdf  (validation copy, not for submission)
```

### 12.7 Handoff after generation

When done, Claude Code reports:
- Path to the markdown (`/cv-variants/[company].md`)
- Path to the docx (`/cv-variants/[company]/Michael Korenevsky Resume.docx`)
- Validation page count
- Reminder: "Upload the .docx to Google Docs, do a final visual check, export to PDF, then submit. The validation PDF in this folder is NOT for submission."

### 12.8 Hard prohibitions

- Do not submit the LibreOffice-generated PDF as if it were the final output. It's a sanity check only.
- Do not write a workflow that skips the user's Google Docs review step.
- Do not generate the docx without verifying `reference.docx` exists in `/kb/output-specs/`.
