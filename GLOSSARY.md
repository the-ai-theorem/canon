---
title: Glossary — core terms
project: The AI Theorem
doc: GLOSSARY
version: 0.0.3
last-reviewed: 2026-06-26
status: draft
audience: everyone
---

# Glossary — Core Terms

> Canon's vocabulary. Terms for the *runnable mechanism* (process contracts, runtime
> substrate, plug-in resolver) are **not** here — they belong to the Tool, not the standard.

| Term | Definition |
|---|---|
| **The AI Theorem** | The claim that the reusable part of expert work is a *method* that can be standardized as Canon, executed with AI, and combined with supplied knowledge so that any role-cleared participant — regardless of skill above the role's baseline — reaches the project's quality standard. The vision; its testable form is a falsifiable hypothesis ([`CANON.md` §1](CANON.md#1-the-claim--vision-and-the-testable-form)). |
| **Canon** | The domain- and vendor-neutral **standard method** for how humans and AI collaborate. It defines *what must be true and how conformance is judged* — not the software that runs it. |
| **Standard method** | The part of expertise that is a *repeatable way of working*, externalized once and shared, so a participant need not personally keep up with AI advances to work at the standard. |
| **Method vs. knowledge** | Canon's founding split: the **method** (Canon, one for all domains) is separated from the project **knowledge** (supplied per project). The method is stable; only the knowledge changes per project. |
| **Lifecycle (L1–L6)** | The six stages accountable work passes through — Inception, Specification, Execution, Verification, Operation, Evolution. Canon's normative **audit/evidence spine**: it states entry/exit and required evidence, not the runnable procedure. |
| **Gate** | A cross-cutting check a step must clear to advance: `quality`, `risk-safety`, `cost`, `traceability`, `collaboration` (base), and `uplift`, `operator-readiness` (opt-in). A project may **strengthen** a gate, never weaken it. |
| **Collaboration surface (shared state)** | The small, always-current shared picture — objective, plan, assumptions, open questions, confidence, disagreements — that both human and AI read and correct. Canon **guarantees it is available**; it does not impose a click quota. |
| **Rationale** | What a material decision must expose: the claim, evidence, assumptions, rejected alternatives, uncertainty, and *what would change the recommendation*. |
| **AI leads / Human leads** | The two directions of the collaboration model. *AI leads* by running the method and structuring the work path; *human leads* by steering, on which the AI **accepts the lead and evolves a conformant project specialization** (the applied process, not the standard itself). Both valid; the human always keeps authority and the right to contest. |
| **Steersman / Guided operator** | The engagement spectrum. A *guided operator* mostly executes the method and still reaches the standard via AI guidance; a *steersman* also trains, challenges, and evolves the AI and Canon, and grows most. Both valid; passive approval-clicking alone is not valid collaboration. |
| **Capability leveling** | Canon's central **falsifiable hypothesis**: role-cleared participants working through Canon reach **one common high standard** regardless of skill *above the role baseline*. Measured against declared criteria, not asserted. |
| **Capability uplift** | The *secondary*, opt-in promise that a steersman grows over time (teach-while-doing). Offered, not guaranteed. |
| **Standard-grade / target common standard** | The concrete bar leveling targets: work passes the acceptance criteria + Definition of Done, clears every **required gate**, and meets the project's supplied criteria and org threshold. Declared at L1; raised each cycle (L6). Not a vibe — a checklist. |
| **Specialization** | A project fitting Canon to itself by **adding** knowledge and **stricter** rules — never forking or weakening it. Bound by the specialization invariants. |
| **Specialization invariants** | The rules every specialization must preserve: **monotonic / stricter-only** (add or strengthen, never weaken/remove), **authority order**, **provenance**, and **conformance** ([`CANON.md` §7](CANON.md#7-specialization--projects-do-not-fork-canon)). |
| **Canon ↔ Tool boundary** | The load-bearing rule: Canon owns *what must be true and how conformance is judged*; the Tool/agent owns *everything executable* (runnable procedures, checkers, runtime state, resolvers, tool/command choices, planning, recovery). |
| **Tool** | The runnable mechanism that *uses* Canon to do work — a reference runner and/or a vendor's agent. It **conforms to** Canon; it is not part of the standard, and is built in its own repository. |
| **Conformance / Canon-conformant** | A claim that a tool or process complies with Canon's method at a stated level — attesting *process compliance*, never warranting an outcome. |
| **Canon trace** | The strict, typed, machine-checkable audit/evidence record a conformant tool must emit. The one thing Canon actually standardizes ([`CONFORMANCE.md` §2](CONFORMANCE.md#2-the-canon-trace--the-one-thing-that-is-standardized)). |
| **Evidence class** | The allowed backings for a "done" claim: **test · eval · review · measurement**. Assertion is not evidence. |
| **Provenance** | Source, author, and time attached to any artifact, claim, or promoted change — required by the traceability gate. |
| **Conformance profile** | A named requirement set: **Core Audit** (base) plus optional **Regulated Enterprise** and **Learning/Uplift** layers. They compose; the active gate set is their union. |
| **Operator readiness** | An opt-in (Regulated Enterprise) **prerequisite check** that an operator holds the **authority/credentials** a decision requires; routes out-of-fit decisions to a cleared operator. Transparent and contestable — **never a worker score**. |
| **Differentiation-preserving neutrality** | Why vendors can share Canon: it standardizes only the portable audit/evidence interface, leaving each vendor's agent workflow (planning, memory, tools, recovery, UX) untouched as their moat. |

## Retired terms

`3-frame matrix`, `72 process cells`, `Knowledge Area (K01–K13)` — retired in the v0.0.3
lean-core build. Mechanism terms (`Process Contract P0–P6`, `Substrate`, `Runtime Bind`,
`Reasoning Ladder`, `plug-in extends`) belong to the **Tool**, not Canon.

## See Also

- [`CANON.md`](CANON.md) · [`CONFORMANCE.md`](CONFORMANCE.md) · [`_INDEX.md`](_INDEX.md)
