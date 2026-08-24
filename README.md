# Core-First Governance v0.7.0

Provider-neutral governance for AI-assisted software work, currently packaged as a Codex plugin. The user-facing **primary agent remains the orchestrator, must apply Core-First itself when architecture is material, and is the final integrator**.

## What v0.7.0 adds

v0.7.0 extends only the existing `core-first-orchestration` capability at the portable Skill-body level. It preserves all v0.6.0 behavior and keeps the other four Skill bodies byte-identical.

- **Progressive Skill routing** — the primary agent has a compact routing capsule that tells it which sibling procedure is material without preloading every full `SKILL.md`.
- **Primary-agent Core-First duty made explicit at the routing boundary** — Core-First is not a subagent-only concern. When architecture/ownership/reuse is material, the primary agent itself loads and applies `core-first-extension-architecture` before direct implementation or delegation.
- **Adaptive execution** — non-trivial authorized work gets a lightweight/native execution frame with meaningful steps/checkpoints; evidence is reconciled as work progresses and invalidating evidence causes replanning before further material execution.
- **Context-rot / continuation reconciliation** — after compaction, continuation, material authority changes, or new evidence, the agent re-inspects current state, reloads only required Skills/authorities, reconciles progress/assumptions, and does not trust a stale plan as authority.
- **Native-capability substitution** — native host Skill discovery and planning/task tracking may satisfy the portable invariant efficiently; Governance does not create duplicate plan artifacts or delete the invariant because one host already supplies it.

Core design law:

```text
Reduce duplicate execution, not duplicate requirements.
```

## Five canonical Skills

| Skill | Responsibility | Primary-agent relationship |
| --- | --- | --- |
| `core-first-orchestration` | Primary-agent routing, grounded preflight, adaptive execution/replanning, context/delegation, verification escalation, completion-authority routing. | Runs in the primary-agent governance path. |
| `core-first-extension-architecture` | Canonical architecture method for ownership, reuse, composition, modules/providers/extensions and reverse debugging. | **Primary agent MUST load and apply it itself whenever material.** |
| `observable-product-verification` | Real user/external outcome evidence, settled-state checks, bounded adjacent exploration, raw-evidence traceability. | Primary agent ensures it occurs when required; may perform or route it. |
| `core-first-verifier` | Fresh read-only two-phase Core-First architecture conformance verification. | Separate verification context when feasible; never substitutes for primary Core-First reasoning. |
| `independent-review` | Anti-anchored review for consequential, high-risk, difficult-to-verify or materially blocked work. | Separate anti-anchored review path when its trigger is material. |

## Progressive Skill routing

The orchestrator knows the **trigger and responsibility** of each sibling Skill, not its full detailed method. Detailed methods remain with their canonical owners and are loaded just in time.

```text
ROUTING KNOWLEDGE
!= PROCEDURAL KNOWLEDGE
```

A host may expose Skill names/descriptions natively. Use that discovery when useful, but the portable routing contract remains in `core-first-orchestration`; host metadata is a projection/optimization, not a second policy authority.

Do not preload all five Skills merely because the context window can hold them. Context is finite attention, not free storage.

## Primary-agent Core-First invariant

```text
User request
  ↓
Primary agent
  ↓
Is architecture / ownership / reuse material?
  ├─ no  → shortest safe path
  └─ yes → load + apply core-first-extension-architecture ITSELF
             ↓
          determine owner/reuse/change boundary
             ↓
          direct implementation OR bounded delegation
```

Delegation does not discharge this obligation. If a task begins as trivial and later exposes shared authoritative behavior, the primary agent must stop treating it as trivial and apply Core-First before further material architecture work.

## Grounded + adaptive execution

v0.6.0 Grounded Execution Preflight remains intact:

```text
DISCOVERED → INSPECTED → EXTRACTED → MAPPED → CONSUMED
```

v0.7.0 adds the execution loop around it:

```text
current requirement / authorities / repo state
  ↓
grounded preflight when material
  ↓
Core-First decision by primary agent when material
  ↓
lightweight/native execution frame for non-trivial authorized work
  ↓
execute meaningful checkpoint
  ↓
inspect actual result
  ↓
new evidence changes owner / constraints / dependencies / feasibility / best path?
  ├─ yes → reframe/replan BEFORE further material execution
  └─ no  → continue
  ↓
applicable verification / review / external completion authority
```

A plan is execution state, not product truth, architecture ownership, or completion authority. Trivial/single-step work should not gain ceremonial planning.

## Context-rot resilience

After fresh context, major compaction/context loss, continuation, relevant Skill/authority revision, repo/external-state change, or material new user evidence:

```text
inspect CURRENT state
→ reload only required Skills + authorities
→ reconcile completed/remaining work + assumptions
→ update plan when next best action changed
→ continue
```

Do not replay all historical context or preload unrelated procedures to regain confidence. Use a small stable routing/goal state and exact JIT reads.

## Existing v0.6.0 protections remain

- exact prerequisite/toolchain compatibility checks;
- two-phase Core-First verifier (expectation before change evidence when feasible);
- traceable material OPV raw evidence;
- Independent Review anti-anchoring;
- project-defined external Completion Authority respected rather than replaced;
- provider/tool neutrality;
- five Skills only;
- no second QA/evidence graph or orchestration owner.

## Provider neutrality

Portable semantics do not depend on Codex `update_plan`, Codex subagents, Claude/Gemini planning modes, MCP, a particular browser/computer-use system, PowerShell, or a specific external completion platform.

Host-native capabilities are providers/adapters:

```text
portable invariant
→ strongest suitable native host capability when available
→ simplest valid fallback otherwise
```

## Windows / Codex UI installation

From the extracted release directory:

```powershell
Set-ExecutionPolicy -Scope Process Bypass
.\install-personal-windows.ps1
```

The installer copies the plugin source to `%USERPROFILE%\.codex\plugins\core-first-governance` and creates/updates `%USERPROFILE%\.agents\plugins\marketplace.json`. Fully restart ChatGPT desktop, install **Core-First Governance** from the Personal source in Plugins Directory, then start a new Codex thread.

The installer is unsigned unless you sign it with your own code-signing certificate using `sign-installer.ps1`.

## Repository layout

```text
.
├── README.md
├── CONTEXT_HANDOFF_2026-08-24_v0.7.0.md
├── RELEASE_AUDIT_v0.7.0.md
├── INSTALL-WINDOWS.md
├── install-personal-windows.ps1
├── sign-installer.ps1
├── validate_release.py
├── SHA256SUMS.txt
└── core-first-governance/
    ├── .codex-plugin/plugin.json
    ├── SOURCE_PROVENANCE.md
    └── skills/
        ├── core-first-orchestration/
        ├── core-first-extension-architecture/
        ├── observable-product-verification/
        ├── core-first-verifier/
        └── independent-review/
```

## Development rules

1. One canonical owner per responsibility/rule/state transition.
2. Primary agent = orchestrator + Core-First participant for its own architecture-relevant work + final integrator.
3. Routing knowledge may be compact; detailed procedure knowledge stays at the sibling Skill owner and loads JIT.
4. Do not preload every Skill/history merely because a large context is available.
5. Use native planning/discovery when suitable, but do not duplicate it or remove portable invariants.
6. Reconcile current repo/authority state after compaction/continuation before trusting an old plan.
7. Preserve all v0.6.0 grounded-preflight, verifier, OPV, review and completion-authority boundaries.
8. Keep portable semantics provider/tool neutral.
9. Re-run release and host/package validation after Skill or manifest changes.

## License

No repository license has been selected in this package. Add the intended license before public redistribution if explicit terms are required.
