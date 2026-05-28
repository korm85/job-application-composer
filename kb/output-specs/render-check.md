# Render Check — Pre-Finalization Checklist

Run this checklist against every CV markdown before declaring it final.

## Content checks

- [ ] Every metric traceable to `core/facts.md` (search for any number or % in the markdown)
- [ ] No metric present that is marked UNCONFIRMED in facts.md (unless user has just confirmed it)
- [ ] Bullet count per role within limit: max 6 for general CVs, max 7 for technical-depth variants
- [ ] QA roles: exactly 1 bullet each
- [ ] Summary: 2–3 lines, no QA-to-PM narrative, no "Senior" label

## Style checks

- [ ] No em dashes (search for "—" in the markdown)
- [ ] No banned buzzwords (synergistic, leveraged, spearheaded, best-in-class, cutting-edge, "measurable impact on customer efficiency")
- [ ] Contact line uses short LinkedIn URL
- [ ] No "Side Projects" section (RAG portal is an Oqton bullet)

## Structure checks

- [ ] Heading hierarchy: H1 for name, H2 for sections, H3 for roles
- [ ] Date ranges in italic on their own line under each role header
- [ ] Section order: Summary → Experience → Education → Skills (Skills only if signal)

## Output checks

- [ ] Markdown saved to `/cv-variants/[company].md`
- [ ] Docx generated only if pandoc + reference.docx are confirmed present
- [ ] Page count validated via LibreOffice headless (target: exactly 2 pages)

## Change-log

- [ ] If any cuts were made: change-log appended to the variant file

## Reminder to user

> Final two-page validation happens in Google Docs after applying formatting defaults.
> If overflow occurs there, invoke the propose-and-approve loop in `two-page-discipline.md` before cutting anything.
> The LibreOffice validation PDF in `/cv-variants/[company]/` is NOT for submission.
