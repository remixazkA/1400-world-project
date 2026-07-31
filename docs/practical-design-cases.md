# Practical design cases

[← Project README](../README.md) · [Results gallery](results-and-examples.md) · [Technical evidence](technical-evidence.md) · [Quantified QA case](qa-case-study-holes.md)

This page reconstructs recurring design and validation cases from the project's development discussions and decision history. They show how an observed risk or weak result was translated into requirements, trade-offs and validation criteria.

These cases are qualitative unless a linked evidence page provides measurements. They should not be read as claims that every local calibration problem is permanently closed. The separate [unassigned-spatial-holes case study](qa-case-study-holes.md) contains the fully quantified before-and-after example.

---

## 1. Rivers: influence without mechanical splitting

### Problem

Treating every river as an absolute border would divide dense drainage networks into excessive fragments. It would also prevent territories from forming around river valleys, even though rivers can act historically as frontiers, transport corridors or the internal axis of a region.

### Decision

Most rivers are represented as **soft crossing costs** rather than universal hard barriers. Their influence can increase with scale, hierarchy and local context, while exceptional rivers or deltas may receive stronger treatment.

### Validation logic

- Check whether river systems influence boundaries without dictating every boundary.
- Look for excessive fragmentation in dense drainage basins.
- Verify that plausible cross-river territories can still form.
- Compare contrasting environments such as Iberia, Mesopotamia and the Indian subcontinent.

### Current interpretation

The rule establishes a globally reusable tendency rather than a guarantee that every river will become—or never become—a border. Local calibration remains part of regional validation.

---

## 2. Mountains: preventing implausible cross-range provinces

### Problem

Elevation alone does not adequately represent accessibility. With weak terrain constraints, territorial growth can cross major ranges too easily, joining unrelated valleys or producing long provinces that span implausible terrain.

### Decision

Mountain influence combines elevation, slope, continuity and explicit impassability. Severe mountain systems receive stronger treatment than most rivers, while passes and transition zones prevent the model from reducing every range to an impermeable wall.

### Validation logic

- Inspect whether major ranges structure territorial growth.
- Detect elongated provinces crossing several valleys or ridges.
- Check for isolated fragments created by barriers that are too strong.
- Use contrasting prototypes such as the Alps, Balkans, Caucasus and Himalaya-adjacent regions.

### Current interpretation

The objective is not to trace every watershed mechanically. It is to prevent obviously weak connections while preserving geographically plausible corridors.

---

## 3. Deserts: controlling density without erasing strategic space

### Problem

Uniform territorial density would over-segment deserts and other sparsely settled environments. A population-only model would create the opposite risk: reducing large frontier regions to oversized, strategically empty territories and reproducing uncertain historical estimates too literally.

### Decision

Historical population is used as a weighted influence, not a direct blueprint. Broad regional targets act as a finite allocation budget, while terrain, accessibility, corridors, coasts and strategic context help determine how that budget is distributed.

### Validation logic

- Compare province-size distributions between settled corridors and desert interiors.
- Check that low-population regions are coarser without becoming meaningless.
- Preserve meaningful coastal, riverine and trans-Saharan corridors.
- Review the Sahara, Arabia and neighbouring settled zones together rather than in isolation.

### Current interpretation

Regional targets deliberately include design judgement. The goal is controlled variation, not mathematically uniform density or a map dictated by one uncertain demographic source.

---

## 4. Coasts and islands: avoiding strips and arbitrary fragmentation

### Problem

Generic continental growth rules behave poorly around fragmented coastlines and archipelagos. They can create narrow coastal strips, accidental sea access, excessive island micro-provinces or the loss of strategically meaningful islands.

### Decision

Coastal access is treated as an important structural attribute but balanced against compactness and inland connectivity. Islands and archipelagos use specialised logic for minimum viable size, grouping, maritime proximity and preservation of significant locations.

### Validation logic

- Detect elongated coastal provinces created only by shoreline following.
- Verify that coastal territories have meaningful rather than accidental sea access.
- Check whether small islands are grouped coherently without erasing important distinctions.
- Compare the Caribbean, Aegean, Malay world, Japan and other fragmented coasts.

### Current interpretation

Island treatment necessarily mixes geography with gameplay judgement. The system aims for consistent rules and explicit exceptions rather than one-province-per-island or indiscriminate merging.

---

## 5. Regional iteration without rebuilding the world

### Problem

Running every experiment across the complete global dataset would make development slow, difficult to inspect and expensive to recover after failure. Entirely independent regional pipelines, however, would create inconsistent assumptions and visible seams.

### Decision

Expensive global preparation is performed once and persisted. Territorial generation, cleanup and validation can then be rerun by superregion against the same global cell, attribute and adjacency foundation. Checkpoints and deterministic configuration make versions comparable.

### Validation logic

- Confirm that identical inputs and parameters reproduce identical regional outputs.
- Reintegrate regional results against the global active-cell layer.
- Detect missing cells, duplicate identifiers and seam artefacts.
- Compare parameter changes across several contrasting regions before accepting them globally.

### Current interpretation

This architecture enabled regional experimentation while preserving global traceability. The quantified [integration-hole case study](qa-case-study-holes.md) demonstrates the final completeness check and repair cycle on the current world snapshot.

---

## 6. High-latitude distortion: separating topology from presentation

### Problem

The current gallery renders the working data in a metre-based equal-area projection. At high latitudes, this visibly stretches and deforms shapes. A reviewer could mistake that display effect for a province-generation defect.

### Decision

Projection is treated as a presentation layer, distinct from territorial topology and assignment. The working projection remains useful for global processing and area-aware operations, while publication views should use a presentation-appropriate reprojection or explicitly state the limitation.

### Validation logic

- Compare high-latitude regions under more than one projection.
- Distinguish changed screen geometry from changed cell ownership or adjacency.
- Keep projection metadata with every published map.
- Avoid judging compactness from a distorted display alone.

### Current interpretation

The distortion is a known visual limitation of the current screenshots, especially in northern Europe and other high-latitude regions. It does not by itself indicate broken province topology.

---

## What these cases demonstrate

Together, these cases show a repeatable functional-analysis pattern:

1. identify a failure mode or global design risk;
2. separate symptoms from underlying causes;
3. compare plausible alternatives;
4. define a rule with explicit trade-offs;
5. test it across contrasting regional prototypes;
6. check that a local improvement does not create a global regression.

The purpose of documenting them is not to imply that the map is finished. It is to make the project's reasoning, quality criteria and iterative decision-making inspectable.

[Back to top ↑](#practical-design-cases)
