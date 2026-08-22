---
name: core-first-orchestration
description: Govern the user-facing primary agent's use of Core-First architecture reasoning, delegated-agent routing, context isolation, verification, and independent review. Use for non-trivial software work where ownership, reuse, composition, extension boundaries, delegation, context loss, or review strategy may be material. The primary agent remains the orchestrator and final integrator; this skill is its decision procedure, not a separate orchestrator agent.
metadata:
  short-description: Route Core-First work and reviews safely
---

# Core-First Orchestration

## Purpose

This Skill governs **how the user-facing primary agent works**. It does not create another architecture owner or another orchestration agent.

Terminology is intentionally provider-neutral:
- **primary agent** = the user-facing root/main/parent agent that owns final integration and response;
- **delegated agent** = any child/subagent/specialist/session/model invoked for a bounded lane;
- **worker** = delegated agent with bounded implementation authority;
- **advisor** = delegated agent that may investigate or recommend architecture;
- **verifier/reviewer** = delegated or external agent used for read-only verification.

A host may call these subagents, child agents, workers, sessions, tools, or something else. Map host-specific primitives onto these roles; do not make the governance model depend on a provider's naming or API.

The primary agent that receives the user's requirement remains responsible for:
- understanding the requirement;
- applying Core-First itself when architecture is material;
- deciding whether and how to delegate;
- controlling what context and skill knowledge each delegated agent receives;
- integrating delegated work;
- deciding which verification layers are required;
- resolving findings and returning the final result to the user.

Do not duplicate the rules of `core-first-extension-architecture` or `independent-review` here. Load those canonical Skills when their responsibilities are needed.

## Canonical sibling skills

This bundle provides:
- `core-first-extension-architecture` — canonical architecture/reuse/ownership decision method;
- `core-first-verifier` — read-only fresh verification of Core-First conformance;
- `independent-review` — unbiased review for consequential, high-risk, difficult-to-verify, or materially blocked work.

When a delegated agent requires a Skill, use the host's strongest reliable mechanism to make that Skill available **fresh**. Prefer, in order:
1. host-native explicit Skill attachment/injection;
2. a resolved installed `SKILL.md` path with an instruction to read it fresh;
3. another verifiable mechanism that supplies the canonical Skill content without relying on inherited conversation memory.

Do not assume delegated agents inherit the primary agent's loaded Skill state.

## Primary-agent invariant

Delegation never discharges the primary agent's own Core-First responsibility.

For architecture-relevant work, the primary agent MUST itself:
1. identify the repository/project root and applicable instructions;
2. inspect relevant repository/Git state and diffs when available;
3. load the canonical `core-first-extension-architecture` Skill fresh when required by the freshness rules below;
4. identify the relevant project authorities;
5. identify the canonical responsibility owner and relevant runtime/data path;
6. apply the canonical Core-First classification/reuse decision method;
7. define the allowed ownership and change boundary before implementing or delegating;
8. independently evaluate delegated results before integration.

A Core-First-aware advisor or verifier is evidence/advice, not a substitute for this duty.

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

## Step 2 — Decide whether to delegate

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

## Step 3 — Choose the delegated-agent mode

### A. Targeted worker — no Core-First Skill by default

Use when architecture and ownership boundaries are already canonical and the delegated agent only implements or investigates a bounded leaf.

Give:
- exact requirement slice;
- canonical owner/capability/contract boundary already decided by the primary agent;
- relevant files/interfaces/data flow;
- explicit allowed write scope;
- forbidden ownership/bypass decisions;
- relevant acceptance criteria and verification commands.

Do NOT give the full Core-First Skill merely "just in case".

The worker MUST escalate with `ARCHITECTURE_DECISION_REQUIRED` instead of silently inventing architecture when it encounters an unresolved question about ownership, reuse, capability boundaries, extension seams, or foreign authoritative state.

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

Use for bounded evidence gathering: call graph, failing test localization, API behavior, file discovery, benchmark/profiling evidence, or similar investigation.

Give only the evidence question and necessary project context. If the investigator reaches an architecture decision boundary, it returns the evidence and escalates rather than deciding outside its authority.

## Step 4 — Integrate delegated results

The primary agent MUST inspect the returned evidence/result and reconcile it with:
- the original requirement;
- applicable project instructions;
- canonical project authorities;
- Core-First reasoning when material;
- actual repository state/diff;
- relevant tests or user-visible behavior.

Do not accept a delegated agent's conclusion merely because it used the Core-First Skill.

## Step 5 — Core-First verification gate

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
- receive original requirements, applicable instructions, relevant authorities, raw diff/files, and actual verification evidence;
- NOT receive the implementation agent's rationale, confidence, conclusions, or prior verifier conclusions unless needed only after an independent finding has already been produced.

A persistent Core-First advisor MUST NOT serve as the final Core-First verifier of its own work.

If the host cannot create a fresh delegated context, use the strongest available isolation mechanism and state the limitation; do not falsely claim independent freshness.

## Step 6 — Independent review gate

Use `independent-review` according to its own trigger: consequential, high-risk, difficult-to-verify, or materially blocked implementation work. It supplements but never replaces primary verification or Core-First verification.

For independence:
- use a fresh reviewer/context/model when feasible;
- do not preload `core-first-extension-architecture` merely because the implementation used it;
- do not pass the primary agent's implementation narrative, conclusions, confidence, or justification;
- do not pass Core-First-verifier conclusions before the independent reviewer derives its own findings;
- do pass the original requirements, complete applicable project instructions, relevant raw diffs/files, and actual verification-command output as required by `independent-review`.

If the project's own applicable instructions explicitly require Core-First, do not hide that project requirement from the independent reviewer. Context isolation removes prior reasoning/priming; it does not falsify project truth.

## Step 7 — Reconcile findings

The primary agent owns final reconciliation.

For each material verifier/reviewer finding:
- fix it; or
- reject it with direct evidence; or
- explicitly accept the risk when the user/authority permits that choice.

If Core-First verification and independent review disagree, investigate the conflicting evidence. Do not resolve disagreement by majority vote.

## Routing summary

```text
User
  → Primary Agent (user-facing orchestrator + final integrator)
      → Core-First itself when architecture is material
      → Targeted worker: bounded implementation, no Core-First Skill by default
      → Core-First advisor/worker: architecture reasoning, Core-First Skill fresh
      → Investigator: bounded evidence, no extra Skill unless needed
      → Fresh Core-First verifier: architecture conformance
      → Fresh independent reviewer: consequential/high-risk unbiased review
```

## Host capability degradation

The governance model is semantic, not tied to one agent runtime. If a host lacks a capability:
- no delegated agents → primary agent performs the lane itself and uses another fresh context/model only when available and justified;
- no persistent delegated context → use fresh bounded tasks instead;
- no explicit Skill injection → resolve/read the canonical Skill through the host's available file/context mechanism;
- no read-only enforcement → instruct read-only behavior and verify no writes occurred; do not claim enforced isolation;
- no independent model/context → perform best-effort review and report the independence limitation.

Do not emulate missing host machinery by inventing a complex orchestration framework unless the product actually requires one.

## Anti-patterns

Do not:
- create a separate "orchestrator agent" that becomes a parallel owner to the primary agent;
- outsource the primary agent's own Core-First duty;
- give every worker every Skill and the entire project history;
- assume delegated agents inherit Skill state;
- use a persistent architecture advisor as its own final verifier;
- feed implementation narratives into independent review;
- run expensive multi-layer review for trivial edits;
- duplicate canonical Core-First or Independent Review rules inside this Skill;
- encode provider-specific agent names or APIs as universal governance rules.

## Completion condition

Before claiming completion, the primary agent must be able to state from actual evidence:
- which canonical owner/path the change used when architecture was material;
- what was delegated and with which knowledge/authority boundary;
- what verification actually ran;
- whether Core-First verification was required and its status;
- whether Independent Review was required and how its material findings were resolved;
- any host limitation that materially weakened freshness, isolation, or enforcement.
