---
title: Epistemology
type: theory
classification: public
status: draft
confidence: inferred
version: 0.1
updated: 2026-07-16
---

# Epistemology

## How AxiomCE determines what is known

> **Canon graph.** Depends on: `00_AXIOMS`, `03_ONTOLOGY` · Defines: knowledge vs information, the epistemic pipeline, the three temporal coordinates, evidence > confidence, ratification · Required by: `06_ARCHITECTURE`, `11_SEMANTICS`, `RECONCILIATION`.

Every information system contains an implicit theory of knowledge.

A database records values but may not distinguish observation from truth.

A document preserves conclusions but may discard the evidence that justified them.

An AI may produce a confident statement without retaining where it came from.

AxiomCE makes its epistemology explicit.

The objective is not to make the engine appear knowledgeable.

The objective is to make it possible to determine:

- what is asserted;
- why it is believed;
- who owns it;
- when it was true;
- when it became known;
- when it was revised;
- what contradicts it;
- and how it became canonical.

## 1. Information is not knowledge

Information is encountered content.

Knowledge is information that has been evaluated and situated.

For information to become durable knowledge, the engine must be able to answer:

- What is being asserted?
- What entity or relationship does it concern?
- What evidence supports it?
- Where did it originate?
- When was it true?
- When was it observed?
- When was it revised?
- How certain is the assessment?
- Who owns the canonical answer?
- What contradicts it?
- Has it been superseded?
- For which scope is it applicable?

Without these dimensions, information may be useful, but it is not governed knowledge.

Two further terms complete the picture, and the canon holds them distinct:

- **Intelligence** is the vehicle that reasons over knowledge — the model or execution engine. It generates, summarizes, transforms, and applies knowledge, but it is neither the knowledge nor its custodian (Axiom 7). Intelligence is replaceable; the knowledge it operates on is the durable asset.
- **Meaning** is the interpretation of knowledge — what a claim actually asserts, which must survive every transformation (see `11_SEMANTICS.md`).

So the stack is: information becomes **knowledge** when it is evaluated and situated; knowledge compounded over time across platforms is **continuity** (`05_CONTINUITY.md`); **context** is the disposable, task-relevant projection drawn from it (`03_ONTOLOGY.md` §16); **intelligence** is the replaceable vehicle that operates on it; and **meaning** is what all of the above must preserve.

## 2. The epistemic pipeline

AxiomCE processes potential knowledge through a recursive pipeline:

```text
Reality
  ↓
Observation
  ↓
Evidence binding
  ↓
Claim formation
  ↓
Evaluation
  ↓
Conflict detection
  ↓
Authority resolution
  ↓
Ratification
  ↓
Canonical knowledge
  ↓
Context projection
  ↓
Action and outcome
  ↓
New observation
```

This is the knowledge-formation view of the engine cycle: conflict detection and
authority resolution (reconciliation) precede ratification, which precedes
canonical commit. The authoritative operational enumeration is the recursive
continuity cycle in `06_ARCHITECTURE.md` (§4); this pipeline condenses it to the
epistemic stages.

The pipeline is not necessarily synchronous.

A claim may remain unresolved for years.

An observation may arrive after the relevant reality period has ended.

A canonical claim may later be revised without erasing the history of why it was previously accepted.

## 3. Three temporal coordinates

AxiomCE distinguishes three primary temporal dimensions.

### Reality time

When was the claim true in the world?

Reality time may be a point, interval, open-ended period, estimate, or unknown.

### Observation time

When did the engine learn or record the claim?

Observation time belongs to the knowledge system's history.

### Revision time

When did the engine determine that the claim was no longer current, had been superseded, or required correction?

Revision time records the evolution of knowledge.

These dimensions must remain independent.

A move may occur on June 1, be reported on August 10, and cause the prior address to be revised on August 10.

The prior address was no longer true beginning June 1.

The system did not know that until August 10.

Collapsing those events produces false history.

## 4. Evidence outranks confidence

Confidence cannot substitute for provenance.

A model may be highly confident and wrong.

A source may be direct but stale.

A human statement may be authoritative about personal preference but not about an external technical fact.

AxiomCE therefore records confidence as an assessment, not as proof.

Evidence explains why confidence is warranted.

## 5. Provenance is constitutive

Provenance is part of knowledge itself.

When a claim loses its derivation path, the engine can no longer reliably distinguish:

- direct observation;
- user testimony;
- third-party reporting;
- inference;
- calculation;
- estimate;
- generated summary;
- or repeated folklore.

Every transformation should preserve a traceable relationship to its inputs.

## 6. Authority is separate from evidence

Evidence and authority are related but not identical.

A source may provide strong evidence without having canonical authority.

The human may have canonical authority over personal goals but not over the physical properties of a component.

A domain expert may have authority within one scope and none outside it.

Canonical resolution must therefore consider:

- evidence quality;
- source directness;
- domain authority;
- temporal relevance;
- and explicit ownership.

## 7. Truth is temporally and epistemically qualified

AxiomCE avoids reducing truth to a boolean.

A claim may be:

- currently supported;
- historically supported;
- reported;
- inferred;
- calculated;
- estimated;
- planned;
- desired;
- disputed;
- unresolved;
- retracted;
- or superseded.

These labels describe epistemic status, not merely confidence.

## 8. Contradictions are preserved

Contradictions are not automatically resolved by selecting the newest statement or the most confident source.

They may indicate:

- a real change over time;
- mistaken identity;
- different scopes;
- multiple valid perspectives;
- incomplete evidence;
- or error.

The engine preserves the competing claims and their provenance until reconciliation is justified.

## 9. Reconciliation is governed, not automatic truth creation

Reconciliation may:

- choose a current operational value;
- merge equivalent claims;
- split incorrectly merged entities;
- narrow a claim's scope;
- qualify uncertainty;
- or leave the conflict unresolved.

Reconciliation does not destroy the losing evidence.

It creates a governed projection for present use.

## 10. Canonical does not mean final

Canonical knowledge is the best governed current representation.

It remains revisable.

AxiomCE must support correction without pretending that the previous canonical state never existed.

This preserves both operational usability and historical honesty.

## 11. Human ratification

AI may:

- extract observations;
- suggest claims;
- identify conflicts;
- infer relationships;
- propose policy changes;
- and evaluate outputs.

AI does not have unilateral authority to redefine the human's canonical continuity.

Human ratification is required for changes that materially define:

- identity;
- personal policy;
- collaboration expectations;
- sensitive interpretation;
- or disputed canonical state.

Delegated authority may exist, but it must be explicit.

## 12. Collaboration knowledge has a different evidence model

Factual knowledge is validated through evidence and provenance.

Collaboration knowledge is validated through repeated outcomes, correction, and ratification.

A rule such as “present the recommendation before the tutorial” is not proven by a document.

It becomes justified because repeated use reduces friction and the human ratifies it.

These knowledge classes share governance discipline but not identical validation mechanisms.

## 13. Calibration prevents policy from remaining abstract

Policy terms such as “concise,” “actionable,” “anticipate blockers,” or “push back” are underdetermined.

Calibration cases anchor these terms in examples.

A calibration case is stronger when it includes:

- the triggering task;
- the produced response;
- the preferred response or outcome;
- policy IDs;
- evaluator reasoning;
- human judgment;
- and scope.

## 14. Models may propose; humans ratify

This principle prevents a recursive error:

1. a model performs poorly;
2. the model interprets its failure as a user preference;
3. the preference becomes policy;
4. future models reproduce the failure;
5. the system now treats the error as truth about the human.

Ratification breaks this loop.

## 15. Knowledge remains open to revision

AxiomCE's epistemology is durable but not dogmatic.

The theory of knowledge remains stable because storage technology changes.

It changes only when observation demonstrates that the theory itself is incomplete.

Implementation novelty is not sufficient reason to revise epistemology.

Evidence is.

## 16. The canonical question

Every proposed addition to durable continuity must answer:

> Why does this deserve to influence future work?

That question requires evidence, authority, scope, temporal qualification, and governance.

AxiomCE is not an engine for remembering everything.

It is an engine for preserving what should compound.
