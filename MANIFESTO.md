---
title: The Continuity Manifesto
type: theory
classification: public
status: draft
created: 2026-07-17
updated: 2026-07-17
version: 0.1
confidence: user-stated
tags: [manifesto, continuity, local-first, portability, provenance, authority]
---

# The Continuity Manifesto

**The model is the commodity. Your accumulated context is the asset. It should
be owned by you, portable across models, and inspectable by any human or
machine without permission.**

This is a claim about where durable value lives in the age of AI, and who should
hold it. It is stated plainly here so it can be read, dated, argued with, and —
if it is wrong — falsified.

## The thesis

1. **AI reasoning models are interchangeable computation.** They improve,
   deprecate, get acquired, change their terms, and are replaced. Treating any
   one of them as the permanent home of what you know is a category error.

2. **The durable, valuable asset is the accumulated record** of what you have
   established, decided, corrected, and come to understand through working with
   these systems — together with *where each piece came from* (its provenance),
   *when it was true* (its temporal history), and *who has authority over it*.

3. **That record must be human-owned, portable, and inspectable.** It should
   live as plain text under version control — readable today by a person, and
   tomorrow by any model, with no migration step, no vendor account, and no
   database only one company can open.

4. **The human is the continuity agent; the model is a tool passing through.**
   A model may *propose* additions to the record. Authority over the record is
   human-held — never self-certified by a model, and always reversible.

We call the thing that operationalizes this a **Continuity Engine**: the
inspectable seam between replaceable black-box models, through which knowledge
passes without being lost and without being owned by the vehicle that carried
it. The objective is not better memory. The objective is that every future
iteration begins farther ahead than the last.

## What is broken now

Every major AI platform stores your accumulated relationship on its own servers,
in its own format, under its own terms. Export exists for legal compliance, and
it produces a blob of transcripts — not a structured context another system can
actually use. The newer "improved" memories are *less* portable than the old
key-value ones, not more, because opacity is the point: the more the system
knows you, the harder you are to leave. Memory is the moat.

The clearest cautionary tale is already on the record: a company whose entire
value was the personal AI memory it captured from its users was acquired, and
that accumulated relationship became someone else's asset overnight. Users got
an export button. That is what "portability" means when the incentives run the
other way.

## Honest lineage

This position did not appear from nothing, and it would be dishonest to imply it
did. It stands on:

- **Local-first software** (Kleppmann et al., Ink & Switch, 2019) — you own your
  data, on your device, in spite of the cloud. The architecture of this
  manifesto is that essay's seventh ideal, carried into the AI era.
- **Separating applications from data** (Berners-Lee, *Socially Aware Cloud
  Storage*, 2009; the Solid project) — swap the app, keep the data. Here the
  "app" is the model.
- **Data dignity** (Lanier, *Who Owns the Future?*, 2013) — your accumulated
  contribution has value and should not be taken by default.
- **The agent-memory field** (MemGPT/Letta, Mem0, Graphiti, and others) — which
  has built real machinery for AI memory, provenance, and temporal validity.

Each of these has part of the picture. None has assembled the specific one this
manifesto makes.

## What is actually new here

The agent-memory field built **memory layers for AI** — help the model remember.
This is a **knowledge layer for humans** — help the human's knowledge survive the
model. Three commitments distinguish it, and as of this writing no system has
made all three at once:

- **Plain text and version control as the ground truth** — not a vector store,
  relational database, or graph engine you cannot open without the vendor's
  tooling. Diff, blame, rollback, and fork applied to what you know.
- **The human as ratifying authority** — the model proposes into a provisional,
  labeled state; a human promotes it into the record. Everywhere else, the model
  is the epistemological authority and the human is a passenger.
- **Provenance and evidence as first-class, governed constructs** — every claim
  carries how it is known and where it came from; confidence never earns belief
  on its own; evidence outranks it; and a withdrawn fact is retired with its
  history intact, never silently erased.

## What we are *not* claiming

Honesty is load-bearing here, so the limits are stated as plainly as the thesis:

- **The central portability claim is a hypothesis, not a proven result.** That a
  human's collaboration context can be carried across model families with little
  loss is *plausible and, at present, under-evidenced.* It needs many more cases
  across many more models before it earns the weight of a fact. Anyone who tells
  you this is solved — including a future version of us — should be asked for the
  data.
- **This is not a legal ownership claim.** It is an argument about architecture
  and stewardship, not a patent or a property line.
- **Plain text is a deliberate trade, not a free win.** It buys ownership and
  inspectability at the cost of the retrieval sophistication a vector database
  gives you. That cost is real and must be paid down with engineering, not
  waved away.

## The test that settles it

The thesis is not an essay to be admired; it is a claim to be run. It succeeds or
fails on one demonstration:

> Take everything a human has built up with one model. Hand it to a different
> model, from a different company. Lose nothing that mattered — and be able to
> audit, line by line, what was carried and why.

Do that repeatably, across model families, with the record legible the whole way
through, and the thesis is proven. Fail to, and it is just another manifesto.
We intend to run the test.

---

*Stated publicly on 2026-07-17. This is a living document; its claims are labeled
by how they are known and will be revised as evidence arrives. The theory it
belongs to is the Axiom canon (`00_AXIOMS.md`); the engine that operationalizes
it is AxiomCE.*
