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

## v0.8.0

### Context-budget refactor inside `core-first-orchestration`

Classification: `EXTEND_EXISTING_CAPABILITY` / owner-local refactor of the existing orchestration capability.

The v0.7.0 orchestration monolith was compressed into a small always-loaded kernel plus explicit JIT references. No semantic owner was moved to another Skill. The kernel retains the non-negotiable primary-agent Core-First duty, compact sibling routing, current-truth/cache law, progressive disclosure, grounded/adaptive execution trigger, and verification/completion routing trigger.

Detailed owner-local procedures are now under:
- `references/GROUNDED_EXECUTION_PREFLIGHT.md`
- `references/ADAPTIVE_EXECUTION_AND_CONTEXT.md`
- `references/DELEGATION_CONTEXT.md`
- `references/VERIFICATION_AND_COMPLETION_ROUTING.md`

This is progressive disclosure, not deletion: each reference has an explicit material trigger in the kernel and must be read before crossing that boundary.

### Observable visual evidence hardening

Classification: `EXTEND_EXISTING_CAPABILITY` in `observable-product-verification`.

The existing ambient-observation rule is made explicit for user-visible work:
- logs/telemetry/internal success state are supporting evidence, not substitutes for the real visible surface;
- a current screenshot/frame is a whole relevant visible-state snapshot rather than a one-element assertion;
- current visual evidence may be reused for unchanged visible facts;
- relevant visual/state changes invalidate the affected old snapshot and require fresh visual evidence;
- a static screenshot does not prove interaction/temporal behavior.

No new QA/evidence owner, screenshot archive, visual-verifier Skill, or tool binding was introduced.

### Protected owners

`core-first-extension-architecture`, `core-first-verifier`, and `independent-review` Skill bodies remain unchanged from v0.7.0. `observable-product-verification` is intentionally changed only within its existing evidence responsibility.


## v0.9.0

### User-Surface Authority red thread

Classification: `EXTEND_EXISTING_CAPABILITY` in `core-first-orchestration` + `observable-product-verification`; no new Skill/owner.

Material user-surface work now consumes existing project design/layout/placement authorities before implementation, derives only a task-relevant surface working model, and verifies the rendered whole surface against the same applicable authority. Exact specified constraints and specified holistic intent both matter; relative guidance remains relative and does not create invented coordinates.

### Optional derived Working View / Atlas

For complex/spatial/multi-system/restart-sensitive work, orchestration may externalize its current model as compact notes/Markdown/ASCII/HTML/SVG/storyboard. It must link canonical sources and distinguish `CONFIRMED | INFERRED | UNKNOWN`. This view is disposable cache, never project truth or a new authority.

### Consumer-tool decision

No MCP server or new consumer tool is introduced. The current failure class is solvable by compact Skill guidance plus existing host read/search/visual capabilities. Tooling remains admitted only for a concrete bounded gap where it reduces repeated deterministic work, errors, or context/token cost without creating a parallel owner or general-purpose toolbox.

## v0.10.0

### Evidence-driven debugging

Classification: `EXTEND_EXISTING_CAPABILITY` in `core-first-orchestration`; no new Skill/owner.

A focused JIT debugging reference now requires negative evidence to invalidate the causal premises and dependent hypothesis families it disproves. Visual/runtime source identity is routed from the actual observable owner/path rather than resemblance or visible artifact size alone; effective runtime geometry may differ from declared/local bounds. The rule remains provider/domain neutral.

### Workspace reconciliation after context loss

Continuation/compaction now explicitly uses `WORKSPACE AWARENESS != WORKSPACE HYDRATION`: cheaply rediscover current repository/workspace state and existing routing/working aids first, then JIT-read only material sources. Derived aids remain cache, current authority/runtime state wins, suitable aids are reused, and no parallel helper index/manifest is created merely for discoverability.

### Tool and ownership boundary

No MCP server, computer-use stack, debugging tool, workspace database, sixth Skill, or new architecture owner is introduced. The observed failures are attention/evidence-consumption/context-continuity problems that remain solvable by concise Skill guidance plus host-native read/search/runtime capabilities.

## v0.11.0

### Responsibility-relative ownership and role resolution

Classification: `EXTEND_EXISTING_CAPABILITY` in canonical `core-first-extension-architecture`; no new Skill/owner.

Repeated ownership-audit tests exposed a semantic interpretation gap: an agent could decompose responsibilities yet still infer owners from class boundaries/names, treat current code placement as canonical ownership, centralize data while leaving behavior duplicated, or equate capability identity with implementation count.

v0.11.0 hardens the existing architecture owner with these invariants:
- name the responsibility before declaring an owner;
- distinguish canonical owner, current carrier/effective decision path, implementation anchor, capability/module/provider, consumer, data/profile, migration target, and unresolved gap;
- current code location/size/name is evidence of placement, not proof of canonical ownership;
- parallel owners mean independent active authority over the same responsibility, not multiple controlled providers behind one capability;
- unresolved ownership stays unresolved until evidence supports the smallest semantic path;
- centralized data does not centralize duplicated semantic behavior;
- capability identity is semantic, not a function of implementation count;
- architectural role is determined by semantics/authority/runtime flow, not symbol naming conventions.

The detailed recovery examples live in the existing `EXTENSION_ARCHITECTURE_METHOD.md` reference. The five-Skill model, orchestration JIT structure, OPV, verifier, independent review, and Skills-only tooling boundary remain unchanged.
