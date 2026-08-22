# Source provenance

## v0.5.0

### `core-first-extension-architecture`

Copied byte-for-byte from the supplied canonical standalone `core-first-extension-architecture` source. v0.5.0 intentionally does **not** add product-verification or routing policy to that Skill. Its architecture ownership remains unchanged.

### `core-first-orchestration`

Derived from the v0.4.0 provider-neutral orchestration Skill and extended only in its existing routing responsibility to decide when observable product verification is material, how its evidence feeds correction/review, and how missing runtime capabilities degrade explicitly.

### `observable-product-verification`

New v0.5.0 canonical procedure for user/external observable runtime evidence. It owns:
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

Preserved from v0.4.0 semantics: anti-anchored evidence-based review for consequential/high-risk/difficult-to-verify/materially blocked work.

## Boundary

Portable Skill semantics remain provider-neutral. Codex packaging metadata and Windows installation are host adapters only. No MCP, browser implementation, computer-use implementation, or provider-specific interaction technology is required by the governance model.
