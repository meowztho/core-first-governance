# Core-First Governance v0.5.1

Provider-neutral agent governance for **Core-First software architecture plus observable product verification**, currently packaged as a Codex plugin.

## What v0.5.1 changes

v0.5.1 hardens the handoff from observable product verification to independent review: the independent reviewer receives the **raw runtime/observable evidence**, but not the observable verifier's interpreted `VERIFIED | FAILED | INCONCLUSIVE` result, conclusion, confidence, or finding narrative before independently deriving its own findings. It also removes the duplicate context-handoff document from the release.

## Why v0.5.0 exists

Good code, passing builds, and clean architecture do not prove that a product actually works at the user/external boundary. A button can exist but do nothing, a slider can receive an input without moving, a game can pass unit tests and still fail after landing, and an API call can succeed without producing its required external effect.

v0.5.0 adds a separate verification procedure while preserving the existing ownership model:

| Skill | Responsibility |
| --- | --- |
| `core-first-orchestration` | Primary-agent routing for Core-First, delegation, observable verification, freshness, and review escalation. |
| `core-first-extension-architecture` | Canonical architecture method for ownership, reuse, composition, providers, extensions, and core-rule changes. |
| `observable-product-verification` | Proves real user/external runtime outcomes and makes already-acquired evidence work harder without turning every check into a full regression pass. |
| `core-first-verifier` | Fresh, read-only Core-First architecture conformance verification. |
| `independent-review` | Unbiased read-only review for consequential, high-risk, difficult-to-verify, or materially blocked work. |

## Operating model

```text
User requirement
  ↓
Primary agent = orchestrator + final integrator
  ↓
core-first-orchestration
  ├─ Core-First architecture when ownership/reuse is material
  ├─ bounded implementation/investigation delegation when useful
  ├─ observable-product-verification when a real runtime/user outcome is material
  │    ├─ before → action → settled after
  │    ├─ inspect already-acquired surrounding evidence
  │    ├─ cheap bounded adjacent actions
  │    └─ preserve failures as evidence
  ├─ Core-First reverse trace for architecture/root-cause correction when needed
  ├─ fresh Core-First verifier for material architecture changes
  └─ independent review for consequential/high-risk/difficult work
```

### Important invariants

- **The primary agent remains the orchestrator.** No new product-verification agent becomes a parallel owner.
- **Successful actions are not successful outcomes.** A click/input/request/build/tool call proves only what was actually observed.
- **Use the real boundary when the claim depends on it.** If it cannot be exercised, report the claim as unverified/inconclusive rather than silently downgrading to static evidence.
- **Use already-acquired evidence fully.** Observe obvious material contradictions in the same visible/runtime evidence instead of tunnel-visioning on a single assertion.
- **Observation does not expand write authority.** Adjacent/unrelated defects may be reported without being opportunistically fixed.
- **Explore only cheaply and locally.** Perform a few natural adjacent actions when they are low-cost and likely to reveal integration failures; do not force a full-product regression for every change.
- **Reuse project navigation.** A runtime failure should follow existing project index/system/capability/runtime-trace/Blueprint/implementation-anchor routes first; validate the anchor and broaden discovery only when the route is missing, stale, ambiguous, or contradicted.
- **No second QA architecture.** Verification does not create a duplicate project graph.
- **Tooling is abstract.** The governance model requires capabilities/evidence, not a particular MCP, browser, computer-use system, script, or provider.

## Provider-neutral roles

The existing roles remain unchanged:

- **primary agent** — user-facing root agent; orchestrator and final integrator;
- **delegated agent** — bounded child/specialist execution context;
- **targeted worker** — bounded implementation/investigation with architecture already decided;
- **Core-First advisor/worker** — architecture lane using Core-First fresh;
- **Core-First verifier** — fresh read-only architecture conformance context;
- **independent reviewer** — anti-anchored consequential/high-risk review context.

`observable-product-verification` is a **Skill/procedure**, not a mandatory new role. The primary agent can run it itself or give the procedure to an appropriately bounded existing role.

## Windows / Codex UI installation

From the extracted release directory:

```powershell
Set-ExecutionPolicy -Scope Process Bypass
.\install-personal-windows.ps1
```

The installer copies the plugin source to:

```text
%USERPROFILE%\.codex\plugins\core-first-governance
```

and updates:

```text
%USERPROFILE%\.agents\plugins\marketplace.json
```

Then fully restart the ChatGPT desktop app, open the Plugins Directory, install **Core-First Governance** from the personal source, and start a **new Codex thread** so the updated five-Skill package is picked up cleanly.

## Repository layout

```text
.
├── README.md
├── CONTEXT_HANDOFF_2026-08-22_v0.5.1.md
├── INSTALL-WINDOWS.md
├── install-personal-windows.ps1
├── sign-installer.ps1
├── validate_release.py
├── SHA256SUMS.txt
└── core-first-governance/
    ├── .codex-plugin/
    │   └── plugin.json
    ├── SOURCE_PROVENANCE.md
    └── skills/
        ├── core-first-orchestration/
        ├── core-first-extension-architecture/
        ├── observable-product-verification/
        ├── core-first-verifier/
        └── independent-review/
```

## Validation

`validate_release.py` is a release-local structural/provenance validator included in this bundle. It checks the manifest, five Skill layouts, YAML/JSON syntax, and byte identity of the packaged canonical Core-First Skill against the supplied canonical source hash recorded for this release.

For Codex publishing/ingestion, also run the host's current canonical plugin validator when available. Host-specific validation is an adapter concern and may evolve independently of the portable Skill semantics.

## Development rules

1. Preserve one canonical owner per rule.
2. Keep `core-first-extension-architecture` canonical; do not duplicate architecture taxonomy into product verification or orchestration.
3. Keep observable-product outcome/evidence semantics inside `observable-product-verification`.
4. Keep `core-first-verifier` architecture-focused and fresh/read-only.
5. Keep `independent-review` anti-anchored and high-signal: pass raw evidence, not prior verifier interpretations, before independent derivation.
6. Keep portable semantics provider/tool neutral.
7. Do not turn ambient observation into automatic scope expansion.
8. Re-run release and host/package validation after Skill or manifest changes.

## License

No repository license has been selected in this package. Add the intended license before public redistribution if explicit terms are required.
