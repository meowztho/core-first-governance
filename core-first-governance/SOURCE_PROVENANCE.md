# Source provenance

## v0.6.0

### `core-first-extension-architecture`

Copied byte-for-byte from the supplied canonical standalone source. v0.6.0 intentionally does **not** move grounded execution, product-verification, review, or completion-routing policy into the architecture owner.

### `core-first-orchestration`

Extended in its existing orchestration responsibility with two narrow procedures:
- **Grounded Execution Preflight**: material sources/prerequisites progress from `DISCOVERED → INSPECTED → EXTRACTED → MAPPED → CONSUMED` before expensive execution, with exact toolchain/input compatibility checks and early surfacing of real external blockers;
- **External Completion Authority respect**: when a project already defines a separate acceptance/completion owner or validator, Governance supplements rather than replaces it. No specific APC/compiler/validator is hardwired.

### `core-first-verifier`

Extended with a provider-neutral two-phase anti-rationalization protocol: freeze expected owner/path/classification from requirement, authorities, and baseline project state before inspecting the change-under-review when the host can enforce that ordering; then compare the implementation to the frozen expectation.

### `observable-product-verification`

Extended with raw-evidence traceability for material observable claims through the current completion/review boundary. Existing project evidence stores are reused when present; no new evidence database/QA graph is required.

### `independent-review`

Unchanged from v0.5.1: anti-anchored evidence-based review receives raw evidence but not prior verifier interpretations before independent derivation.

## Boundary

Portable Skill semantics remain provider-neutral. Codex packaging metadata and Windows installation are host adapters only. No MCP, browser implementation, computer-use implementation, provider-specific agent API, or specific external completion platform is required by the governance model.
