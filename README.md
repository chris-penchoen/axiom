---
title: Axiom & AxiomCE — Canon
type: index
classification: public
status: active
version: 0.1
updated: 2026-07-16
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

0. `./MANIFESTO.md` — the public, dated statement of the thesis (start here)
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

## Publication editions (derived)

`MONOGRAPH.md` is the reader-facing publication edition of this Canon — a single
portable file (and its DOCX/PDF snapshots) meant for human readers who want the
argument without navigating the repository. It is a **derived rendering, not a
source of truth.**

**Binding rule — the monograph must match the Canon:**

- The **Canon chapters are authoritative**. `MONOGRAPH.md` carries the Canon's
  principal ideas in portable form and MUST NOT introduce, alter, or drop a
  principal idea that is not also present in a Canon file.
- Any substantive change to a canonical idea and any meaning-bearing change made
  in the monograph is **not complete until both are updated in the same change**.
  The monograph and the Canon are edited as one unit, never allowed to diverge.
- The monograph MAY compile, re-order, and add reader-facing connective prose
  (transitions, framing, headings) that carries **no new principal claim**; such
  prose is editorial, not canonical.
- On any divergence, the **Canon wins** and the monograph is corrected to match.

**Two classes of publication** (all registered in `publication-manifest.json`):

- **Faithful renderings** (e.g., `MONOGRAPH.md`) are bound by the rule above:
  they carry the Canon's principal ideas with none added or dropped, and are
  edited as one unit with the Canon. The monograph is publication #1.
- **Derivative publications** — interpretations, expansions, essays, or talks
  built *from* the Canon — are **not** required to match it and may interpret and
  expand freely. They carry no obligation of word-for-word fidelity; they are only
  **logged in `publication-manifest.json`** for provenance and tracking, recording
  the Canon version they derive from.

This follows layer invariance (Axiom 21): the theory is authoritative; every
rendering of it is replaceable and must not become the definition of the thing
rendered.