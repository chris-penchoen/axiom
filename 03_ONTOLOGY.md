---
title: Ontology
type: theory
classification: public
status: draft
confidence: inferred
updated: 2026-07-15
---

# Ontology

## What AxiomCE treats as existing

Every information system contains an ontology whether or not it declares one.

A database schema, directory tree, prompt template, or product interface implicitly decides which things exist, which things are identical, which distinctions matter, and which relationships may be represented.

AxiomCE makes those commitments explicit.

The ontology is not the current data model. It defines the conceptual objects that any faithful implementation must be capable of representing.

## 1. Human

The human is the root continuity authority.

The human is not merely another entity in the graph. The human is the persistent subject for whom continuity is being accumulated and governed.

AxiomCE may represent multiple people, organizations, or communities, but every continuity domain must have an explicit root authority or ratification structure.

## 2. Reality

Reality exists independently of the engine's representation.

AxiomCE does not equate canonical state with reality. Canonical state is the engine's governed current understanding of reality.

This distinction permits correction without contradiction:

- reality may change;
- observations may arrive late;
- sources may conflict;
- canonical knowledge may be incomplete;
- and the engine may revise its prior understanding.

## 3. Observation

An observation is an encountered statement, event, artifact, measurement, behavior, or outcome that may contribute to knowledge.

An observation is not automatically true and not automatically canonical.

It is an input to evaluation.

Observations may originate from:

- the human;
- another person;
- a document;
- an external system;
- a sensor;
- an imported archive;
- an AI-generated inference;
- or the outcome of prior collaboration.

## 4. Evidence

Evidence is an observation or artifact used to support, challenge, qualify, or date a claim.

Evidence differs from confidence.

Evidence is inspectable support.

Confidence is an assessment of belief.

## 5. Claim

A claim is an atomic assertion about an entity, relationship, event, policy, or state.

Atomicity means that the claim can be evaluated, superseded, contradicted, or temporally bounded without rewriting unrelated assertions.

A claim is not synonymous with truth.

A claim may be:

- supported;
- contradicted;
- inferred;
- estimated;
- unresolved;
- historical;
- current;
- planned;
- retired;
- or superseded.

## 6. Entity

An entity is a persistently identifiable subject or object about which claims may be made.

Examples include:

- people;
- organizations;
- projects;
- vehicles;
- places;
- accounts;
- events;
- documents;
- systems;
- and concepts.

The identity of an entity must survive changes in label, representation, location, and platform.

## 7. Identity

Identity is the continuity of an entity across changing descriptions and observations.

Identity includes:

- a stable identifier;
- names and aliases;
- scope;
- merge and split history;
- confidence of identity resolution;
- and lifecycle state.

Identity is not reducible to a name.

## 8. Relationship

A relationship connects entities or concepts.

Relationships may carry their own:

- direction;
- type;
- validity;
- provenance;
- confidence;
- scope;
- and lifecycle.

A relationship is therefore not merely an edge. It is a potentially claim-bearing object.

## 9. Source

A source is the preserved origin from which evidence or observations were obtained.

A source establishes provenance but does not automatically establish truth.

Source reliability, directness, authority, and temporal relevance remain separate dimensions.

## 10. Provenance

Provenance is the derivation history of knowledge.

It includes:

- origin;
- transformations;
- summaries;
- inferences;
- evaluators;
- ratifiers;
- and generated projections.

Provenance is a graph, not merely a citation string.

## 11. Time

Time is a first-class property of knowledge.

At minimum, claims must be able to distinguish three independent temporal coordinates:

1. **Reality time** — when the assertion was true in the world.
2. **Observation time** — when the assertion was recorded or learned.
3. **Revision time** — when the engine determined that the assertion was no longer current or required correction.

Additional temporal concepts may include review time, planned time, expiration, and archival time, but they must not collapse the three primary axes.

## 12. Authority

Authority is the right to control the canonical representation of a concept.

Authority may include:

- origin authority;
- domain authority;
- canonical ownership;
- ratification authority;
- delegated authority;
- and revocation.

Authority exists whether or not the system models it. AxiomCE requires it to be explicit.

## 13. Conflict

A conflict is the coexistence of claims, sources, identities, or policies that cannot all be treated as the same current canonical answer.

Conflict is not corruption.

It is a represented state of unresolved knowledge.

## 14. Reconciliation

Reconciliation is the governed process of selecting, merging, splitting, qualifying, superseding, or preserving conflicting knowledge.

Reconciliation produces an operational canonical state without erasing the underlying record.

## 15. Canonical knowledge

Canonical knowledge is the currently authoritative, governed understanding used for downstream work.

Canonical does not mean infallible.

It means:

- explicitly owned;
- traceable;
- temporally qualified;
- reviewable;
- and selected for current use.

## 16. Context

Context is the task-relevant projection of continuity.

Context is not all known information and not merely the text inside a prompt.

It may include:

- current state;
- historical state;
- relevant relationships;
- active constraints;
- unresolved conflicts;
- collaboration policy;
- task intent;
- and environment.

Context is assembled.

It does not own truth.

## 17. Collaboration knowledge

Collaboration knowledge is the durable operational understanding produced through repeated work between humans and AI.

It includes:

- successful interaction patterns;
- correction history;
- decision heuristics;
- shared vocabulary;
- expected initiative;
- delivery contracts;
- known friction;
- and failure modes.

Collaboration knowledge is not equivalent to personality modeling.

It records what repeatedly enables effective work.

## 18. Policy

Policy is a normative rule governing how the engine, AI, or human participants should act.

Policy may define:

- authority;
- validation;
- privacy;
- delivery expectations;
- ratification;
- exceptions;
- priority;
- scope;
- and lifecycle.

## 19. Calibration case

A calibration case is an empirical example that connects policy to observed outcomes.

It contains a task, response, judgment, relevant rules, evidence, and ratification state.

Calibration cases convert abstract policy into operationally testable behavior.

## 20. Adapter

An adapter is a model- or runtime-specific adjustment that helps a replaceable execution engine satisfy canonical policy.

Adapters may change emphasis, order, format, or guardrails.

They must not redefine the human or fork canonical policy.

## 21. Evaluation

Evaluation is a recorded comparison between an output or system behavior and the relevant factual, policy, privacy, and task requirements.

Evaluation produces evidence.

It does not automatically produce authority.

## 22. Ratification

Ratification is the authoritative act by which a proposal becomes canonical.

Models may suggest.

Evaluators may score.

The human or delegated authority ratifies.

## 23. Continuity

Continuity is knowledge compounded over time across platforms.

Expanded:

> Continuity is the accumulated, governed state that allows future work to begin from the progress of prior work despite changes in platforms, representations, implementations, and execution engines.

Continuity is not one stored object.

It emerges from the preservation and recursive refinement of knowledge, identity, provenance, policy, and collaboration.

## 24. Iteration

An iteration is one pass through the Continuity Engine:

- encounter;
- observe;
- represent;
- evaluate;
- reconcile;
- ratify;
- project;
- execute;
- learn.

Reconciliation precedes ratification: the engine first selects an operational
treatment of conflicting knowledge, then the human or delegated authority
ratifies it. This condensed list is the ontological view of the operational
cycle; the authoritative stage-by-stage enumeration is the recursive continuity
cycle in `06_ARCHITECTURE.md` (§4). Where the two are read together, that cycle
governs.

Iterations have no final terminal state.

The engine exists to improve the starting condition of future iterations.

## Ontological boundary

The ontology defines what must remain representable.

It does not require a particular schema.

A graph database, relational system, append-only log, file repository, or future computational substrate may implement these objects differently.

If an implementation collapses distinctions the ontology treats as independent, it is not a faithful implementation of Axiom.
