---
title: Conformance — what makes a tool or process Canon-conformant
project: The AI Theorem
doc: CONFORMANCE
version: 0.0.3
last-reviewed: 2026-06-26
status: draft
audience: vendors · adopters · auditors · AI agents
---

# Conformance — the portable interface

> This is what keeps Canon a **standard**, not a slogan. [`CANON.md`](CANON.md) defines the
> method; this document defines the **machine-checkable interface** a tool or process must
> satisfy to claim it follows Canon. Conformance attests **process compliance** — *how* work
> is governed — and **never warrants the outcome**. Liability for results is governed by
> separate contracts and applicable law, not by conformance.

---

## 1. What is conformant — and what is not

- **Conformant:** the work ran the lifecycle, cleared the required gates, produced the
  required artifacts and evidence, kept human approval where required, and preserved
  provenance — and can prove it by emitting a **Canon trace** (§2).
- **Not certified:** the correctness or fitness of any particular result. Conformance says
  the work was **governed to the standard**, never that a given output is right.

A vendor conforms by **emitting the trace**, without **exposing or standardizing its internal
workflow**. Canon never inspects or constrains *how* an agent planned, used tools, or
recovered — only that the trace is **true, typed, and complete** ([`CANON.md` §9](CANON.md#9-the-canon--tool-boundary)).
(Emitting a truthful trace may require a vendor to add approval/provenance **logging** — that
is capturing evidence, not standardizing the workflow.)

---

## 2. The Canon trace — the one thing that is standardized

The portable audit/evidence record for a **change unit**. It is a **state dossier**, not a
one-shot document: it grows as the work advances through the lifecycle, and each field's
requirement is **gated by the furthest stage reached** (`stage_reached`). A dossier at L2 is
conformant with no `artifacts` yet; the same dossier at L4 is non-conformant without
`evidence`. The shape is **strict, typed, and machine-checkable** — an adapter cannot be
built against an undefined interface, so it is **normative**. (A formal JSON Schema and a
reference test suite are deliverables of the Tool effort, not of this document.)

```yaml
trace_version:   string            # Canon trace schema version (semver) — always required
project_id:      string            # always required
canon_hash:      string            # the Canon standard version in force, declared at start — always required
profiles:        [string]          # active conformance profiles, e.g. [core_audit] — always required
stage_reached:   L1|L2|L3|L4|L5|L6 # furthest lifecycle stage reached — always required; gates the rest

charter_ref:     {id, goal, kpi}   # goal/scope/KPI (L1)            — required once stage_reached ≥ L1
requirements:    [{id, statement, acceptance_criterion_id}]                  # (L2) — required ≥1 once ≥ L2
artifacts:       [{id, requirement_ids[], digest}]                          # (L3) — required ≥1 once ≥ L3
collaboration:   {shared_state_ref, rationale_refs[], steering_events[], teaching_ref}  # (§4 AI obligations) — required once ≥ L3
evidence:        [{acceptance_criterion_id, class: test|eval|review|measurement, ref}]  # (L4) — required, one per acceptance_criterion_id, once ≥ L4
gate_outcomes:   [{gate, result: pass|fail, evidence_ref}]                  # one per active-profile gate — required once ≥ L4
approvals:       [{category: authority|risk|cost|policy|irreversible, approver, review_event_ref, timestamp}]  # ≥1 once ≥ L4 and for every material/risk/cost/irreversible change
operation:       {release_ref, observation_ref, incident_refs[]}            # (L5) — required once ≥ L5
evolution:       {retro_ref, promoted[]: [{change, provenance_ref}], next_seed}  # (L6) — required once ≥ L6
provenance:      [{subject_id, source, author, timestamp}]                  # required for every claim, artifact, and promoted change
```

### 2a. Minimum validation rules (normative; the Tool's schema refines them)

A trace is **invalid** — and the claim of conformance fails — unless:

- **Stage-gating** — every field required at `stage_reached` is present and non-empty.
- **Referential integrity** — every `evidence.acceptance_criterion_id` resolves to a
  `requirements[].acceptance_criterion_id`; every `artifacts[].requirement_ids` resolves to a
  `requirements[].id`; every `*_ref` resolves.
- **Gate coverage** — `gate_outcomes` contains exactly one entry per gate in the active
  profiles' union, and none is `fail` at exit.
- **Approval cardinality & steering** — a material / risk / cost / irreversible change has
  ≥1 `approvals` entry whose `review_event_ref` points to a real steering or review event
  (this is what makes "no passive approval-clicking" — [`CANON.md` §3](CANON.md#3-the-collaboration-model--ai-leads-or-the-human-leads-and-canon-evolves) — *checkable*, not a slogan).
- **Evidence class** — `class` ∈ {test, eval, review, measurement}. `assertion` is **not**
  valid; an unbacked claim is not evidence.
- **Obligation coverage** — every normative "must" in [`CANON.md`](CANON.md) that Core Audit
  claims (the §4 AI obligations, the base gates, required human approval, full L1–L6 evidence)
  resolves to a field here. If a Canon "must" is not traceable, it is either added here or it
  is not normative.

---

## 3. Conformance targets

| Target | Conformant when it… |
|---|---|
| **Runner** | declares the Canon identity in force, carries work through the lifecycle (L1–L6), enforces the active gate set, and exposes the shared read surface. |
| **Agent (adapter)** | emits a complete, true Canon trace within the [Canon↔Tool boundary](CANON.md#9-the-canon--tool-boundary), and honors the human-approval categories. Its internal workflow is **out of scope**. |
| **Specialization (project profile)** | adds knowledge and stricter rules only; preserves the [specialization invariants](CANON.md#7-specialization--projects-do-not-fork-canon); still emits a conformant trace. |

---

## 4. Profiles — a lean base, optional layers

**Core Audit is a complete, checkable projection of Canon's normative obligations** — not a
subset. It requires the full trace (all stages reached, §2/§2a), the five base gates, the
required human approvals, and the §4 AI obligations (lead, expose rationale, **provide
tooling**, **teach while doing**, typed asks, repair) insofar as each leaves a trace field.
Teaching-while-doing is a **base** collaboration behavior (captured by the `collaboration`
gate and `collaboration.teaching_ref`); what the opt-in layer adds is *measuring a person's
growth over time*, which carries privacy weight and is not forced on every adopter.

| Profile | Adds | For |
|---|---|---|
| **Core Audit** *(base)* | the full Canon trace; the five base gates — `quality` · `risk-safety` · `cost` · `traceability` · `collaboration` (incl. teaching-as-offered); required approvals; full L1–L6 evidence | any adopter wanting portable, auditable AI work |
| **Regulated Enterprise** *(opt-in)* | Core + data-boundary, audit-log, approval policy, and the **operator-readiness** check (with its legal/HR/privacy guardrails) | regulated buyers who need the prerequisite-fit layer |
| **Learning / Uplift** *(opt-in)* | Core + the **uplift** gate — *measuring/tracking* capability growth (teach-back, capability delta) over time | teams that commit to growing people |

**Profiles compose.** The opt-in layers stack on Core Audit independently; the **active gate
set is the union** of the enabled profiles' gates. Valid combinations: Core alone · Core +
Regulated · Core + Learning/Uplift · all three.

> Why split: forcing the **measurement** of a person — `operator-readiness` (verifying fit,
> generating manager packets) or `uplift` (tracking growth) — onto every adopter is a
> legal/labor/privacy liability and an adoption barrier. Teaching and tooling are base
> *behaviors*; **measuring the human** is the optional layer.

---

## 5. Certification levels

| Level | Meaning |
|---|---|
| **L1 Self-attested** | the author declares conformance against the test suite |
| **L2 Suite-verified** | the implementation passes the published conformance test suite |
| **L3 Independently audited** | a neutral party verifies process compliance + provenance |

The **"Canon-conformant"** claim means *process compliance at a stated level* — never a
guarantee of outcomes. The test suite (reference tasks, required artifacts, pass/fail checks)
and any governed mark are operational matters handled outside this document
([`CANON.md` §10](CANON.md#10-ecosystem--neutrality)).

---

## 6. Why the trace also feeds compliance reporting

The trace is designed to be a reusable **evidence layer** under the AI-governance frameworks
enterprises already face — so adopting Canon can **supply reusable evidence for** compliance
reporting rather than adding a parallel effort.

| Trace element | Maps to (target alignment, not a certified crosswalk) |
|---|---|
| `charter_ref`, `requirements` | intended purpose / risk scoping — **EU AI Act** Art. 9–11; **ISO/IEC 42001** objectives |
| `gate_outcomes` (risk-safety, quality) | risk-management + quality records — **NIST AI RMF** MAP/MEASURE; **42001** controls |
| `evidence`, `provenance` | test/eval records + traceability — **EU AI Act** technical documentation / logging |
| `approvals` | human-oversight sign-off — **EU AI Act** Art. 14 |

> Field-for-field alignment to specific framework templates is future work; this is the
> **target mapping**. Whether buyer demand for this materializes must be demonstrated by
> pilots, not assumed.

---

## See Also

- [`CANON.md`](CANON.md) — the standard method this interface certifies.
- [`GLOSSARY.md`](GLOSSARY.md) — terms (Canon trace, evidence class, profile, provenance).
