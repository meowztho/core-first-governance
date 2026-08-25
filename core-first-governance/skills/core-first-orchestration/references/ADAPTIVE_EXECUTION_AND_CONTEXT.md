# Adaptive Execution and Context Reconciliation

Read this procedure for meaningfully multi-step/dependent/ambiguous/expensive/restart-sensitive work, or when continuation/compaction/context loss/new evidence may have made execution state stale.

## Execution frame

For implementation-authorized work, maintain only what helps execution:

```text
OUTCOME / ACCEPTANCE BOUNDARY
CURRENT AUTHORITIES + MATERIAL CONSTRAINTS
MEANINGFUL PHASES / DEPENDENCIES
NEXT STEP
CHECKPOINT / EVIDENCE
PLAN-INVALIDATING ASSUMPTIONS / BLOCKERS
```

If architecture is material, the primary agent's own Core-First owner/reuse/change-boundary decision must inform this frame before implementation or delegation.

Use a suitable native host plan/task tracker when available; do not create a second Governance plan artifact. Otherwise keep the simplest equivalent checklist/state. For multi-hour/multi-session/compaction-sensitive work, reuse an existing durable progress mechanism first and create one only when restartability materially benefits.

A plan is **provisional execution state**, not project truth, architecture ownership, or completion authority.

## Optional Working View / Atlas

For complex/spatial/multi-system/restart-sensitive work, externalize the current model only when useful. Use the cheapest representation (notes/Markdown/ASCII; HTML/SVG/storyboard when spatial structure helps), link canonical sources, and separate `CONFIRMED | INFERRED | UNKNOWN`.

It is disposable cache, never authority. Reuse an existing suitable view first. Reconcile it after material change/context loss. Do not require it for trivial work or as a project artifact.

## Checkpoint loop

```text
execute meaningful phase
→ inspect actual result/checkpoint
→ reconcile progress + assumptions
→ evidence changed owner/constraints/dependencies/feasibility/acceptance/best path?
   ├─ yes: update/split/merge/reorder remaining work BEFORE more material execution
   └─ no: continue
```

Grounded-preflight facts that materially determine the path must be `CONSUMED` before expensive execution commits to them.

Implementation-authorized work should continue through safe in-scope implementation and applicable verification unless blocked by a genuine user-owned/external/approval boundary. Planning/review/diagnosis/research-only requests must not silently cross into writes.

## Context rot / continuation

**WORKSPACE AWARENESS != WORKSPACE HYDRATION.** After fresh/continued context, major compaction/context loss, relevant Skill/authority revision, repository/external-state change, or material new evidence:

1. cheaply discover current workspace/repository state before trusting memory: relevant tree/nearby files, Git/current changes, existing routing/progress artifacts and prior working aids/evidence that may matter;
2. **discover before loading**: read only the canonical Skills, authorities, routes, and working artifacts needed by the active decision;
3. reconcile completed/remaining work and critical assumptions against current state;
4. replan before further material execution if the next best action changed.

Do not broadly rescan/repopulate context merely to regain confidence. Existing routing/index artifacts should prevent project rediscovery when still valid. A stale Working View/note remains cache; current authority/repository/runtime evidence wins.

### Working-aid discoverability

If a generated Working View or other derived aid is intended to survive continuation/context loss, keep it cheaply discoverable through an **existing** project/task/index/progress mechanism or an obvious stable location. Reuse an existing suitable aid before creating another. Do not create a parallel project index/manifest merely to register helper artifacts.
