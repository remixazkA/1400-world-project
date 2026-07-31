# Technical evidence

[← Project README](../README.md) · [Results gallery](results-and-examples.md) · [QA case study](qa-case-study-holes.md)

This page records measurable evidence produced by the current Project 1400 pipeline. It separates the complete global spatial grid from the subset of cells that are active and playable.

## Verified global snapshot

| Measure | Current value |
|---|---:|
| Total global hexagonal cells | 32,437,371 |
| Active playable cells | 24,146,859 |
| Adjacency relationships | 97,045,268 |
| Duplicate hex identifiers detected during the global merge | 0 |
| Assigned active playable cells | 24,146,859 |
| Unassigned active playable cells | 0 |
| Final provinces after post-processing | 31,264 |
| Province size, 10th percentile | 201 cells |
| Province size, median | 583 cells |
| Province size, 90th percentile | 1,580 cells |

The difference between total and active cells reflects water and locations excluded by the current playability and impassability masks. The final playable layer therefore contains **24.15 million assigned cells inside a 32.44-million-cell global spatial foundation**.

## Coverage and territorial completion

The current final layer contains every active playable cell and reports no unassigned playable locations. Province membership is therefore complete across the active map.

The global output is stored in EPSG:6933 and divided operationally into **43 superregions**. Those partitions support regional execution, target allocation and validation without becoming intended visible borders in the final world.

## Hole detection and repair

An intermediate integration stage detected gaps left between regional outputs:

| Measure | Value |
|---|---:|
| Unassigned hexes detected | 924,750 |
| Connected hole components | 35,639 |
| Largest component | 123,505 cells |
| Small components absorbed | 35,491 |
| Large components rebuilt | 148 |
| New provinces created during repair | 686 |
| Patched hexes | 924,750 |
| Remaining holes | 0 |

The result demonstrates that completeness is tested explicitly rather than assumed from visual inspection. See the [full QA case study](qa-case-study-holes.md).

## Post-processing evidence

After hole repair, the refinement stage performed four cleanup passes:

| Pass | Cells reassigned |
|---:|---:|
| 1 | 60,741 |
| 2 | 58,952 |
| 3 | 56,497 |
| 4 | 53,988 |
| **Total** | **230,178** |

The same stage identified 53 merge candidates and merged 20 provinces. The resulting snapshot contains 31,264 final provinces.

## Evidence boundaries

These figures come from pipeline-generated summaries and validation reports associated with the current working dataset. They describe a reproducible project snapshot, not an immutable final release. Values may change as inputs, masks, regional targets and cleanup rules are refined.

The complete raw datasets are not included in this repository because the working environment contains hundreds of gigabytes of GeoPackage, raster, Parquet and SQLite data. The repository publishes compact evidence, methodology and representative visual outputs instead.

---

[← Project README](../README.md) · [Validation strategy](validation.md) · [Status and roadmap](status-and-roadmap.md)
