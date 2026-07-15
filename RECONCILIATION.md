---
title: Reconciliation
type: theory
classification: public
status: draft
confidence: inferred
version: 0.1
updated: 2026-07-15
---

# Reconciliation

## Theory <-> implementation, axiom classification, and honest maturity

> **Canon graph.** Depends on: all canon files · Defines: the three-layer identity, the axiom classification, the theory -> implementation maturity map, the terminology glossary · Required by: the reference implementation.

This document connects the Axiom theory to its reference implementation and
states, without inflation, what is actually built versus what is specification or
hypothesis. It exists because Axiom preaches provenance, explicit authority, and
honest maturity (Axioms 9, 14, and Design Principle 25) — the canon must hold
itself to that standard.

Repository mechanisms below refer to the reference implementation (the current
build of AxiomCE, formerly "ChrisOS").

## The three layers

- **Axiom** — invariant theory (implementation-agnostic).
- **AxiomCE** — the engine/architecture that operationalizes Axiom.
- **Reference implementation** — the current build (Markdown + JSONL + Git),
  scoped today to continuity across AI agents.

See `./README.md` and `./09_LAYER_INVARIANCE.md`.

## Terminology equivalence (glossary)

One concept sometimes carries different names across the three layers. The
**Axiom (canon) term is primary**; implementation-facing aliases are valid but
must be introduced with this mapping wherever they appear. This resolves the
naming drift between the canon, the AxiomCE preview, and the reference build.

| Canonical term (Axiom) | Alias(es) | Where the alias is used | Meaning |
|------------------------|-----------|-------------------------|---------|
| Collaboration plane / collaboration knowledge | Cognitive-model (pillar / `cognitive-model/`) | AxiomCE preview; reference implementation | Durable operational knowledge of how humans and AI collaborate: policy, calibration, adapters, evaluation. |
| Knowledge plane | Knowledge pillar | AxiomCE preview | Factual and temporal state: claims, entities, provenance, reconciliation. |
| Canonical state / canonical knowledge | canonical continuity | canon (used interchangeably) | The governed, currently authoritative representation used for downstream work. |
| Reference implementation / instance | "ChrisOS" | the current personal build | The current Markdown + JSONL + Git build of AxiomCE. |
| Continuity | (no alias) | all layers | Knowledge compounded over time across platforms (see `./05_CONTINUITY.md`). |

Rule: prefer the canonical term in specification text. "Cognitive-model" is the
implementation alias for the **collaboration plane** and must not be treated as a
separate concept.

---

## A. Axiom classification (applied as draft; ratification pending)

The 26 entries in `./00_AXIOMS.md` are presented uniformly as "axioms," but they
are not all the same kind of claim. A true axiom is foundational and non-optional.
Several entries are instead *derived principles*, *value/policy choices*, or
*empirical hypotheses* wearing an axiom's clothing. Conflating them weakens the
rigor the theory claims for itself.

This classification is now applied as the **four-tier draft structure** in
`./00_AXIOMS.md` (stable `Axiom N` IDs preserved). It remains `status: draft`: per
Axiom 18 (models propose; humans ratify), final ratification — and any change to
which tier a given axiom belongs in — is the owner's call.

**Kinds:** `Foundational` (invariant premise) · `Derived principle` (follows from
a foundational axiom) · `Value/policy` (a normative choice, not an empirical
fact) · `Empirical hypothesis` (a testable prediction; belongs in research until
evidence exists).

| # | Axiom (short) | Kind | Basis / cross-ref |
|---|---------------|------|-------------------|
| 1 | Human persistent; platform replaceable | Foundational | Root premise |
| 2 | Continuity must not depend on one platform | Derived principle | from 1 |
| 3 | Knowledge should outlive its systems | Value/policy | normative goal |
| 4 | Canonical continuity belongs to the human | Value/policy | ownership/ethics claim |
| 5 | Ownership = inspect/preserve/migrate/govern independently | Derived principle | definition |
| 6 | Portability succeeds only if human need not start over | Derived principle | definition / success test |
| 7 | Reasoning transient; context durable | Foundational | framing premise |
| 8 | Intelligence replaced more easily than context | **Empirical hypothesis** | = H9 (market bet) |
| 9 | Provenance is part of knowledge | Foundational | epistemology |
| 10 | Evidence outranks confidence | Foundational | epistemology |
| 11 | Uncertainty represented, not concealed | Derived principle | epistemic policy |
| 12 | Contradictions kept until resolved | Derived principle | epistemic policy |
| 13 | Reality/observation/revision time independent | Foundational | temporal ontology |
| 14 | Authority must be explicit | Derived principle | governance policy |
| 15 | One authoritative owner per concept | Derived principle | governance (drift-driven) |
| 16 | Collaboration is knowledge | Foundational | domain claim |
| 17 | World-knowledge vs collaboration-knowledge governed separately | Derived principle | tested by H2/H3 |
| 18 | Models propose; humans ratify | Value/policy | governance choice; effect = H6 |
| 19 | On divergence, preserve the human | Value/policy | explicit value commitment |
| 20 | Good continuity infra makes engines less important | **Empirical hypothesis** | depends on H9 |
| 21 | Theory must outlive representation | Foundational | layer-invariance core |
| 22 | AxiomCE independent of the form of computation | **Empirical hypothesis** | untested aspiration |
| 23 | Closer to human reality => less tech-dependent | Derived principle | layer-invariance heuristic |
| 24 | Ownership includes revise/restrict/retire/delete | Value/policy | rights claim |
| 25 | Convenience must not become a condition of continuity | Derived principle | from 1/3 |
| 26 | Preserve continuity, not software | Derived principle | restates 1/3 |

**Tally (proposed):** Foundational **7** (1, 7, 9, 10, 13, 16, 21) · Derived
principle **11** · Value/policy **5** (3, 4, 18, 19, 24) · Empirical hypothesis
**3** (8, 20, 22). The genuinely invariant core is small; that is expected and
healthy. The three empirical hypotheses should be governed as research (`08`),
not asserted as axioms.

---

## B. Theory -> reference-implementation map

Every ontology object and architectural component, mapped to the mechanism that
implements it today, with honest maturity.

**Maturity:** `Implemented` (exists and is exercised) · `Partial` (exists,
incomplete or manual) · `Spec-only` (described, not built) · `Hypothesis`
(a claim awaiting evidence) · `External` (deliberately outside the engine).

### Evidence plane

| Concept | Mechanism | Maturity |
|---------|-----------|----------|
| Source store | `sources/*.md`; claim `source` field is required | Implemented |
| Evidence binding | `source` MUST be present; `tools/validate-claims.mjs` checks refs | Implemented |
| Observation log / raw imports | `sources/` import records; `layers: raw_imports` (immutable) | Partial (no separate append-only log) |

### Knowledge plane

| Concept | Mechanism | Maturity |
|---------|-----------|----------|
| Claim store | `claims/*.jsonl`; schema in `kernel/ontology.yaml` | Implemented |
| Entity registry | `entities/*.md`; `entity_id = <type>:<slug>` | Implemented |
| Relationship graph | entity cross-refs + claim predicates | Partial (prose/claims, no typed graph) |
| Conflict registry | `lifecycle.contradiction` + `governing_precedence`; conflicting claims coexist (append-only) | Implemented (preserved + governed; no dedicated store) |
| Reconciliation manifest | `reconcile/manifest.jsonl` + `tools/reconcile.mjs` | Implemented |
| Projection engine | `tools/generate-views.mjs` -> `*.view.md` (disposable) | Implemented |

### Temporal architecture (Axiom 13)

| Coordinate | Mechanism | Maturity |
|------------|-----------|----------|
| Reality time | claim `valid_from` / `valid_to` | Implemented |
| Observation time | claim `asserted_at` | Implemented |
| Revision time | `retracted_at` / `supersedes` (+ superseding claim's `asserted_at`) | Implemented |
| Temporal queries ("belief on date X") | derivable from fields; no query tool | Partial |

### Collaboration plane

| Concept | Mechanism | Maturity |
|---------|-----------|----------|
| Canonical collaboration policy | `cognitive-model/policy/*` (5 docs, rule IDs) | Implemented |
| Calibration corpus | `cognitive-model/calibration/cases/*` | Implemented (thin: n=5) |
| Model adapters | `cognitive-model/adapters/{gpt,gemini}.md` | Implemented (evidence-gated, unratified) |
| Evaluation records | `cognitive-model/evaluation/` | **Spec-only** (README only; no records) |
| Retrieval policy (task-scoped selection) | — | **Spec-only** |

### Governance plane

| Concept | Mechanism | Maturity |
|---------|-----------|----------|
| Classification policy | `DATA_CLASSIFICATION.md`; `privacy.classifications`; `tools/privacy-check.mjs` | Implemented |
| Lifecycle policy | `kernel/ontology.yaml` lifecycle (active/superseded/retracted/expired) | Implemented |
| Change control | Git + `tools/validate*.mjs` + `tools/hooks/pre-commit` | Implemented |
| Deterministic validators | `validate.mjs`, `validate-claims.mjs`, `privacy-check.mjs`, `generate-views --check`, `reconcile.mjs` | Implemented |
| Authority registry | classification + `AGENTS.md` ownership; no registry file | Partial |
| Ratification | human process (`AGENTS.md` §7); not tooled | Partial (process, not automated) |

### Execution plane

| Concept | Mechanism | Maturity |
|---------|-----------|----------|
| Reasoning engine / tools / UI | external AI runtime (Copilot/Agency, ChatGPT) | External (by design) |

### Recursive continuity cycle (Architecture §4)

| Stage | Mechanism | Maturity |
|-------|-----------|----------|
| Encounter -> Observe -> Bind -> Normalize -> Commit | `sources/` -> `claims/` pipeline; `tools/runner.mjs capture` + `inbox/capture-envelope-spec.md` tool the Normalize -> Commit steps (structure + privacy enforced deterministically; semantic fidelity bound by the envelope contract) | Implemented (capture tooled; upstream still manual) |
| Project context (context manifest, Arch §9) | `tools/runner.mjs project` assembles an authority-scoped context package + reproducible provenance manifest (+ capture contract); task-scoped retrieval still pending | Partial |
| Execute -> Evaluate outcome -> Capture learning | `tools/runner.mjs capture` ingests an agent-normalized envelope (validate -> privacy-gate -> mint id -> append; human ratification pending); corrections still manual; no eval records | Partial (tooled ingest; no automated eval loop) |

### Portability (Architecture §11)

| Concept | Mechanism | Maturity |
|---------|-----------|----------|
| Open canonical formats | Markdown / JSONL / YAML / Git (whole repo) | Implemented |
| Portable continuity package + schema docs | `kernel/ontology.yaml` documents schema; `tools/runner.mjs project` exports a portable, self-describing context package | Partial (export exists; import/round-trip untested) |

### Cross-cutting empirical claims (from `./08_RESEARCH.md`)

| Claim | Evidence today | Maturity |
|-------|----------------|----------|
| H1 cross-model portability | one n=1 cross-model run -> adapters | Hypothesis |
| H4 adapter effectiveness | adapters exist; effect unmeasured | Hypothesis |
| H7 continuity reduces total labor | none | Hypothesis |
| H9 context outvalues intelligence | none (market bet) | Hypothesis |

---

## C. Open reconciliation items

1. **Ratify the axiom classification (§A).** The four-tier split is applied in
   `./00_AXIOMS.md` as a draft (stable IDs preserved). Confirm the tier
   assignments, or move any axiom between tiers.
2. **Where the Axiom canon lives — RESOLVED.** The canon is its own git
   repository (`C:\axiom`, branch `main`, local-only until the owner adds a
   remote and pushes), per layer invariance (Axiom 21): the theory is not
   coupled to any one implementation's repository. The canon stands alone as the
   defining principles from which *multiple* continuity engines may be built
   (cross-AI continuity, cross-platform/social continuity, etc.). AxiomCE is one
   such engine: it lives in its own repository and is referenced from the canon
   repo as a **git submodule** at `axiomCE/` (not vendored), so the engine's
   history stays independent and reusable while the canon remains self-contained.
3. **Authority link into the reference implementation.** Add a pointer that names
   the repo as the *reference implementation of AxiomCE* and Axiom as the
   theory-of-record. (Added as `THEORY.md` in the reference repo; committed
   locally, pushed manually by the owner.)
4. **Naming.** The reference implementation still self-identifies as "ChrisOS" /
   "cognitive-model" (provisional). The term equivalences are now fixed in the
   **Terminology glossary** above ("cognitive-model" = the collaboration plane);
   the remaining open call is whether to rename the instance or explicitly keep
   "ChrisOS" as the instance name over an AxiomCE engine.
5. **Front-matter/type reconciliation if merged.** `type: theory` and
   `status: draft` are new values not yet in the reference implementation's
   `CONVENTIONS.md`; merging would require adding them there or mapping.
6. **Close the evidence gaps, not the theory gaps.** The map marks evaluation
   records, retrieval/context manifest, and the H-list as Spec-only/Hypothesis.
   These — not additional doctrine — are the bottleneck (consistent with
   `cognitive-model/calibration/cases/cm-cal-0002.md`: avoid premature frameworks;
   let evidence lead).
7. **Deferred spec-maturity apparatus (gated on observed coordination failure).**
   An external RFC review proposed RFC-2119 keywords (MUST/SHOULD/MAY) across the
   doctrine, documentation-level concept IDs (e.g. `ONT-003`, `EPI-011`), and a
   normative `SPECIFICATION.md` defining conformance for any Continuity Engine.
   These are deferred, not rejected: their payoff is external implementability,
   which presumes multiple implementers — itself hypothesis H1 (n=1 today).

   **Gate.** A second implementer does *not* automatically trigger all three
   mechanisms. Their first independent implementation attempt is itself the
   experiment: let them build against the Canon as it exists, and record where
   ambiguity or incompatibility *actually* blocks compatibility. Those observed
   failures determine which specific requirements need normative language and
   which concepts need stable identifiers — nothing more. This keeps
   specification **downstream of observed coordination failure, not upstream of
   it**; otherwise the project risks pre-specifying the wrong boundaries.

   This is consistent with §B item 6, Design Principle 24 (avoid empty
   abstractions), and the research posture in `08_RESEARCH.md` (H8; preserve
   negative results). The existing architectural invariants (`06_ARCHITECTURE.md`
   §3) are the low-risk seed for a spec once specific coordination failures
   justify one.
