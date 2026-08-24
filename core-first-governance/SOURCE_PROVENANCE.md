# Source provenance

## v0.7.0

### `core-first-orchestration`

Extended in its existing orchestration responsibility (`EXTEND_EXISTING_CAPABILITY`) with two provider-neutral behaviors while preserving all v0.6.0 gates:
- **Progressive Skill routing**: a compact routing capsule tells the primary agent when each sibling Skill is material, without preloading every Skill body. The primary agent must still load and apply `core-first-extension-architecture` itself whenever architecture is material; delegation never substitutes for this duty. Host Skill metadata is a discovery optimization, not a policy owner.
- **Adaptive execution / context reconciliation**: non-trivial authorized work uses a lightweight/native execution plan or checklist, reconciles checkpoints against current evidence, replans before continuing when material evidence changes the correct path, and after compaction/continuation re-inspects current state and reloads only required Skills/authorities. Trivial work does not gain planning ceremony.

The v0.6.0 Grounded Execution Preflight and external Completion Authority routing remain in the same owner.

### Protected sibling Skill bodies

The following `SKILL.md` files are intentionally byte-identical to v0.6.0:
- `core-first-extension-architecture`
- `observable-product-verification`
- `core-first-verifier`
- `independent-review`

No responsibility was moved out of those canonical procedure owners merely to make the orchestrator more informed.

## Boundary

Portable Governance owns semantic invariants. Native host capabilities (Skill discovery, planning/task tracking, subagents, read-only isolation, product-surface tools) are providers/adapters that may satisfy those invariants efficiently. Missing host capabilities use the simplest valid fallback.

**Reduce duplicate execution, not duplicate requirements.**
