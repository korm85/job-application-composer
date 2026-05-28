# CV Assembly — Build Order

Follow this sequence every time a tailored CV is generated:

1. Read `core/facts.md`, `core/voice-and-rules.md`, `core/target-roles.md`, `core/decisions-log.md`.
2. Identify role archetype from JD. Confirm with user if ambiguous.
3. Select summary candidate from `core/master-cv.md` matching archetype tag.
4. Select bullets from `core/master-cv.md` by matching archetype tags. Enforce bullet count limits.
5. Compress QA roles to 1 bullet each (pick strongest from Bench for that role).
6. Apply `core/voice-and-rules.md` — check em dashes, buzzwords, bullet count.
7. Validate every metric against `core/facts.md`. If metric not in facts.md, ask user before using it.
8. Apply markdown structure from `output-specs/cv-format.md`.
9. Run `output-specs/render-check.md` checklist.
10. Save markdown to `/cv-variants/[company].md`.
11. Generate docx via pandoc using `reference.docx`.
12. Run LibreOffice headless page-count validation.
13. If exactly 2 pages: report success, paths to user.
14. If overflow: invoke `output-specs/two-page-discipline.md` — propose options, do not cut.
15. Create entry in `tracking/applications-log.md`.
16. Run `enhancement/retro-checklist.md`. Add candidates to `enhancement/promotion-queue.md`.
