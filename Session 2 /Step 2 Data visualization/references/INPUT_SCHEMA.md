# Input schema (recommended)

You can ask the user for content in free text, but this schema makes generation repeatable.

## Presentation (PPTX) request
```json
{
  "type": "pptx",
  "title": "Deck title",
  "author_line": "Name | Department",
  "slides": [
    {
      "layout": "WHU_Slide_White_Textmaster",
      "topic": "Topic",
      "headline": "Here is a two-line headline",
      "subheadline": "Optional subhead",
      "bullets": ["Point 1", "Point 2"],
      "body": "Optional paragraph text",
      "image": null
    }
  ]
}
```

## Report (DOCX/PDF) request
```json
{
  "type": "docx",
  "title": "Report title",
  "subtitle": "Optional subtitle",
  "author_line": "Name | Department",
  "sections": [
    {"heading": "Section heading", "paragraphs": ["Text..."], "bullets": ["A", "B"]}
  ]
}
```

## Dashboard (XLSX) request
```json
{
  "type": "xlsx",
  "title": "Dashboard title",
  "kpis": [{"label": "Applicants", "value": 1234}, {"label": "Conversion", "value": "12%"}],
  "data": {
    "columns": ["Month", "Leads", "Applicants"],
    "rows": [["2026-01", 120, 45], ["2026-02", 150, 60]]
  }
}
```
