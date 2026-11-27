# Sources

Official Lehrpläne, Gymnasium Sachsen. Download page: https://www.schulportal.sachsen.de/lplandb/

| File | Fach | Schulart | Version | URL | Downloaded on |
|---|---|---|---|---|---|
| GY_MA.pdf | Mathematik | Gymnasium | 2004/2009/2011/2013/2019/2021 (file lp_gy_mathematik_2021.pdf) | https://www.schulportal.sachsen.de/lplandb/ | 2026-11-27 |
| | | | | | |

For every PDF there is a `.txt` copy made with `pdftotext -layout`.

## sachsen_gy_topics.csv

Lehrplan text for Gymnasium Sachsen, all subjects except Biologie (1,666 rows), copied from my own earlier
extraction of the official Lehrpläne. Columns: subject, grade, topic, source_list, block_index, language,
curriculum_text. Note: the original Lernbereiche were split into several topics (max 6 per Lernbereich),
so one Lernbereich can be several rows, and the own LB number is not stored. Cross-references
(`→ Fach, Kl. x, LB y` and `⇒ ...`) are kept inside curriculum_text.
Not on GitHub (same reason as the PDFs), only in the upload.
