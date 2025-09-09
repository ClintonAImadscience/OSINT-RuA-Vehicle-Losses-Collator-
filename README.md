# OSINT-RuA-Vehicle-Losses-Collator-


WarSpotting × ISW: Russian Unit Loss Enrichment (OSINT MVP)

TL;DR. I built a reproducible OSINT pipeline that turns WarSpotting loss events into structured data, then enriches those rows with the Institute for the Study of War’s Russian ORBAT (Oct 12, 2023) to add unit echelon / service / military district. Outputs are analyst-ready CSV/Excel and interactive maps.



What this project does

Normalize WarSpotting losses into a clean, tabular dataset (one row = one loss).

Visualize losses as an interactive Folium map (one dot per loss; filter by class/unit/date; multiple basemaps).

Enrich rows by resolving the referenced unit to an ISW ORBAT unit identity, adding organizational context.

Scope note (MVP): We do not include garrison basing or confidence scoring. ISW ORBAT is treated as organizational context (baseline as-of 2023-01-01), not current deployments.




Files in this repo

OSINT_RU_Vehicle_Losses_ETL.ipynb — WarSpotting ETL (raw → normalized CSV).

Visualizations_RU_Equipment_Losses (2).ipynb — Visualizer (Folium map with filters + HTML export).

ISW_ORBAT_ETL_and_Enrich.ipynb — ISW Enricher (parse ISW PDF → isw_units.csv, isw_hierarchy.csv, isw_aliases.csv; join back to WarSpotting).

warspotting_enriched.xlsx — Excel workbook with selected outputs for sharing (derived from the notebooks).

README.md — this file.


Quickstart


Install dependencies

pip install pandas folium pdfminer.six PyPDF2 rapidfuzz Unidecode


Stage inputs

WarSpotting normalized CSV (from the ETL notebook), e.g. warspotting_norm_2025-09-08.csv

ISW PDF: October 12, 2023 Russian Orbat_Final.pdf

Run notebooks in order

ETL: OSINT_RU_Vehicle_Losses_ETL.ipynb → produces warspotting_norm_*.csv

Visualizer: Visualizations_RU_Equipment_Losses (2).ipynb → exports loss_map_<run>.html

Enricher: ISW_ORBAT_ETL_and_Enrich.ipynb → writes:

isw_units.csv (unit attributes)

isw_hierarchy.csv (parent→child edges)

isw_aliases.csv (alias bank)

warspotting_enriched.csv (loss rows + ISW enrichment)







Acknowledgments & sources

WarSpotting — visually verified equipment losses (community OSINT).

Institute for the Study of War (ISW) — Russian ORBAT (Oct 12, 2023). Baseline date 2023-01-01.
