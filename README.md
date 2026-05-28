# Job Application Composer

Michael Korenevsky's personal job search knowledge base — CV generation, outreach templates, and application tracking, designed for use with Claude Code.

## Quick start

```bash
git clone https://github.com/korm85/job-application-composer.git
cd job-application-composer
claude .
```

Claude will load `CLAUDE.md` automatically and read session context from `.claude/memory/` before doing anything.

## What's inside

| Path | Purpose |
|---|---|
| `kb/core/` | Source of truth: facts, master CV bullets, voice rules, target roles, decisions |
| `kb/cv-variants/` | 18 tailored CV files (7 submitted, 11 draft) |
| `kb/output-specs/` | 16-step CV assembly workflow, format rules, render checklist |
| `kb/outreach/` | Email and DM templates (cold, warm, post-interview) |
| `kb/tracking/` | Application log |
| `kb/templates/` | Job input form — fill before generating any CV |
| `kb/_source-cache/` | Raw Google Drive exports (do not edit) |
| `.claude/memory/` | Session context: user profile and project status |

## Before first use

Install the PDF pipeline tools (required for docx/page-count validation):
```bash
sudo apt-get install -y pandoc libreoffice
```

Then generate the reference style file:
```bash
pandoc --print-default-data-file reference.docx > kb/output-specs/reference.docx
```

## Operating manual

See `kb/README.md` for the full workflow: CV generation, outreach, enhancement loop, and application tracking.
