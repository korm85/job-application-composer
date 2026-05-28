# Job Search KB — Operating Manual

## Purpose

This knowledge base is the source of truth for Michael Korenevsky's job search materials. It drives all CV generation, outreach, and application tracking.

## Folder map

| Folder | Purpose |
|--------|---------|
| `core/` | Source-of-truth files: master CV, facts, voice rules, archetypes, decisions |
| `cv-variants/` | One `.md` file per application, plus source drive metadata |
| `output-specs/` | Pipeline specs: format, assembly order, two-page rules, render checklist |
| `linkedin/` | LinkedIn profile and experience section (with drift flags) |
| `outreach/` | DM and email templates (cold, warm, post-interview) |
| `templates/` | Job input form — fill before generating any CV |
| `enhancement/` | Retro checklist, promotion queue, promotion log |
| `tracking/` | Application log, active application folders, archive |
| `_source-cache/` | Raw exports from Google Drive — do not edit manually |

## Before starting any session

Read these files in order:
1. `core/facts.md`
2. `core/voice-and-rules.md`
3. `core/target-roles.md`
4. `core/decisions-log.md`

## Generating a tailored CV

1. User fills out `templates/job-input.md`
2. Follow `output-specs/cv-assembly.md` (16-step build order)
3. Run `output-specs/render-check.md` before declaring done
4. If overflow: follow `output-specs/two-page-discipline.md`

## Outreach

1. Ask user: relationship depth (none / weak / warm / strong)
2. Pull base template from matching `outreach/` file
3. Tailor with company specifics from `templates/job-input.md`
4. Present for approval before sending

## Enhancement loop

After each application AND after each interview:
1. Run `enhancement/retro-checklist.md`
2. Add candidates to `enhancement/promotion-queue.md`
3. Do NOT merge into `core/master-cv.md` — wait for batched user review
4. On approval: update `core/master-cv.md`, log in `enhancement/promotion-log.md`

## Application tracking

- Every generated variant creates a row in `tracking/applications-log.md`
- On `screen-scheduled` or beyond: promote to `tracking/active/[company]-[role].md`
- On close: move to `tracking/archive/` with a short retro at the top
- Auto-flag `ghosted` after 3 weeks of silence
- On `interview-done`, `rejected`, or `offer`: run retro checklist

## DO NOT list

- Never invent a metric, number, percentage, or customer count. Every claim must trace to `core/facts.md`.
- Never silently cut content to make a CV fit two pages. Use the propose-and-approve loop in `output-specs/two-page-discipline.md`.
- Never use em dashes. Convert to colons or commas.
- Never use: synergistic, leveraged, spearheaded, best-in-class, cutting-edge, "measurable impact on customer efficiency".
- Never add "Senior" to the tagline or summary.
- Never include a "Side Projects" section (RAG portal is an Oqton bullet).
- Never generate a final PDF via LibreOffice — that PDF is for page-count validation only. The submission PDF comes from the user's Google Docs export.
- Never generate a docx without verifying `output-specs/reference.docx` exists.
- Never add a bullet just to match a JD theme — adjust existing bullets only.

## PDF pipeline status

- `pandoc`: needs installation (`sudo apt-get install -y pandoc`) — required for docx generation
- `libreoffice`: needs installation (`sudo apt-get install -y libreoffice`) — required for page-count validation
- `pdfinfo`: installed (v26.01.0)
- `output-specs/reference.docx`: not yet generated (requires pandoc)
- Once pandoc/libreoffice are installed: run `pandoc --print-default-data-file reference.docx > /kb/output-specs/reference.docx`, then customize styles per `output-specs/cv-format.md`.

## Source cache

All Google Drive files fetched during setup are cached in `_source-cache/`. See `KB-MANIFEST.md` for the full audit trail. Do not re-fetch unless the user asks to refresh.
