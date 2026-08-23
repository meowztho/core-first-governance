---
name: core-first-orchestration
description: Govern the user-facing primary agent's use of Core-First architecture reasoning, grounded execution preflight, delegated-agent routing, context isolation, observable product verification, architecture verification, independent review, and existing external completion authorities. Use for non-trivial software work where ownership, reuse, source consumption, prerequisites/toolchain assumptions, delegation, context loss, user-observable runtime behavior, or review strategy may be material. The primary agent remains the orchestrator and final integrator; this skill is its decision procedure, not a separate orchestrator agent.
metadata:
  short-description: Route Core-First work and verification safely
---

# Core-First Orchestration

## Purpose

This Skill governs **how the user-facing primary agent works**. It does not create another architecture owner, product-verification owner, or orchestration agent.

Terminology is intentionally provider-neutral:
- **primary agent** = the user-facing root/main/parent agent that owns final integration and response;
- **delegated agent** = any child/subagent/specialist/session/model invoked for a bounded lane;
- **worker** = delegated agent with bounded implementation authority;
- **advisor** = delegated agent that may investigate or recommend architecture;
- **investigator** = delegated agent used for bounded evidence gathering;
- **verifier/reviewer** = delegated or external agent used for read-only verification or review.

A host may call these subagents, child agents, workers, sessions, tools, or something else. Map host-specific primitives onto these roles; do not make the governance model depend on a provider's naming or API.

The primary agent that receives the user's requirement remains responsible for:
- understanding the requirement;
- ensuring material plans are grounded in actually inspected/consumed sources and verified prerequisites before expensive execution;
- applying Core-First itself when architecture is material;
- deciding whether and how to delegate;
- controlling what context and skill knowledge each delegated agent receives;
- integrating delegated work;
- deciding which verification layers are required;
- ensuring user/external runtime claims receive appropriate observable verification;
- resolving findings and returning the final result to the user.

Do not duplicate the rules of `core-first-extension-architecture`, `observable-product-verification`, or `independent-review` here. Load those canonical Skills when their responsibilities are needed.

## Canonical sibling skills

This bundle provides:
- `core-first-extension-architecture` — canonical architecture/reuse/ownership decision method;
- `observable-product-verification` — canonical procedure for proving user/external observable runtime outcomes without confusing actions, builds, or static evidence with product success;
- `core-first-verifier` — read-only fresh verification of Core-First conformance;
- `independent-review` — unbiased review for consequential, high-risk, difficult-to-verify, or materially blocked work.

When a delegated agent requires a Skill, use the host's strongest reliable mechanism to make that Skill available **fresh**. Prefer, in order:
1. host-native explicit Skill attachment/injection;
2. a resolved installed `SKILL.md` path with an instruction to read it fresh;
3. another verifiable mechanism that supplies the canonical Skill content without relying on inherited conversation memory.

Do not assume delegated agents inherit the primary agent's loaded Skill state. Do not make correctness depend on simultaneous multi-Skill activation when the host cannot guarantee it; sequence the procedures and pass raw evidence/findings between them instead.

## Primary-agent invariant

Delegation never discharges the primary agent's own Core-First responsibility or its responsibility to verify material completion claims.

For architecture-relevant work, the primary agent MUST itself:
1. identify the repository/project root and applicable instructions;
2. inspect relevant repository/Git state and diffs when available;
3. load the canonical `core-first-extension-architecture` Skill fresh when required by the freshness rules below;
4. identify the relevant project authorities;
5. identify the canonical responsibility owner and relevant runtime/data path;
6. apply the canonical Core-First classification/reuse decision method;
7. define the allowed ownership and change boundary before implementing or delegating;
8. independently evaluate delegated results before integration.

For a material user/external runtime claim, the primary agent MUST also ensure that the appropriate observable verification actually occurred before reporting the claim as verified.

A Core-First-aware advisor, product-verification worker, or verifier is evidence/advice, not a substitute for these duties.

## Freshness and context invalidation

Treat remembered Skill content as cache, not authority.

Before another architecture-relevant decision, reload the canonical Core-First Skill when any of these apply:
- fresh session/context;
- major context loss or compaction;
- repository/project switch;
- relevant Skill revision;
- relevant architecture-authority revision;
- major domain/workstream switch;
- uncertainty whether the Skill was actually loaded in the current valid context.

Also reload the required project authorities affected by the invalidation. Do not treat a summary, prior agent narrative, or old verification result as a normative reread.

For observable product verification, use current executable-surface evidence. Do not treat an old screenshot, stale runtime capture, or pre-change manual run as proof of the current revision unless the project explicitly establishes that evidence as still valid.

## Step 1 — Determine whether Core-First is material

Core-First is material when the task can affect, require, or discover any of the following:
- responsibility ownership or authoritative state;
- reuse versus duplication;
- capability/module/provider boundaries;
- consumer composition;
- producer convergence;
- extension points, plugins, adapters, or providers;
- cross-boundary contracts;
- architecture repair/refactor;
- a reusable feature whose correct owner/path is not already settled.

For a truly trivial isolated edit with no material ownership/reuse/system-boundary question, do not force architecture machinery. Use the smallest relevant verification.


## Step 2 — Grounded execution preflight

Before committing to a material implementation plan, determine whether a grounded preflight is required. Use it when one or more of these conditions materially apply:
- multiple supplied/repository sources determine the solution;
- unfamiliar, proprietary, binary, legacy, generated, or otherwise opaque formats are involved;
- migration, import/export, porting, decompilation, reverse engineering, or format conversion is involved;
- web/external research materially determines the implementation choice;
- tool, dependency, runtime, parser, SDK, compiler, converter, license, credential, permission, or environment compatibility is an assumption;
- a wrong prerequisite assumption could cause substantial rework, wasted execution, or context/token churn;
- the task is expensive/long enough that cheap uncertainty reduction is materially valuable.

For material sources and prerequisites, distinguish these states:

```text
DISCOVERED  = source/tool/input is known to exist
INSPECTED   = relevant content/format/capability was actually examined
EXTRACTED   = task-relevant facts/constraints were identified
MAPPED      = those facts were connected to the requirement/plan
CONSUMED    = the plan/decision demonstrably uses them
```

`DISCOVERED` is never equivalent to `CONSUMED`. Listing files, search results, tools, libraries, or documentation does not satisfy the preflight. A material source must be inspected deeply enough for the active decision, and its relevant facts must affect the plan before execution proceeds.

For toolchain-dependent work, verify the exact compatibility chain rather than relying on category/name similarity:

```text
actual input/format/state
→ required operation
→ required capability
→ candidate tool/dependency
→ exact-case support verified?
→ required access/license/credential/environment available?
→ executable path proven enough to proceed
```

Challenge the small number of assumptions that could invalidate the whole plan. If a material assumption can be resolved cheaply from available files, repository state, documentation, tool help/version output, or focused research, resolve it before implementation instead of coding around the uncertainty.

Use the user as an early boundary only when the blocker is genuinely user-owned or externally unavailable, such as a product decision, credential/access grant, licensed/external program, unavailable hardware/data, destructive authorization, or material cost. Do not ask the user to resolve discoverable technical facts, but do surface a real blocker before constructing a speculative substitute.

For trivial/local work whose inputs and execution path are already well understood, do not force this preflight ceremonially.

## Step 3 — Decide whether observable product verification is material

Use `observable-product-verification` when the requirement, bug fix, acceptance criterion, regression claim, or completion claim materially depends on behavior observable at a real user or external system boundary.

Typical triggers include:
- interactive UI, web, desktop, mobile, game, or device behavior;
- navigation, controls, animation, input, visual state, persistence, or workflow completion;
- CLI behavior as experienced by a caller;
- API/service behavior whose contract includes externally observable state or side effects;
- library/integration behavior that must work through a realistic consumer path;
- automation/batch behavior whose result is defined by real output or side effects;
- any bug whose symptom exists only or primarily at runtime.

Do not invoke it ceremonially for a pure internal refactor, formatting change, isolated static asset edit, or other change whose acceptance is fully and reliably proven by narrower evidence.

The `observable-product-verification` Skill owns the detailed evidence procedure and status semantics. Do not restate or approximate that method here.

## Step 4 — Decide whether to delegate

Do not delegate merely because the host supports delegated agents. Prefer the primary agent when the work is small, tightly coupled, or cheaper to verify directly.

Delegate when a bounded lane can materially improve parallelism, specialist depth, context isolation, or independent evidence.

For every delegated task, choose its **role**, **skill knowledge**, **project context**, **authority**, and **lifecycle** explicitly.

### Context envelope

Use this conceptual envelope for every delegated agent:

```text
ROLE
SKILL KNOWLEDGE
PROJECT/TASK CONTEXT
EXCLUDED CONTEXT
WRITE/DECISION AUTHORITY
FRESHNESS / PERSISTENCE
EXPECTED OUTPUT / EVIDENCE
```

Give minimum sufficient context, not maximum available context.

## Step 5 — Choose the delegated-agent mode

### A. Targeted worker — no Core-First Skill by default

Use when architecture and ownership boundaries are already canonical and the delegated agent only implements or investigates a bounded leaf.

Give:
- exact requirement slice;
- canonical owner/capability/contract boundary already decided by the primary agent;
- relevant files/interfaces/data flow;
- grounded facts/prerequisites already established by Step 2 when material;
- explicit allowed write scope;
- forbidden ownership/bypass decisions;
- relevant acceptance criteria and verification commands.

Do NOT give the full Core-First Skill merely "just in case".

The worker MUST escalate with `ARCHITECTURE_DECISION_REQUIRED` instead of silently inventing architecture when it encounters an unresolved question about ownership, reuse, capability boundaries, extension seams, or foreign authoritative state.

A targeted worker may use `observable-product-verification` when its bounded lane includes runtime/product verification and the host can provide that procedure without changing the worker's write authority.

### B. Core-First advisor/worker — Core-First Skill required

Use when the delegated lane itself must investigate or decide architecture-relevant questions.

Give:
- original requirement or faithful scoped requirement;
- applicable project instructions;
- relevant canonical authorities and raw project evidence;
- the canonical `core-first-extension-architecture` Skill through a fresh host-native attachment/read mechanism;
- the specific architecture question or implementation scope.

Avoid priming the delegated agent with the primary agent's preferred conclusion when an independent architecture analysis is desired.

A persistent Core-First advisor may be reused for long-running work, but persistence never makes it suitable as the final independent Core-First verifier.

### C. Investigator — no architecture Skill unless needed

Use for bounded evidence gathering: call graph, failing test localization, API behavior, file discovery, benchmark/profiling evidence, product-surface observation, or similar investigation.

Give only the evidence question and necessary project context. If the investigator reaches an architecture decision boundary, it returns the evidence and escalates rather than deciding outside its authority.

## Step 6 — Integrate delegated results

The primary agent MUST inspect the returned evidence/result and reconcile it with:
- the original requirement;
- applicable project instructions;
- canonical project authorities;
- Core-First reasoning when material;
- actual repository state/diff;
- relevant tests;
- relevant observable product behavior when material.

Do not accept a delegated agent's conclusion merely because it used a Skill.

## Step 7 — Observable product verification gate

When Step 3 says observable verification is material, apply `observable-product-verification` using the strongest appropriate interaction/observation capability actually available in the current environment. The sibling Skill owns the exercise method, evidence semantics, ambient observation, bounded adjacent exploration, and `VERIFIED | FAILED | INCONCLUSIVE` status.

The governance layer does not prescribe a particular interaction technology or provider. Tooling is a host/runtime capability, not project truth and not the verification method itself.

If observable verification returns a material defect requiring correction:
1. preserve its raw observable evidence and finding classification;
2. return control to the primary agent;
3. use the project's existing authorities/routing and the canonical Core-First method when ownership/reuse/architecture is material;
4. correct within the allowed boundary;
5. invoke `observable-product-verification` again for the affected claim.

If observable verification is `INCONCLUSIVE`, do not report the affected user/external outcome as verified.

## Step 8 — Core-First verification gate

Use `core-first-verifier` when a meaningful change materially affects or depends on architecture/reuse/ownership boundaries, including material changes to:
- canonical ownership or authoritative state paths;
- reusable capability/module/provider boundaries;
- consumer composition;
- producer convergence;
- extension seams or external extension behavior;
- provider/adapter contracts;
- core rules or architecture migrations.

Also use a fresh Core-First verifier at important milestones or final completion of long-running architecture work.

The verifier MUST:
- run in a fresh verification context separate from the implementation/advisor context;
- load `core-first-verifier` and the canonical Core-First Skill fresh;
- be read-only;
- perform its two-phase anti-rationalization protocol: first freeze the expected owner/path/classification from the requirement, authorities, and baseline project state **before** seeing the change-under-review diff/patch when the host can enforce that ordering; only then inspect the implementation evidence and compare it to the frozen expectation;
- receive raw diff/files and actual verification evidence only for the comparison phase;
- NOT receive the implementation agent's rationale, confidence, conclusions, or prior verifier conclusions unless needed only after an independent finding has already been produced.

A persistent Core-First advisor MUST NOT serve as the final Core-First verifier of its own work.

If the host cannot create a fresh delegated context, use the strongest available isolation mechanism and state the limitation; do not falsely claim independent freshness.

## Step 9 — Independent review gate

Use `independent-review` according to its own trigger: consequential, high-risk, difficult-to-verify, or materially blocked implementation work. It supplements but never replaces primary verification, observable product verification when required, or Core-First verification.

For independence:
- use a fresh reviewer/context/model when feasible;
- do not preload `core-first-extension-architecture` merely because the implementation used it;
- do not pass the primary agent's implementation narrative, conclusions, confidence, or justification;
- do not pass Core-First-verifier conclusions before the independent reviewer derives its own findings;
- when observable-product verification ran, do not pass its interpreted status, conclusion, confidence, or finding narrative before independent derivation;
- do pass the original requirements, complete applicable project instructions, relevant raw diffs/files, actual verification-command/output evidence, and relevant raw observable/runtime evidence as required by `independent-review`.

If the project's own applicable instructions explicitly require Core-First, do not hide that project requirement from the independent reviewer. Context isolation removes prior reasoning/priming; it does not falsify project truth.

## Step 10 — Reconcile findings

The primary agent owns final reconciliation.

For each material verifier/reviewer/product-verification finding:
- fix it when it is in scope and required;
- reject it with direct evidence;
- record/report it without expanding write scope when it is a valid adjacent/unrelated observation;
- or explicitly accept the risk when the user/authority permits that choice.

If verification layers disagree, investigate the conflicting evidence. Do not resolve disagreement by majority vote.

## Step 11 — Respect existing external completion authority

Before self-certifying completion, determine whether the project/repository defines a separate acceptance/completion authority or validator (for example a project acceptance store/validator, CI/release gate, regulated approval process, or another explicit completion owner).

If such an authority exists:
- follow its project-defined acceptance contract and required evidence;
- route the relevant raw verification evidence into that authority using the project's existing mechanism when required;
- do not treat Governance status, a verifier PASS, or an independent-review result as a replacement for that authority's decision;
- if the authority is unavailable or cannot be satisfied, report the completion state accordingly instead of silently self-certifying.

If no separate completion authority exists, do not invent one and do not hardwire Governance to any specific external compiler/validator product. Governance remains a procedural layer, not a universal completion platform.

## Routing summary

```text
User
  → Primary Agent (user-facing orchestrator + final integrator)
      → Grounded execution preflight when source/prerequisite uncertainty is material
      → Core-First itself when architecture is material
      → Targeted worker: bounded implementation, no Core-First Skill by default
      → Core-First advisor/worker: architecture reasoning, Core-First Skill fresh
      → Investigator: bounded evidence, no extra Skill unless needed
      → Observable product verification when runtime/user outcome is material
      → Fresh Core-First verifier: architecture conformance
      → Fresh independent reviewer: consequential/high-risk unbiased review
      → Existing external completion authority when project-defined
```

## Host capability degradation

The governance model is semantic, not tied to one agent runtime. If a host lacks a capability:
- no delegated agents → primary agent performs the lane itself and uses another fresh context/model only when available and justified;
- no persistent delegated context → use fresh bounded tasks instead;
- no explicit Skill injection → resolve/read the canonical Skill through the host's available file/context mechanism;
- no read-only enforcement → instruct read-only behavior and verify no writes occurred; do not claim enforced isolation;
- no independent model/context → perform best-effort review and report the independence limitation;
- no suitable executable/product-surface interaction capability → mark the affected observable claim unverified/inconclusive instead of pretending static evidence proves it.

Do not emulate missing host machinery by inventing a complex orchestration, QA, or computer-control framework unless the product actually requires one.

## Anti-patterns

Do not:
- create a separate "orchestrator agent" that becomes a parallel owner to the primary agent;
- outsource the primary agent's own Core-First duty;
- treat discovered/listed sources or tools as if their relevant knowledge/capability had been consumed;
- implement around a material prerequisite assumption that available evidence could cheaply resolve;
- give every worker every Skill and the entire project history;
- assume delegated agents inherit Skill state;
- use a persistent architecture advisor as its own final verifier;
- feed implementation narratives into independent review;
- run expensive multi-layer review for trivial edits;
- duplicate canonical Core-First, Observable Product Verification, or Independent Review rules inside this Skill;
- encode provider-specific agent names, APIs, browser tools, computer-use tools, or protocols as universal governance rules;
- bypass or replace a project-defined external completion authority with Governance self-certification.

## Completion condition

Before claiming completion, the primary agent must be able to state from actual evidence:
- when grounded preflight was material, which critical sources/prerequisites were inspected and how their extracted facts were consumed by the plan;
- which canonical owner/path the change used when architecture was material;
- what was delegated and with which knowledge/authority boundary;
- what automated/static verification actually ran;
- whether observable product verification was required, what real boundary was exercised, and its status;
- whether Core-First verification was required and its status;
- whether Independent Review was required and how its material findings were resolved;
- whether a separate project-defined completion authority existed and, if so, its actual acceptance result;
- any host limitation that materially weakened runtime evidence, freshness, isolation, or enforcement.
