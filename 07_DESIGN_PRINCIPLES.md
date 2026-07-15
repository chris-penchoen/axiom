---
title: Design Principles
type: theory
classification: public
status: draft
confidence: inferred
version: 0.1
updated: 2026-07-15
---

# Design Principles

## Engineering rules derived from the Axiom foundation

> **Canon graph.** Depends on: `00_AXIOMS`, `03_ONTOLOGY`, `04_EPISTEMOLOGY`, `06_ARCHITECTURE` · Defines: 25 engineering principles derived from the axioms · Required by: the reference implementation.

### 1. Preserve continuity, not implementations

Technology is replaceable. Durable human progress is not.

### 2. Theory before representation

Ontology and epistemology determine architecture. Architecture determines data models. Data models determine storage.

Never allow a convenient schema to redefine the theory.

### 3. One authoritative owner per durable concept

Duplication for presentation is acceptable.

Duplicated authority is not.

### 4. Provenance is part of knowledge

Never separate a durable conclusion from the evidence and transformations that produced it.

### 5. Evidence outranks confidence

Confidence influences action. Evidence justifies belief.

### 6. Preserve uncertainty

Unknown, disputed, inferred, estimated, and superseded are valid states.

Do not replace them with artificial certainty.

### 7. Preserve contradiction until reconciliation is justified

Conflict is information.

### 8. Keep temporal dimensions independent

Reality time, observation time, and revision time answer different questions.

### 9. Models propose; humans ratify

AI assists knowledge formation but does not unilaterally define the human.

### 10. Separate factual knowledge from collaboration knowledge

They require different evidence, lifecycle, and evaluation.

### 11. Separate canonical policy from model adapters

The human does not change because the execution engine changes.

### 12. Context is a projection

Context assembly may select, compress, and format.

It may not silently create authority.

### 13. Prefer deterministic validation for structural invariants

Use AI for interpretation.

Use deterministic tools for schemas, references, privacy checks, and reproducible correctness.

### 14. Keep canonical formats open and inspectable

Optional acceleration layers may be proprietary or disposable.

Canonical continuity must remain independently interpretable.

### 15. Design for exit

A platform relationship is healthy only when leaving does not require rebuilding continuity.

### 16. Minimize maintenance burden

Preserve only what has sufficient future value.

Continuity must reduce work, not become a second full-time job.

### 17. Classify derived data

Sensitive source material can produce sensitive claims, views, prompts, and evaluations.

Privacy follows derivation.

### 18. Record implementation evidence without hardening anecdotes

A single model failure belongs in evaluation or an adapter proposal, not automatically in canonical policy.

### 19. Make runs reproducible

Record the model, context manifest, policy, calibration, adapter, tools, and output for meaningful evaluations.

### 20. Optimize for compounding

Every subsystem should improve the value or reliability of future iterations.

### 21. Allow lower layers to evolve freely

Storage, languages, indexes, and AI models should be replaceable without philosophical redesign.

### 22. Revise higher layers only when reality disproves them

Fashion and implementation convenience are not evidence against an axiom.

### 23. Preserve human agency

Ownership includes the right to correct, restrict, archive, retire, inherit, and delete.

### 24. Avoid empty abstractions

Do not create categories, directories, or subsystems without real evidence that they are needed.

### 25. State maturity honestly

Distinguish implemented capability, observed evidence, hypothesis, and future intent.
