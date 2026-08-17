# Bank Market Analyzer

Market categorization engine and supporting data for analyzing a regional bank footprint across size tier, growth tier, and franchise stage.

## Contents

| Path | Description |
|------|-------------|
| `market_categorizer.py` | Python engine — classifies footprint markets using cached public data (no network calls) |
| `market_scores.csv` / `market_scores.xlsx` | Scored output for all footprint markets |
| `methodology.md` | Full methodology write-up with thresholds, sources, and caveats |
| `methodology_overview.html` | Visual overview of the framework |
| `data/` | Cached public inputs (Census, BEA, BLS, FDIC SOD, OMB crosswalks) |
| `out/` | Export copies of scores and methodology |

## Quick start

```bash
python market_categorizer.py
```

Requires Python 3.10+ and dependencies listed in the script header. All source data is local under `data/` — the script does not call external APIs at runtime.

## Framework

Each market receives three labels:

- **Size tier** — Census population within OMB market boundaries (Major / Secondary / Small Metro, Micropolitan, Rural)
- **Growth tier** — Composite of population, migration, GDP, employment, and income vs. all US metros
- **Franchise stage** — FDIC deposit and branch history through ordered classification gates

See `methodology.md` for definitions, data sources, and external-use cautions.
