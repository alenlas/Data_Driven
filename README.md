## Data_Driven

A small collection of Jupyter notebooks and sample Excel data that document a step-by-step data preparation workflow for a "Session 1" data exercise. The notebooks walk through generating variables, building an organization database, preprocessing headquarter location data, and processing announced dates.

This repository is organized as a sequence of steps (Step 1 .. Step 4). Each step contains one or two notebooks (an "empty" template and a completed notebook) and any data files used by the notebooks.

### Project structure (top-level)

- `Session 1/`
  - `Step 1 Create new metric/` — notebooks for generating variables and example transaction data.
  - `Step 2 Creation of organization database/` — notebooks that create and preprocess the organization database; contains `Creation of organization database.ipynb` and an `empty` template version.
  - `Step 3 Process headquarter information/` — notebooks and spreadsheets for preprocessing headquarter locations.
  - `Step 4 Process announded date/` — notebooks and spreadsheets for preprocessing announced dates and transactions.

Each step folder includes the Excel files used for examples (for example `organizations.xlsx`, `transactions preprocessed.xlsx`, etc.).

## Getting started

Prerequisites
- Python 3.8+ (3.9/3.10 recommended)
- A virtual environment (venv or conda)

Quick setup (macOS / zsh):

```bash
# create and activate a venv
python3 -m venv .venv
source .venv/bin/activate

# install minimal dependencies
pip install -r requirements.txt

# start JupyterLab (or `jupyter notebook` if you prefer)
jupyter lab
```

Open the notebooks from JupyterLab and run cells in order. If you prefer Jupyter Notebook, use `jupyter notebook` instead of `jupyter lab`.

## Recommended notebook run order

Run the notebooks step-by-step to preserve data flow and assumptions:
1. `Session 1/Step 1 Create new metric/` — run `generating variables.ipynb` (or use the `empty` template to re-create exercises)
2. `Session 1/Step 2 Creation of organization database/` — run `Creation of organization database.ipynb`
3. `Session 1/Step 3 Process headquarter information/` — run `Preprocess headquarter location.ipynb`
4. `Session 1/Step 4 Process announded date/` — run `Preprocess announced date.ipynb`

## Data files

This project stores example data as Excel files inside the step folders. The notebooks read and write `.xlsx` files. Be careful not to overwrite original files unless you intend to.

## Dependencies

See `requirements.txt` for a minimal set of packages used by the notebooks. If a notebook requires additional packages (for geocoding, mapping, or advanced analysis), the notebook header typically notes them.

## Contributing & extension ideas

- Add a `requirements-dev.txt` or `environment.yml` for reproducible environments (conda users).
- Add small data validation tests or a `Makefile` targets that run all notebooks end-to-end using `nbconvert` or `papermill`.
- Add short README files inside each Step folder describing inputs/outputs for that step.

## Assumptions and notes

- I assumed these notebooks are designed to be run interactively with Jupyter (not as a packaged application).
- The minimal `requirements.txt` covers common data packages; some notebooks may need extra libraries. If you want, I can scan the notebooks and create a more precise requirements list.

## Next steps (optional)

- I can: generate a more precise `requirements.txt` by scanning imports in the notebooks; add a small `Makefile` or scripts to run all notebooks headless; or create per-step README files.

---
Project owner: repository files in this folder (no contact email provided)
