# Water Quality Portal Queries

Discrete field-activity records used to construct storm-sampling campaigns were
retrieved from the Water Quality Portal (WQP).

## Source

The Water Quality Portal provides public water-quality records contributed by
USGS and other participating organizations.

## Study period

```text
2017-10-13 through 2023-12-20
```

## Monitoring locations

| USGS site number | WQP monitoring-location identifier |
|---:|---|
| `16238000` | `USGS-16238000` |
| `16247100` | `USGS-16247100` |
| `16265000` | `USGS-16265000` |
| `16274100` | `USGS-16274100` |

## Records retrieved

The retrieval workflow collected the WQP activity and station information
needed to identify storm-related field visits and construct campaign windows.
Relevant fields included:

- organization identifier;
- monitoring-location identifier;
- activity identifier;
- activity start date;
- activity start time;
- activity type;
- sample media;
- project or sampling-design information;
- hydrologic-condition or event descriptors; and
- station metadata.

## Query logic

The same retrieval logic was applied to each monitoring location:

```text
Monitoring location: USGS-{SITE_NUMBER}
Start date: 2017-10-13
End date: 2023-12-20
Source organization: USGS / NWIS records available through WQP
Requested content: station and sampling-activity records
```

Locations queried:

```text
USGS-16238000
USGS-16247100
USGS-16265000
USGS-16274100
```

## Campaign construction

Individual WQP records were not treated automatically as independent storm
events. The processing workflow:

1. retained records meeting the study's storm-related labeling criteria;
2. parsed activity dates and times;
3. associated each activity with a study station;
4. grouped temporally related field activities into campaigns;
5. constructed campaign windows using the finalized methods;
6. checked campaign eligibility separately for each detector and available
   continuous record; and
7. exported campaign-level diagnostics used in evaluation.

Campaign-level outputs are stored in:

```text
data/processed/campaign_diagnostics/
```

## Raw-data policy

Raw WQP downloads are not tracked in this repository because the source records
are publicly retrievable. The repository instead provides:

- monitoring-location identifiers;
- study dates;
- retrieval and processing code;
- campaign diagnostics;
- detector outputs; and
- final evaluation tables.

## Reproducibility note

Water Quality Portal records can change as contributing organizations revise or
add data. Future downloads may therefore differ slightly from the records used
for the manuscript.

For a fully frozen reproduction, the project should also preserve or record:

- retrieval date;
- exact WQP endpoint and profile;
- complete request parameters;
- downloaded filenames; and
- optional SHA-256 checksums of the original responses.

The exact endpoint, profile name, and request syntax should be confirmed against
the final retrieval script before the repository is tagged as version `1.0.0`.
