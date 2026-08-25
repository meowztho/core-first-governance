# Verification, Review, and Completion Routing

Read this procedure when observable product verification, Core-First conformance verification, Independent Review, finding reconciliation, or a project-defined external completion authority is material.

## Observable product verification

Trigger when a requirement/bug/acceptance/completion claim materially depends on behavior observable at a real user or external-system boundary: interactive UI/web/desktop/mobile/game/device behavior; navigation/control/animation/input/visual state/persistence/workflow; CLI output/effects; API/service external state/side effects; realistic library/integration consumer path; automation/batch real output/effects; runtime-only symptoms.

Load `observable-product-verification` JIT and use the strongest suitable real interaction/observation capability available. Logs, tests, implementation state, or tool success may support diagnosis but do not replace the real surface for a user-visible claim. `INCONCLUSIVE` is not verified.

If it finds a material defect: preserve raw evidence/finding class; return control to the primary agent; route through existing project authorities and Core-First when architecture is material; correct within scope; rerun the affected observable path.

## Core-First verifier

Use `core-first-verifier` for material architecture/reuse/ownership conformance changes or important/final milestones of long-running architecture work.

Required semantics:
- separate fresh verification context when feasible;
- read-only;
- load verifier + canonical Core-First fresh;
- two-phase anti-rationalization: freeze expected owner/path/classification/allowed writes from requirement + authorities + baseline project state before seeing the change-under-review evidence when the host can enforce ordering; then compare the actual diff/files/tests/runtime evidence;
- no implementer rationale/confidence/conclusions or prior verifier conclusion before independent derivation.

If freshness/order/read-only isolation cannot be guaranteed, use the strongest available mechanism and disclose the limitation.

## Independent Review

Use `independent-review` only for consequential, high-risk, difficult-to-verify, or materially blocked implementation work. It supplements rather than replaces primary verification, OPV, or Core-First verification.

Before independent derivation, withhold implementer narrative/conclusions/confidence/justification, Core-First-verifier conclusions, and OPV interpreted status/conclusion/confidence/finding narrative. Pass original requirements, complete applicable project instructions, relevant raw diffs/files, actual verification-command/output evidence, and relevant raw observable/runtime evidence. Project truth is never hidden to manufacture independence.

## Reconcile findings

For each material finding: fix when in-scope/required; reject with direct evidence; record/report valid adjacent/unrelated observations without automatic scope expansion; or explicitly accept risk when authority permits. Resolve disagreements by investigating evidence, not majority vote.

## Existing external completion authority

Before self-certifying completion, determine whether the project/repository defines a separate acceptance/completion owner or validator (project evidence/acceptance store, CI/release gate, regulated approval, or equivalent).

If present, follow its project-defined acceptance contract and route required raw evidence through the existing mechanism. Governance, verifier PASS, OPV status, or reviewer result never replaces that authority's decision. If unavailable/unsatisfied, report the actual completion state.

If none exists, do not invent one and do not hardwire Governance to a specific external compiler/validator product.
