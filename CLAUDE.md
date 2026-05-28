# Job Application Composer — Claude Code Instructions

This is Michael Korenevsky's personal job search knowledge base. All CV generation, outreach, and application tracking flows through the `kb/` directory.

## Start of every session

Read these files in order before doing anything else:
1. `.claude/memory/user_michael_korenevsky.md` — who Michael is, career arc, targets
2. `.claude/memory/project_job_search_kb.md` — KB status, pending items, structural corrections
3. `kb/core/facts.md`
4. `kb/core/voice-and-rules.md`
5. `kb/core/target-roles.md`
6. `kb/core/decisions-log.md`

Full operating manual: `kb/README.md`

## Key rules (never violate)

- Never invent a metric, number, percentage, or customer count. Every claim must trace to `kb/core/facts.md`.
- Never silently cut content to fit two pages. Use the propose-and-approve loop in `kb/output-specs/two-page-discipline.md`.
- Never use em dashes. Convert to colons or commas.
- Never use: synergistic, leveraged, spearheaded, best-in-class, cutting-edge.
- Never add a bullet just to match a JD theme — adjust existing bullets only.
- Never generate a final PDF — the submission PDF comes from the user's Google Docs export.

## CV generation workflow

1. User fills `kb/templates/job-input.md`
2. Follow `kb/output-specs/cv-assembly.md` (16-step build order)
3. Run `kb/output-specs/render-check.md` before declaring done

## PDF pipeline

- `pandoc` and `libreoffice` need manual install: `sudo apt-get install -y pandoc libreoffice`
- `kb/output-specs/reference.docx` not yet generated (requires pandoc first)

## Pending items before KB is fully operational

1. Install pandoc + libreoffice (must be done by user in a regular terminal)
2. Generate `reference.docx` after pandoc is installed
3. Confirm submission status for 11 draft-only CV variants (see `kb/tracking/applications-log.md`)
4. Verify 20+ UNCONFIRMED metrics in `kb/core/facts.md` before any outbound use
5. Resolve Russian language level conflict: NICE submitted says "Native", all others say "Fluent"
