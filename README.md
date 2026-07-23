# Public-Data Stormwater Event Screening
Reproducible public-data framework for stormwater event screening across Oʻahu streams using BOCPD, USGS records, and Water Quality Portal campaign labels. Manuscript, A Public-Data Framework for Online Stormwater Event Screening Across Oʻahu Streams, submitted to OJSS.

This repository contains the code, processed outputs, and figure-generation workflow for:

**A Public-Data Framework for Online Stormwater Event Screening Across Oʻahu Streams**
**Authors:** Arvid Sword and Hanuma Kota  

The analysis combines:

- U.S. Geological Survey instantaneous discharge and turbidity records
- Water Quality Portal field-activity labels
- Campaign-based event construction
- Bayesian Online Changepoint Detection
- A static station-specific discharge p95 baseline
- Chronological holdout evaluation at Makiki Stream
- Locked transfer to three external Oʻahu stations

## Study stations

| Station | USGS ID | Role |
|---|---:|---|
| Makiki Stream at King St. bridge | 16238000 | Development and temporal holdout |
| Mānoa-Pālolo Drainage Canal at Moʻiliʻili | 16247100 | External transfer |
| Kawa Stream at Kāneʻohe | 16265000 | External transfer |
| Kāneʻohe Stream below Kamehameha Hwy | 16274100 | External transfer |

The nominal analysis period was **2017-10-13 through 2023-12-20**.

USGS parameter codes:

- Discharge: `00060`
- Turbidity: `63680`

## Repository structure

```text
stormwater-event-screening/
- README.md
- LICENSE
- CITATION.cff
- requirements.txt
- src/          # Data processing, BOCPD, alarm extraction, and evaluation code
- data/         # Data documentation and small reproducibility inputs
- figures/      # Final manuscript figures

