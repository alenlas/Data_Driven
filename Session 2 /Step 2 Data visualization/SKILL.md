---
name: whu-template-studio
description: Create WHU Otto Beisheim School of Management styled presentations, documents, visuals, and Excel dashboards using the official PPTX template, Arial typography, and the WHU blue palette. Use when the user asks for WHU-branded slides, reports, charts, or dashboards.
license: Proprietary. For internal WHU use unless explicitly cleared for external distribution.
compatibility: Requires Python with python-pptx, python-docx, openpyxl. Uses bundled PowerPoint template and works offline.
metadata:
  author: whu-template-studio
  version: "1.0"
---

# WHU Template Studio

## When to use this skill
Use this skill when the user wants any of the following in **WHU Otto Beisheim School of Management** branding:
- A PowerPoint deck that matches the WHU template
- Report-style documents (DOCX/PDF) that visually align with WHU slides
- Clean visuals (charts, diagrams, tables) in WHU colors and typography
- Excel dashboards (XLSX) with WHU styling

## What to ask the user for (minimum)
1. Output format(s): PPTX, DOCX, PDF, XLSX (or a mix).
2. Audience and purpose (internal update, executive summary, lecture, recruiting, etc.).
3. Content:
   - Titles and key messages
   - Data for charts and dashboards (table or CSV)
   - Any images or logos to include (if any)
4. Constraints: length (pages/slides), language, and deadline.

If the user gives incomplete information, create a best-effort first draft and clearly mark placeholders.

## Brand tokens (do not improvise)
This skill is anchored to the official WHU template:
- PowerPoint template: [assets/whu-overall-template.pptx](assets/whu-overall-template.pptx)
- Style guide: [references/STYLE_GUIDE.md](references/STYLE_GUIDE.md)
- Layout and placeholder map: [references/LAYOUTS.json](references/LAYOUTS.json)

### Core rules
- **Font**: Arial everywhere (including charts).
- **Color palette**: use the WHU palette from the style guide. Default to dark blue + light blue + light grey-blue.
- **Whitespace**: keep slides clean, avoid dense paragraphs. Prefer bullets, tables, and callouts.
- **Consistency**: do not manually recreate layouts. Reuse the template layouts and only replace placeholder content.

## PowerPoint workflow (PPTX)
### Step 1: Pick the right base layout
Choose one of these common layouts (names match the PPTX template):
- Cover:
  - `WHU_4-Part Headline` (or `WHU_4-Part-Headline + Image`)
  - `WHU_Long Title + Image`
  - `WHU_Long Title_Blue`
- Standard content:
  - `WHU_Slide_White_Textmaster` (topic + 40pt headline + optional subheadline + body)
  - `WHU_Slide_White_Bulletmaster` (bullets)
  - `WHU_Slide_White_2-Column-Master` (two columns)
- Color backgrounds for emphasis:
  - `WHU_Slide_Blue_Textmaster`
  - `WHU_Slide_Light-Blue_Textmaster`
  - `WHU_Slide_Silver-Grey_Textmaster`

### Step 2: Fill placeholders, do not restyle
- Replace placeholder text only.
- Preserve font sizes and colors from the template.

### Step 3: Charts and figures
- Use dark blue for the main series and light blue for the secondary series.
- Keep labels short and readable. Prefer direct labels over legends when possible.
- No 3D, no heavy shadows.

### Step 4: QA checklist
- Slide titles are aligned and consistent.
- No mixed fonts.
- Colors follow the palette.
- Spelling and punctuation consistent.
- Data labels and axes are legible.

## Document workflow (DOCX/PDF)
Use WHU styling in Word documents:
- Arial body font
- Dark blue for H1 headings
- Light blue for H2 headings
- Keep sections short, with bullets and numbered steps.

Template you can start from:
- [assets/whu-report-template.docx](assets/whu-report-template.docx)

If PDF is required, generate DOCX first, then export to PDF in the host environment.

## Dashboard workflow (XLSX)
Use Excel dashboards when the user wants a shareable, editable dashboard:
- Title in dark blue, Arial, bold
- KPI cards with light grey-blue headers and light blue key numbers
- Data tables on a separate sheet, clean column names, consistent number formatting

Template you can start from:
- [assets/whu-dashboard-template.xlsx](assets/whu-dashboard-template.xlsx)

## Optional scripts (for automation)
If the agent environment can execute scripts, use:
- `scripts/create_pptx.py` with a JSON outline
- `scripts/create_docx.py` with a JSON outline
- `scripts/create_dashboard_xlsx.py` with KPI + data JSON

Input schema examples:
- [references/INPUT_SCHEMA.md](references/INPUT_SCHEMA.md)
- Example specs in `assets/`

## Common pitfalls
- Rebuilding layouts by hand instead of using the template.
- Overusing colors. Default to 1 to 2 accent colors.
- Tiny fonts. Keep body at 16pt on slides.
- Adding too much text per slide. Split into multiple slides.

## Example: Quick slide plan (recommended)
- Cover (4-part headline)
- Agenda
- 3 to 5 content slides (problem, insight, recommendation)
- 1 chart slide (key metric trend)
- Next steps
- Contact / legal footer if needed
