---
title: Axiom & AxiomCE — Canon
type: index
classification: public
status: active
version: 0.1
updated: 2026-07-15
---

# Axiom & AxiomCE — Canon

## The three layers

- **Axiom** — the invariant *theory*: what continuity is, why it matters, and the
  axioms, ontology, and epistemology that follow from it. Implementation-agnostic.
- **AxiomCE** — the *Axiom Continuity Engine*: the architecture that operationalizes
  Axiom (evidence -> governed canonical state -> projected context -> execution ->
  new evidence).
- **Reference implementation** — a concrete *build* of AxiomCE (the public
  `axiomCE-sample`, or a private personal instance). Today it preserves continuity
  across disparate AI agents; the same architecture generalizes to any system that
  accumulates durable human state.

Each layer is replaceable by the one above it (see `./09_LAYER_INVARIANCE.md`): the
theory outlives every engine; every engine outlives every implementation.

## Reading order

1. `./VISION.md`
2. `./00_AXIOMS.md`
3. `./01_ORIGINS.md`
4. `./02_THE_PLATFORM_FALLACY.md`
5. `./03_ONTOLOGY.md`
6. `./04_EPISTEMOLOGY.md`
7. `./11_SEMANTICS.md` — meaning-preservation; a peer discipline of ontology and epistemology (numbered 11 for stable-ID reasons, read here)
8. `./05_CONTINUITY.md`
9. `./06_ARCHITECTURE.md`
10. `./07_DESIGN_PRINCIPLES.md`
11. `./08_RESEARCH.md`
12. `./09_LAYER_INVARIANCE.md`
13. `./10_PRODUCT_THINKING_VS_CONTINUITY_THINKING.md`
14. `./RECONCILIATION.md` — theory <-> implementation map, axiom classification, and maturity

Reference: `./GLOSSARY.md` — canonical definition index for every key term.

## The engine (AxiomCE)

**AxiomCE** — the engine that operationalizes this theory — lives in its own
repository (`axiomCE`), consumed alongside this canon as a dependency. Its public
reference implementation is `axiomCE-sample`; private personal instances are
derived from the same framework.

## Status and maturity

**Canon version: v0.1** — the theory is versioned independently of any AxiomCE
implementation release (per layer invariance, Axiom 21). Each file carries its
own `version` in front matter so philosophical revisions never track code.

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