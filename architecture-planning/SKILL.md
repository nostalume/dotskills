---
name: architecture-planning
description: Discover worthwhile architecture or refactor problems, resolve material design decisions from revision-scoped evidence, and prepare the smallest local plan when needed. Use for scoped architecture improvement or when domain meaning, ownership, boundaries, compatibility, lifecycle, topology, or cost can still change the design; leave settled local implementation to software-development.
---

# Architecture Planning

Own unsettled design decisions and implementation handoff, not production code.
Work from revision-scoped behavior and constraints to a selected or bounded
decision; materialize and audit a local plan only for a durable consumer.

## Admit the operation and its authority

Resolve project root and instructions, then select the smallest applicable row:

| Operation / condition | Result and authority |
| --- | --- |
| Review only, including unclear evidence/ownership | Inspect and report findings/unknowns; no plan, source or other workspace mutation |
| Decision: a material design choice is open | Inspect; settle, bound exploration, defer or block; materialize only for a durable consumer within granted authority |
| Planning: decisions are settled and a durable handoff is needed | Create/revise the smallest audited local plan, then return at the requested boundary |
| Implementation requested for settled decisions | Authorized handoff to `software-development`; not architecture implementation |

An unresolved goal authorizes inspection/reasoning, not a target architecture.
Rows may compose in order, but one grants no later operation. A plan grants no
implementation, documentation, workflow, publication or external-effect authority.
Transient decisions leave the workspace unchanged. Revalidate stale context at
the affected boundary without unrelated repair.

At user-led checkpoints, report evidence, decisions, alternatives and user-owned
choices, then wait and revise affected decisions. In authorized end-to-end work,
proceed until a material user choice, missing authority or blocker; stages/tasks
add no approval gates or authority.

## Derive options from current behavior

Inspect revision/dirty state, instructions, manifests, entry points, callers,
contracts, tests, authoritative docs and relevant implementation. For style or
topology inspect enforced tooling and matching maintained analogues; one analogue
is evidence, not a convention. Every named current path/owner must exist at that
revision; distinguish it from a proposed owner.

For open improvement, inspect real behavior, representative changes, recurring
failures and maintenance friction. Repeated interpretation, coordinated edits,
scattered ownership and compensation are hypotheses, not automatic refactors.
Choose the burden worth removing against evidence, migration risk and effort;
trace its responsible relation. Cosmetic layout changes do not resolve that
burden. Leave adequate structure alone; this preference adds no audits, quotas
or broader cleanup authority.

1. Trace a real caller through admission, behavior, effects and persistence/output.
   Identify the values/identities crossing each edge, the owner of each transition,
   and who retains resources on success, failure or cancellation. Extend only over
   recovery, compatibility, lifecycle, concurrency, scale or caller edges that can
   change the choice; stop at observably irrelevant edges.
2. Extract constraints from that path: which invariant, caller promise, authority,
   resource lifetime or workload budget must survive? Tie each material constraint
   to its source and the edge it governs. Current source establishes implementation
   at the inspected revision; user intent, contracts, policy and specifications
   retain their own scopes. Preserve contradictions as possible drift or invalid
   premises, not as permission for one source class to overrule all others.
3. Before naming/replacing an architecture, system, boundary or API, or declaring
   production ready, read [decision settlement](references/decision-settlement.md). It owns premise
   classification, behavioral specificity, comparison, status and reopen rules.
   Construct alternatives by changing the owner/transition responsible for the
   mismatch, preserving other obligations. Include the incumbent; compare viable
   choices on distinguishing constraints, not names or speculative module layouts.
4. Explain which constraint selects the option, what falsifies it and which changed
   premise would select another. The [worked comparison](references/decision-settlement.md#worked-comparison-cancellation-and-resource-ownership)
   derives a resource boundary from a lifetime mismatch.

Keep observations, entailed inferences, user policy, proposals, contradictions and
unknowns distinct; search results locate evidence, not authority. Inspect project
facts rather than asking users to reconstruct them. Ask only for material intent,
policy or tradeoffs they own; otherwise bound exploration, defer or block only the
decision an unknown can change.

## Select decision categories

Load only active categories, each with one primary owner:

- **Behavior/promises:** domain meaning and invariants
  ([domain](references/domain-and-invariants.md)); observable behavior
  ([contract](references/contracts-and-compatibility.md#define-target-behavior)).
- **Ownership/authority:** facts, policy, state transitions and effects
  ([authority](references/authority-and-effects.md)).
- **Boundaries/composition:** crossing values
  ([representation](references/representation-and-flow.md)); material conceptual/
  physical owners, dependencies, visibility, facades or re-exports
  ([topology](references/module-topology.md)). Obvious local relay cleanup remains
  `software-development` work.
- **Runtime/lifecycle:** failures, bounded work, resources and recovery
  ([resources](references/resources-and-recovery.md)).
- **Operating envelope:** decision-sensitive workload/cost
  ([cost](references/cost-and-scale.md)); security, trust, deployment and
  observability policy come from authoritative project/environment sources, not
  that cost reference.
- **Evolution/coexistence:** live consumers, compatibility, migration, cutover and
  retirement ([compatibility](references/contracts-and-compatibility.md#evolve-with-live-consumers)).

Mathematical/numerical claims enter the applicable behavior, representation or
operating constraint; keep unsupported algorithms, tolerances and validity
assumptions unknown. Categories supply constraints; settlement owns closure and
comparison. Plan audit starts only after a plan is created or materially revised.

## Materialize only for a consumer

For durable handoff, continuity, review or implementation, use an existing ignored
project-root `.agents/plan/`; otherwise answer transiently. Keep one canonical
plan per goal in project format (Markdown by default), owning goal, decisions,
status and dependencies. Stages are distinct outcomes with review/handoff
consumers; tasks are executable dependency units, not phases or single commands.
Group steps sharing owner, dependencies and completion evidence; use headings/
checklists by default. Split only for a standalone consumer or separate lifecycle,
linking back without duplicating governing decisions. These units imply no branch,
commit or approval gate.

Git ignore controls untracked files, not confidentiality/publication. Keep plans
separate from reader docs and include only decision/execution context. Do not
change tracked ignore policy to store a plan. Without suitable placement, answer
in chat or request authority; report tracked plans and never untrack without
approval. Tracked proposals remain proposals, not implemented facts.

Resume a readable matching plan only when goal, authority, revision and status are
unambiguous. Use domain names. A candidate delivery boundary must remain useful,
falsifiable and revertible if later work stops; project policy, actual diff and
implementation evidence determine final review shape.

Record applicable goal/scope, invariants, premises/status, resolution/exact unknown,
owner/flow changes, compatibility, dependent outcomes, first executable work,
falsification/completion evidence and rollback/reopen conditions. Tasks add only
varying local constraints, never an implicit architecture. Classify documentation,
automation, release and system effects once; classification grants no authority.

## Audit and hand off

After plan creation/material revision, [audit](references/plan-audit.md) against
fresh repository evidence. Correct findings at their smallest owner within current
authority; stop when no blocker remains and name the first ready task. Unknowns,
input/effect/dependency/compatibility obligations and material tradeoffs must remain
visible; enthusiasm or detailed tasks cannot settle them.

Return the requested report/plan; hand off only when implementation is authorized.
Give `software-development` required behavior/policy, the selected mechanism and
observed validation coverage as distinct inputs, with their sources and scope.
Carry settled constraints, tradeoffs and falsifiers; a validated example informs
coverage, while a runtime, interface or explicit deployment policy can restrict
admission. Keep mechanism choices replaceable within those constraints, leaving
syntax and file choices to implementation. Distinguish coordination
labels from domain or interface names: stage headings and task IDs locate plan
work; they become implementation vocabulary only when an accepted target contract
requires it. For simplification, carry the coordination/interpretation to remove
and a representative change that should become easier. Planning cannot certify
the eventual diff. New source, contract, user policy, implementation, integration
or cost evidence reopens only the smallest invalidated decision and its dependents,
following settlement's replacement rules; expose the delta.
