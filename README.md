# matteo_aksel

# F1 Track Personality 2020–2025

**Authors:** Matteo Asscher & Aksel
**Course:** Foundations of Data Projects — Albert School (Prof. Jaime Aznar)

A six-season analysis of constructor–circuit affinity in Formula 1. We ask whether
certain constructors systematically over- or under-perform at specific circuits,
beyond what their seasonal strength would predict.

## Project structure

```
data/
  raw/         API and scraped data (immutable, timestamped)
  processed/   Analysis-ready parquet (timestamped)
reports/
  figures/     PNG charts for the deck
notebooks/
  01_api_collection.ipynb   Pull race results from jolpica-f1
  02_scraping.ipynb         Scrape circuit metadata from Wikipedia
  03_cleaning.ipynb         Clean, engineer features, join sources
  04_eda_viz.ipynb          Generate heatmap + 5 supporting charts
  05_final_report.ipynb     Narrative report
```

## How to reproduce

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
# Run notebooks 01 -> 02 -> 03 -> 04 -> 05 in order
```

## Headline finding

Across 2020–2025, constructor–circuit affinity is a real and measurable signal,
but it favors midfield teams. The Monza intuition is wrong: Ferrari finishes
at Monza about where it finishes everywhere else, while Williams is the
actual Monza specialist with a −3.4 mean delta over 6 races.

Full methodology and findings: see `notebooks/05_final_report.ipynb`.

## Data sources

- jolpica-f1 API (race results) — Ergast-compatible, free
- English Wikipedia (circuit metadata) — CC BY-SA 4.0
