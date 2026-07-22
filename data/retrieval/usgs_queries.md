# USGS Instantaneous-Values Queries

Continuous discharge and turbidity records for this study were retrieved from
the U.S. Geological Survey (USGS) Instantaneous Values web service.

## Endpoint

```text
https://waterservices.usgs.gov/nwis/iv/
```

## Study period

```text
2017-10-13 through 2023-12-20
```

## Parameters

| Variable | USGS parameter code |
|---|---:|
| Discharge | `00060` |
| Turbidity | `63680` |

## Study stations

| USGS site number | Station |
|---:|---|
| `16238000` | Makiki Stream at King Street Bridge |
| `16247100` | Mānoa-Pālolo Drainage Canal at Moʻiliʻili |
| `16265000` | Kawa Stream at Kāneʻohe |
| `16274100` | Kāneʻohe Stream below Kamehameha Highway |

## Query template

```text
https://waterservices.usgs.gov/nwis/iv/?format=json&sites={SITE_NUMBER}&startDT=2017-10-13&endDT=2023-12-20&parameterCd=00060,63680&siteStatus=all
```

## Site-specific requests

### Makiki Stream: `16238000`

```text
https://waterservices.usgs.gov/nwis/iv/?format=json&sites=16238000&startDT=2017-10-13&endDT=2023-12-20&parameterCd=00060,63680&siteStatus=all
```

### Mānoa-Pālolo Drainage Canal: `16247100`

```text
https://waterservices.usgs.gov/nwis/iv/?format=json&sites=16247100&startDT=2017-10-13&endDT=2023-12-20&parameterCd=00060,63680&siteStatus=all
```

### Kawa Stream: `16265000`

```text
https://waterservices.usgs.gov/nwis/iv/?format=json&sites=16265000&startDT=2017-10-13&endDT=2023-12-20&parameterCd=00060,63680&siteStatus=all
```

### Kāneʻohe Stream: `16274100`

```text
https://waterservices.usgs.gov/nwis/iv/?format=json&sites=16274100&startDT=2017-10-13&endDT=2023-12-20&parameterCd=00060,63680&siteStatus=all
```

## Processing summary

The raw JSON responses were saved before processing. The analysis workflow then:

1. extracted timestamped values and USGS qualifier fields;
2. separated discharge and turbidity time series;
3. converted timestamps to a consistent timezone;
4. removed or flagged invalid observations;
5. constructed regular analysis grids;
6. split records at data gaps into continuous valid segments; and
7. passed the resulting series into the event-screening workflow.

## Raw-data policy

Raw API responses are not tracked in this repository because they can be
regenerated from the public USGS service. Processed outputs used in the
manuscript are stored under `data/processed/`.

## Notes

Parameter availability differs by station and date. Including a parameter code
in a request does not guarantee that observations exist for the full study
period.

The raw USGS response remains the source record. Processed files may include
quality filtering, resampling, gap segmentation, and analysis-specific fields
added by this project.
