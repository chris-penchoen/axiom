---
title: Axiom & AxiomCE — Canon
type: index
classification: public
status: active
updated: 2026-07-15
---

# Axiom & AxiomCE — Canon

## The three layers

- **Axiom** — the invariant *theory*: what continuity is, why it matters, and the
  axioms, ontology, and epistemology that follow from it. Implementation-agnostic.
- **AxiomCE** — the *Axiom Continuity Engine*: the architecture that operationalizes
  Axiom (evidence -> governed canonical state -> projected context -> execution ->
  new evidence).
- **Reference implementation** — the current *build* of AxiomCE (the ChrisOS
  repository). Today it preserves continuity across disparate AI agents; the same
  architecture generalizes to any system that accumulates durable human state.

Each layer is replaceable by the one above it (see `./09_LAYER_INVARIANCE.md`): the
theory outlives every engine; every engine outlives every implementation.

## Reading order

1. `./VISION.md`
2. `./00_AXIOMS.md`
3. `./01_ORIGINS.md`
4. `./02_THE_PLATFORM_FALLACY.md`
5. `./03_ONTOLOGY.md`
6. `./04_EPISTEMOLOGY.md`
7. `./05_CONTINUITY.md`
8. `./06_ARCHITECTURE.md`
9. `./07_DESIGN_PRINCIPLES.md`
10. `./08_RESEARCH.md`
11. `./09_LAYER_INVARIANCE.md`
12. `./10_PRODUCT_THINKING_VS_CONTINUITY_THINKING.md`
13. `./RECONCILIATION.md` — theory <-> implementation map, axiom classification, and maturity

## The engine (AxiomCE)

The [`./axiomCE/`](./axiomCE/README.md) directory holds the sanitized
public-preview package for **AxiomCE** — the engine that operationalizes this
theory. Its first reference implementation is ChrisOS (the author's private
instance).

## Status and maturity

These are **working Canon drafts** (`status: draft`), not ratified doctrine. The
theory is internally coherent and faithfully generalizes the reference
implementation, but its empirical claims are evidence-limited (see
`./08_RESEARCH.md`). Read every file accordingly:

- **Axioms and derived principles** are reasoned from observation
  (`confidence: inferred`), not empirically proven.
- **Several "axioms" are really empirical hypotheses or value choices.** They are
  classified explicitly in `./RECONCILIATION.md` and cross-referenced to the
  hypothesis list (H1-H9) in `./08_RESEARCH.md`.
- **Nothing here is canonical until reconciled** with the reference
  implementation's governance, front matter, and rule IDs, and ratified by the
  human owner (Axiom 18: models propose; humans ratify).

## Conventions

Every file carries front matter (`title`, `type`, `classification`, `status`,
`confidence`, `updated`) consistent with the reference implementation's
conventions — so the canon obeys its own epistemology: inspectable, classified,
and confidence-labeled.