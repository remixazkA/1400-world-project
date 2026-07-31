# QA case study: repairing unassigned spatial holes

## Problem

After independently generated superregions were combined, the global integration test found active playable cells that did not belong to any province. A visually convincing map could still conceal these gaps, so completeness was evaluated directly at cell level.

The validation stage detected:

- **924,750 unassigned active cells**;
- **35,639 connected components**;
- a largest component containing **123,505 cells**.

This was treated as a pipeline defect rather than as acceptable residual noise.

## Repair strategy

The repair process classified connected hole components by scale and context:

- **35,491 small components** were absorbed into compatible neighbouring territories;
- **148 large components** were rebuilt rather than forced into a single neighbour;
- **686 new provinces** were created where absorption would have produced implausible territorial shapes.

The repair operated against the world cell layer, adjacency graph and available regional inputs. Its purpose was to restore complete assignment while preserving contiguity and avoiding arbitrary long-distance attachment.

## Result

| Measure | Before repair | After repair |
|---|---:|---:|
| Assigned active playable cells | 23,222,109 | 24,146,859 |
| Unassigned active playable cells | 924,750 | 0 |
| Patched cells | — | 924,750 |

All detected active cells were assigned and the final validation reported **zero remaining holes**.

## Subsequent cleanup

Completeness alone does not guarantee good shapes. After repairing the gaps, four additional cleanup passes reconsidered local province membership and reassigned **230,178 cells**. The post-processing stage also evaluated 53 merge candidates and merged 20 provinces, producing a current total of **31,264 final provinces**.

## Why this case matters

This case demonstrates several parts of the project's quality approach:

- validation is performed on the full cell set, not only through screenshots;
- defects are quantified before correction;
- repair methods differ according to component scale;
- results are checked again after the transformation;
- completeness and visual quality are treated as related but separate requirements.

It also illustrates the project owner's role: defining acceptable behaviour, identifying the defect class, evaluating the repair strategy and validating the resulting world output while the technical implementation is produced through AI-assisted workflows.

## Limitations

Zero unassigned cells establishes topological completeness, not historical or geographic perfection. Individual repaired provinces still require shape, density, barrier and regional-coherence review. This case therefore documents one passed quality gate inside a wider iterative validation process.
