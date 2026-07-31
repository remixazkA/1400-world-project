# Project status and roadmap

[← Project README](../README.md) · [Results gallery](results-and-examples.md) · [Technical evidence](technical-evidence.md)

Project 1400 is under active development. The current phase focuses on refining territorial quality across geographically different regions while preserving a common global methodology.

The project is iterative by design: tests expose failure modes, proposed changes are evaluated against comparable outputs, and improvements are retained only when they do not create unacceptable regressions elsewhere.

## Established foundation

The current verified snapshot includes:

- **32,437,371** total global hexagonal cells;
- **24,146,859** active playable cells, all assigned;
- **97,045,268** explicit adjacency relationships;
- **31,264** final provinces after post-processing;
- **43** operational superregions supporting regional execution and validation;
- a staged architecture separating global preprocessing from regional generation;
- explicit requirements for contiguity, shape quality and geographic coherence;
- reproducible, inspectable and incrementally saved processing stages.

## Evidence published in this repository

- A [global regional gallery](results-and-examples.md) covering temperate, arid, mountainous, coastal and archipelagic environments.
- A [verified technical snapshot](technical-evidence.md) distinguishing total cells, active cells, adjacency relationships and final provinces.
- A [QA case study](qa-case-study-holes.md) documenting the detection and repair of 924,750 unassigned active cells.
- A transparent [project-role statement](project-role.md) separating requirements, validation and decision ownership from AI-assisted Python implementation.

## Current work

Current development is concentrated on:

- calibrating regional density within the global territorial budget;
- refining seed selection, constrained growth and cleanup behaviour;
- improving the treatment of rivers, mountains, coastlines and impassable terrain;
- detecting slivers, excessive elongation, fragmentation and artificial borders;
- comparing changes across geographically diverse test regions;
- identifying presentation artefacts separately from defects in territorial logic.

## Next milestones

1. Publish focused before-and-after comparisons for representative defect classes.
2. Consolidate a repeatable suite of geographically diverse regional regression tests.
3. Expand quantitative summaries for shape, contiguity, density and target compliance.
4. Add structured provenance records for production datasets where licensing permits disclosure.
5. Produce presentation maps in a display projection better suited to familiar regional shapes.
6. Prepare a broader global generation candidate once regional behaviour is sufficiently stable.

## Known limitations

- The generated territories are plausible strategic units, not exact political or administrative borders from the year 1400.
- Parameters and outputs remain provisional while regional calibration continues.
- A convincing result in one region does not by itself demonstrate global generalisation.
- The published regional screenshots use **EPSG:6933**, a metre-based equal-area projection. It preserves area for analysis but visibly distorts shapes at high latitudes; this presentation effect does not change province membership or adjacency.
- Zero unassigned active cells proves topological completeness, not geographic or historical perfection.
- The complete processing stack and raw datasets are not published because the working environment includes large third-party and intermediate data whose licensing and size are unsuitable for this repository.

## Definition of progress

Progress is not measured only by producing more territories or more detailed images. A meaningful improvement must be reproducible, explainable and demonstrably beneficial across more than one geographic context.

The roadmap may therefore change when testing reveals a more important global failure mode.

---

[← Project README](../README.md) · [Architecture](architecture.md) · [Validation strategy](validation.md)
