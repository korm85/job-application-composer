---
name: project-job-search-kb
description: "Job search KB for Michael Korenevsky — bootstrap complete, structure and key operational facts"
metadata: 
  node_type: memory
  type: project
  originSessionId: 327d02d5-d7b1-4623-b46d-56f0a5167db3
---

KB bootstrapped 2026-05-26 at `/home/michaek/job-application-composer/kb`.

**Why:** Michael is actively job searching (currently in SysAid interview process) and built a KB to systematically generate tailored CVs, track applications, and manage outreach.

**How to apply:** Before any CV, outreach, or tracking work, read the four core files in order: `core/facts.md`, `core/voice-and-rules.md`, `core/target-roles.md`, `core/decisions-log.md`. Follow the 16-step build order in `output-specs/cv-assembly.md`.

## KB status (as of bootstrap)
- 18 cv-variants files created (7 submitted, 11 draft-only awaiting user confirmation)
- 71 total files across all KB folders
- `core/master-cv.md`: 17 active bullets, 38 bench bullets, 14 summary candidates, 7 tagline candidates

## Pending before KB is operational
1. `pandoc` + `libreoffice` need manual install: `sudo apt-get install -y pandoc libreoffice` (in a regular terminal — sudo fails in Claude Code shell)
2. `output-specs/reference.docx` not yet generated — requires pandoc
3. 11 draft-only variants need user confirmation of submission status: XTEND, Enterprise AI Startup, Elbit, SysAid, Defense, Medison, Bagira, Windward, Portfolio, Stratasys, CyberSecurity
4. 20+ metrics in `core/facts.md` marked UNCONFIRMED — user must verify each before any outbound use

## Key structural facts (corrections from bootstrap vs. brief)
- Two distinct Oqton roles: PM (Feb 2022–Feb 2025) and Senior PM (Feb 2025–Present) — NOT one role
- QA Team Lead is at 3D Systems (NOT Cimatron) — Cimatron was Software QA Engineer
- Education: B.Sc. Mechanical Engineering, Ben-Gurion University of the Negev, 2012
- Russian language level CONFLICT: NICE submitted says "Native", all others say "Fluent" — user to confirm

## Current applications (from tracker)
- SysAid Technologies — AI PM: interview-done status as of 2026-05-15 (draft-only variant, yet interview occurred)

## LinkedIn drift
12 drift flags documented in `linkedin/profile.md` and `linkedin/experience-section.md`. Notable: customer names missing from LinkedIn, Simulation Suite bullets are generic, Label Studio/OPC-UA/MQTT absent.
