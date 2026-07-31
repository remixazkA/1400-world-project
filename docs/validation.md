# Validation strategy

## Purpose

Territorial quality is partly measurable and partly perceptual. A province can satisfy formal rules while still looking geographically wrong, and a visually convincing map can hide disconnected cells or serious distribution errors.

Project 1400 therefore combines quantitative checks with structured visual review.

## Defect taxonomy

### Connectivity

- disconnected components assigned to one territory;
- technically connected shapes held together by a narrow corridor;
- isolated residual cells;
- incorrect crossing of impassable terrain.

### Shape

- extreme elongation;
- branching tendrils;
- slivers and very small residual territories;
- excessive perimeter relative to area;
- repetitive or unnaturally geometric borders.

### Geographic coherence

- implausible crossing of major mountain systems;
- inappropriate river behaviour;
- weak treatment of peninsulas, islands or archipelagos;
- coastal territories with accidental or meaningless sea access;
- borders that ignore strong local geographic structure.

### Density and scale

- regional territory count outside its target range;
- extreme size outliers without geographic justification;
- excessive concentration around one variable, such as population;
- sparse regions becoming strategically empty.

## Quantitative checks

The validation layer can evaluate:

- component count and contiguity;
- territory-size distribution and outliers;
- adjacency validity;
- elongation and compactness indicators;
- narrow connections and sliver thresholds;
- target count deviation;
- barrier crossings;
- unassigned or duplicated cells;
- changes in defect counts between iterations.

Metrics are treated as diagnostic evidence, not as a single universal quality score.

## Visual review

Structured visual review checks characteristics that are difficult to express numerically:

- whether regional density has a believable rhythm;
- whether borders respond to terrain without tracing every feature mechanically;
- whether coastlines and islands remain readable;
- whether the result contains repeated procedural patterns;
- whether a territory appears strategically meaningful;
- whether a technically acceptable result still looks artificial.

## Regional test suite

Test regions are selected to expose different failure modes:

| Region type | Examples of what it tests |
|---|---|
| Mixed terrain and coastline | Iberia |
| Narrow peninsula | Italy |
| Dense territorial structure | Central Europe |
| Mountains and fragmented geography | Balkans and Caucasus |
| Desert and sparse settlement | Arabia and Sahara |
| High population and major rivers | India |
| Tropical forest and large river basins | Amazon basin |
| Islands and fragmented coastline | Indonesia and Southeast Asia |
| Flat, low-density interior | Steppe and Siberia |

## Regression workflow

1. Generate a controlled regional output.
2. Record quantitative defects and visual observations.
3. Classify each failure by likely stage or rule.
4. Change one explainable part of the model.
5. Rerun comparable regions with the same inputs.
6. Compare the intended improvement and any new defects.
7. Test geographically different regions.
8. Retain the change only if system-wide quality improves.

## Acceptance principle

The target is not a perfect border in every location. The target is stable, explainable and broadly convincing performance across the world, with serious defects rare enough to identify and improve systematically.
