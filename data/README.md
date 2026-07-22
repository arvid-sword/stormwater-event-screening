# Data

This repository uses publicly available hydrologic and water-quality records.

## Sources

- U.S. Geological Survey (USGS) Instantaneous Values API
- Water Quality Portal (WQP)

## Stations

| Station | USGS ID |
|---------|---------|
| Makiki Stream | 16238000 |
| Mānoa-Pālolo Drainage Canal | 16247100 |
| Kawa Stream | 16265000 |
| Kāneʻohe Stream | 16274100 |

## Raw data

Raw downloads are **not** distributed with this repository because they are publicly available from their original providers.

Scripts in `src/` reproduce the downloads from the public APIs.

## Processed data

Processed datasets are provided in `processed/`.

These include:

- event campaign summaries
- evaluation tables
- station summaries
- performance metrics
