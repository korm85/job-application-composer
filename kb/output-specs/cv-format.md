# CV Format — Output Pipeline

## Pipeline

1. Claude Code generates the tailored CV as markdown in `/cv-variants/[company].md`.
2. Claude Code uses pandoc with `/output-specs/reference.docx` to produce `[company]-cv.docx`.
3. User opens the `.docx` in Google Docs, performs a visual check, and exports to PDF.
4. The PDF is what gets submitted. The LibreOffice validation PDF is NOT for submission.

## Google Docs formatting defaults

Apply these when importing the markdown into Google Docs before final export:

- **Page:** 0.5" margins all sides; US Letter default (A4 alternative)
- **Body (Normal style):** 11pt Calibri, single line spacing, 0pt before/after paragraphs and bullets
- **Section headings (H2):** 12–13pt Calibri bold, 10pt before / 2pt after
- **Role headers (H3):** 11pt Calibri bold
- **Bullet indent:** 0.25" left, hanging indent
- **Bullet character:** use consistently (en dash or bullet — pick one)
- **Name block (H1):** 18pt Calibri bold
- **Tagline:** 11pt Calibri
- **Contact line:** 10–11pt Calibri, single line
- **Contact separators:** `  •  ` or ` | ` — pick one and use consistently
- **Date format:** "Mon YYYY – Mon YYYY" or "Mon YYYY – Present"; right-aligned (use italic on own line in markdown)
- **Section order:** Summary → Experience → Education → Skills (Skills only if signal)
- **No horizontal rules, no color, no icons, no photo**

## Markdown structure requirements (for pandoc mapping)

```markdown
# Michael Korenevsky

Product Manager | [contact line]

## Summary

[2–3 lines]

## Experience

### Oqton — Senior Product Manager
*Feb 2025 – Present*

- Bullet

### Oqton — Product Manager
*Feb 2022 – Feb 2025*

- Bullet

### [Role] — [Company]
*Date range*

- Bullet

## Education

- B.Sc. Mechanical Engineering, Ben-Gurion University of the Negev, 2012
```

## Pandoc conversion command

```bash
pandoc /kb/cv-variants/[company].md \
  --reference-doc=/kb/output-specs/reference.docx \
  --output=/kb/cv-variants/[company]/Michael\ Korenevsky\ Resume.docx
```

## Post-conversion validation (page count check)

```bash
libreoffice --headless --convert-to pdf --outdir /tmp /kb/cv-variants/[company]/Michael\ Korenevsky\ Resume.docx
pdfinfo /tmp/Michael\ Korenevsky\ Resume.pdf | grep "^Pages:"
```

- Pages = 2: proceed
- Pages = 1: note for user (may want to add Bench content)
- Pages ≥ 3: STOP — invoke two-page-discipline.md

## Filename convention

```
/cv-variants/
  [company].md
  [company]/
    Michael Korenevsky Resume.docx
    Michael Korenevsky Resume.pdf  (validation only — NOT for submission)
```

## Hard prohibitions

- Do not submit the LibreOffice PDF — it is a sanity check only
- Do not skip the Google Docs review step
- Do not generate docx without verifying reference.docx exists in /output-specs/
