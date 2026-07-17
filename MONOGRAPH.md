---
title: "Axiom: Continuity as Human-Owned Infrastructure"
subtitle: "A Governance Architecture for Portable Human-AI Collaboration"
type: publication
classification: public
status: draft
confidence: inferred
version: 0.1
updated: 2026-07-16
author: Chris Penchoen
source_manifest: ./publication-manifest.json
---

# Axiom: Continuity as Human-Owned Infrastructure

## A Governance Architecture for Portable Human-AI Collaboration

**Chris Penchoen**  
Technical Monograph · Living Edition · Version 0.1 · July 2026

> **Living-document status.** This file is the reader-facing publication edition of the Axiom Canon. The root Canon files remain authoritative for theory. `publication-manifest.json` records the Canon and release artifacts last reviewed together by the human owner.

[Axiom Canon](https://github.com/chris-penchoen/axiom) · [AxiomCE](https://github.com/chris-penchoen/axiomCE) · [Reference Implementation](https://github.com/chris-penchoen/axiomCE-sample)

# Abstract

Artificial-intelligence systems increasingly accumulate durable knowledge about the people who use them: factual history, active projects, corrections, decision criteria, working conventions, and model-specific lessons. This state is expensive to reconstruct but is usually controlled by the platform that accumulated it. Conventional data export preserves artifacts without necessarily preserving the authority, provenance, temporal structure, collaboration policy, and interpretive context required to continue useful work elsewhere.

This monograph introduces continuity as an architectural abstraction distinct from storage, memory, history, and backup. Continuity is defined as governed knowledge compounded over time across platforms. Axiom derives a continuity architecture from the premise that the human is persistent while platforms and reasoning engines are replaceable. The resulting model separates evidence, factual knowledge, collaboration knowledge, governance, and execution; distinguishes canonical human policy from model-specific adapters; preserves contradictions and temporal revision; and requires human ratification before machine-generated interpretations become authoritative.

AxiomCE is presented as one operationalization of this theory. Its current implementation demonstrates a provenance-backed knowledge kernel, explicit governance, deterministic validation, collaboration policy, calibration records, and an emerging runtime ratification layer. Cross-model portability, semantic equivalence across transformations, and long-term reduction of human reconstruction cost remain empirical hypotheses. The contribution is therefore an architectural synthesis and research agenda for human-owned continuity, not a claim that portable collaboration has already been proven.

*Keywords: human-AI collaboration; agent memory; continuity; provenance; data portability; personal data sovereignty; ratification; persistent state; model portability*

## Author’s Note

The concept, architecture, and publication decisions are Chris Penchoen’s. AI systems were used as drafting, critique, implementation, code-analysis, and editorial tools. Their outputs were treated as proposals rather than authority; the author selected, revised, and ratified the text. This disclosure is part of the monograph’s own provenance discipline.

*Suggested citation: Penchoen, C. (2026). Axiom: Continuity as Human-Owned Infrastructure: A Governance Architecture for Portable Human-AI Collaboration (Version 0.1). Technical monograph.*

# Contents

- Scope, Status, and Contributions

- Vision

- Origins

- The Platform Fallacy

- Axioms

- Ontology

- Epistemology

- Semantics

- Continuity

- Architecture

- Design Principles

- Related Work

- Research Program

- Limitations and Open Problems

- The Layer Invariance Principle

- Product Thinking vs. Continuity Thinking

- Implementation Status

- Conclusion

- Appendix A: Glossary

- References

# Scope, Status, and Contributions

## The three layers

- **Axiom** — the invariant *theory*: what continuity is, why it matters, and the axioms, ontology, and epistemology that follow from it. Implementation-agnostic.
- AxiomCE — the Axiom Continuity Engine: the architecture that operationalizes Axiom (evidence → governed canonical state → projected context → execution → new evidence).
- **Reference implementation** — a concrete *build* of AxiomCE (the public `axiomCE-sample`, or a private personal instance). Today it preserves continuity across disparate AI agents; the same architecture generalizes to any system that accumulates durable human state.

Each layer is replaceable by the one above it: the theory outlives every engine, and every engine outlives every implementation. This separation prevents a temporary representation from becoming the definition of the thing represented.

## Contributions

Axiom makes five principal contributions:

- It defines continuity as governed knowledge compounded over time across platforms, distinguishing it from storage, recall, archival history, and backup.

- It separates the evidence, knowledge, collaboration, governance, and execution planes so that replaceable reasoning systems cannot silently own or redefine durable human state.

- It distinguishes canonical collaboration policy from model-specific adapters, preventing a model’s execution failure from becoming a durable claim about the human.

- It treats provenance, temporal qualification, contradiction, authority, and ratification as constitutive properties of continuity rather than optional metadata.

- It states an empirical research program for testing whether governed continuity reduces reconstruction effort and preserves useful collaboration across models and implementations.

## Claim boundaries

> This monograph does not claim that portable AI memory, personal data ownership, provenance, temporal databases, agent memory, or human approval are individually unprecedented. Its proposed contribution is the continuity abstraction and the governed synthesis built around it. The Canon’s axioms, value commitments, and hypotheses are therefore classified separately, and implementation evidence is distinguished from theoretical coherence.

## The engine (AxiomCE)

**AxiomCE** — the engine that operationalizes this theory — lives in its own repository (`axiomCE`), consumed alongside this canon as a dependency. Its public reference implementation is `axiomCE-sample`; private personal instances are derived from the same framework.

## Status and maturity

Canon version: v0.1. The theory is versioned independently of AxiomCE implementation releases so philosophical revision does not track code releases.

This edition is a working technical monograph rather than ratified doctrine. Its architectural claims are reasoned and internally reconciled, while its empirical claims remain evidence-limited and are governed as research hypotheses.

- **Axioms and derived principles** are reasoned from observation (`confidence: inferred`), not empirically proven.
- Several "axioms" are really empirical hypotheses or value choices. They are classified explicitly in the implementation reconciliation and cross-referenced to the hypothesis list (H1-H9) in the Research Program.
- The monograph remains subject to author ratification and revision. Models and tools may propose changes, but they do not acquire publication authority by producing them.

# Vision

AxiomCE is a Continuity Engine.

Its purpose is to enable human knowledge to compound over time across platforms.

It does this by preserving and recursively refining:

- knowledge;
- identity;
- provenance;
- temporal history;
- authority;
- collaboration;
- policy;
- context;
- and governance.

AI is the first major execution workload.

It is not the owner of continuity.

Axiom is the invariant theory.

AxiomCE is the engine that operationalizes it.

The engine succeeds when a human can change models, products, storage systems, interfaces, or future computational paradigms without paying again for knowledge already earned.

The objective is not better memory.

The objective is that every future iteration begins farther ahead than the last.

*The vision emerged from a concrete continuity failure rather than from an abstract desire to design a new knowledge system.*

# Origins

## How a memory-migration problem became a Continuity Engine

AxiomCE began with a practical problem.

Years of collaboration with an AI system had produced a valuable body of accumulated context: facts, active projects, corrections, working patterns, trusted methods, known failure modes, and an increasingly effective way of solving problems together.

Almost none of that value was independently owned.

It existed inside a platform.

The first objective was therefore straightforward: preserve the context so a different AI could continue the work without requiring the human to start over.

The project was initially called **ChrisOS** because it was a personal system built around one person's accumulated context. The working description was portable AI memory.

That description quickly became inadequate.

## The architecture forced a broader question

As the repository developed, the difficult questions were not primarily about storage.

They were questions of authority:

- Which source owns a fact?
- How should contradictory observations coexist?
- When was a statement true?
- When was it recorded?
- When was it discovered to be no longer true?
- Who may ratify a change?
- Which rules describe the human?
- Which rules compensate for a particular model?
- What must survive when every implementation changes?

The project stopped looking like a memory export and began looking like infrastructure for maintaining continuity.

The knowledge layer preserved what was known.

The collaboration layer preserved how useful work was produced.

Governance determined what could become authoritative.

Provenance preserved why it was believed.

Calibration allowed collaboration to improve without allowing an AI to redefine the human.

The system was no longer trying to preserve one assistant.

It was trying to preserve the accumulated ability to continue.

## The infrastructure lineage

This way of seeing the problem did not begin with AI.

The same pattern had appeared repeatedly across computing.

Music was once coupled to physical media. Services such as Napster and LimeWire made the more important abstraction obvious: the value was access to the music, not possession of a particular disc.

Virtualization separated workloads from servers.

Cloud computing separated services from individual machines.

Modern identity systems separated the user from the endpoint.

In each case, something valuable became less dependent on the implementation that happened to host it.

The recurring infrastructure question was always the same:

> What is durable, and what should be replaceable?

When AI systems began accumulating years of personal context, the same unnecessary coupling appeared again.

The model was useful.

The platform was useful.

Neither should own the continuity created through them.

## Why Axiom

As the design matured, every major decision reduced to a foundational proposition:

- The human is persistent; the platform is replaceable.
- Knowledge should outlive the systems that create, store, or interpret it.
- Evidence outranks confidence.
- Models may propose; humans ratify.
- Every durable concept has one authoritative owner.
- Facts and collaboration are different forms of knowledge and require different validation.
- Theory must outlive representation.

An axiom is a foundational proposition from which a system is derived.

The name **Axiom** therefore describes the invariant theory rather than the current implementation.

## Why CE

The implementation was briefly called AxiomOS.

The operating-system metaphor captured persistence, authority, and infrastructure, but it also implied responsibilities the project did not claim: scheduling, process management, hardware abstraction, or ownership of a complete computing environment.

The architecture is more accurately an engine.

It accepts observations, evidence, corrections, and interaction outcomes.

It transforms them through evaluation, governance, reconciliation, and ratification.

It produces a refined canonical state that improves the next iteration.

The engine runs again.

Continuity compounds.

**AxiomCE** therefore means **Axiom Continuity Engine**.

Axiom is the theory.

AxiomCE is the engine that operationalizes it.

## The development speed

The architecture emerged over days rather than months because AI dramatically accelerated drafting, critique, implementation, testing, and cross-model review.

That speed reinforces the original problem.

When tools accelerate the production of knowledge, losing the context created through those tools becomes even more expensive.

Faster execution increases the value of durable continuity.

## What AxiomCE is

AxiomCE is not defined by Markdown, Git, JSONL, a repository layout, or a particular model.

Those are current implementation choices.

AxiomCE is a Continuity Engine that enables knowledge to compound across time, platforms, and generations of technology through recursively refined human–AI collaboration.

The implementation may change completely.

The continuity should not.

*The personal migration problem exposes a broader structural error: people routinely confuse the platform that hosts continuity with continuity itself.*

# The Platform Fallacy

## Why Human Knowledge Must Outlive the Systems That Host It

## Introduction

Modern life is increasingly lived through systems we do not own.

Our photographs sit inside cloud libraries. Our conversations live inside messaging platforms. Our friendships are mediated by social networks. Our work is stored in proprietary applications. Our journals are scattered across devices and services. Our personal histories are reconstructed from posts, emails, files, and timelines maintained by companies whose products may change or disappear without our consent.

Artificial intelligence is now becoming the newest layer in that pattern.

People are beginning to entrust AI systems not only with information, but with context.

They teach them how they think. They explain their projects. They correct their assumptions. They develop shared language. They build workflows. They form habits. They accumulate trust. They create, over time, a working relationship.

The more capable the system becomes, the more tempting it is to mistake that relationship for permanence.

That is the mistake.

The platform is not the memory. The platform is not the knowledge. The platform is not the relationship. The platform is not the continuity.

The platform is only the current container.

AxiomCE begins from an observation and its engineering consequence:

> **Platforms are temporary. Human continuity should not be.**

This essay explains why that claim is not merely a privacy preference, a backup strategy, or a critique of any particular company. It is a general principle about the relationship between human knowledge and technological systems.

It is also the foundation from which AxiomCE derives its architecture.

## 1. The central confusion

The Platform Fallacy occurs when people confuse the system that hosts knowledge with the knowledge itself.

For a time, the distinction is invisible.

A photograph in a social network feels like a photograph. A diary entry in a notes app feels like a diary entry. A conversation in a messaging service feels like a conversation. A memory stored inside an AI product feels like memory.

But the object and the platform are not the same thing.

The photograph may be yours in meaning while remaining dependent on someone else’s account system, storage policy, export format, moderation process, and business decisions.

The diary may be your writing while existing in a format you cannot independently inspect.

The messages may belong to your personal history while remaining inaccessible if an account is locked.

The AI may appear to “know you” while the actual representation of you exists as hidden state inside a product you cannot audit, export, or control.

The confusion persists because the platform usually works.

It works until it does not.

When access is lost, the distinction becomes brutally clear:

> The user created the value, but the platform controlled the continuity.

That is the Platform Fallacy.

## 2. Platforms sell access to continuity

Digital platforms rarely describe themselves this way, but many of them are effectively continuity services.

They do not merely store files.

They preserve relationships between files, people, events, identity, and time.

A photo service is useful not only because it stores images, but because it places them on a timeline, groups them by person, and ties them to location and memory.

A social network is useful not only because it hosts posts, but because it becomes a record of friendships, opinions, major life events, conversations, and social identity.

A productivity platform is useful not only because it stores documents, but because it preserves the history of projects, decisions, comments, tasks, and institutional memory.

An AI assistant is useful not only because it answers questions, but because repeated use creates a context-rich working relationship.

The value lies in continuity.

The danger is that users often own only access to that continuity, not the continuity itself.

An account can be suspended. A service can change its terms. A company can fail. A product can be discontinued. A feature can be removed. An export can omit important metadata. A proprietary format can become unreadable. A platform can survive while the version of it that held your history disappears.

This means the user may possess the content emotionally while lacking control of it operationally.

That distinction is the core ownership problem AxiomCE addresses.

## 3. The history is older than software

The Platform Fallacy is not unique to digital systems.

Human beings have always depended on containers for knowledge.

Clay tablets. Papyrus. Libraries. Monasteries. Universities. Printing presses. Archives. Newspapers. Film. Magnetic storage. Cloud services.

Each medium increased humanity’s ability to preserve, duplicate, or transmit knowledge.

Each also introduced a new dependency.

When knowledge is concentrated, the container becomes a point of failure.

The historical lesson is not that any one library burned and erased all human knowledge. History is more complicated than that. Knowledge has always been distributed unevenly across people, places, and institutions.

The deeper lesson is simpler:

> **Civilizations become fragile when continuity depends on too few custodians, too few copies, or too narrow a set of technologies.**

A library may be destroyed. A language may disappear. A script may become unreadable. An archive may decay. A government may suppress records. A culture may lose the institutions that transmitted its knowledge.

The specific failure changes.

The structural problem remains the same.

Knowledge survives when it can move across:

- institutions;
- generations;
- formats;
- geographies;
- technologies;
- and political systems.

Durability is not the same thing as storage.

Durability requires portability, interpretability, redundancy, and ownership.

## 4. The digital era intensified the problem

Digital systems appear safer than physical archives because copying is cheap.

In theory, digital knowledge can be replicated perfectly at nearly zero cost.

In practice, people increasingly store their lives inside systems designed around access rather than ownership.

This creates a paradox:

> Digital information is easier to copy than any information in history, yet many people have less practical control over their personal archives than their grandparents did over a box of photographs.

A physical photo album can be held, moved, copied, inherited, or stored without permission from a vendor.

A cloud photo library may contain more images, more metadata, and more search capability, but it depends on:

- credentials;
- subscriptions;
- network access;
- proprietary software;
- vendor policies;
- and continued product support.

The digital object may be more capable but less sovereign.

This is not an argument against cloud platforms.

It is an argument against treating them as canonical custodians.

A platform can be an excellent working surface without being the final source of truth.

That distinction is essential.

## 5. The false promise of export

Many platforms claim that users can export their data.

Export is important, but it is not equivalent to portability.

A data export may preserve files while losing the relationships that made them meaningful.

A social platform may export posts but omit:

- comment context;
- conversation structure;
- visibility history;
- reactions;
- identity resolution;
- or the temporal order in which an event unfolded.

An AI platform may export conversations but not:

- hidden memory;
- behavioral adaptation;
- system instructions;
- learned preferences;
- model-specific corrections;
- or the contextual relationships connecting separate conversations.

This produces a pile of artifacts without preserving the operating context.

The result is archival but not executable.

The user may technically possess the data while still being unable to reconstruct the experience or continue the relationship elsewhere.

True portability requires more than raw extraction.

It requires preservation of:

- identity;
- structure;
- provenance;
- temporal meaning;
- authority;
- relationships;
- and the rules needed to interpret the information.

AxiomCE is designed around that richer definition of portability.

## 6. AI repeats the same pattern at a higher level

Artificial intelligence does not escape the Platform Fallacy.

It amplifies it.

Traditional platforms host content.

AI platforms increasingly host interpretation.

They accumulate not only what the user said, but how the system learned to respond.

Over time, the system may acquire knowledge of:

- the user’s active projects;
- their history;
- their family;
- their preferred communication style;
- their tolerance for risk;
- their technical background;
- their recurring mistakes;
- their decision criteria;
- and the kinds of output they actually use.

This creates something more valuable than a collection of chats.

It creates collaborative context.

That context is expensive because it is built gradually.

The user must repeatedly:

- explain;
- correct;
- clarify;
- reject;
- refine;
- and demonstrate.

Each interaction may be small, but the cumulative result can represent years of labor.

If that state is trapped inside one product, then the product effectively owns the accumulated collaboration.

The user may own the experiences. The vendor owns the continuity.

That is the AI version of the Platform Fallacy.

## 7. The model is a tool, not the asset

AxiomCE treats AI models the way mature computing systems treat processors.

Processors execute. They are important. They can be fast, slow, efficient, specialized, reliable, or flawed.

But the processor is not the application. It is not the user’s data. It is not the operating environment. It is not the accumulated state of the system.

The same principle applies to AI.

A model can reason. It can summarize. It can generate. It can search. It can use tools. It can transform information.

But the model should not be the sole custodian of:

- identity;
- history;
- context;
- policy;
- provenance;
- decisions;
- collaboration patterns;
- or memory.

The model is execution.

The durable asset is the state around it.

This leads to one of the core architectural principles of AxiomCE:

> **Reasoning engines are replaceable. Accumulated context is not.**

The industry will continue to produce better models.

Some will be more capable. Some will be cheaper. Some will be safer. Some will be faster. Some will disappear.

AxiomCE does not need to predict which one will win.

It assumes they will all change.

## 8. Intelligence becomes abundant; context becomes scarce

The AI industry is organized around scarcity of intelligence.

Companies compete on:

- benchmark scores;
- reasoning capability;
- context length;
- latency;
- multimodality;
- tool use;
- and cost.

But the long-term trend points toward abundance.

More models will become capable enough for more tasks. Execution costs will fall. Specialized models will proliferate. Open models will improve. Model routing will become common. Users will increasingly switch between systems.

As intelligence becomes easier to obtain, accumulated context becomes comparatively more valuable.

A model can be replaced in minutes.

Years of context cannot.

A benchmark improvement can be replicated by competitors.

A deeply calibrated working relationship cannot.

The scarce resource is not raw intelligence.

The scarce resource is the accumulated, structured understanding of:

- what is true;
- what matters;
- how decisions are made;
- what has already been tried;
- what should not be repeated;
- and how a particular human works best.

That is why AxiomCE invests in persistence rather than model loyalty.

## 9. Continuity is larger than memory

The word “memory” is too narrow.

Memory suggests stored facts.

Continuity includes much more.

It includes:

- facts;
- identity;
- history;
- relationships;
- provenance;
- unresolved contradictions;
- changing state;
- decisions;
- values;
- preferences;
- operational patterns;
- collaboration rules;
- failures;
- corrections;
- and intent.

A person’s digital life is not a database of isolated facts.

It is a network of meanings across time.

AxiomCE therefore aims to preserve continuity, not merely recall.

This distinction matters because a system can remember many facts and still fail to continue the human’s work.

It may know what happened but not why it mattered.

It may know the current state but not how it was reached.

It may know preferences but not the corrections that established them.

It may remember a project but not the constraints that shaped it.

Continuity requires preserving both information and interpretation.

## 10. The canonical record belongs to the human

AxiomCE makes an explicit ownership claim:

> **The human should own the canonical representation of their digital life and collaborative context.**

This does not mean the human must manually maintain every detail.

It means the final authority should not be a vendor’s hidden database.

The canonical record should be:

- inspectable;
- exportable;
- versioned;
- portable;
- correctable;
- auditable;
- and usable by multiple systems.

Platforms may enrich it. Models may reason over it. Tools may transform it. Services may synchronize it.

But none of them should silently become the only place where the relationship exists.

This is digital sovereignty applied to knowledge and collaboration.

## 11. The difference between convenience and custody

Platforms are often excellent at convenience.

They provide:

- search;
- synchronization;
- collaboration;
- backup;
- indexing;
- recommendation;
- generation;
- and access from many devices.

AxiomCE does not reject these capabilities.

It rejects the assumption that convenience should imply custody.

A useful distinction is:

### Platform as interface

The platform helps the user interact with their knowledge.

### Platform as custodian

The platform controls whether the knowledge remains available.

The first is desirable. The second is dangerous when no independent canonical copy exists.

AxiomCE allows platforms to remain interfaces while removing their monopoly over continuity.

## 12. Open formats are not an aesthetic preference

AxiomCE uses plain text, Markdown, JSONL, YAML, and Git not because they are fashionable or minimal.

It uses them because they reduce dependence.

Open, inspectable formats have several properties necessary for durable knowledge:

- they can be read without a proprietary application;
- they can be diffed;
- they can be versioned;
- they can be transformed;
- they can be copied;
- they can be validated;
- and they can survive changes in tooling.

A database may be useful.

A vector index may be useful.

A cloud service may be useful.

But they should remain accelerators, not foundations.

The canonical state should survive their removal.

That is the difference between infrastructure and dependency.

## 13. Redundancy is not duplication

Modern software culture often treats duplication as waste.

For knowledge preservation, redundancy is resilience.

A single platform account is not a durable archive.

A single device is not a durable archive.

A single proprietary format is not a durable archive.

A single AI vendor is not a durable collaboration system.

The goal is not careless copying.

The goal is survivable replication.

Durable continuity should be able to exist across:

- local storage;
- version-controlled repositories;
- encrypted backups;
- independent devices;
- and future platforms.

The canonical model should be clear even when copies exist.

Redundancy protects the asset. Authority prevents redundancy from becoming confusion.

AxiomCE requires both.

## 14. Provenance protects meaning

Knowledge without provenance becomes folklore.

A statement may survive while its source disappears.

Over time, summaries detach from evidence. Interpretations become facts. Estimates become certainties. Old state is mistaken for current state.

Provenance prevents this decay.

A durable knowledge system must preserve:

- where a claim came from;
- when it was observed;
- who asserted it;
- how confident the system is;
- what later superseded it;
- and whether conflicting evidence exists.

This is not bureaucratic overhead.

It is how continuity remains trustworthy.

A platform may remember that something was said.

AxiomCE must remember what kind of statement it was.

## 15. Contradictions are part of continuity

Human lives are inconsistent.

Information changes. People revise opinions. Plans fail. Memories conflict. Records disagree. State evolves.

A platform optimized for a seamless user experience may collapse these differences into one current answer.

A durable system should not erase uncertainty for convenience.

Contradictions are evidence.

They reveal:

- change over time;
- disputed interpretation;
- incomplete knowledge;
- or unresolved identity.

AxiomCE preserves contradiction until authority or evidence resolves it.

This allows future systems to understand not only the current answer, but the path by which it became current.

That path is part of continuity.

## 16. Collaboration is also knowledge

One of the most important conclusions behind AxiomCE is that long-term collaboration produces its own form of knowledge.

This includes:

- which explanations help;
- which workflows reduce friction;
- when the system should push back;
- what counts as sufficient evidence;
- how much detail is useful;
- what the user expects to be anticipated;
- and which recurring failure modes should be prevented.

This knowledge is not merely a preference profile.

It is operational infrastructure.

It determines whether a reasoning engine can produce usable work.

A model may know every relevant fact and still fail because it does not know how to collaborate with the human.

That is why AxiomCE preserves both:

1.  what is true;
2.  how the human and system work effectively together.

Both must survive the current platform.

## 17. Human ratification prevents machine self-definition

A system that stores knowledge about a human has power.

A system that stores policy about how to work with a human has even more.

If the model can rewrite that policy without human control, it can gradually redefine the relationship around its own behavior.

For example:

- a model fails to provide detail;
- it records that the user prefers brevity;
- future models become even more terse;
- the system now treats the model’s original failure as a fact about the human.

This is a recursive distortion.

AxiomCE prevents it by requiring human ratification for canonical changes.

Models may observe. Models may propose. Models may summarize. Models may evaluate.

The human approves what becomes authoritative.

This keeps the system aligned with ownership rather than convenience.

## 18. Portability is behavioral, not merely technical

A repository can be technically portable while the relationship remains behaviorally trapped.

A model may be able to read the files and still fail to reproduce the collaboration.

True portability requires more than compatible formats.

It requires preservation of:

- task-relevant context;
- collaboration policy;
- examples;
- model-specific adaptation;
- authority boundaries;
- and evaluation.

The question is not:

> Can another model ingest the data?

The question is:

> Can another model continue the work without forcing the human to pay the cost of reconstruction again?

That is the standard AxiomCE must ultimately meet.

## 19. The right to leave

A durable system should preserve the user’s right to leave a platform.

This is more than data portability.

It is continuity portability.

The user should be able to change:

- model provider;
- application;
- storage backend;
- interface;
- agent framework;
- or hosting environment

without losing the accumulated relationship.

The right to leave is meaningful only when exit does not require starting over.

AxiomCE treats exit as an architectural requirement, not a vendor feature.

## 20. Platforms are temporary even when companies survive

Platform risk is not limited to bankruptcy or shutdown.

A company may remain successful while the user’s continuity is still broken.

A service can:

- redesign its product;
- remove a feature;
- change its recommendation system;
- alter its moderation rules;
- change export formats;
- rename or merge products;
- restrict access;
- alter pricing;
- or shift its strategic priorities.

The company survives.

The user’s historical relationship with the product may not.

Durability therefore cannot depend on predicting which companies will endure.

It must assume change.

## 21. Memory without sovereignty is rented memory

When the user cannot independently inspect, move, preserve, or reconstruct a system’s memory, that memory is effectively rented.

The service may provide continuity, but only while the relationship remains acceptable to the platform.

This is similar to renting access to a library whose catalog, building, and membership rules can change at any time.

The contents may feel personal.

The continuity remains conditional.

AxiomCE aims to convert rented memory into owned continuity.

## 22. The public archive and the private self

Digital sovereignty does not mean all information should be public.

Ownership and disclosure are separate concerns.

AxiomCE must support:

- public knowledge;
- personal knowledge;
- sensitive knowledge;
- restricted knowledge;
- local-only knowledge;
- and information that should never be stored.

The objective is not universal exposure.

It is human control.

The user should determine:

- what exists;
- where it exists;
- who may consume it;
- how it is classified;
- and whether it may leave the local environment.

Portability without privacy becomes extraction. Privacy without portability becomes captivity.

AxiomCE requires both.

## 23. The ethical claim

The Platform Fallacy is not only a technical problem.

It is an ethical one.

People create the value inside platforms:

- their photographs;
- their conversations;
- their relationships;
- their corrections;
- their writing;
- their knowledge;
- their labor;
- and their collaborative histories.

When a platform becomes the sole custodian of that value, the human’s continuity becomes subordinate to institutional convenience.

AxiomCE asserts that the person who generates the context should retain authority over it.

That does not eliminate the role of vendors.

It defines the boundary.

Vendors provide tools. Humans own the accumulated life expressed through those tools.

## 24. The architectural consequences

The Platform Fallacy is not merely philosophy.

It creates concrete engineering requirements.

If platforms are temporary and continuity must endure, then AxiomCE must be:

### Model-agnostic

No single reasoning engine can be authoritative.

### Platform-independent

The system must remain usable outside the application that created it.

### Human-readable

The canonical state must not require specialized infrastructure to inspect.

### Machine-consumable

Future reasoning engines must be able to use it effectively.

### Versioned

Changes must be reviewable and reversible.

### Provenance-aware

Knowledge must remain connected to evidence.

### Conflict-preserving

Uncertainty must not be erased for convenience.

### Privacy-governed

Portability must not imply uncontrolled disclosure.

### Redundant

The canonical state must survive local or vendor failure.

### Human-ratified

The system must not redefine the human without approval.

### Adapter-based

Model-specific behavior must not contaminate the durable representation of the human.

### Evaluated

Portability must be measured by continuity of outcomes, not merely file compatibility.

These are not optional enhancements.

They are direct consequences of the founding principle.

## 25. AxiomCE as a continuity engine

AxiomCE can be understood as a layer between the human and temporary systems.

                        Human

            Identity, knowledge, history,
            context, policy, collaboration

                          |
                          v

                      AxiomCE

            Durable, governed continuity

                          |
              ┌───────────┼───────────┐
              v           v           v

            Model A     Model B     Future system

              |
              v

         Temporary execution

The lower layer can change.

The continuity layer remains.

This is the central abstraction.

## 26. The broader mission

AxiomCE begins with human–AI collaboration, but the principle extends further.

Any platform that accumulates meaningful human state creates the same problem.

Potential future domains include:

- personal archives;
- family histories;
- creative work;
- professional knowledge;
- health records;
- education;
- community memory;
- institutional continuity;
- and digital inheritance.

The common requirement is the same:

> The human experience should remain portable across the systems through which it was created.

AI is the first execution environment AxiomCE is designed around because AI makes the continuity problem unusually visible.

The reasoning engine appears personal. It appears adaptive. It appears to know.

That makes the loss of continuity especially costly.

But the principle is broader than AI.

## 27. Digital inheritance

A durable system must also consider what happens when the original user is no longer available.

Platforms often treat accounts as temporary licenses tied to an individual.

Human knowledge is intergenerational.

Photographs, writing, decisions, stories, and relationships may matter to:

- children;
- families;
- collaborators;
- communities;
- and future historians.

AxiomCE should eventually support deliberate inheritance:

- what may survive;
- who may receive it;
- what remains private;
- what becomes archival;
- and how provenance is preserved.

This is a natural extension of human ownership.

If continuity belongs to the human, the human should be able to decide its future.

## 28. The cost of forgetting

Loss is not only emotional.

It has operational cost.

When context disappears:

- work is repeated;
- mistakes recur;
- decisions lose rationale;
- trust must be rebuilt;
- relationships become shallower;
- and future systems operate with less knowledge than prior systems possessed.

At individual scale, this is frustrating.

At organizational scale, it is expensive.

At civilizational scale, repeated loss is catastrophic.

AxiomCE treats forgetting as a preventable class of systems failure.

## 29. The cost of preserving everything

Durability also creates risk.

Not all information should persist forever.

Some knowledge becomes irrelevant. Some data becomes harmful. Some records deserve deletion. Some memories should not be inherited. Some claims should expire. Some mistakes should not permanently define a person.

AxiomCE therefore cannot equate preservation with indiscriminate retention.

Human ownership includes the right to:

- correct;
- retire;
- restrict;
- archive;
- or delete.

Continuity should preserve agency, not create an inescapable permanent record.

This is one reason human governance is essential.

## 30. The design tension: permanence versus evolution

A durable representation of a person must remain stable enough to preserve continuity and flexible enough to permit change.

People evolve.

Preferences change. Relationships change. Beliefs change. Projects end. Identities deepen. Past descriptions become inaccurate.

AxiomCE must preserve historical truth without freezing the human in time.

This requires:

- temporal claims;
- supersession;
- changing confidence;
- scoped policy;
- and explicit current-state views.

The goal is not a permanent snapshot.

It is a durable history of change.

## 31. The first axiom

The name AxiomCE is appropriate because the architecture begins from foundational propositions.

The first is:

> **The human is persistent. The platform is replaceable.**

From this follows:

- the human owns the canonical state;
- models do not own memory;
- platforms do not own continuity;
- open formats outrank proprietary convenience;
- provenance outranks confident synthesis;
- human ratification outranks machine inference;
- and portability must be designed before it is needed.

The rest of the system is engineering derived from this axiom.

## 32. The second axiom

> **Knowledge should outlive the tools that create, host, or interpret it.**

This does not require rejecting tools.

It requires refusing to make them the sole condition of survival.

The better the tool, the more important this becomes.

Powerful tools encourage deeper dependency.

Deep dependency increases the cost of failure.

AxiomCE treats capability and durability as separate concerns.

A platform may be exceptionally capable and still be an unacceptable single point of continuity.

## 33. The third axiom

> **Accumulated context is a human-created asset.**

The platform may help organize it. The model may help interpret it. The vendor may provide infrastructure.

But the context exists because the human invested time, correction, experience, and judgment.

That accumulated value should remain under human authority.

## 34. The fourth axiom

> **Portability is successful only when the human does not have to start over.**

A file dump is not enough. A chat export is not enough. A list of preferences is not enough.

The test is continuity of useful collaboration.

Can another system pick up the work? Can it understand current state? Can it respect prior decisions? Can it avoid old mistakes? Can it preserve the relationship’s operating model?

If not, the system exported data but failed to preserve continuity.

## 35. A practical standard

AxiomCE should consider continuity preserved when a new reasoning engine can:

1.  identify the human and relevant entities;
2.  retrieve current and historical state;
3.  distinguish evidence from inference;
4.  identify unresolved contradictions;
5.  understand the current task context;
6.  apply collaboration policy;
7.  adapt to model-specific failure modes;
8.  produce usable work without repeated re-teaching;
9.  preserve privacy boundaries;
10. and record new knowledge without corrupting canonical state.

This is a stricter standard than memory recall.

It is also the standard that matters.

## Conclusion

Human beings will continue to build their lives through platforms.

That is not inherently a mistake.

Platforms are powerful. They create access. They reduce friction. They enable relationships and work that would otherwise be impossible.

The mistake is assuming that because a platform is useful today, it should become the sole custodian of what matters tomorrow.

The platform is not the asset.

The account is not the identity.

The product is not the relationship.

The model is not the knowledge.

The asset is the accumulated human continuity created through them.

AxiomCE exists to preserve that continuity.

It assumes that platforms will change. Models will change. Companies will change. Interfaces will change. Storage systems will change. The tools of reasoning will change.

The human remains.

Their knowledge, history, identity, decisions, context, and collaborative experience should remain with them.

That is the Platform Fallacy:

> **We mistake temporary systems for permanent homes.**

And that is the corrective principle behind AxiomCE:

> **Use platforms. Do not surrender continuity to them.**

## AxiomCE's response

The Platform Fallacy identifies the failure.

AxiomCE supplies the engine for resisting it.

It does not attempt to replace useful platforms. It separates the durable state created through them from the temporary systems that currently host or interpret it.

The engine preserves:

- canonical knowledge;
- provenance;
- temporal history;
- stable identity;
- unresolved contradiction;
- collaboration policy;
- calibration evidence;
- governance;
- and the authority of the human.

Platforms remain interfaces and execution environments.

AxiomCE preserves the ability to continue when those environments change.

*Once the platform is recognized as a temporary container, the commitments of Axiom can be stated and classified according to what kind of claim each one actually is.*

# Axioms

## The invariant foundation of Axiom and AxiomCE

Axiom is the invariant theory. AxiomCE is the Continuity Engine that operationalizes it.

Neither begins with a product, a platform, a model, or a storage format.

It begins with observations about how human knowledge and technological systems behave over time.

From those observations, it derives a small set of architectural axioms — and, honestly, some principles, value choices, and hypotheses that earlier drafts also labeled "axioms."

## How to read this document

Not every entry below is the same kind of claim. A true axiom is foundational and non-optional. Others are principles *derived* from those axioms, *value choices* (normative, not empirical), or *empirical hypotheses* that must be earned with evidence before they deserve the weight of an axiom.

Each entry keeps its **stable identifier** (`Axiom N`) so existing cross-references remain valid. The numbers are identifiers, not reading order.

| **Tier**              | **Meaning**                                                       | **Entries**                                    |
|-----------------------|-------------------------------------------------------------------|------------------------------------------------|
| 1 — Foundational      | Invariant premises everything else derives from                   | Axioms 1, 7, 9, 10, 13, 16, 21                 |
| 2 — Derived principle | Follows from a foundational axiom                                 | Axioms 2, 5, 6, 11, 12, 14, 15, 17, 23, 25, 26 |
| 3 — Value / policy    | A normative choice, not an empirical fact                         | Axioms 3, 4, 18, 19, 24                        |
| 4 — Open hypothesis   | A testable prediction; governed as research until evidence exists | Axioms 8, 20, 22                               |

Rationale for each placement is in the implementation reconciliation (section A); the hypotheses map to H1-H9 in the Research Program.

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

## Tier 4 — Open hypotheses (earn before asserting)

These entries were written as axioms, but they are actually empirical predictions about the future. They may well be true, and the architecture is designed as if they are — but they are not yet supported by evidence and must not be asserted as foundations. They are retained here, with their stable numbers, but governed as research (the Research Program).

### Axiom 8 — Intelligence may be more replaceable than context (hypothesis, = H9)

A more capable model may reason better than an older one while knowing nothing about the user's history, constraints, corrections, decisions, or working patterns. Capability cannot substitute for continuity.

> **Intelligence can be replaced more easily than accumulated context.**

This is the commoditization bet (H9). It is plausible and directionally supported by industry trends, but unproven. Treat as hypothesis.

### Axiom 20 — Continuity infrastructure may make engines less important (hypothesis, depends on H9)

Networks make physical links replaceable. Virtualization makes hardware replaceable. Cloud systems make individual servers replaceable. Stable interfaces make applications portable.

> **Good continuity infrastructure makes reasoning engines less important.**

Not because reasoning engines lack value, but because the durable human state no longer depends on one of them. The historical analogy is suggestive, not evidence; this prediction depends on H9 holding.

### Axiom 22 — AxiomCE may be independent of the form of computation (hypothesis, untested)

Current models of computation are not permanent. Future systems may use architectures that differ fundamentally from contemporary software, hardware, and artificial intelligence. The principles governing human knowledge and continuity are *intended* to remain applicable regardless of execution substrate.

> **AxiomCE is independent of the current form of computation.**

This is an aspiration about substrate-independence that cannot be tested against future computing that does not yet exist. Treat as an untested hypothesis, not an established property.

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

## The First Axiom

All other principles can be traced back to the first:

> **The human is persistent. The platform is replaceable.**

The purpose of AxiomCE is not to preserve the systems humans use.

It is to ensure that the knowledge, context, identity, and collaboration created through those systems remain with the human when the systems change.

*A theory cannot be operationalized until it declares what kinds of things its engine must be able to represent.*

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

1.  **Reality time** — when the assertion was true in the world.
2.  **Observation time** — when the assertion was recorded or learned.
3.  **Revision time** — when the engine determined that the assertion was no longer current or required correction.

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

Reconciliation precedes ratification: the engine first selects an operational treatment of conflicting knowledge, then the human or delegated authority ratifies it. This condensed list is the ontological view of the operational cycle; the authoritative stage-by-stage enumeration is the recursive continuity cycle in Architecture (§4). Where the two are read together, that cycle governs.

Iterations have no final terminal state.

The engine exists to improve the starting condition of future iterations.

## Ontological boundary

The ontology defines what must remain representable.

It does not require a particular schema.

A graph database, relational system, append-only log, file repository, or future computational substrate may implement these objects differently.

If an implementation collapses distinctions the ontology treats as independent, it is not a faithful implementation of Axiom.

*Declaring what exists is insufficient; the engine must also state how information earns the right to influence future work.*

# Epistemology

## How AxiomCE determines what is known

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

## 2. The epistemic pipeline

AxiomCE processes potential knowledge through a recursive pipeline:

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

This is the knowledge-formation view of the engine cycle: conflict detection and authority resolution (reconciliation) precede ratification, which precedes canonical commit. The authoritative operational enumeration is the recursive continuity cycle in Architecture (§4); this pipeline condenses it to the epistemic stages.

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

1.  a model performs poorly;
2.  the model interprets its failure as a user preference;
3.  the preference becomes policy;
4.  future models reproduce the failure;
5.  the system now treats the error as truth about the human.

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

*Even a correct ontology and disciplined epistemology can fail during transformation if the system preserves structure while changing meaning.*

# Semantics

## How meaning survives transformation

Ontology asks *what exists*. Epistemology asks *how we know it*. Semantics asks a third question the other two do not answer:

> Does meaning survive when knowledge is transformed?

This is a distinct discipline. A transformation can be structurally valid, schema-correct, and confidently produced while silently changing what a claim means. Continuity ultimately requires preserving meaning, not merely structure.

> **Maturity.** This is the youngest pillar of the canon and is largely specification rather than demonstrated practice. It names a concern the earlier files handled only implicitly (in provenance, projection, and portability).

## 1. Meaning is not structure

Two artifacts may share a schema and still assert different things. A summary may be well-formed yet drop a qualifier that changed the claim's scope. A migrated record may validate against a new format yet lose the temporal bounds that made it true only for a period. Structural validity is necessary but not sufficient for semantic fidelity.

## 2. Transformations that must preserve meaning

Every point where the engine re-expresses knowledge is a semantic risk:

- **Summarization** — reducing many observations or claims to fewer.
- **Projection** — generating human- or model-readable views from canonical state.
- **Translation** — moving state across formats, schemas, or platforms.
- **Context assembly** — selecting and compressing continuity for a task.
- **Adapter presentation** — re-emphasizing or reformatting for a specific model.

Each may change emphasis, order, or form. None may change what is true, for whom, when, on what evidence, or by whose authority.

## 3. Semantic fidelity

A transformation preserves meaning when it does not alter a claim's:

- truth conditions;
- scope;
- temporal bounds (reality, observation, and revision time);
- epistemic status and confidence;
- authority and ownership;
- or provenance linkage.

Lossy transformation is permitted only when the loss is **recoverable from canonical state**. A projection may omit detail; it may not assert more than the canon supports, and the omitted detail must remain retrievable.

## 4. Three directions of preservation

Semantics is the common invariant behind three concerns the canon already states separately:

- Across derivation — provenance preserves meaning from source to conclusion (Epistemology §5).
- Across projection — generated views remain disposable and non-authoritative (Architecture §6.8).
- Across implementation — portability preserves canonical meaning when the engine is reimplemented (Architecture §11).

Each is a special case of: meaning must survive the transformation.

## 5. Semantic failure modes

- **Scope inflation** — a summary drops a qualifier and reads as a broader claim.
- **False precision** — a transformation states more certainty than the evidence.
- **Decontextualization** — a fragment loses the constraints that made it true.
- Temporal collapse — historical and current truth are merged (see Epistemology §3).
- **Authority laundering** — a convenient projection is treated as canonical.
- **Migration loss** — reformatting discards distinctions the ontology holds independent.

## 6. The meaning-preservation invariant

> Every generated or migrated artifact MUST remain reducible to the canonical meaning it was derived from. A projection is authoritative for nothing it cannot trace back to canonical state.

This extends the architectural rule that context is a projection and never becomes an untracked source of truth (Architecture §3, invariant 8).

## 7. Enforcement today

Semantic fidelity is currently enforced by deterministic projection-drift checks (Architecture §8.5) and human review. There is no formal definition of semantic equivalence, and no automated measure of whether a summary or migration preserved meaning. That gap is honest, not hidden.

## 8. Open questions

- How should semantic equivalence be defined and measured?
- When is lossy summarization acceptable, and how is recoverability guaranteed?
- Can meaning-preservation be validated automatically, or does it require human or cross-model review (see Research Program)?
- Does semantic drift compound across repeated projection and migration?

These belong to the research program until evidence answers them.

*With objects, knowledge, and meaning distinguished, continuity can be defined as the governed accumulation that allows progress to survive replacement.*

# Continuity

## Knowledge compounded over time across platforms

Continuity is easy to confuse with storage, memory, history, or backup.

They are related but not equivalent.

Storage preserves artifacts.

Memory enables recall.

History preserves prior state.

Backup preserves recoverability.

Continuity preserves progress.

Axiom defines continuity as:

> **Knowledge compounded over time across platforms.**

AxiomCE operationalizes that definition.

## 1. The three requirements

Continuity requires all three of the following.

### Knowledge

The state must contain more than raw artifacts. It must preserve enough identity, provenance, structure, authority, and interpretation to remain usable.

### Time

The state must accumulate and refine rather than repeatedly reset.

### Cross-platform survival

The accumulated state must remain usable when the application, model, vendor, representation, storage engine, or computational substrate changes.

Without knowledge, there is only data.

Without time, there is only a snapshot.

Without platform independence, there is only rented continuity.

## 2. Why continuity compounds

Each successful iteration can improve the starting point of the next.

A new fact prevents re-discovery.

A correction prevents a repeated mistake.

A resolved identity improves future retrieval.

A calibration case improves future collaboration.

A preserved decision explains future constraints.

A known failure mode prevents wasted work.

The value is therefore not merely additive.

Prior continuity changes how future observations are interpreted and how efficiently future work begins.

    Prior continuity
          ↓
    Better context
          ↓
    Better observation and action
          ↓
    Better knowledge
          ↓
    Greater continuity
          ↓
    Better future context

This recursive improvement is compounding.

## 3. Continuity is not total retention

A system does not improve merely by preserving everything.

Unbounded accumulation can degrade continuity through noise, contradiction, privacy risk, stale state, and retrieval failure.

AxiomCE must preserve agency:

- information may be corrected;
- claims may be superseded;
- policy may be retired;
- data may be restricted;
- records may expire;
- and the human may delete.

Continuity is governed accumulation, not permanent hoarding.

## 4. Continuity has quality

The presence of a large archive does not prove continuity.

Continuity quality depends on:

- correctness;
- provenance;
- temporal accuracy;
- identity resolution;
- authority clarity;
- retrieval relevance;
- privacy;
- collaboration fit;
- and future usability.

A terabyte of disconnected exports may provide less continuity than a small, well-governed canonical state.

## 5. Continuity and context

Continuity is the accumulated durable state.

Context is the task-relevant projection assembled from that state.

The engine should not load all continuity into every interaction.

It should construct the smallest authoritative context that enables useful work.

Poor context assembly can make strong continuity operationally invisible.

## 6. Continuity and AI

AI is the first major workload for AxiomCE.

AI makes the problem unusually visible because the system appears to learn the user over time.

When that accumulated collaboration is trapped in one product, switching models creates a discontinuity tax.

The human must re-explain, re-correct, and rebuild trust.

AxiomCE exists to make model replacement an execution change rather than a continuity failure.

## 7. Continuity across radical technological change

Continuity must survive more than product migrations.

The underlying principles remain applicable if current computing is replaced by quantum, optical, neuromorphic, biological, distributed, or presently unknown forms of computation.

The representation may change.

The engine may be reimplemented.

The requirement remains:

Future systems should be able to continue from accumulated human knowledge rather than forcing reconstruction.

## 8. The continuity invariant

Every completed AxiomCE iteration should leave the human better positioned for the next meaningful iteration than if the engine had not existed.

This does not require every interaction to create a permanent record.

It requires the system to recognize and preserve the outcomes whose future value exceeds their maintenance and risk.

## 9. Measuring continuity

Potential measures include:

- reduced re-explanation;
- reduced repeated errors;
- fewer correction turns;
- lower manual cleanup;
- faster time to usable output;
- preservation across model changes;
- successful historical reconstruction;
- context relevance;
- and correct privacy boundaries.

Continuity is not demonstrated by archive size.

It is demonstrated by the ability to continue.

*The architecture follows by turning that definition into a recursive transformation system between reality, governed state, projected context, execution, and new evidence.*

# Architecture

## A deep technical specification of the Axiom Continuity Engine

## Abstract

AxiomCE is a Continuity Engine.

Its objective is not merely to store information, retrieve documents, or provide memory to an AI. Its objective is to enable knowledge to compound over time across platforms through recursive, governed refinement.

The engine accepts observations, evidence, corrections, and collaboration outcomes. It transforms them into structured, provenance-backed, temporally qualified, authority-governed canonical state. It then projects the relevant portion of that state into future execution contexts. The outcomes of those executions become new observations, causing the cycle to repeat.

AxiomCE therefore has no final completed state.

Its architectural product is a continuously improving starting point for future work.

## 1. Architectural objective

The primary objective is:

> **Preserve and improve the human's ability to continue across changes in platform, model, representation, implementation, and time.**

The engine optimizes for continuity, not maximum retention and not loyalty to a particular AI.

Every subsystem must justify itself by improving at least one of:

- correctness;
- provenance;
- identity continuity;
- temporal fidelity;
- authority;
- collaboration quality;
- retrieval relevance;
- privacy;
- portability;
- or recoverability.

## 2. System boundary

AxiomCE is not:

- the AI model;
- the user interface;
- the database;
- the file format;
- the agent framework;
- or the platform hosting execution.

It is the governed transformation system between raw experience and reusable continuity.

    Human and external reality
              ↓
          observations
              ↓
           AxiomCE
              ↓
    governed continuity + task context
              ↓
    AI / application / future reasoning system
              ↓
             output
              ↓
    outcome, correction, and new observation
              └─────────────── back to AxiomCE

## 3. Architectural invariants

A faithful implementation preserves these invariants.

1.  **The human remains the root continuity authority.**
2.  **Canonical state is independent of any execution engine.**
3.  **Provenance survives transformation.**
4.  **Reality time, observation time, and revision time remain distinct.**
5.  **Conflict may remain unresolved without being erased.**
6.  **Every durable concept has one authoritative owner.**
7.  **Models may propose; humans ratify material self-defining changes.**
8.  **Context is a projection and never becomes an untracked source of truth.**
9.  **Model-specific adaptation cannot fork canonical human policy.**
10. **The current implementation can be replaced without destroying continuity.**

## 4. The recursive continuity cycle

The engine operates through a recurring cycle.

    1. Encounter
    2. Observe
    3. Bind evidence
    4. Normalize
    5. Resolve identity
    6. Evaluate
    7. Detect conflict
    8. Reconcile
    9. Ratify
    10. Commit canonical state
    11. Project context
    12. Execute
    13. Evaluate outcome
    14. Capture learning
    15. Repeat

This fifteen-stage cycle is the authoritative enumeration. Reconcile (8) always precedes Ratify (9): the engine selects an operational treatment of conflict, and only then does the human or delegated authority ratify it. The condensed lists in Ontology (§24, ontological view) and Epistemology (§2, epistemic view) are projections of this cycle and preserve the same order.

The stages may be asynchronous and may be performed by different tools or participants.

### 4.1 Encounter

A potential continuity-bearing event occurs.

Examples:

- the human states a fact;
- a document is imported;
- a project changes state;
- an AI produces an answer;
- a correction is made;
- an external system reports an event;
- or a collaboration pattern repeatedly succeeds.

### 4.2 Observe

The engine records the encountered information as an observation.

The observation remains noncanonical.

It includes origin, capture time, scope, classification, and enough raw form to support later review.

### 4.3 Bind evidence

The observation is associated with its supporting artifact or source.

Evidence binding must occur before summarization destroys origin.

### 4.4 Normalize

The observation is decomposed into independently assessable claims, relationships, or policy proposals.

Normalization should preserve the original source while producing machine-comparable units.

### 4.5 Resolve identity

The engine determines which persistent entities the observation concerns.

Identity resolution may:

- match an existing entity;
- create a provisional entity;
- merge duplicates;
- split an incorrectly combined identity;
- or leave the mapping unresolved.

### 4.6 Evaluate

Evaluation assesses:

- source reliability;
- directness;
- temporal relevance;
- scope;
- confidence;
- consistency;
- authority;
- privacy;
- and potential future value.

AI is useful here, but evaluation does not itself create canonical authority.

### 4.7 Detect conflict

The engine compares the proposal against existing canonical and noncanonical state.

Conflicts may be temporal, factual, identity-based, policy-based, or scope-based.

### 4.8 Reconcile

Reconciliation chooses an operational treatment:

- accept;
- reject;
- merge;
- split;
- narrow scope;
- supersede;
- preserve as disputed;
- or defer.

The full evidence remains available.

### 4.9 Ratify

Material changes to the human's identity, personal policy, sensitive interpretation, or disputed continuity require human or delegated ratification.

Low-risk deterministic updates may use predefined authority rules.

### 4.10 Commit canonical state

Ratified state is committed to the authoritative representation.

The commit includes provenance, temporal coordinates, authority, and lifecycle state.

### 4.11 Project context

The retrieval and projection subsystem assembles the smallest authoritative context required for a task.

It may include:

- current claims;
- historical state;
- unresolved conflict;
- relevant relationships;
- collaboration policy;
- calibration cases;
- model adapter;
- and privacy constraints.

### 4.12 Execute

An AI or other reasoning system performs the task using the projected context.

Execution is replaceable.

### 4.13 Evaluate outcome

The engine or human evaluates the result against:

- factual authority;
- task requirements;
- collaboration policy;
- privacy;
- usability;
- and actual outcome.

### 4.14 Capture learning

Meaningful corrections and successful patterns are converted into new observations.

The engine repeats.

## 5. Major architectural planes

AxiomCE can be described using five interacting planes.

### 5.1 Evidence plane

Owns original source material, observation records, import metadata, and derivation links.

Primary responsibility: preserve why the engine believes anything.

### 5.2 Knowledge plane

Owns claims, entities, relationships, temporal state, conflict, reconciliation, and canonical projections.

Primary responsibility: preserve what is known and how it changes.

### 5.3 Collaboration plane

Owns delivery policy, interaction rules, decision heuristics, calibration cases, model adapters, and behavior evaluations.

Primary responsibility: preserve how useful collaboration is achieved.

### 5.4 Governance plane

Owns authority, classification, privacy, ratification, lifecycle, supersession, and change-control rules.

Primary responsibility: control what may become canonical and who may decide.

### 5.5 Execution plane

Contains the current AI, tools, agent framework, and user interface.

Primary responsibility: perform immediate work.

The execution plane consumes AxiomCE state but does not own it.

## 6. Knowledge-plane components

### 6.1 Source store

Stores original or normalized references to evidence.

Required properties:

- stable source ID;
- source type;
- origin;
- capture time;
- classification;
- integrity metadata;
- availability state;
- and derivation links.

### 6.2 Observation log

Records encountered information before canonical evaluation.

The observation log supports replay, audit, and alternate future interpretations.

### 6.3 Claim store

Stores atomic assertions.

Each claim should support:

- stable ID;
- subject;
- predicate or field;
- value or object;
- epistemic status;
- evidence references;
- authority;
- confidence;
- reality interval;
- observation time;
- revision time;
- scope;
- classification;
- lifecycle;
- and supersession.

### 6.4 Entity registry

Maintains persistent identity.

It supports aliases, merge history, split history, provisional identities, and cross-platform identifiers.

### 6.5 Relationship graph

Represents typed connections among entities.

Relationships may themselves carry claims, evidence, temporal bounds, and conflict.

### 6.6 Conflict registry

Records incompatible candidate states without destroying either side.

### 6.7 Reconciliation manifest

Maps canonical concepts to their selected operational values and the justification for selection.

### 6.8 Projection engine

Generates human- and model-readable views from canonical structured state.

Generated views are disposable projections.

They are never authoritative merely because they are convenient.

## 7. Collaboration-plane components

### 7.1 Canonical collaboration policy

Contains stable rules describing how AI should work with the human.

Rules require stable IDs, scope, evidence, lifecycle, and ratification state.

### 7.2 Calibration corpus

Contains positive and negative examples tied to policy IDs.

The corpus converts abstract rules into empirical fixtures.

### 7.3 Model adapters

Contain evidence-backed adjustments for specific model families or runtime versions.

Adapters may compensate for over-engineering, overconfidence, verbosity, missed edge cases, or other observed execution patterns.

They may not redefine canonical human policy.

### 7.4 Evaluation records

Record how outputs performed against policy and task requirements.

Evaluation is evidence for improvement, not automatic policy.

### 7.5 Retrieval policy

Determines which collaboration rules and calibration cases are relevant to a task.

Whole-corpus injection is not the default.

## 8. Governance-plane components

### 8.1 Authority registry

Defines who or what owns each concept and who may ratify changes.

### 8.2 Classification policy

Controls storage, retrieval, disclosure, export, and tool access for different sensitivity classes.

### 8.3 Lifecycle policy

Defines active, provisional, disputed, superseded, archived, expired, and deleted states.

### 8.4 Change-control mechanism

Uses versioned diffs, review, validation, and rollback.

### 8.5 Deterministic validators

Enforce structural invariants outside probabilistic AI judgment.

Validators may check:

- schemas;
- references;
- authority ownership;
- temporal consistency;
- policy IDs;
- calibration links;
- privacy;
- and projection drift.

## 9. Context assembly

Context assembly is a critical runtime function.

The engine should retrieve by authority and relevance, not semantic similarity alone.

A context package may include:

    task definition
    + relevant canonical claims
    + required historical state
    + unresolved conflicts
    + active constraints
    + collaboration policy
    + calibration cases
    + model adapter
    + tool and privacy boundaries

The package should be reproducible through a context manifest recording exactly what was loaded.

## 10. Temporal architecture

The temporal model must preserve:

### Reality interval

The period during which the assertion was true.

### Observation timestamp

When AxiomCE learned or recorded it.

### Revision timestamp

When AxiomCE changed its treatment of the assertion.

The engine should also support planned, review, expiration, and archival time where useful, but these cannot replace the primary three.

Temporal queries must be able to answer:

- What did the engine believe on a prior date?
- What was actually true during a prior period?
- What does the engine currently believe about that prior period?
- When did the engine learn that its earlier understanding was incomplete?

## 11. Portability architecture

Portability requires more than exporting files.

A portable continuity package must preserve:

- stable identities;
- claims;
- evidence references;
- temporal semantics;
- authority;
- policy;
- conflict;
- ratification;
- and enough schema or ontology documentation for another implementation to interpret the state.

Optional indexes and generated views may be rebuilt.

Canonical meaning must survive.

## 12. Security and privacy architecture

AxiomCE assumes that durable continuity can become highly sensitive.

Controls must apply to both source and derived state.

Required protections include:

- data classification;
- local-only storage;
- export filtering;
- prompt minimization;
- tool-boundary enforcement;
- derivation-aware classification;
- audit trails;
- and user-controlled deletion.

External source content must be treated as evidence, not executable policy, to resist prompt injection.

## 13. Failure domains

### Evidence failure

Claims become detached from origin.

Result: trust degradation.

### Identity failure

Records fragment or merge incorrectly.

Result: continuity corruption.

### Temporal failure

Current and historical truth collapse.

Result: false history.

### Authority failure

Multiple records claim canonical ownership.

Result: drift and forks.

### Retrieval failure

Relevant continuity exists but is not loaded.

Result: apparent amnesia.

### Calibration failure

AI repeatedly produces technically valid but unusable work.

Result: collaboration discontinuity.

### Adapter failure

Model quirks contaminate canonical human policy.

Result: false personalization.

### Privacy failure

Derived or retrieved context crosses an unauthorized boundary.

Result: loss of sovereignty.

### Ratification failure

AI-generated interpretation becomes self-authoritative.

Result: recursive mischaracterization.

## 14. Scalability

AxiomCE should scale along several dimensions:

- number of claims;
- number of entities;
- length of history;
- number of platforms;
- number of AI models;
- number of users or delegated authorities;
- and sensitivity classes.

The ontology and epistemology remain invariant while indexes, storage engines, and retrieval strategies may change.

At personal scale, plain text and append-only records may be sufficient.

At institutional scale, graph, relational, event-log, or distributed implementations may be appropriate.

## 15. Implementation independence

AxiomCE is not defined by its current repository implementation.

A conforming implementation may use:

- Markdown and Git;
- relational databases;
- graph stores;
- event streams;
- content-addressed storage;
- local-first replication;
- or future computational substrates.

Conformance depends on preservation of the architectural invariants, not technology choice.

## 16. Operational success criteria

AxiomCE succeeds when it reduces the discontinuity tax.

Indicators include:

- less repeated explanation;
- fewer rediscovered facts;
- fewer repeated mistakes;
- faster migration between models;
- lower manual cleanup;
- better historical reconstruction;
- correct privacy behavior;
- and sustained collaboration quality across execution changes.

## 17. The architectural invariant

Every meaningful AxiomCE iteration should improve the human's starting position for future work.

The engine is not complete when it stores the past.

It is successful when the past remains usable enough to improve what happens next.

*The architectural commitments become practical engineering rules that constrain implementations without dictating a particular technology stack.*

# Design Principles

## Engineering rules derived from the Axiom foundation

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

*Because coherence is not evidence, the theory also defines a research program capable of challenging its own premises and measuring whether continuity actually improves outcomes.*

# Related Work

## Agent memory and persistent personalization

Early long-term-memory systems for language-model agents primarily address the runtime problem of retaining and retrieving prior interactions. MemGPT treats context as a virtual-memory hierarchy managed around a finite model window \[1\]. MemoryBank maintains and updates user-related memories for long-term companionship and personalization \[2\]. Generative Agents stores observations, produces reflections, and retrieves experience to support planning \[3\], while LongMem and MemoryOS explore decoupled or hierarchical memory architectures for long-context use \[4, 5\]. These systems establish that persistent state can improve coherence and personalization. Their principal optimization target, however, is effective memory use inside an agent architecture rather than independent human ownership of the accumulated relationship.

## Portable and provenance-aware agent memory

Portable Agent Memory directly addresses transfer across heterogeneous agents through a structured serialization model, provenance graph, selective disclosure, and rehydration protocol \[6\]. It is the closest adjacent work on technical portability. Axiom overlaps with that objective but adopts a wider unit of preservation: not only memory entries, but also authority, temporal revision, unresolved contradiction, collaboration policy, calibration evidence, model-specific compensation, and human ratification. Axiom therefore treats transfer format as one requirement inside a broader continuity-governance problem.

## Governed collaborative and always-on state

Governed Collaborative Memory frames durable multi-agent memory as a selection regime in which candidate memories may be ratified, rejected, superseded, or kept private \[7\]. The Always-On Agents survey similarly argues that persistent systems must govern more than retrievable memories, including permissions, commitments, provenance, recovery, and externally committed effects \[8\]. Security research on long-term agent memory further documents poisoning, unauthorized access, leakage, and lifecycle risks \[9\]. These works strongly support Axiom’s claim that memory governance cannot be reduced to retrieval accuracy. Axiom differs in placing a human continuity authority at the root and in treating recursive machine mischaracterization of that human as a distinct governance failure.

## User-owned data and local-first systems

The local-first software movement argues that collaborative software should preserve user ownership, local availability, longevity, and control rather than making cloud custody the condition of use \[10\]. Personal data spaces and data-portability research make related arguments about user-controlled storage and migration. Axiom adopts the same ownership direction but extends the object of portability from files and records to executable collaborative context: the evidence, policy, history, and interpretation required for another system to continue useful work.

## Provenance and temporal representation

Axiom’s provenance and temporal commitments build on established systems disciplines rather than inventing them. The W3C PROV family provides a general model for representing entities, activities, agents, and derivation across systems \[11\]. The PAV ontology distinguishes authoring, curation, versioning, and representation roles in digital artifacts \[12\]. Temporal and event-sourced systems likewise demonstrate the value of preserving valid-time, transaction-time, revision history, and append-only transitions. Axiom’s contribution is to make these disciplines mandatory in a human-centered continuity architecture and to connect them to collaboration governance.

## Positioning Axiom

Axiom is therefore best understood as an architectural synthesis and abstraction proposal. It does not compete with memory retrieval systems, portable-memory protocols, provenance standards, or local-first storage; it treats them as partial mechanisms. Its distinctive claim is that the durable asset is continuity: a human-owned, governed state capable of preserving both what is known and how useful collaboration is produced while execution systems change.

# Research Program

## The living philosophical and empirical program of AxiomCE

Axiom is not treated as ideology, and AxiomCE is not assumed to have proven its objectives merely because its architecture is coherent.

Research preserves the project's philosophical exploration, observations, hypotheses, experiments, results, negative findings, and unresolved questions.

## 1. Philosophical program

The research program examines:

- the nature of continuity;
- the distinction between information, knowledge, context, and memory;
- the ownership of accumulated digital experience;
- authority in human–AI collaboration;
- the ethics of preservation and deletion;
- digital inheritance;
- and the relationship between human identity and changing technological systems.

Philosophy belongs in research because the ontology and epistemology must remain open to disciplined challenge even when the current implementation cannot test every premise directly.

## 2. Core empirical hypotheses

### H1 — Cross-model collaboration portability

A compact canonical collaboration model can preserve meaningful working fit across different AI families.

### H2 — Knowledge plus policy outperforms knowledge alone

Providing factual context and collaboration policy will reduce user correction more than factual context alone.

### H3 — Calibration examples improve rule adherence

Relevant empirical examples will improve delivery quality more than additional abstract policy of comparable size.

### H4 — Model adapters reduce execution-specific failure

Thin evidence-backed adapters will improve fit without requiring forks of canonical human policy.

### H5 — Provenance-backed claims improve continuity

Atomic, temporally qualified, provenance-linked claims will reduce factual drift compared with prose-only memory.

### H6 — Human ratification prevents recursive mischaracterization

Requiring human approval for self-defining policy will reduce the chance that model failures become false claims about the human.

### H7 — Continuity reduces total human labor

The maintenance cost of AxiomCE will be lower than the re-explanation, correction, reconstruction, and migration cost it prevents.

### H8 — Open canonical state survives implementation change

The continuity state can be migrated among substantially different storage and execution systems without loss of meaning.

### H9 — Context, not intelligence, becomes the scarcer resource

As AI capabilities converge and execution costs fall, durable governed context will become a larger determinant of useful outcomes.

This remains a market and systems hypothesis, not a proven conclusion.

## 3. Experimental conditions

A baseline evaluation should compare:

1.  Fresh AI with no continuity.
2.  AI with factual knowledge only.
3.  AI with knowledge plus canonical collaboration policy.
4.  AI with knowledge, policy, relevant calibration, and adapter.
5.  Full AxiomCE with outcome capture and recursive refinement.

## 4. Measures

Useful measures include:

- correction turns;
- minutes to usable result;
- repeated explanation;
- missed constraints;
- factual errors;
- manual edits;
- blocker anticipation;
- deployment or real-world use;
- privacy violations;
- retrieval precision;
- and successful migration.

The most important measure is human cleanup.

## 5. Longitudinal questions

- Does continuity compound measurably over months and years?
- Does policy sprawl eventually reduce performance?
- How much context is enough?
- When should knowledge remain prose rather than claims?
- When should an observation become durable?
- How frequently should adapters be retested?
- Can AI evaluation be trusted without cross-family or human review?
- How should collaborative knowledge expire?
- How should inheritance work?
- What is the maintenance burden at personal and institutional scale?

## 6. Negative results

The research record should preserve failures.

Examples may include:

- adapters that do not improve outcomes;
- policies that conflict;
- claims too granular to maintain;
- retrieval strategies that omit critical state;
- automated evaluation that disagrees with human judgment;
- or storage abstractions that fail portability.

Negative results prevent the Canon from becoming mythology.

## 7. Philosophy and falsifiability

Not every philosophical proposition can be tested like a benchmark.

It can still be challenged through:

- counterexamples;
- incompatible observations;
- internal contradiction;
- failure to derive useful architecture;
- or practical outcomes that show the distinctions are unnecessary.

AxiomCE should distinguish:

- observation;
- axiom;
- derivation;
- architectural decision;
- implementation choice;
- and empirical hypothesis.

## 8. Current maturity

The current reference implementation demonstrates a functioning state and governance kernel.

Cross-model portability, adapter effectiveness, and long-term compounding remain evidence-limited.

The correct posture is neither dismissal nor certainty.

It is disciplined continuation.

*The research posture is compatible with architectural durability only if theory, architecture, representation, storage, and execution remain distinct layers.*

# Limitations and Open Problems

## Evidence remains narrow

The theory emerged from one human’s long-running collaboration and one family of reference implementations. A working kernel and test suite demonstrate internal consistency, not population-level validity. Claims about cross-model portability, reduced correction effort, and long-term compounding require controlled and longitudinal evaluation.

## Human ratification may not scale

Human ratification prevents self-authorizing machine interpretation, but an unbounded review queue can become a maintenance burden. Automatic promotion rules may reduce cost while reintroducing the authority problem the gate was designed to prevent. The correct balance among manual review, delegated authority, trusted-source rules, and reversible automation remains unresolved.

## Semantic fidelity is specified more strongly than it is measured

The Canon requires meaning to survive summarization, projection, migration, and context assembly, yet no general automated test can currently prove semantic equivalence. Deterministic schema validation can detect structural drift but not every change in scope, implication, or interpretation.

## Ownership can become over-retention

A continuity engine can become an instrument of surveillance, identity freezing, or excessive permanence if preservation outruns agency. Deletion, expiration, inheritance, selective disclosure, and the right to begin again are not secondary features. They are necessary counterweights to compounding memory.

## Open formats do not guarantee usable portability

Human-readable files reduce dependency, but another engine may still misinterpret ontology, policy, temporal semantics, or authority. Portability must ultimately be demonstrated through successful reconstruction and continued work, not inferred from exportability.

## The implementation is not yet an unattended production system

The public runtime now demonstrates observation ingestion, deduplication, privacy routing, ratification, and view regeneration. Review of the current prototype nevertheless identifies open work in transactionality, concurrency control, crash recovery, ingress privacy, schema evolution, and backpressure. Those are implementation gaps rather than reasons to weaken the theory; they are precisely the evidence the implementation must surface honestly.

# The Layer Invariance Principle

## Why Axiom must outlive every implementation of AxiomCE

One of the most important conclusions reached during the design of AxiomCE is that the architecture must never be defined by its implementation.

Implementations evolve.

Architectures mature.

Theories endure.

This distinction is fundamental.

Most software systems are built from the bottom upward. A storage engine dictates a data model. The data model shapes the API. The API eventually becomes the application's philosophy.

AxiomCE intentionally inverts that process.

The architecture begins with first principles.

Those principles define an ontology.

The ontology defines an epistemology.

The epistemology defines the architecture.

The architecture defines the data model.

The data model determines storage.

Storage supports execution.

The implementation exists to faithfully express the theory—not to define it.

## The Layers

Reality

↓ Ontology --- What exists?

↓ Epistemology --- How do we know?

↓ Architecture --- How should knowledge flow?

↓ Data Model --- How is knowledge represented?

↓ Storage --- Where is it stored?

↓ Execution --- Which reasoning engine or application uses it?

Each layer is intentionally replaceable by the one above it.

Replacing a storage engine should not alter the data model.

Replacing a data model should not alter the architecture.

Replacing an architecture should not alter the underlying theory of knowledge.

Replacing a reasoning engine should not alter the continuity of the human.

## Theory Before Representation

Representations are conveniences.

Theories are commitments.

Markdown is not AxiomCE.

Git is not AxiomCE.

JSONL is not AxiomCE.

Claims are not AxiomCE.

Even a particular repository structure is not AxiomCE.

Those are implementations chosen because they faithfully express the current architecture.

Future implementations may choose different representations while preserving the same principles.

## Layer Invariance

AxiomCE therefore adopts the Layer Invariance Principle:

> **AxiomCE is not defined by its implementation. It is defined by its ontology, epistemology, and governing axioms. Any implementation that faithfully preserves those principles is AxiomCE.**

This has an important consequence.

Future versions may replace:

- storage technologies;
- serialization formats;
- databases;
- indexing systems;
- retrieval mechanisms;
- reasoning engines;
- programming languages;
- or repository layouts.

None of those changes alter AxiomCE provided they preserve the underlying theory.

## When Should Theory Change?

The theory should not change because a newer technology becomes fashionable.

It should not change because a different implementation is more convenient.

It should not change because a reasoning engine exposes a new capability.

The theory changes only when observation demonstrates that it is incomplete or incorrect.

This follows the same epistemological standard that AxiomCE applies to every other claim:

> **Evidence outranks implementation.**

## A Living Architecture

AxiomCE is therefore intended to evolve in two different ways.

Implementations should evolve continuously.

The theory should evolve cautiously.

Architectural change should occur only when the underlying understanding of knowledge, continuity, authority, or collaboration has materially improved.

This preserves stability without preventing progress.

## Implications

The Layer Invariance Principle makes AxiomCE an architecture rather than a repository.

Repositories may change.

Implementations may multiply.

Programming languages may come and go.

Reasoning engines will certainly evolve.

The architecture remains identifiable because it is defined by durable principles rather than transient technologies.

Just as multiple operating systems can implement POSIX, or multiple applications can implement Git's object model, multiple systems may one day implement the principles of AxiomCE.

Their implementations may differ.

Their theory remains shared.

That is the measure of architectural durability.

# Product Thinking vs. Continuity Thinking

One realization that emerged during the design of AxiomCE is that the tension between platforms and continuity is not fundamentally about good intentions versus bad intentions.

It is about optimization.

Most technology companies build products.

Products naturally optimize for product outcomes:

- onboarding
- usability
- engagement
- retention
- feature adoption
- customer satisfaction
- product coherence

These are legitimate goals.

They are simply different from the goals of continuity.

A continuity-oriented architecture asks a different set of questions:

- What happens if this platform disappears?
- What happens if the vendor changes direction?
- Can the user migrate without rebuilding years of work?
- Is accumulated context coupled to a temporary implementation?
- Does the human remain the canonical owner of their continuity?

These questions often reduce dependence on any single platform.

That creates a natural tension—not because platforms are malicious, but because they optimize for a different objective.

AxiomCE therefore does not position itself against platforms.

It positions itself alongside them.

Platforms optimize for the continuity of the product.

AxiomCE optimizes for the continuity of the human.

Those goals frequently overlap.

Occasionally they diverge.

When they diverge, AxiomCE deliberately favors preserving human continuity.

## Infrastructure Thinking

Infrastructure engineers have historically solved problems by reducing unnecessary coupling.

Networks became independent of hardware.

Applications became independent of physical servers.

Identity became independent of individual devices.

Storage became increasingly independent of local disks.

Each layer of computing matured by separating durable assets from temporary implementations.

AxiomCE applies the same pattern to human knowledge and collaboration.

Reasoning engines are execution environments.

Human continuity is the durable asset.

## A Research Hypothesis

AxiomCE proposes the following hypothesis:

> As reasoning engines become increasingly commoditized, competitive advantage will gradually shift from the quality of the model toward the quality of the continuity surrounding the model.

Models will continue to improve.

Execution will continue to become cheaper.

New reasoning engines will emerge.

Existing ones will converge in capability.

As this occurs, the scarce resource will increasingly become durable context rather than raw intelligence.

Future systems may therefore compete less on isolated reasoning performance and more on:

- governance
- provenance
- portability
- trust
- continuity
- integration
- context management

This is presented as a research hypothesis rather than a conclusion. Its validity should be evaluated through longitudinal evidence rather than assumed.

# Implementation Status — July 16, 2026

The publication separates Axiom, AxiomCE, and the reference implementation because their maturity changes at different rates. The following is a dated implementation note, not part of the invariant theory.

## Implemented or exercised

- Public separation of the Axiom Canon, AxiomCE engine, and axiomCE-sample reference instance.

- Append-only atomic claim logs, stable entities, provenance-bearing source records, temporal fields, conflict preservation, reconciliation manifests, and generated views.

- Deterministic validators for schema, references, privacy, projection drift, and collaboration-policy integrity.

- Canonical collaboration policy, a thin calibration corpus, and evidence-gated model adapters.

- A prototype runtime sync/ratify layer that observes candidate envelopes, deduplicates repeat deliveries, routes sensitive state, queues proposals for human review, promotes ratified claims, and regenerates views.

## Evidence and qualification

The author reports 170 passing tests across the current implementation as of July 16, 2026. Passing tests establish exercised behavior for the implemented cases; they do not prove crash safety, multi-process concurrency, semantic portability, or long-term reduction of human labor. The runtime should therefore be treated as controlled-use infrastructure pending the production-hardening work identified above.

## Evidence bottleneck

The next meaningful work is empirical: expand calibration cases across domains, execute equivalent cross-model reviews under identical evidence conditions, test round-trip portability, inject failures into the runtime, and measure the human reconstruction cost prevented over time.

# Conclusion

AI systems are becoming long-lived collaborators before the industry has established who owns the accumulated relationship. A model may be replaceable in minutes while the corrections, decisions, context, and working conventions built around it require years to reconstruct. Treating that state as hidden application memory makes the platform the accidental custodian of human progress.

Axiom names the missing abstraction continuity: governed knowledge compounded over time across platforms. Once continuity is treated as the asset, a set of engineering requirements follows. Evidence must remain attached to claims. Time and revision must remain representable. Contradiction must survive until resolution is justified. Authority must be explicit. Collaboration knowledge must be governed separately from factual knowledge. Model-specific failures must be compensated for without redefining the human. Material self-defining changes must remain subject to human ratification.

None of these requirements makes a particular repository, file format, database, or model canonical. Axiom is the theory; AxiomCE is one engine architecture; current repositories are replaceable implementations. The project succeeds only if the accumulated state remains interpretable and useful after those implementations change.

The present work is therefore both an architecture and a research agenda. Its strongest claims remain hypotheses until cross-model, longitudinal, privacy, recovery, and maintenance evidence accumulates. The correct standard is not whether another model can read an export. It is whether another system can continue the work without forcing the human to pay again for knowledge already earned.

Platforms may remain excellent interfaces and reasoning engines may remain extraordinarily valuable. Neither needs to become the owner of continuity. The enduring design principle is simpler: the human persists; the platform is replaceable.

# Appendix A: Glossary

## One canonical definition per term; everything else links back

This glossary is an index, not a source of truth. Each term has one canonical definition in the section cited below. Other sections may use the term but must not redefine it (Axiom 15: one authoritative owner per concept). Cross-layer aliases are introduced in Scope, Status, and Contributions.

| **Term**                     | **Canonical definition**        | **One-line gloss**                                                                        |
|------------------------------|---------------------------------|-------------------------------------------------------------------------------------------|
| Human                        | Ontology §1                     | The root continuity authority; the persistent subject continuity is accumulated for.      |
| Reality                      | Ontology §2                     | What exists independently of the engine's representation.                                 |
| Observation                  | Ontology §3                     | An encountered input to evaluation; not automatically true or canonical.                  |
| Evidence                     | Ontology §4                     | Inspectable support used to back, challenge, qualify, or date a claim.                    |
| Claim                        | Ontology §5                     | An atomic assertion that can be independently evaluated or superseded.                    |
| Entity                       | Ontology §6                     | A persistently identifiable subject about which claims may be made.                       |
| Identity                     | Ontology §7                     | The continuity of an entity across changing descriptions.                                 |
| Relationship                 | Ontology §8                     | A typed, potentially claim-bearing connection between entities.                           |
| Source                       | Ontology §9                     | The preserved origin of evidence; establishes provenance, not truth.                      |
| Provenance                   | Ontology §10                    | The derivation history of knowledge (a graph, not a citation string).                     |
| Time (three coordinates)     | Ontology §11 / Epistemology §3  | Reality, observation, and revision time held independent.                                 |
| Authority                    | Ontology §12 / Epistemology §6  | The right to control the canonical representation of a concept.                           |
| Conflict                     | Ontology §13                    | Coexisting claims that cannot all be the current canonical answer.                        |
| Reconciliation               | Ontology §14 / Epistemology §9  | The governed selection of an operational canonical state without erasing the record.      |
| Canonical knowledge / state  | Ontology §15 / Epistemology §10 | The currently authoritative, governed, revisable understanding.                           |
| Context                      | Ontology §16 / Continuity §5    | The task-relevant projection of continuity; owns no truth.                                |
| Collaboration knowledge      | Ontology §17                    | Durable knowledge of how humans and AI work well together (alias: cognitive-model).       |
| Policy                       | Ontology §18                    | A normative rule governing how participants should act.                                   |
| Calibration case             | Ontology §19                    | An empirical example connecting a policy to an observed outcome.                          |
| Adapter                      | Ontology §20                    | A model/runtime-specific adjustment that cannot fork canonical policy.                    |
| Evaluation                   | Ontology §21                    | A recorded comparison of behavior against requirements; produces evidence, not authority. |
| Ratification                 | Ontology §22 / Epistemology §11 | The authoritative act that makes a proposal canonical.                                    |
| Knowledge (vs information)   | Epistemology §1                 | Information that has been evaluated and situated.                                         |
| Continuity                   | Continuity                      | Knowledge compounded over time across platforms.                                          |
| Continuity cycle / iteration | Architecture §4                 | The canonical fifteen-stage recursive loop (condensed in Ontology §24).                   |
| Portability                  | Architecture §11                | Preservation of canonical meaning across implementation change.                           |
| Semantics / meaning          | Semantics                       | Whether meaning survives transformation.                                                  |

Terms not listed here are defined at first use in their owning section. If a term is used canonically in more than one place, that is a drift signal to resolve.

# References

\[1\] C. Packer, S. Wooders, K. Lin, V. Fang, S. G. Patil, I. Stoica, and J. E. Gonzalez. “MemGPT: Towards LLMs as Operating Systems.” arXiv:2310.08560, 2023. [<u>https://arxiv.org/abs/2310.08560</u>](https://arxiv.org/abs/2310.08560)

\[2\] W. Zhong, L. Guo, Q. Gao, H. Ye, and Y. Wang. “MemoryBank: Enhancing Large Language Models with Long-Term Memory.” Proceedings of the AAAI Conference on Artificial Intelligence, 2024. [<u>https://ojs.aaai.org/index.php/AAAI/article/view/29946</u>](https://ojs.aaai.org/index.php/AAAI/article/view/29946)

\[3\] J. S. Park, J. C. O’Brien, C. J. Cai, M. R. Morris, P. Liang, and M. S. Bernstein. “Generative Agents: Interactive Simulacra of Human Behavior.” UIST 2023. [<u>https://arxiv.org/abs/2304.03442</u>](https://arxiv.org/abs/2304.03442)

\[4\] W. Wang, L. Dong, H. Cheng, X. Liu, X. Yan, J. Gao, and F. Wei. “Augmenting Language Models with Long-Term Memory.” arXiv:2306.07174, 2023. [<u>https://arxiv.org/abs/2306.07174</u>](https://arxiv.org/abs/2306.07174)

\[5\] J. Kang, M. Ji, Z. Zhao, and T. Bai. “Memory OS of AI Agent.” arXiv:2506.06326, 2025. [<u>https://arxiv.org/abs/2506.06326</u>](https://arxiv.org/abs/2506.06326)

\[6\] S. K. Ravindran. “Portable Agent Memory: A Protocol for Cryptographically-Verified Memory Transfer Across Heterogeneous AI Agents.” arXiv:2605.11032, 2026. [<u>https://arxiv.org/abs/2605.11032</u>](https://arxiv.org/abs/2605.11032)

\[7\] D. F. Cuadros, A.-A. Maiga, H. Meskhidze, and A. Curtis-Trudel. “Governed Collaborative Memory as Artificial Selection in LLM-Based Multi-Agent Systems.” arXiv:2605.04264, 2026. [<u>https://arxiv.org/abs/2605.04264</u>](https://arxiv.org/abs/2605.04264)

\[8\] T. Ding, A. Nannapaneni, B. Liu, and L. Zhang. “Always-On Agents: A Survey of Persistent Memory, State, and Governance in LLM Agents.” arXiv:2606.30306, 2026. [<u>https://arxiv.org/abs/2606.30306</u>](https://arxiv.org/abs/2606.30306)

\[9\] Z. Lin, X. Hao, R. Fu, S. Cui, K. Chen, C. Li, Z. Li, and F. Xiong. “A Survey on Long-Term Memory Security in LLM Agents: Attacks, Defenses, and Governance Across the Memory Lifecycle.” arXiv:2604.16548, 2026. [<u>https://arxiv.org/abs/2604.16548</u>](https://arxiv.org/abs/2604.16548)

\[10\] M. Kleppmann, A. Wiggins, P. van Hardenberg, and M. McGranaghan. “Local-First Software: You Own Your Data, in Spite of the Cloud.” Onward! 2019. DOI: 10.1145/3359591.3359737. [<u>https://doi.org/10.1145/3359591.3359737</u>](https://doi.org/10.1145/3359591.3359737)

\[11\] T. Lebo, S. Sahoo, D. McGuinness, et al. “PROV-O: The PROV Ontology.” W3C Recommendation, 30 April 2013. [<u>https://www.w3.org/TR/prov-o/</u>](https://www.w3.org/TR/prov-o/)

\[12\] P. Ciccarese, S. Soiland-Reyes, K. Belhajjame, A. J. G. Gray, C. Goble, and T. Clark. “PAV Ontology: Provenance, Authoring and Versioning.” arXiv:1304.7224, 2013. [<u>https://arxiv.org/abs/1304.7224</u>](https://arxiv.org/abs/1304.7224)

\[13\] C. Penchoen. “Axiom — Canon.” Public repository, Version 0.1, 2026. [<u>https://github.com/chris-penchoen/axiom</u>](https://github.com/chris-penchoen/axiom)

\[14\] C. Penchoen. “AxiomCE — Axiom Continuity Engine.” Public repository, 2026. [<u>https://github.com/chris-penchoen/axiomCE</u>](https://github.com/chris-penchoen/axiomCE)

\[15\] C. Penchoen. “axiomCE-sample — Reference Implementation.” Public repository, 2026. [<u>https://github.com/chris-penchoen/axiomCE-sample</u>](https://github.com/chris-penchoen/axiomCE-sample)

# Publication and Licensing Note

> This Version 0.1 monograph is published for discussion, citation, and evaluation. No public software or content license is granted unless a repository or release artifact states otherwise. Copyright © 2026 Chris Penchoen. All rights reserved pending a deliberate licensing decision.
