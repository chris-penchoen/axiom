---
title: Glossary
type: index
classification: public
status: draft
confidence: inferred
version: 0.1
updated: 2026-07-16
---

# Glossary

## One canonical definition per term; everything else links back

This glossary is an index, not a source of truth. Each term has exactly one
canonical definition in the file listed below. Other documents may use the term
but must not redefine it (Axiom 15: one authoritative owner per concept). For
cross-layer *aliases* (e.g. "cognitive-model" = collaboration plane), see the
terminology equivalence table in `RECONCILIATION.md`.

| Term | Canonical definition | One-line gloss |
|------|----------------------|----------------|
| Human | `03_ONTOLOGY.md` §1 | The root continuity authority; the persistent subject continuity is accumulated for. |
| Reality | `03_ONTOLOGY.md` §2 | What exists independently of the engine's representation. |
| Observation | `03_ONTOLOGY.md` §3 | An encountered input to evaluation; not automatically true or canonical. |
| Evidence | `03_ONTOLOGY.md` §4 | Inspectable support used to back, challenge, qualify, or date a claim. |
| Claim | `03_ONTOLOGY.md` §5 | An atomic assertion that can be independently evaluated or superseded. |
| Entity | `03_ONTOLOGY.md` §6 | A persistently identifiable subject about which claims may be made. |
| Identity | `03_ONTOLOGY.md` §7 | The continuity of an entity across changing descriptions. |
| Relationship | `03_ONTOLOGY.md` §8 | A typed, potentially claim-bearing connection between entities. |
| Source | `03_ONTOLOGY.md` §9 | The preserved origin of evidence; establishes provenance, not truth. |
| Provenance | `03_ONTOLOGY.md` §10 | The derivation history of knowledge (a graph, not a citation string). |
| Time (three coordinates) | `03_ONTOLOGY.md` §11 / `04_EPISTEMOLOGY.md` §3 | Reality, observation, and revision time held independent. |
| Authority | `03_ONTOLOGY.md` §12 / `04_EPISTEMOLOGY.md` §6 | The right to control the canonical representation of a concept. |
| Conflict | `03_ONTOLOGY.md` §13 | Coexisting claims that cannot all be the current canonical answer. |
| Reconciliation | `03_ONTOLOGY.md` §14 / `04_EPISTEMOLOGY.md` §9 | The governed selection of an operational canonical state without erasing the record. |
| Canonical knowledge / state | `03_ONTOLOGY.md` §15 / `04_EPISTEMOLOGY.md` §10 | The currently authoritative, governed, revisable understanding. |
| Context | `03_ONTOLOGY.md` §16 / `05_CONTINUITY.md` §5 | The task-relevant projection of continuity; owns no truth. |
| Collaboration knowledge | `03_ONTOLOGY.md` §17 | Durable knowledge of how humans and AI work well together (alias: cognitive-model). |
| Policy | `03_ONTOLOGY.md` §18 | A normative rule governing how participants should act. |
| Calibration case | `03_ONTOLOGY.md` §19 | An empirical example connecting a policy to an observed outcome. |
| Adapter | `03_ONTOLOGY.md` §20 | A model/runtime-specific adjustment that cannot fork canonical policy. |
| Evaluation | `03_ONTOLOGY.md` §21 | A recorded comparison of behavior against requirements; produces evidence, not authority. |
| Ratification | `03_ONTOLOGY.md` §22 / `04_EPISTEMOLOGY.md` §11 | The authoritative act that makes a proposal canonical. |
| Knowledge (vs information) | `04_EPISTEMOLOGY.md` §1 | Information that has been evaluated and situated; the durable asset. |
| Intelligence | `04_EPISTEMOLOGY.md` §1 | The replaceable vehicle that reasons over knowledge; the execution plane, not a custodian of it. |
| Continuity | `05_CONTINUITY.md` | Knowledge compounded over time across platforms. |
| Continuity cycle / iteration | `06_ARCHITECTURE.md` §4 | The canonical fifteen-stage recursive loop (condensed in `03_ONTOLOGY.md` §24). |
| Portability | `06_ARCHITECTURE.md` §11 | Preservation of canonical meaning across implementation change. |
| Semantics / meaning | `11_SEMANTICS.md` | The interpretation of knowledge; what must survive transformation. |

Terms not listed here are defined at first use in their owning file. If a term is
used canonically in more than one place, that is a drift signal to resolve.
