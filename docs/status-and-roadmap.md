# Project status and roadmap

Project 1400 is under active development. The current phase focuses on refining territorial generation and validation across geographically different regions while preserving a common global methodology.

The project is iterative by design: regional tests expose failure modes, proposed changes are evaluated against comparable outputs, and improvements are retained only when they do not create unacceptable regressions elsewhere.

## Established foundation

The project currently has a documented foundation consisting of:

- a global spatial base of approximately 24.3 million hexagonal cells;
- roughly 72 million explicit adjacency relationships;
- a target of approximately 32,000 final territorial units;
- a staged architecture separating global preprocessing from regional generation;
- integration principles for geographic, environmental and historical inputs;
- explicit requirements for contiguity, shape quality and geographic coherence;
- a validation approach combining quantitative checks and structured visual review;
- reproducible, inspectable and incrementally saved processing stages.

## Current work

Current development is concentrated on:

- calibrating regional density within the global territorial budget;
- refining seed selection, constrained growth and cleanup behaviour;
- improving the treatment of rivers, mountains, coastlines and impassable terrain;
- detecting slivers, excessive elongation, fragmentation and artificial borders;
- comparing changes across geographically diverse test regions;
- preparing representative outputs and validation cases for publication.

## Next milestones

1. Expand the visual gallery with regional examples and before-and-after comparisons.
2. Consolidate a repeatable suite of geographically diverse regional test cases.
3. Improve quantitative summaries for shape, contiguity, density and target compliance.
4. Run broader regression comparisons across combined regions.
5. Prepare a global generation candidate once regional behaviour is sufficiently stable.
6. Document the resulting limitations, unresolved edge cases and lessons learned.

## Known limitations

- The published repository documents the system design and quality process, but not the complete processing stack or source datasets.
- The generated territories are intended as plausible strategic units, not exact political or administrative borders from the year 1400.
- Parameters and outputs remain provisional while regional calibration continues.
- A convincing result in one region does not by itself demonstrate global generalisation.
- Some edge cases will require further model refinement even after a first global candidate is produced.

## Definition of progress

Progress is not measured only by producing more territories or more detailed images. A meaningful improvement must be reproducible, explainable and demonstrably beneficial across more than one geographic context.

The roadmap may therefore change when testing reveals a more important global failure mode.
