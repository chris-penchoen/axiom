---
title: Semantics
type: theory
classification: public
status: draft
confidence: inferred
version: 0.1
updated: 2026-07-16
---

# Semantics

## How meaning survives transformation

> **Canon graph.** Depends on: `03_ONTOLOGY`, `04_EPISTEMOLOGY` · Defines: meaning, semantic fidelity, transformation types, the meaning-preservation invariant · Required by: `06_ARCHITECTURE` (projection, portability).

Ontology asks *what exists*. Epistemology asks *how we know it*. Semantics asks a
third question the other two do not answer:

> Does meaning survive when knowledge is transformed?

This is a distinct discipline. A transformation can be structurally valid,
schema-correct, and confidently produced while silently changing what a claim
means. Continuity ultimately requires preserving meaning, not merely structure.

> **Maturity.** This is the youngest pillar of the canon and is largely
> specification rather than demonstrated practice. It names a concern the earlier
> files handled only implicitly (in provenance, projection, and portability).

## 1. Meaning is not structure

**Meaning is the interpretation of knowledge** — what a claim actually asserts, as distinct from how it is stored, phrased, or projected. Preserving it is the concern of this pillar.

Two artifacts may share a schema and still assert different things. A summary may
be well-formed yet drop a qualifier that changed the claim's scope. A migrated
record may validate against a new format yet lose the temporal bounds that made
it true only for a period. Structural validity is necessary but not sufficient
for semantic fidelity.

## 2. Transformations that must preserve meaning

Every point where the engine re-expresses knowledge is a semantic risk:

- **Summarization** — reducing many observations or claims to fewer.
- **Projection** — generating human- or model-readable views from canonical state.
- **Translation** — moving state across formats, schemas, or platforms.
- **Context assembly** — selecting and compressing continuity for a task.
- **Adapter presentation** — re-emphasizing or reformatting for a specific model.

Each may change emphasis, order, or form. None may change what is true, for whom,
when, on what evidence, or by whose authority.

## 3. Semantic fidelity

A transformation preserves meaning when it does not alter a claim's:

- truth conditions;
- scope;
- temporal bounds (reality, observation, and revision time);
- epistemic status and confidence;
- authority and ownership;
- or provenance linkage.

Lossy transformation is permitted only when the loss is **recoverable from
canonical state**. A projection may omit detail; it may not assert more than the
canon supports, and the omitted detail must remain retrievable.

## 4. Three directions of preservation

Semantics is the common invariant behind three concerns the canon already states
separately:

- **Across derivation** — provenance preserves meaning from source to conclusion (`04_EPISTEMOLOGY.md` §5).
- **Across projection** — generated views remain disposable and non-authoritative (`06_ARCHITECTURE.md` §6.8).
- **Across implementation** — portability preserves canonical meaning when the engine is reimplemented (`06_ARCHITECTURE.md` §11).

Each is a special case of: meaning must survive the transformation.

## 5. Semantic failure modes

- **Scope inflation** — a summary drops a qualifier and reads as a broader claim.
- **False precision** — a transformation states more certainty than the evidence.
- **Decontextualization** — a fragment loses the constraints that made it true.
- **Temporal collapse** — historical and current truth are merged (see `04_EPISTEMOLOGY.md` §3).
- **Authority laundering** — a convenient projection is treated as canonical.
- **Migration loss** — reformatting discards distinctions the ontology holds independent.

## 6. The meaning-preservation invariant

> Every generated or migrated artifact MUST remain reducible to the canonical
> meaning it was derived from. A projection is authoritative for nothing it cannot
> trace back to canonical state.

This extends the architectural rule that context is a projection and never becomes
an untracked source of truth (`06_ARCHITECTURE.md` §3, invariant 8).

## 7. Enforcement today

Semantic fidelity is currently enforced by deterministic projection-drift checks
(`06_ARCHITECTURE.md` §8.5) and human review. There is no formal definition of
semantic equivalence, and no automated measure of whether a summary or migration
preserved meaning. That gap is honest, not hidden.

## 8. Open questions

- How should semantic equivalence be defined and measured?
- When is lossy summarization acceptable, and how is recoverability guaranteed?
- Can meaning-preservation be validated automatically, or does it require human or
  cross-model review (see `08_RESEARCH.md`)?
- Does semantic drift compound across repeated projection and migration?

These belong to the research program until evidence answers them.
