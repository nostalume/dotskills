---
name: architecture-planning
description: Resolve material, unsettled software architecture or refactor decisions from revision-scoped evidence and prepare the smallest dependency-ordered local plan before coding. Use when domain meaning, ownership, boundaries, compatibility, lifecycle, topology, or cost can still change the design; leave settled local implementation to software-development.
---

# Architecture Planning

Own decision settlement and implementation handoff, not production code. Use one
visible control flow:

```text
goal and authority
  -> current evidence and material decision scope
  -> active decision categories and references
  -> settle, bound exploration, defer, or block
  -> optional smallest sufficient local plan
  -> plan audit when materialized
  -> implementation handoff or stop
```

## Admit the operation and its authority

Resolve the project root and applicable instructions, then distinguish:

- **review only:** inspect and report; do not write a plan or source;
- **decision:** inspect and settle or bound the decision; materialize only when a
  durable consumer needs it;
- **planning:** create or revise the smallest local handoff after decisions close;
- **implementation:** route settled work to `software-development`.

Framing an unresolved goal authorizes inspection and bounded reasoning, not a
target architecture. A plan does not authorize implementation, documentation,
workflow changes, publication, or external effects.

Current source is authoritative evidence of current implementation at the
inspected revision. User intent, accepted contracts, project policy, and governing
specifications retain their own normative scopes. Preserve contradictions: they
may reveal implementation drift, stale documentation, or an invalid premise rather
than allowing one source class to overrule all others.

## Route by decision state

Select the smallest route that can change the user's decision:

| Condition | Route | Allowed result |
|---|---|---|
| evidence or ownership is unclear | **Review** | findings and bounded unknowns; no plan or source edits |
| a material design choice is open | **Decision** | settled, bounded, deferred, or blocked decision |
| decisions are settled and a durable handoff is needed | **Planning** | smallest audited local plan |
| implementation is requested for settled decisions | **Handoff** | authorized transfer to `software-development` |

Routes may compose in that order, but no later route is implied by an earlier
one. Stale project context is reported and revalidated at the affected boundary;
it is not silently repaired during an unrelated decision.

## Inspect to decision sensitivity

Inspect the dirty state, revision, instructions, manifests, public entry points,
callers, contracts, tests, authoritative documentation, and relevant
implementation. Where style or topology matters, inspect enforced tooling and
matching maintained analogues; one analogue is evidence, not a convention.

Trace one real path as initial evidence:

```text
input -> admission -> behavior -> effect -> persistence or output
```

Extend it only across success, failure/recovery, compatibility, lifecycle,
concurrency, scale, or caller edges that can change the decision. Stop when an edge
is observably irrelevant. Label observations, entailed inferences, user policy,
proposals, contradictions, and unknowns; search results locate evidence but do not
become its authority.

Before naming or replacing an architecture, boundary, system, or API—or declaring
production work ready—use [decision settlement](references/decision-settlement.md).
It determines what evidence and behavior must be settled, compares material
alternatives, and governs decision status and replacement. Ask the user only for a
material intent, policy, or tradeoff they own; keep other unresolved choices
exploratory, deferred, or blocked at the smallest affected boundary.

## Select decision categories

Select only categories whose decisions could change the architecture. Each
decision has one primary owner; do not read every reference by default.

- **Behavior and promises:** domain meaning, invariants, and externally observable
  behavior ([domain and invariants](references/domain-and-invariants.md),
  [observable contract](references/contracts-and-compatibility.md#define-target-behavior)).
- **Ownership and authority:** authoritative facts, policy, state transitions, and
  effects ([authority and effects](references/authority-and-effects.md)).
- **Boundaries and composition:** values crossing boundaries and conceptual or
  physical ownership/dependency structure
  ([representation and flow](references/representation-and-flow.md),
  [module topology](references/module-topology.md) when topology is material).
- **Runtime and lifecycle:** execution, failure, bounded work, resources, and
  recovery ([resources and recovery](references/resources-and-recovery.md)).
- **Operating envelope:** workload and cost constraints that can alter the choice
  ([cost and scale](references/cost-and-scale.md)); consider deployment, trust,
  security, or observability only when they can change this design.
- **Evolution and coexistence:** migration, compatibility, cutover, and retirement
  when live consumers or an incumbent system matter
  ([compatibility and migration](references/contracts-and-compatibility.md#evolve-with-live-consumers)).

Mathematical or numerical claims are not a separate architecture category. Treat
them as behavior, representation, or operating constraints when they can change
the decision; keep unsupported claims unknown rather than supplying conventional
algorithms, tolerances, or validity assumptions. A proposal that materially
changes conceptual/physical owners, dependencies, visibility, facades, or
re-exports activates module topology. An obvious implementation-local relay
cleanup remains `software-development` work.

The operating-envelope reference covers workload and cost, not security or
deployment policy. When those constraints can change a decision, inspect their
authoritative project or environment source; do not infer policy from this skill.

Use decision settlement across active categories; do not copy its closure or
comparison protocol into their references. Use plan audit only after creating or
materially revising a plan.

## Materialize only for a consumer

Use an existing ignored project-root `.agents/plan/` only when a durable handoff,
continuity, review, or implementation consumer needs a plan; otherwise keep the
answer transient. Use one canonical plan file per goal, following project format
(Markdown if none exists); it owns goal, decisions, status, and dependencies. Keep
stages as headings and tasks as checklists by default. A stage is a distinct
outcome with a consumer that merits separate review or handoff; a task is an
executable dependency unit, not a phase or individual command. Group steps with
the same owner, dependencies, and completion evidence. Split a unit into another
file only when a downstream consumer needs a standalone artifact or separate
lifecycle; link it from the canonical plan without copying governing decisions.
These boundaries do not imply branches, commits, or approval gates. Git ignore
rules affect untracked-file handling, not confidentiality or
publication: keep plans separate from reader docs and include only context needed
to decide or execute the plan. Do not change tracked ignore policy merely to store
a plan. If no suitable local location exists, answer in chat or request authority;
report tracked plans and never untrack them without approval.

Resume a matching readable plan only when goal, authority, revision, and status are
unambiguous. Use functional domain names. Record only a candidate delivery
boundary when the outcome would remain useful, falsifiable, and revertible if
later work stopped; project policy,
the eventual actual diff, and implementation evidence decide the final review
shape.

Record only applicable goal/scope, invariants, premises and status, resolution
or exact unknown, owner and flow changes, compatibility boundary, dependent
outcomes, first executable work, falsification/completion evidence, and rollback
or reopen conditions. A task adds local constraints only where they vary; it does
not silently choose architecture. Classify documentation, automation, release,
and system-effect impact once, without treating classification as authority.

## Audit and hand off

After creating or materially revising a plan, read [plan audit](references/plan-audit.md)
and falsify the artifact against fresh repository evidence. Correct findings at
their smallest owner. Stop revising when no blocker remains and name the first
ready task. Return the report or plan at the requested boundary; hand off to
`software-development` only when implementation is authorized.

Hand `software-development` settled conceptual constraints, accepted tradeoffs,
and falsification obligations—not mandatory pseudocode or a predicted file
manifest. Planning evidence cannot certify the eventual diff. Reopen only the
smallest decision invalidated by new source, contract, user policy,
implementation, integration, or cost evidence, and expose the resulting delta.

Choose interaction cadence separately from request authority. In a user-led
examination loop, report evidence, decisions, alternatives, and any user-owned
choice at requested checkpoints; wait for input before proceeding past one. After
input, revise only the affected decision or plan section. In an explicitly
authorized end-to-end loop, proceed without per-stage approval and pause only for a
material user-owned choice, missing authority, or blocker. Hand off settled
implementation and re-enter planning only when new evidence invalidates a premise.
Stage and task boundaries grant no authority; follow the user's explicit scope.

## Hard gates

- Review-only work and transient decisions leave no workspace mutation.
- Plans use a location suitable for their intended audience; Git ignore is not
  confidentiality. Tracked proposals never pose as implemented facts.
- Every named current path and owner exists at the inspected revision.
- No material unknown is hidden by a system/API name, detailed task, or user
  enthusiasm, and no production task is ready while its governing decision or
  audit has a blocker.
- Surface style requires project evidence. A semantic topology decision instead
  requires an effect on ownership, dependency, visibility, compatibility,
  lifecycle, or evidenced change locality.
- No stage or task hides an input, authority, effect, dependency, compatibility
  obligation, or material tradeoff.
