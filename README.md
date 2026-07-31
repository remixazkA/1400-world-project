<div align="center">

# Project 1400

### Global territorial modelling for a historical grand-strategy simulation

**24M+ hexagonal cells** · **72M+ adjacency relationships** · **~32,000 territorial units**

[The challenge](#the-challenge) · [Design principles](#design-principles) · [Project documentation](#project-documentation)

</div>

<p align="center">
  <img src="images/world-map.png" alt="Global territorial-generation prototype" width="100%" />
</p>

## The challenge

Project 1400 is not simply an attempt to draw a detailed world map. Its purpose is to build a reproducible geospatial system capable of transforming a global base of more than 24 million hexagonal cells and around 72 million adjacency relationships into approximately 32,000 coherent territorial units.

**Scale.** Geographic, demographic and environmental information must be processed across the entire world while keeping the pipeline efficient enough to test, compare and refine repeatedly. The system therefore has to preserve meaningful local detail without making global iteration impractical.

**Territorial plausibility.** Borders should not emerge from geometry alone. Rivers, coastlines, elevation, slope, mountain barriers, historical population estimates, vegetation and climate all affect how space is divided. These variables do not always point towards the same solution, so they must be combined carefully rather than applied as rigid rules.

**Procedural quality.** Procedural generation creates its own structural problems. Without explicit controls, it tends to produce elongated provinces, fragmented territories, unnatural straight borders, narrow slivers and repetitive geometric patterns. Avoiding these defects requires criteria for compactness, continuity, border quality and the treatment of isolated or awkward areas.

**Global generalisation.** A method that produces convincing results in the Iberian Peninsula may fail completely in the Sahara, the Himalayas, the Amazon basin, Siberia or the Indonesian archipelago. The objective is not to handcraft each region independently, but to create a common generation pipeline that adapts to radically different geographic conditions while preserving a consistent global standard.

**Validation and iteration.** Visual inspection is useful, but insufficient at this scale. Regional test cases, measurable quality criteria and repeated comparison between iterations are necessary to identify defects and determine whether a change improves the map globally rather than merely solving one local problem at the expense of another.

The project is therefore as much about designing a reliable decision-making process as it is about producing the final map. Each stage must remain reproducible, inspectable and flexible enough to evolve as new constraints, datasets and validation criteria are introduced.

---

## Design principles

- Geography should influence borders without determining them mechanically.
- Regional variation should emerge primarily from data rather than extensive manual tuning.
- Historical plausibility, geographic coherence and visual quality must be balanced.
- The same pipeline should remain effective across radically different environments.
- Every stage should be reproducible, inspectable and open to iteration.
- Local improvements should not reduce global consistency.

---

## Project documentation

| Area | Description |
|---|---|
| [Overview](docs/overview.md) | Scope, objectives, constraints and success criteria |
| [Architecture](docs/architecture.md) | Processing stages, data flow and operational structure |
| [Design decisions](docs/design-decisions.md) | Major choices, alternatives and trade-offs |
| [Validation](docs/validation.md) | Defect taxonomy, regional tests and regression workflow |
| [Project role](docs/project-role.md) | Responsibilities and AI-assisted implementation model |
| [Data sources](assets/data-sources.md) | Source categories, quality questions and provenance policy |
| [Results and examples](docs/results-and-examples.md) | Visual outputs, regional comparisons and validation cases |
| [Status and roadmap](docs/status-and-roadmap.md) | Current phase, established foundation and next milestones |

<p align="right"><a href="#project-1400">Back to top ↑</a></p>
