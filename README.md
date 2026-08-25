# Core-First Governance v0.10.0

Provider-neutral governance for AI-assisted software work, currently packaged as a Codex **Skills-only** plugin.

## What v0.10.0 changes

v0.10.0 addresses two empirically observed agent failures without adding a new Skill, MCP server, debugger, workspace database, or general-purpose tool layer.

### 1. Evidence-driven debugging

A negative test must change the active causal model.

```text
observed failure
→ actual runtime/user surface
→ existing owner/flow route
→ candidate producer
→ effective runtime geometry/state
→ focused falsification
→ remove disproven premise + dependent hypothesis family
→ re-derive next best check
```

Visual resemblance is not source identity, and **visible footprint is not producer bounds**. A small/differently bounded child can create a much larger artifact through layout, minimum/content sizing, overflow/clipping, transforms, stretch/fit/expand behavior, or framework equivalents. The plugin does not hard-code Godot/CSS/UMG/etc.; the agent inspects only the runtime geometry semantics material to the current stack.

### 2. Workspace awareness after context loss

```text
WORKSPACE AWARENESS != WORKSPACE HYDRATION
```

After major compaction/continuation, the agent cheaply rediscovers what currently exists before trusting memory: relevant files/tree, current Git changes, existing project routing/progress artifacts, and prior working aids/evidence likely to matter. It then **discovers before loading** and JIT-reads only material sources.

Existing valid routing prevents broad project rediscovery. A Working View/Atlas remains derived cache; current project/repository/runtime truth wins. If a derived aid is intended to survive continuation, it should be cheaply discoverable through an existing project/task/index/progress mechanism or an obvious stable location. Do not create a second helper index merely to register it.

## Existing v0.9 surface model remains intact

For material user-surface work:

```text
PROJECT USER-SURFACE AUTHORITY
        ↓
consume before implementation
        ↓
STYLE | STRUCTURE | PLACEMENT | HIERARCHY
SPACING/SCALE | STATES | RESPONSIVE | REFERENCES
        ↓
implementation
        ↓
REAL WHOLE SURFACE
        ↓
OPV against the same applicable authority
```

The agent distinguishes `CONFIRMED | INFERRED | UNKNOWN`; relative guidance stays relative. Optional Working Views/Atlases are disposable interpretation/cache, not authority.

## Context budget

The always-loaded kernel remains below the existing v0.8 ceiling. The new debugging discipline is a **separate JIT reference**, so normal non-debug tasks do not preload it.

- v0.9 always-loaded kernel: **10,250 bytes**
- v0.10 always-loaded kernel: **10,594 bytes**
- v0.10 kernel + five owner-local JIT references: **25,997 bytes**
- hard ceilings: **11,000-byte kernel**, **4,000 bytes per JIT reference**, **26,500-byte total owner corpus**

The total-corpus ceiling increases only because debugging is now isolated into its own on-demand procedure; it is not an always-loaded context increase.

## Consumer-tool decision

No mandatory consumer-tool gap is introduced. The observed failures are reasoning/attention/evidence-consumption/context-continuity problems that can be corrected with small JIT Skill guidance plus existing host read/search/runtime/vision capabilities.

No bundled:

- `.mcp.json` / MCP server;
- computer-use stack;
- debugger tool;
- workspace database;
- atlas generator;
- sixth Skill.

## Hard invariants preserved

- Primary agent = orchestrator + final integrator, not dispatcher-only.
- When architecture/ownership/reuse is material, the primary agent **MUST load and apply `core-first-extension-architecture` itself**.
- Current repository/project/runtime truth outranks memory, old plans and derived views.
- Grounded Execution remains `DISCOVERED → INSPECTED → EXTRACTED → MAPPED → CONSUMED`.
- Non-trivial execution remains adaptive and replans on invalidating evidence.
- Existing project routing/index artifacts are reused before broad rediscovery.
- Core-First verifier remains fresh/read-only/two-phase.
- Independent Review remains anti-anchored.
- Project-defined external completion authority remains external.
- Portable Governance remains provider/tool neutral.

## Five Skills

| Skill | Canonical responsibility |
| --- | --- |
| `core-first-orchestration` | minimal-context routing, grounded/adaptive execution, workspace reconciliation, evidence-driven debugging, delegation/completion routing |
| `core-first-extension-architecture` | ownership, reuse, composition, capabilities/providers/extensions, reverse-debug architecture path |
| `observable-product-verification` | real user/external outcomes, whole-surface fidelity, evidence reuse/traceability |
| `core-first-verifier` | fresh read-only two-phase Core-First conformance |
| `independent-review` | anti-anchored consequential/high-risk review |

## Windows / Codex UI installation

From the extracted release directory:

```powershell
Set-ExecutionPolicy -Scope Process Bypass
.\install-personal-windows.ps1
```

The installer copies the plugin to `%USERPROFILE%\.codex\plugins\core-first-governance` and updates `%USERPROFILE%\.agents\plugins\marketplace.json`. Restart the ChatGPT desktop app, install/update **Core-First Governance** from the Personal source, and start a new Codex thread.

## Repository layout

```text
.
├── README.md
├── CONTEXT_HANDOFF_2026-08-25_v0.10.0.md
├── RELEASE_AUDIT_v0.10.0.md
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
        │   ├── SKILL.md
        │   └── references/
        │       ├── GROUNDED_EXECUTION_PREFLIGHT.md
        │       ├── ADAPTIVE_EXECUTION_AND_CONTEXT.md
        │       ├── EVIDENCE_DRIVEN_DEBUGGING.md
        │       ├── DELEGATION_CONTEXT.md
        │       └── VERIFICATION_AND_COMPLETION_ROUTING.md
        ├── core-first-extension-architecture/
        ├── observable-product-verification/
        ├── core-first-verifier/
        └── independent-review/
```

## Development rules

1. One canonical owner per durable responsibility.
2. JIT detail must be explicitly routed; context optimization may not weaken semantics.
3. Negative evidence must invalidate dependent hypotheses, not merely add another note.
4. Do not identify visual/runtime sources from resemblance or matching visible size alone.
5. After context loss, discover current workspace state cheaply before JIT loading; never hydrate everything by default.
6. Working aids remain cache and reuse existing discoverability/routing mechanisms.
7. Do not add consumer tools merely because the host/plugin format supports them.
8. Re-run release + host validation after Skill/manifest changes.

## License

No repository license has been selected in this package. Add the intended license before public redistribution if explicit terms are required.
