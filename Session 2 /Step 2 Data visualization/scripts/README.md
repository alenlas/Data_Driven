# Scripts

These scripts are optional helpers. They generate WHU-styled artifacts using the bundled assets.

## 1) Create a presentation from JSON
```bash
python scripts/create_pptx.py --spec assets/example_pptx_spec.json --out out.pptx
```

## 2) Create a Word report from JSON
```bash
python scripts/create_docx.py --spec assets/example_docx_spec.json --out out.docx
```

## 3) Create an Excel dashboard from JSON
```bash
python scripts/create_dashboard_xlsx.py --spec assets/example_xlsx_spec.json --out out.xlsx
```
