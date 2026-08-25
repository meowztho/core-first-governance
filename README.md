# Core-First Governance v0.9.0

Provider-neutral governance for AI-assisted software work, currently packaged as a Codex **Skills-only** plugin.

## What v0.9.0 changes

v0.9.0 closes a visual/spatial reasoning gap without adding a new Skill, MCP server, tool bundle, design framework, or coordinate system.

```text
PROJECT USER-SURFACE AUTHORITY
        ↓
consume before material surface implementation
        ↓
derive only task-relevant working model
        ↓
implementation
        ↓
REAL WHOLE SURFACE
        ↓
OPV against the same applicable authority
```

**User-Surface Authority** is a semantic role, not a required filename. Existing project sources may supply it: product/UI specifications, design/style guides, layout rules, mockups/reference screenshots, design tokens, product vision, existing approved surfaces, Figma/export data, or project-specific equivalents.

The agent pays attention to:

```text
STYLE | STRUCTURE | PLACEMENT | HIERARCHY
SPACING/SCALE | STATES | RESPONSIVE | REFERENCES
```

It preserves provenance and distinguishes `CONFIRMED | INFERRED | UNKNOWN`. Relative layout guidance remains relative; the plugin does not invent exact coordinates that the project did not specify.

## Optional Working View / Atlas

For complex/spatial/multi-system/restart-sensitive work, the agent may externalize its current model as the cheapest useful derived view: notes/Markdown/ASCII, or HTML/SVG/storyboard when spatial reasoning benefits.

```text
project/repository authority > Working View/Atlas > memory
```

The Working View is disposable cache. It may link source files, map flows, sketch a screen, or show a storyboard, but it never becomes project truth or a mandatory artifact. Trivial work should not generate one.

## Visual / E2E fidelity

`observable-product-verification` still requires the real surface and now explicitly compares material visual/layout outcomes to the applicable project authority.

```text
correct tokens + wrong placement      → FAILED visual claim
all controls present + wrong layout   → FAILED visual claim
log says screen loaded + distorted UI → FAILED visual claim
relative approved layout matches      → no invented x/y coordinates required
```

A current screenshot/frame remains evidence for the whole relevant visible state and may be reused while that state is unchanged. A relevant change invalidates affected old visual evidence. A static screenshot still does not prove interaction.

## Context budget

The v0.8 progressive-disclosure ceiling is preserved. v0.9 adds the new behavior inside the existing JIT owners rather than creating another always-loaded procedure.

- always-loaded orchestration kernel: **10,250 bytes**
- kernel + all four orchestration references: **22,975 bytes**
- ceilings remain **11,000 / 23,000 bytes**

Compared with v0.8, the always-loaded kernel grows by only **48 bytes**; most new surface/Working-View guidance is JIT.

## Consumer-tool decision

The audit found **no mandatory consumer-tool gap** for this change. v0.9.0 therefore ships no `.mcp.json` and no bundled MCP server. Skills guide attention/structure; existing host capabilities perform reading, searching, screenshots/computer use, shell work, etc. A future tool should be admitted only for a concrete bounded, preferably deterministic gap where it measurably reduces repeated work/errors or context/token cost.

## Hard invariants preserved

- Primary agent = orchestrator + final integrator, not dispatcher-only.
- When architecture/ownership/reuse is material, the primary agent **MUST load and apply `core-first-extension-architecture` itself**.
- Current repository/project truth outranks memory, old plans and derived Working Views.
- Exactly five Skills; no sixth visual/design/atlas Skill.
- Grounded Execution remains `DISCOVERED → INSPECTED → EXTRACTED → MAPPED → CONSUMED`.
- Non-trivial execution stays adaptive and replans on invalidating evidence.
- Core-First verifier remains fresh/read-only/two-phase.
- Independent Review remains anti-anchored.
- Project-defined external completion authority remains external.
- Portable Governance remains provider/tool neutral.

## Five Skills

| Skill | Canonical responsibility |
| --- | --- |
| `core-first-orchestration` | minimal-context routing, grounded execution including surface-authority consumption, adaptive execution/Working View, delegation and completion routing |
| `core-first-extension-architecture` | ownership, reuse, composition, capabilities/providers/extensions, reverse-debugging |
| `observable-product-verification` | real user/external outcomes, whole-surface fidelity to applicable authority, evidence reuse/traceability |
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
├── CONTEXT_HANDOFF_2026-08-25_v0.9.0.md
├── RELEASE_AUDIT_v0.9.0.md
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
        ├── core-first-extension-architecture/
        ├── observable-product-verification/
        ├── core-first-verifier/
        └── independent-review/
```

## Development rules

1. One canonical owner per durable responsibility.
2. Context optimization may JIT procedure detail only through explicit routing; it may not weaken semantics.
3. Surface/design/layout sources remain project authorities; derived models/Working Views remain cache.
4. Do not force exact coordinates where the project only specifies relative placement.
5. Logs/debug state and element presence do not substitute for whole-surface correctness.
6. Do not add consumer tools merely because the host/plugin format supports them.
7. Re-run release + host validation after Skill/manifest changes.

## License

No repository license has been selected in this package. Add the intended license before public redistribution if explicit terms are required.
