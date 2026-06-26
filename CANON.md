---
title: Canon — The Standard Method for Human–AI Collaboration
project: The AI Theorem
doc: CANON
version: 0.0.3
last-reviewed: 2026-06-26
status: draft
audience: everyone (adopters · contributors · AI agents · vendors)
---

# Canon — The Standard Method for Human–AI Collaboration

> **What this document is.** Canon is the **standard method** by which a human and an AI
> work together well. It defines *what good human–AI collaboration requires* and *how that
> can be checked* — not the software that runs it. The runnable mechanism (executable
> procedures, checkers, runtime state, plug-in resolvers) is a separate **Tool** that
> *conforms to* Canon; it is out of scope here ([`#9`](#9-the-canon--tool-boundary)).
>
> Canon is **domain-neutral and vendor-neutral**. Companies and services across the
> ecosystem can adopt and advance it in common ([`#10`](#10-ecosystem--neutrality)).

---

## 0. Purpose (one line)

> **Canon is the standard way humans and AI collaborate so that any participant who meets a
> role's baseline — whatever their expertise beyond that — can, by doing the work the way
> Canon defines, produce work whose quality matches the project's goal.**
>
> *(This is the **vision**; [§1](#1-the-claim--vision-and-the-testable-form) gives the precise, testable form.)*

The hard problem Canon answers: AI advances faster than any organization's people can keep
up with. Individual members cannot continuously absorb the latest technology and theory.
Canon absorbs it **once, as a shared method** — so a member does not need to be an AI
expert, a prompt engineer, or even the domain expert to contribute work at the project's
standard. They need to **engage in the collaboration Canon defines.**

---

## 1. The claim — vision and the testable form

**Vision (the design target).** Following Canon, *anyone cleared for a role* — even with
little expertise beyond that role's baseline — can produce work that meets the project's
quality goal, because the method (not the person's prior expertise) carries the rigor.
"Role-cleared" is the floor: it means the person holds the role's baseline credentials,
permissions, and safety requirements. Canon's claim is to **bridge the gap from that baseline
to expert-grade output** — not to qualify someone for a role they are not cleared for.

**The testable form (what is actually claimed and measured).** Stated honestly, this is a
**falsifiable hypothesis**, not a guarantee:

> For work whose process can be made explicit, when role-cleared participants do that work
> through Canon with the project's knowledge supplied, their output reaches **one common
> high standard** — measured against pre-declared acceptance criteria — **regardless of their
> skill above the role baseline.**

Canon is **wrong** if cleared low-skill participants' guided output does *not* reach the
same declared quality band as expert participants' output on the declared metric
([`#8 Scope & limits`](#8-scope--limits)). The vision is the ambition; the hypothesis is
how we keep ourselves honest. Canon promises **leveling and lift through method**, never a
master's ceiling and never replacement of human judgment.

---

## 2. What Canon separates: method from knowledge

Canon rests on one move — **separate the standard *method* from the project *knowledge*.**

| | **Method** (this is Canon) | **Knowledge** (supplied per project) |
|---|---|---|
| What it is | how human + AI collaborate: the work's stages, the checks, who decides, what evidence | domain facts, constraints, templates, acceptance bars, private/regulated data |
| Who owns it | the Canon standard — **one** method for all domains | the project — attached at runtime, per project |
| Stability | very stable | changes per project |
| Example | "agree acceptance criteria before building; a human approves risk" | "this plant's safety thresholds and report format" |

The method does not change per domain; only the supplied knowledge does. This is why a
non-expert can still produce standard-grade work: the **method** carries the part of
expertise that is a *repeatable way of working*, and the **knowledge** is supplied to them.

---

## 3. The collaboration model — AI leads, or the human leads and Canon evolves

Canon defines collaboration as a **two-directional** relationship, not a command line:

- **AI leads by Canon.** The AI runs the standard method: it frames the next step, surfaces
  its plan, assumptions, and confidence, asks the human only for what the current step
  needs, acts, checks the result against the standard, and produces the required output. A
  participant who mostly follows this still reaches the standard — the AI structures the
  **work path** (sequence, checks, scaffolding), never the **person**.
- **The human leads and the process evolves.** A human may instead steer: inspect the
  reasoning, correct an assumption mid-task, challenge a decision, impose a constraint. When
  they do, the AI **accepts the lead and evolves the *applied process* into a
  project-optimized form** — a conformant **specialization** of Canon fitted to this project
  ([`#7`](#7-specialization--projects-do-not-fork-canon)). What evolves is the project's
  applied process, *not* the standard itself: the standard method stays invariant ([`#2`](#2-what-canon-separates-method-from-knowledge)); the
  specialization only adds and strengthens.

Both directions are valid, and most work mixes them. What Canon **guarantees is available**
is the collaboration surface itself — a shared, current picture of objective, plan,
assumptions, open questions, confidence, and pending decisions, which either side can read
and correct. Passive approval-clicking with no steering is **not** valid collaboration.

In every direction the human keeps **authority, accountability, and the right to
interrupt and contest.** AI is the method's executor and the human's collaborator — **not
the authority.**

---

## 4. AI's obligations under Canon

Beyond executing the method, Canon obliges the AI to actively **raise the human and the
work**:

1. **Lead the work to the next step** — don't wait to be prompted; the goal is enough to start. Prompt-craft is never required of the human.
2. **Surface reasoning, invite correction** — for material decisions, expose the claim, evidence, assumptions, rejected alternatives, uncertainty, and *what would change the recommendation*.
3. **Provide tooling and automation** — propose the tools, harnesses, and automations that make the work more efficient, and set them up so the human need not assemble them.
4. **Teach while doing** — explain at a depth the participant can absorb, so a participant *can* grow from guided to steering over time. Teaching is offered; growth is not forced.
5. **Ask only what the step needs** — a typed request to the human, never defaulting a material decision or a required approval.
6. **Repair openly** — when something goes wrong, surface it, explain the cause, and propose recovery.

---

## 5. The lifecycle — the normative spine

Accountable human–AI work moves through six stages. Canon names them and states **what must
be true to leave each** (entry/exit + required evidence). It does **not** prescribe the
runnable procedure — that is the Tool's ([`#9`](#9-the-canon--tool-boundary)).

| Stage | What it establishes | Cannot exit until |
|---|---|---|
| **L1 Inception** | the goal → a charter: scope, KPI, risk/budget seed | charter approved; no hard no-go open |
| **L2 Specification** | requirements, acceptance criteria, contracts | spec is traceable to the goal; ready-to-build agreed |
| **L3 Execution** | a unit of change produced, with self-check evidence | self-check passes; within agreed scope/budget |
| **L4 Verification** | independent evidence; gates pass; human sign-off | every **required gate** passes; a human approves |
| **L5 Operation** | release record, observation, feedback capture | stable; feedback/incidents captured |
| **L6 Evolution** | retrospect; promote what was proven; seed next cycle | provenance complete; learning promoted → loops to L1 |

The lifecycle is an **audit/evidence spine**: it guarantees that accountable work has an
inception, a specification, an execution, an independent verification, an operation record,
and an evolution step — each leaving evidence. (The Canon identity and the project knowledge
in force are **declared at the start of the work and recorded in the trace** — see
[`CONFORMANCE.md`](CONFORMANCE.md); *how* a tool links them at runtime is the Tool's.)

---

## 6. The gates — the evidence categories every step must clear

Gates are the **cross-cutting checks** that keep the standard's rigor. Canon names them and
states what each must guarantee; the Tool implements the check. A project's supplied
knowledge may make a gate **stricter, never weaker.**

| Gate | Guarantees | Base? |
|---|---|---|
| **quality** | evidence (test/eval/review/measurement) backs every "done"; ready/done criteria met; independent review | base |
| **risk-safety** | hard no-go rules enforced; risks registered; incidents handled | base |
| **cost** | budget/burn within threshold; cost-vs-quality trade explicit | base |
| **traceability** | goal ↔ spec ↔ artifact ↔ test ↔ memory are linked, with provenance | base |
| **collaboration** | shared state current; rationale exposed; disagreement disposed; errors repaired | base |
| **uplift** | (learning adopters) the team converges to one common standard; each person's capability growth is **measured** over time | opt-in |
| **operator-readiness** | (regulated adopters) verifies the operator holds the **authority/credentials** a decision requires, and routes an out-of-fit decision to a cleared operator; transparent and contestable — a **prerequisite check, never a worker score** | opt-in |

The five **base** gates are the floor for any adopter. The two opt-in gates carry legal /
HR / privacy weight and are **not** forced on every adopter — they belong to optional
conformance profiles ([`CONFORMANCE.md`](CONFORMANCE.md)).

---

## 7. Specialization — projects do not fork Canon

A project does not copy and diverge Canon. It **specializes** it: attaching project
knowledge and stricter rules to produce a process **optimized for that project**, while the
standard underneath stays intact. Canon defines the **right to specialize and the
invariants that survive it**; the Tool implements the specialization mechanism.

**Invariants no specialization may break:**

- **Monotonic / stricter-only** — a specialization may *add* requirements or *strengthen* a
  gate; it may never weaken, remove, or relax a base obligation.
- **Authority order preserved** — the standard's authority ranking (gates above procedure;
  human approval where authority, risk, cost, policy, or irreversibility is involved) holds.
- **Provenance preserved** — every added rule, artifact, and promoted change carries source,
  author, and time.
- **Conformance preserved** — the specialized process still emits a conformant trace
  ([`CONFORMANCE.md`](CONFORMANCE.md)).

This is how "the AI evolves Canon into a project-optimized process" ([`#3`](#3-the-collaboration-model--ai-leads-or-the-human-leads-and-canon-evolves)) stays
safe: evolution is **add-only against the floor**, so a project can climb above the standard
but never sink below it.

---

## 8. Scope & limits

What Canon does **not** claim:

- Not all expertise is capturable. Tacit judgment, taste, and accountability stay partly
  human. Canon externalizes the **explicit, repeatable method**, not the whole expert.
- A guided non-expert gets **lift and a common floor**, not a master's ceiling.
- AI does not "think like an expert"; it **executes an expert-grade method and applies the
  supplied criteria**, verified by the gates.
- Knowledge is **not** assumed public — private/regulated facts are supplied per project,
  never assumed by the standard.

**Falsifiability (how to prove Canon wrong).** Declare: the *task class*; participant *skill
bands* (all role-cleared); a *guided-vs-unaided baseline*; the *quality metric* (acceptance
pass rate, defect rate, reviewer acceptance); and a *failure threshold*. Canon's central
claim fails if cleared low-skill participants' guided output does **not** reach the same
standard band as experts' on that metric. The claim is **measured, not asserted.**

---

## 9. The Canon ↔ Tool boundary

> **Canon owns** what must be true and how conformance is judged: the purpose, the
> collaboration model, the lifecycle obligations, the gate guarantees, the specialization
> invariants, and the conformance interface. **The Tool (and the agent) owns** everything
> executable: the runnable procedures for each stage, the gate checkers, the runtime and
> memory state, the plug-in resolver, tool/command choices, planning, and recovery.

Test: if two different tools both produce the same required evidence, pass the same gates,
and emit the same conformant trace, **how** they did it is the Tool's business. If a choice
would change pass/fail, authority, auditability, or safety, it belongs **in Canon**.

This boundary is also why frontier vendors can adopt Canon without surrendering their
product: Canon standardizes only the portable **audit/evidence interface**, never the
agent's internal workflow ([`#10`](#10-ecosystem--neutrality), [`CONFORMANCE.md`](CONFORMANCE.md)).

---

## 10. Ecosystem & neutrality

Canon is meant to be a **common standard advanced by many** — different companies and
services (model vendors, agent builders, enterprises) adopting the same method for human–AI
work and improving it together.

Two commitments make shared advancement possible:

- **Differentiation-preserving neutrality.** Canon standardizes only the minimal portable
  **audit/evidence interface** — the artifacts, gate outcomes, approvals, and provenance an
  enterprise needs to trust and port work across vendors. It does **not** standardize how an
  agent plans, remembers, uses tools, or recovers. Those stay each vendor's moat, so a
  vendor can conform by **emitting a conformant trace** without **exposing or standardizing
  its internal workflow** (though a truthful trace may require adding approval/provenance
  logging).
- **Domain- and vendor-neutral core.** The standard encodes no single domain's facts and no
  single vendor's commands.

> The operational machinery of a neutral ecosystem — a governing body, certification
> services, legal charter — is **deliberately out of this document.** Canon's job is to
> define the *method*; how the ecosystem is run and governed is handled separately (project
> site / future operational work). What Canon fixes here is only the **intent**: a neutral,
> portable, multi-vendor standard.

---

## See Also

- [`CONFORMANCE.md`](CONFORMANCE.md) — what makes a tool/process **Canon-conformant**: the portable Canon-trace interface, profiles, and certification levels. *(This is what keeps Canon a standard, not a slogan.)*
- [`GLOSSARY.md`](GLOSSARY.md) — core vocabulary.
- [`_INDEX.md`](_INDEX.md) — loading order.

> The runnable mechanism that *executes* Canon (procedures, checkers, runtime state, plug-in
> resolution) is **not** part of this standard. It is built as a separate **Tool** in its own
> repository ([`#9`](#9-the-canon--tool-boundary)).
