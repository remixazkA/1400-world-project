# Project overview

## Objective

Project 1400 aims to create approximately 32,000 geographically and historically plausible territorial units for a global grand-strategy simulation set around the year 1400.

The output is not intended to reconstruct exact political borders. It is a designed territorial framework: sufficiently detailed for strategic use, informed by real geography and historical settlement patterns, and reproducible from explicit inputs and rules.

## Why this is difficult

The project operates between two incompatible scales:

- a high-resolution geographic foundation of roughly 24.3 million hexagonal cells and 72 million adjacency relationships;
- a final map of roughly 32,000 territories that must remain readable and useful.

The challenge is not merely to reduce the number of spatial units. The aggregation process must respect terrain, hydrology, coastlines, settlement patterns and regional variation without turning any one dataset into an absolute rule.

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

The full processing stack and source datasets are not published in this repository. This repository instead presents the system design, requirements, decision logic and quality-assurance approach.

## Success criteria

The system is considered successful when it produces broadly convincing results across very different geographic environments, when serious defects are infrequent and measurable, and when changes can be evaluated without losing reproducibility or creating hidden regressions.

Perfection at the level of every individual border is not the target. Consistent, explainable quality at global scale is.
