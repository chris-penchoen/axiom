---
title: Axioms
type: theory
classification: public
status: draft
confidence: inferred
updated: 2026-07-15
---

# Axioms

## The invariant foundation of Axiom and AxiomCE

Axiom is the invariant theory. AxiomCE is the Continuity Engine that operationalizes it.

Neither begins with a product, a platform, a model, or a storage format.

It begins with observations about how human knowledge and technological systems behave over time.

From those observations, it derives a small set of architectural axioms — and, honestly, some principles, value choices, and hypotheses that earlier drafts also labeled "axioms."

## How to read this document

Not every entry below is the same kind of claim. A true axiom is foundational and non-optional. Others are principles *derived* from those axioms, *value choices* (normative, not empirical), or *empirical hypotheses* that must be earned with evidence before they deserve the weight of an axiom.

Each entry keeps its **stable identifier** (`Axiom N`) so existing cross-references remain valid. The numbers are identifiers, not reading order.

| Tier | Meaning | Entries |
|------|---------|---------|
| 1 — Foundational | Invariant premises everything else derives from | Axioms 1, 7, 9, 10, 13, 16, 21 |
| 2 — Derived principle | Follows from a foundational axiom | Axioms 2, 5, 6, 11, 12, 14, 15, 17, 23, 25, 26 |
| 3 — Value / policy | A normative choice, not an empirical fact | Axioms 3, 4, 18, 19, 24 |
| 4 — Open hypothesis | A testable prediction; governed as research until evidence exists | Axioms 8, 20, 22 |

Rationale for each placement is in `./RECONCILIATION.md` (section A); the hypotheses map to H1-H9 in `./08_RESEARCH.md`.

---

## Tier 1 — Foundational axioms

The invariant core. If these are wrong, the system is wrong. Everything else derives from them.

### Axiom 1 — The human is persistent; the platform is replaceable

A person may use dozens of devices, operating systems, applications, storage platforms, services, and reasoning engines over the course of a lifetime. The technologies change. The human remains.

> **The human is persistent. The platform is replaceable.**

### Axiom 7 — Reasoning is transient; context is durable

Models reason, generate, summarize, search, transform, and use tools. They are valuable because of what they can execute. They are not inherently authoritative custodians of the human state surrounding that execution.

> **Reasoning is transient. Context is durable.**

### Axiom 9 — Provenance is part of knowledge

When conclusions are separated from their origins, summaries become detached from evidence. Reported facts become inferred facts. Estimates become certainties. Outdated state becomes current state.

> **Provenance is part of knowledge, not metadata added after it.**

### Axiom 10 — Evidence outranks confidence

Systems can be confidently wrong. A confidence estimate may influence action, but it does not explain why a claim deserves belief.

> **Evidence outranks confidence.**

### Axiom 13 — Reality, observation, and revision time are independent

A fact may become true before it is observed. It may cease to be true before the system learns that it changed. The system may revise its understanding long after the underlying event occurred.

> **Reality time, observation time, and revision time are independent.**

Every durable claim must be able to distinguish:

- when it was true;
- when it was recorded;
- and when it was determined to be no longer current.

### Axiom 16 — Collaboration is knowledge

Repeated work between humans and reasoning systems produces shared vocabulary, decision patterns, corrections, known failure modes, expectations, and successful workflows. This operational understanding affects whether future work is usable.

> **Collaboration is knowledge.**

### Axiom 21 — The theory must outlive the representation

Markdown, JSONL, Git, graphs, relational databases, vector indexes, and future storage systems are implementation choices. None defines the underlying theory of knowledge.

> **The theory must outlive the representation.**

---

## Tier 2 — Derived principles

These follow from the foundational axioms. They are strong commitments, but each is a *consequence* rather than a first premise.

### Axiom 2 — Continuity must not depend on one platform

Companies change direction. Products are redesigned. Services are discontinued. Accounts are lost. Standards evolve. Interfaces disappear. Reasoning engines are replaced. No platform should be assumed to remain stable for the full duration of a human life.

> **Human continuity must not depend on the continued existence of any single platform.**

### Axiom 5 — Ownership means independent control

A user may be able to view, search, and interact with information without being able to inspect, migrate, preserve, or reconstruct it independently. Conditional access to a platform is not equivalent to durable ownership of continuity.

> **Continuity is owned only when it can be inspected, preserved, migrated, and governed independently of its current host.**

### Axiom 6 — Portability means not starting over

A file export may preserve content while losing identity, relationships, provenance, temporal structure, authority, collaboration policy, and operational context. Possession of artifacts does not guarantee the ability to continue the work.

> **Portability is successful only when the human does not have to start over.**

### Axiom 11 — Uncertainty is represented, not concealed

Information may be incomplete, disputed, inferred, estimated, outdated, or unresolved. Removing uncertainty does not improve truth. It only hides the limits of knowledge.

> **Uncertainty must be represented, not concealed.**

### Axiom 12 — Contradictions are preserved until resolved

Conflicting statements may indicate change over time, incomplete evidence, multiple perspectives, mistaken identity, or incorrect assumptions. Premature resolution destroys evidence.

> **Contradictions remain part of the record until authority or evidence resolves them.**

### Axiom 14 — Authority must be explicit

Every system ultimately decides which source, record, person, or process controls the current answer. When authority is implicit, inconsistency emerges.

> **Authority must be explicit.**

### Axiom 15 — One authoritative owner per concept

When multiple documents or systems independently own the same concept, they eventually disagree. Cross-referencing does not eliminate the need for ownership.

> **Every durable concept has one authoritative owner.**

### Axiom 17 — Facts and collaboration are governed separately

Factual claims gain authority through evidence and provenance. Collaboration policy gains authority through repeated successful interaction, correction, and human approval. Treating both as one category weakens both.

> **Knowledge of the world and knowledge of collaboration require separate governance.**

### Axiom 23 — Closer to human reality means less technology-dependent

Storage engines, languages, schemas, and models may change quickly. The underlying relationships among knowledge, authority, continuity, provenance, and human ownership do not change merely because new technology appears.

> **The closer a concept is to human reality, the less it should depend on technological change.**

### Axiom 25 — Convenience must not become a condition of continuity

A system may be exceptionally convenient while remaining fragile. A system may be durable while remaining difficult to use. Neither property guarantees the other.

> **Convenience may accelerate continuity, but it must not become a condition of continuity.**

### Axiom 26 — Preserve continuity, not software

A durable system is not defined by how well it works under ideal conditions. It is defined by whether the valuable state survives migration, failure, replacement, and time.

> **Do not preserve software. Preserve continuity.**

---

## Tier 3 — Value and policy choices

These are deliberate normative commitments. They are not empirical facts that could be proven or disproven; they are choices about what the system *should* do. They are held as firmly as axioms, but honesty requires marking them as values rather than derivations.

### Axiom 3 — Knowledge should outlive its systems

Human knowledge has survived changes in language, institutions, media, storage technologies, and political systems. It survives only when it can move beyond the system that currently contains it.

> **Knowledge should outlive the systems that create, store, or interpret it.**

### Axiom 4 — Canonical continuity belongs to the human

Platforms provide tools, storage, interfaces, and execution. The user provides the experience, correction, judgment, context, history, relationships, and labor that make the accumulated state valuable.

> **The canonical representation of human continuity belongs to the human who created it.**

### Axiom 18 — Models propose; humans ratify

If a model may convert its own output failures into permanent claims about the user, the system can recursively distort the relationship. (Whether this control actually reduces mischaracterization is testable — see H6 — but the choice to require ratification is a value.)

> **Models may propose. Humans ratify.**

### Axiom 19 — On divergence, preserve the human

Products naturally optimize for usability, engagement, retention, adoption, coherence, and commercial sustainability. These goals may overlap with human continuity, but they are not identical to it.

> **When product continuity and human continuity diverge, AxiomCE preserves the human.**

### Axiom 24 — Ownership includes the right to retire and delete

Not all information should remain active or accessible forever. People change. Some records should expire, be restricted, be corrected, be archived, or be deleted.

> **Human ownership includes the authority to preserve, revise, restrict, retire, and delete.**

---

## Tier 4 — Open hypotheses (earn before asserting)

These entries were written as axioms, but they are actually **empirical predictions about the future**. They may well be true, and the architecture is designed as if they are — but they are not yet supported by evidence and must not be asserted as foundations. They are retained here, with their stable numbers, but governed as research (`./08_RESEARCH.md`).

### Axiom 8 — Intelligence may be more replaceable than context *(hypothesis, = H9)*

A more capable model may reason better than an older one while knowing nothing about the user's history, constraints, corrections, decisions, or working patterns. Capability cannot substitute for continuity.

> **Intelligence can be replaced more easily than accumulated context.**

This is the commoditization bet (H9). It is plausible and directionally supported by industry trends, but unproven. Treat as hypothesis.

### Axiom 20 — Continuity infrastructure may make engines less important *(hypothesis, depends on H9)*

Networks make physical links replaceable. Virtualization makes hardware replaceable. Cloud systems make individual servers replaceable. Stable interfaces make applications portable.

> **Good continuity infrastructure makes reasoning engines less important.**

Not because reasoning engines lack value, but because the durable human state no longer depends on one of them. The historical analogy is suggestive, not evidence; this prediction depends on H9 holding.

### Axiom 22 — AxiomCE may be independent of the form of computation *(hypothesis, untested)*

Current models of computation are not permanent. Future systems may use architectures that differ fundamentally from contemporary software, hardware, and artificial intelligence. The principles governing human knowledge and continuity are *intended* to remain applicable regardless of execution substrate.

> **AxiomCE is independent of the current form of computation.**

This is an aspiration about substrate-independence that cannot be tested against future computing that does not yet exist. Treat as an untested hypothesis, not an established property.

---

## Definition

Axiom is the body of invariant principles defined here. AxiomCE is any Continuity Engine that faithfully operationalizes them.

It is not defined by:

- a repository;
- a programming language;
- a database;
- a file format;
- a model provider;
- an agent framework;
- or a current theory of computation.

Those are replaceable realizations.

AxiomCE is defined by the durable relationships it preserves among:

- the human;
- knowledge;
- context;
- continuity;
- provenance;
- authority;
- collaboration;
- governance;
- and execution.

---

## The First Axiom

All other principles can be traced back to the first:

> **The human is persistent. The platform is replaceable.**

The purpose of AxiomCE is not to preserve the systems humans use.

It is to ensure that the knowledge, context, identity, and collaboration created through those systems remain with the human when the systems change.