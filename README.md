# Core-First Governance v0.6.0

Provider-neutral governance for AI-assisted software work, currently packaged as a Codex plugin. The primary user-facing agent remains the orchestrator and final integrator.

## What v0.6.0 adds

- **Grounded Execution Preflight** — prevents agents from listing/skimming sources and then implementing from assumptions. Material knowledge progresses `DISCOVERED → INSPECTED → EXTRACTED → MAPPED → CONSUMED` before expensive execution.
- **Exact prerequisite/toolchain checks** — validates the actual input/format and required operation against the candidate tool/dependency before building around an unsupported assumption.
- **Two-phase Core-First verification** — the verifier freezes the expected owner/path/classification before seeing the change-under-review diff when the host can enforce that ordering, then compares the implementation to that baseline.
- **Raw observable-evidence traceability** — material OPV claims retain inspectable before/action/settled-after evidence through the current completion/review boundary without forcing a new evidence system.
- **External Completion Authority respect** — if a project already has an explicit completion/acceptance owner or validator, Governance supplements rather than replaces it. No APC or other platform is hardwired.

## Five canonical Skills

| Skill | Responsibility |
| --- | --- |
| `core-first-orchestration` | Primary-agent routing, grounded execution preflight, context/delegation, verification escalation, external completion-authority routing. |
| `core-first-extension-architecture` | Canonical architecture method for ownership, reuse, composition, modules/providers/extensions and reverse debugging. |
| `observable-product-verification` | Real user/external outcome evidence, settled-state checks, bounded adjacent exploration, raw-evidence traceability. |
| `core-first-verifier` | Fresh read-only two-phase Core-First architecture conformance verification. |
| `independent-review` | Anti-anchored review for consequential, high-risk, difficult-to-verify or materially blocked work. |

## Operating model

```text
User requirement
  ↓
Primary agent = orchestrator + final integrator
  ↓
Ground material plans in actual sources/prerequisites
  ↓
Core-First architecture/reuse reasoning when material
  ↓
Optional bounded delegation
  ↓
Integration
  ↓
Observable Product Verification when the real boundary matters
  ↓
Fresh two-phase Core-First verifier when architecture is material
  ↓
Independent Review when risk/verification difficulty warrants it
  ↓
Project-defined external Completion Authority when one exists
  ↓
Final user response
```

## Grounded Execution Preflight

A discovered source is not automatically usable knowledge:

```text
DISCOVERED  → known to exist
INSPECTED   → actually examined
EXTRACTED   → relevant facts identified
MAPPED      → facts connected to the task/plan
CONSUMED    → plan demonstrably uses them
```

This gate is conditional, not ceremonial. It is intended for multi-source tasks, opaque/legacy/binary formats, port/migration/import/decompile work, research-driven choices, material dependency/tool assumptions and other cases where a cheap prerequisite check can prevent large rework.

## Verification model

```text
successful action != successful outcome
implementation evidence != runtime evidence
status alone != traceable material evidence
```

Observable claims use before → normal action → settled after. Material raw evidence remains traceable through the active completion/review boundary. Existing project evidence storage is reused; Governance does not create a second QA/evidence architecture.

The Core-First verifier uses expectation-before-change-evidence when feasible:

```text
Phase A: requirement + authorities + baseline → freeze expected architecture
Phase B: diff/files/tests/runtime evidence → compare against frozen expectation
```

## Provider neutrality

Portable semantics do not depend on Codex subagents, Claude/Gemini agent APIs, MCP, a particular browser/computer-use system, PowerShell, or any specific external completion platform. Host mechanisms are adapters for the semantic roles/capabilities.

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
├── CONTEXT_HANDOFF_2026-08-23_v0.6.0.md
├── RELEASE_AUDIT_v0.6.0.md
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
2. Keep `core-first-extension-architecture` canonical unless intentionally versioning that architecture method.
3. Extend existing owners before adding new Skills/agent roles.
4. Material source/tool discovery must be consumed by the plan, not merely listed.
5. Preserve verifier anti-anchoring: expectation before change evidence when feasible.
6. Keep raw observable evidence traceable without inventing duplicate evidence infrastructure.
7. Respect project-defined completion authorities without hardwiring a particular product.
8. Keep portable semantics provider/tool neutral.
9. Re-run release and host/package validation after Skill or manifest changes.

## License

No repository license has been selected in this package. Add the intended license before public redistribution if explicit terms are required.
