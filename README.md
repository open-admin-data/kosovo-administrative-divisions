# Kosovo Administrative Divisions / Kosova



## Overview

| Item | Details |
|------|---------|
| District | 7 |
| Municipality | 38 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/xk](https://openadmindata.org/xk/) |
| API | [openadmindata.org/api/xk](https://openadmindata.org/api/xk/) |
| National Anthem | [🎵 Listen & Download Kosovo National Anthem MP3](https://onlygames.me/national-anthems/xk/) |

## Browse by District

| # | District | Municipalitys | Link |
|---|----|----|------|
| 1 | Peja-Pec | 3 | [Browse](divisions/peja-pec-xk01/) |
| 2 | Gjakova | 4 | [Browse](divisions/gjakova-xk02/) |
| 3 | Prizren | 5 | [Browse](divisions/prizren-xk03/) |
| 4 | Ferizaj | 5 | [Browse](divisions/ferizaj-xk04/) |
| 5 | Gjilan | 7 | [Browse](divisions/gjilan-xk05/) |
| 6 | Pristina | 7 | [Browse](divisions/pristina-xk06/) |
| 7 | Mitrovica | 7 | [Browse](divisions/mitrovica-xk07/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-district.json](data/all-district.json) | JSON | All 7 district records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 38 municipality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-district.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['municipality']} municipalitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-district.json", "utf-8"));
console.log(`Total: ${data.length} districts`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=district, 2=municipality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{district-slug}/
```

Municipalitys are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-district links
- [Per-district data](docs/llms-full/) — Full data by district

## Citation

```
Kosovo Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/kosovo-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
