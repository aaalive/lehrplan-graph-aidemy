# LernGraph


## What it is
LernGraph turns Saxony curriculum PDFs and text into a graph of Lernbereiche, goals, and prerequisites. It uses its own query language to show what topics need other topics first. It also has a simple offline web UI.

## Why it matters to me
I am a parent, and it is hard to see how school topics connect across grades and subjects. With this tool, I can quickly check what Klasse 7 Mathe needs from Klasse 5 and 6.

## Definition of done
All example queries in `docs/queries.md` return the right answers, and all gold Lernbereiche parse with no missing goals and no wrong edges.The full project will not be finished in 8 hours. In 8 hours, I expect to build the parser and edges for Mathe, plus a first query engine.


## Data

| Path | What | On GitHub? |
|---|---|---|
| `data/raw/sachsen_gy_topics.csv` | Lehrplan text, Gymnasium Sachsen, 9 subjects (no Biologie), 1,666 topic rows with cross-references in `curriculum_text` | no (licence), only in the upload |
| `data/raw/*.pdf`, `*.txt` | official Lehrplan PDFs and `pdftotext -layout` copies | no (licence), only in the upload |
| `data/raw/SOURCES.md` | where each source comes from, download date, known limits | yes |
| `data/gold/lernbereiche.csv`, `edges.csv` | hand-checked sample: Lernbereiche and prerequisite edges, used as test answers | yes |
| `data/materials_sample.csv` | 18 invented learning materials (Mathe, Physik, Deutsch, Geschichte, Kl. 5-8) for coverage queries | yes |
| `docs/queries.md` | example queries with expected answers | yes |

Known limit of `sachsen_gy_topics.csv`: one Lernbereich was split into up to 6 topic rows,
and the Lernbereich number itself is not stored. Cross-references point to Lernbereich numbers
(`→ ETH, Kl. 5, LB 4`), so the PDFs are needed for the exact structure.

## Repository layout

```
data/raw/      official sources (not on GitHub)
data/gold/     hand-checked test answers
docs/          example queries
```

## Setup

Python 3.12, standard library first. Everything runs offline; all data is in the repo upload.

```bash
python3 -m venv .venv && . .venv/bin/activate
```

## Scope

- Subjects: Mathematik, Physik, Chemie, Deutsch, Geschichte, Geographie, Ethik, Englisch, Französisch.
- Not in scope: Biologie, anything security-related, any online service.

## Licence

MIT for the code and the files written for this repo (see `LICENSE`). The official Lehrplan
documents belong to the Sächsisches Staatsministerium für Kultus and are not covered by it.
