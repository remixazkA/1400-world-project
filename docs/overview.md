# Project overview

[← Project README](../README.md) · [Results gallery](results-and-examples.md) · [Technical evidence](technical-evidence.md)

## Objective

Project 1400 aims to create approximately 32,000 geographically and historically plausible territorial units for a global grand-strategy simulation set around the year 1400.

The output is not intended to reconstruct exact political borders. It is a designed territorial framework: sufficiently detailed for strategic use, informed by real geography and historical settlement patterns, and reproducible from explicit inputs and rules.

## Current verified scale

| Measure | Current value |
|---|---:|
| Total global hexagonal cells | 32,437,371 |
| Active playable cells | 24,146,859 |
| Adjacency relationships | 97,045,268 |
| Final provinces after post-processing | 31,264 |

The distinction between total and active cells is important. The global spatial foundation includes water and locations excluded by the current playability and impassability masks; the territorial layer assigns every active playable cell.

## Why this is difficult

The project operates between two very different scales: a 32.44-million-cell geographic foundation and a final map of roughly 32,000 territories that must remain readable and strategically useful.

The aggregation process must respond to terrain, hydrology, coastlines, settlement patterns and regional variation without turning any one dataset into an absolute rule. It must also perform consistently across environments as different as dense temperate regions, deserts, mountains, river basins and archipelagos.

## Intended properties of the final map

A successful output should be:

- **globally consistent:** regional detail can vary, but the world should still feel like one map;
- **geographically coherent:** major terrain and hydrological structures should influence territorial form;
- **historically plausible:** historical population and settlement patterns should influence density;
- **strategically useful:** territories should support movement, control and regional differentiation;
- **visually readable:** shapes should avoid slivers, excessive elongation and repetitive geometry;
- **reproducible:** identical inputs and configuration should generate identical results;
- **explainable:** a result should be traceable to inputs, rules and processing stages.

## Scope boundaries

The present project focuses on territorial generation and validation. It does not yet attempt to simulate political ownership, culture, economy, warfare or exact administrative jurisdictions in 1400.

The complete processing stack and raw source datasets are not published in this repository. Instead, the repository presents system design, requirements, decision logic, representative outputs and measurable quality evidence. Third-party data is not redistributed without suitable licensing.

## Success criteria

The system is considered successful when it produces broadly convincing results across very different geographic environments, when serious defects are infrequent and measurable, and when changes can be evaluated without losing reproducibility or creating hidden regressions.

Perfection at the level of every individual border is not the target. Consistent, explainable quality at global scale is.

---

[← Project README](../README.md) · [Validation strategy](validation.md) · [Status and roadmap](status-and-roadmap.md)
