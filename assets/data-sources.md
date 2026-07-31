# Data-source categories

Project 1400 combines heterogeneous geographic and historical evidence. This file records the purpose of each source category without redistributing third-party datasets.

| Category | Intended use | Main quality questions |
|---|---|---|
| Elevation | Relief context and terrain structure | Resolution, voids, vertical reference and coastal consistency |
| Slope | Accessibility and barrier strength | Derivation method, scale sensitivity and artefacts |
| Rivers and lakes | Hydrological influence, crossings and connectivity | Hierarchy, width proxies, topology and seasonal uncertainty |
| Coastlines | Land–sea boundary and coastal access | Generalisation, islands, narrow channels and projection effects |
| Climate | Broad environmental context | Classification date, spatial resolution and historical suitability |
| Vegetation | Land-cover character and environmental constraints | Modern bias, category overlap and missing coverage |
| Historical population | Regional density and seed importance | Temporal fit, uncertainty, spatial interpolation and source disagreement |
| Impassable terrain | Strong restrictions on growth and movement | Threshold definition, transition zones and false isolation |

## Selection principles

- Prefer global or near-global coverage when consistency matters.
- Record known limitations before a dataset influences the model.
- Avoid treating modern conditions as exact historical evidence.
- Preserve source resolution and uncertainty in later interpretation.
- Use several independent variables instead of relying on one composite layer.
- Do not publish third-party data unless its licence clearly permits redistribution.

## Provenance policy

Each production dataset should eventually have a provenance record containing its title, provider, version or access date, licence, spatial resolution, projection, processing steps and known limitations. Source selection is part of the quality-assurance process, not merely a preprocessing task.
