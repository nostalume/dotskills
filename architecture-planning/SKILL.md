---
name: architecture-planning
description: Resolve material, unsettled software architecture or refactor decisions from revision-scoped evidence and prepare the smallest dependency-ordered private plan before coding. Use when domain meaning, ownership, boundaries, compatibility, lifecycle, topology, or cost can still change the design; leave settled local implementation to software-development.
---

# Architecture Planning

Own decision settlement and implementation handoff, not production code. Use one
visible control flow:

```text
goal and authority
  -> current evidence and material decision cone
  -> selected owner lenses
  -> settle, bound exploration, defer, or block
  -> optional smallest sufficient private plan
  -> plan audit when materialized
  -> implementation handoff or stop
```

## Admit the operation and its authority

Resolve the project root and applicable instructions, then distinguish:

- **review only:** inspect and report; do not write a plan or source;
- **decision:** inspect and settle or bound the decision; materialize only when a
  durable consumer needs it;
- **planning:** create or revise the smallest private handoff after decisions close;
- **implementation:** route settled work to `software-development`.

Framing an unresolved goal authorizes inspection and bounded reasoning, not a
target architecture. A plan does not authorize implementation, documentation,
workflow changes, publication, or external effects.

Current source is authoritative evidence of current implementation at the
inspected revision. User intent, accepted contracts, project policy, and governing
specifications retain their own normative scopes. Preserve contradictions: they
may reveal implementation drift, stale documentation, or an invalid premise rather
than allowing one source class to overrule all others.

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
production work ready—read [decision readiness](references/decision-readiness.md).
It solely owns decision-cone closure, behavioral specificity, maturity,
comparison, stability, and replacement. Ask the user only for a material intent,
policy, or tradeoff they own; keep other unresolved choices exploratory, deferred,
or blocked at the smallest affected boundary.

## Select decision owners

Read only the lenses whose decisions are active:

- vocabulary, identity, invariants, and transitions:
  [domain and invariants](references/domain-and-invariants.md);
- truth, policy, mutation, and effect authority:
  [authority and effects](references/authority-and-effects.md);
- values crossing boundaries and their admission or transformation:
  [representation and flow](references/representation-and-flow.md);
- conceptual owners projected into helpers, modules, visibility, and dependencies:
  [module topology](references/module-topology.md);
- externally observable behavior and migration promises:
  [contracts and compatibility](references/contracts-and-compatibility.md);
- applicable resource lifetime, bounded work, cleanup, and recovery:
  [resources and recovery](references/resources-and-recovery.md);
- workload and computational or operational budget:
  [cost and scale](references/cost-and-scale.md); and
- accepted mathematical laws or numerical constraints shaping software:
  [mathematics and numerics](references/mathematics-and-numerics.md).

Give each decision one primary lens and import named constraints instead of
copying another protocol. Select module topology whenever a proposal materially
changes a conceptual or physical owner, dependency, visibility, facade, or
re-export. An obvious implementation-local relay cleanup remains
`software-development` work.

## Materialize only for a consumer

Prefer an already ignored project-root `.agents/plan/` workspace when a durable
handoff, multi-turn continuity, independent stage review, or implementation
consumer needs a plan. A review answer or small self-contained decision can remain
transient. Do not edit tracked ignore policy merely to store private reasoning; if
no safe ignored location exists, keep the result in the response or request the
needed project authority. Report an already tracked private workspace and never
untrack it without approval.

Resume a matching readable plan only when goal, authority, revision, and status are
unambiguous. Use functional domain names. A stage exists only for an independently
reviewable or separately handed-off outcome; tasks are dependency-ordered
executable units, not ceremonial phases.

Record only applicable goal/scope, invariants, premises and maturity, resolution
or exact unknown, owner and flow changes, compatibility boundary, dependent
outcomes, first executable work, falsification/completion evidence, and rollback
or reopen conditions. A task adds local constraints only where they vary; it does
not silently choose architecture. Classify documentation, automation, release,
and system-effect impact once, without treating classification as authority.

## Audit and hand off

After creating or materially revising a plan, read [plan audit](references/plan-audit.md)
and falsify the artifact against fresh repository evidence. Correct findings at
their smallest owner. Stop rewriting when no blocker remains, name the first ready
task, and wait for implementation authority.

Hand `software-development` settled conceptual constraints, accepted tradeoffs,
and falsification obligations—not mandatory pseudocode or a predicted file
manifest. Planning evidence cannot certify the eventual diff. Reopen only the
smallest decision invalidated by new source, contract, user policy,
implementation, integration, or cost evidence, and expose the resulting delta.

## Hard gates

- Review-only work and transient decisions leave no workspace mutation.
- Private artifacts use an already safe location; tracked proposals never pose as
  implemented facts.
- Every named current path and owner exists at the inspected revision.
- No material unknown is hidden by a system/API name, detailed task, or user
  enthusiasm, and no production task is ready while its governing decision or
  audit has a blocker.
- Surface style requires project evidence. A semantic topology decision instead
  requires an effect on ownership, dependency, visibility, compatibility,
  lifecycle, or evidenced change locality.
- No stage or task hides an input, authority, effect, dependency, compatibility
  obligation, or material tradeoff.
