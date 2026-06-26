---
purpose: loading-index
audience: everyone · AI agent
folder: (canon root)
version: 0.0.3
last-reviewed: 2026-06-26
status: draft
schema-version: v4-standard-method
---

# Canon — `_INDEX` (the standard method for human–AI collaboration)

> **Read [`CANON.md`](CANON.md) first.** It is the whole standard. This index just says
> what each document is and the order to read them.

## What Canon is (and is not)

Canon is the **standard method** by which humans and AI collaborate so that any role-cleared
participant — whatever their starting capability — can produce work at the project's quality
standard. It defines *what must be true and how conformance is judged*. It is **not** the
software that runs it: the runnable mechanism is a separate **Tool** that *conforms to*
Canon (see [`CANON.md` §9](CANON.md#9-the-canon--tool-boundary)).

## The documents

| Document | What it is |
|---|---|
| [`CANON.md`](CANON.md) | **The standard.** Purpose, the capability claim (vision + falsifiable form), method-vs-knowledge, the collaboration model (AI-leads ↔ human-leads-and-evolves), AI's obligations, the lifecycle spine, the gates, specialization invariants, scope/limits, the Canon↔Tool boundary, and ecosystem neutrality. |
| [`CONFORMANCE.md`](CONFORMANCE.md) | **The interface.** What makes a tool or process Canon-conformant: the portable Canon-trace, conformance targets, profiles, certification levels, regulatory mapping. *Keeps Canon a standard, not a slogan.* |
| [`GLOSSARY.md`](GLOSSARY.md) | **The vocabulary.** Core terms. |

## Reading order

1. [`CANON.md`](CANON.md) — the standard, start to finish (it is lean).
2. [`CONFORMANCE.md`](CONFORMANCE.md) — if you build, audit, or certify a tool against Canon.
3. [`GLOSSARY.md`](GLOSSARY.md) — as a reference while reading the above.

## Not part of Canon

The runnable mechanism (executable lifecycle procedures, gate checkers, runtime state,
plug-in resolution) is **not** published Canon. It is built as a separate **Tool** in its own
repository ([`CANON.md` §9](CANON.md#9-the-canon--tool-boundary)).
