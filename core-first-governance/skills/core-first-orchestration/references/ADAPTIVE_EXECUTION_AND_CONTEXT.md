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

After fresh/continued context, major compaction/context loss, relevant Skill/authority revision, repository/external-state change, or material new evidence:

1. inspect current repository/external state rather than trusting remembered conversation;
2. reload only the canonical Skills/authorities required by the active decision;
3. reconcile completed/remaining work and critical assumptions;
4. replan before further material execution if the next best action changed.

Do not repopulate context with unrelated Skills/history merely because a large context window exists. A compact current routing/goal state + exact JIT reads is preferred.
