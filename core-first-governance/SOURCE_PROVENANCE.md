# Source provenance

## v0.5.1

### `core-first-extension-architecture`

Copied byte-for-byte from the supplied canonical standalone `core-first-extension-architecture` source. v0.5.1 intentionally does **not** add product-verification or routing policy to that Skill. Its architecture ownership remains unchanged.

### `core-first-orchestration`

Derived from the v0.4.0 provider-neutral orchestration Skill and extended only in its existing routing responsibility to decide when observable product verification is material, how its evidence feeds correction/review, and how missing runtime capabilities degrade explicitly.

### `observable-product-verification`

Introduced in v0.5.0; preserved in v0.5.1 as the canonical procedure for user/external observable runtime evidence. It owns:
- outcome-vs-action evidence semantics;
- before/action/settled-after verification;
- ambient use of already-acquired evidence;
- cheap bounded adjacent exploration;
- finding/scope separation;
- runtime-evidence status `VERIFIED | FAILED | INCONCLUSIVE`;
- routing discovered failures through existing project maps/traces rather than inventing a second QA architecture.

It does **not** own software architecture, project truth, orchestration, or independent review.

### `core-first-verifier`

Preserved from v0.4.0 semantics: fresh read-only Core-First conformance verification.

### `independent-review`

Preserved as the anti-anchored evidence-based review owner for consequential/high-risk/difficult-to-verify/materially blocked work. v0.5.1 extends only its evidence handoff contract: raw observable/runtime evidence may be supplied, while prior observable-verification status/conclusions/confidence/finding narrative are withheld until the reviewer independently derives findings.

## Boundary

Portable Skill semantics remain provider-neutral. Codex packaging metadata and Windows installation are host adapters only. No MCP, browser implementation, computer-use implementation, or provider-specific interaction technology is required by the governance model.
