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
