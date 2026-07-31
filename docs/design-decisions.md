# Design decisions

This document records the major methodological choices behind Project 1400. The purpose is not only to state what the system does, but to explain why each approach was selected and what it costs.

## 1. Use a global hexagonal grid

**Decision:** represent the lowest spatial level as hexagonal cells.

**Why:** each regular cell has six adjacent neighbours at approximately equal distance, reducing the directional bias produced by square grids. The grid also creates a common analytical layer for heterogeneous raster and vector sources.

**Alternatives considered:** square raster cells, Voronoi cells, modern administrative polygons and direct polygon generation.

**Trade-off:** preprocessing and storage become expensive, but every later stage operates on one reproducible spatial graph.

## 2. Separate locations from provinces

**Decision:** treat low-level cells and final territories as distinct conceptual layers.

**Why:** high-resolution geographic evidence can be preserved without exposing millions of playable areas. Province boundaries can evolve without rebuilding the geographic foundation.

**Trade-off:** the pipeline requires explicit aggregation and two levels of spatial data.

## 3. Target approximately 32,000 territories

**Decision:** use a global target rather than an exact immutable total.

**Why:** the number balances geographic detail, strategic depth, readability, processing cost and future simulation cost.

**Alternatives considered:** uniform territory size, population-only allocation and equal counts by modern country.

**Trade-off:** increasing density in one region consumes a finite global budget and therefore affects others.

## 4. Use regional allocations inside the global target

**Decision:** constrain broad regions with explicit target ranges.

**Why:** a purely global score can overconcentrate territories in densely populated or highly fragmented areas and leave the rest of the world excessively coarse.

**Trade-off:** this introduces controlled human judgement, but avoids imposing manual province boundaries.

## 5. Use historical population as influence, not blueprint

**Decision:** let population affect density and seed importance without directly defining boundaries.

**Why:** settlement density matters, but population alone would underrepresent mountains, corridors, coasts and strategically significant sparse regions. Historical estimates are also uncertain.

**Trade-off:** weights require calibration and the source model's uncertainty remains present.

## 6. Treat rivers primarily as soft barriers

**Decision:** increase the cost of crossing most rivers rather than making every river impassable.

**Why:** rivers can divide territories, but they can also act as transport corridors and settlement axes. A universal hard-border rule would fragment dense river networks.

**Trade-off:** the system will not force a river border everywhere a human reviewer might expect one.

## 7. Treat major mountains and impassable terrain more strongly

**Decision:** distinguish ordinary elevation from terrain that substantially restricts connectivity.

**Why:** without strong constraints, growth can join unrelated valleys or cross major ranges implausibly.

**Trade-off:** strong barriers can create isolated fragments and difficult transition zones that require cleanup.

## 8. Grow territories over the adjacency graph

**Decision:** use constrained graph growth rather than assigning every cell to the nearest seed by Euclidean distance.

**Why:** geographic proximity is not the same as accessibility. Graph growth can account for rivers, slope, barriers, shape and local context.

**Trade-off:** results can be sensitive to seed placement, growth order and interacting weights.

## 9. Prefer explainable rules to black-box optimisation

**Decision:** use explicit rules and weighted scores as the primary modelling approach.

**Why:** every territorial result should be traceable to source data, weights, barriers, seed placement and cleanup rules. Suitable training data for an ideal global province map does not exist.

**Trade-off:** rule design and calibration demand sustained manual analysis.

## 10. Optimise for global generalisation

**Decision:** judge changes across several geographic environments rather than perfecting one region.

**Why:** a parameter that improves Europe can damage Arabia, India, Siberia or an archipelago. A local improvement is not necessarily a system improvement.

**Trade-off:** no single region may receive every locally desirable adjustment.

## 11. Avoid routine manual correction

**Decision:** use manual edits as diagnostic examples, not as part of the normal production pipeline.

**Why:** correcting one polygon does not improve the generator. A defect should ideally reveal a missing rule, inadequate weight or unsupported condition.

**Trade-off:** visible imperfections may remain while the general solution is developed.

## 12. Treat reproducibility as part of correctness

**Decision:** identical inputs and configuration should produce identical outputs.

**Why:** deterministic runs make regression testing, comparison and debugging possible. Where variation is useful, it must use explicit fixed seeds.

**Trade-off:** reproducibility requires disciplined configuration, staging and version awareness.
