---
name: software-development
description: Implement, refactor, review, or verify a settled software change with claim-appropriate feedback and final checks. Stop on material unresolved design or publication.
---

# Software Development

Own work on a settled software change from its contract to an evidence-backed final
diff, within the authority granted by the request. Domain meaning governs
implementation; tests and tools supply feedback and falsification, not product
vocabulary or architecture.

Reasoning is upstream authority and evidence is downstream falsification; current
source and observed behavior may contradict either and reopen the smallest
governing decision.

## Admission

1. Inspect current instructions, revision, and dirty state. Follow the changed
   contract through only the manifests, implementation, callers, tests, docs, and
   project-native checks that can affect the requested result; widen inspection
   when evidence shows another boundary matters.
2. Freeze only the requested outcome, authority, behavior, owners, compatibility,
   effects, resource/cost constraints, and completion evidence that can affect this
   change. Do not turn irrelevant dimensions into an intake checklist.
3. Stop before implementation when domain meaning, ownership, semantic module
   topology, public boundaries, effects, compatibility, lifecycle, or material cost
   can still change the design. Report the unsettled decision, live alternatives,
   constraints, and evidence needed to settle it; do not choose a design implicitly.
   For an obvious local edit with a settled contract, keep this admission record
   compact.

Workflow selection grants no additional authority for host mutation, external
integration, destructive operations, workflow execution, or publication.
A review- or verification-only request does not authorize implementation edits;
report findings unless the user also asked for fixes.
For authorized implementation, proceed within the requested scope without
inventing per-stage approval gates; pause for a material user-owned choice,
missing authority, or blocker.

Keep plans and scratch separate from durable docs. Before authorized doc edits,
identify reader, purpose, exposure, and destination; include only useful detail,
never copy task plans into public-facing docs. Repository paths and ignore rules
do not establish access control or publication authority.

## Development loop

Enter at the earliest phase required by the request and available evidence. When
inheriting an existing diff, do not manufacture missing test-first or pre-change
history.

1. Establish a fresh baseline at the contract's stable boundary when existing
   behavior or environment state must be characterized to interpret the change;
   otherwise do not add a pre-change run solely as ceremony.
2. Read [feedback methods](references/feedback-methods.md) and select evidence that
   can falsify the actual claim; do not impose TDD where no stable behavioral seam
   exists.
   For an accepted mathematical or numerical contract, also read
   [mathematics and numerics](references/mathematics-and-numerics.md). Do not settle
   its domain, tolerance, solver policy, or accuracy guarantee during
   implementation.
3. Implement the smallest coherent domain capability. For transformations, use
   this as a reasoning model, not a required pipeline shape: admit input once,
   select an explicit variant, transform through domain-bearing values, invoke
   named effect/resource owners, observe the promised result, then return or
   terminally delegate. Read
   [implementation normal form](references/implementation-normal-form.md) when the
   change materially affects semantic flow, ownership, effects, failures,
   resources, abstraction, compatibility, cost, or conceptual/physical topology;
   a file move or routine edit alone is not a trigger.
4. Apply linear or affine machinery only to genuinely single-use capabilities or
   resources. Local mutation is acceptable inside one visible owner when it
   preserves the external value contract and improves clarity or measured cost.
5. Read conditional change guides when their work is in scope: use
   [simplification](references/simplification.md) for behavior-preserving
   reduction; [structural migration](references/structural-migration.md) for
   module/package/API-topology migration; and
   [analytical migration](references/analytical-migration.md) for dataframe/ML
   pipeline or imperative-numerical-script to reactive-notebook migration. These
   guides do not authorize a change to settled behavior or policy.
6. Inspect the final implementation with
   [conformance review](references/conformance-review.md). Fix local defects in the
   development loop; stop and report when the diff contradicts an invariant that
   depends on an unsettled design decision.
7. After the last relevant edit, close the change with
   [delivery verification](references/delivery-verification.md).

The implementation normal form preserves settled architecture; it does not supply
missing architecture. An error boundary must own bounded recovery, contract
translation, compensation, cleanup, or necessary consumer context. Otherwise
preserve the original failure, cancellation, and resource handoff through direct
propagation or terminal delegation. If making the code locally coherent would
change domain meaning, authority, a public contract, lifecycle, compatibility or a
material cost decision, stop and report that smallest unresolved decision instead
of redesigning it inside the diff.

Audit every new conceptual or physical boundary even when the task describes it as
organization or cleanup. Remove an obvious local relay without demanding a plan;
when the owner, dependency direction, visibility, compatibility or change locality
can materially vary, use an existing accepted project decision or stop and report
what must be settled before implementation.

Do not use this code workflow to install or register tools, change host
configuration, reorganize user files, or migrate backups. If one of those effects
is necessary, stop before performing it and report the exact target, required
authority, and evidence needed. Ordinary source and test-file edits remain within
this skill.

Documentation-only and workflow-authoring tasks are outside this code workflow.
For code changes, record documentation, automation, and release impact; modify
those artifacts only when authorized, consistent with project behavior, and
validate each changed artifact directly.

## Hard gate and result

Do not call the change complete unless the final scope is identified, the selected
feedback actually exercised each changed claim, conformance has no blocker, and
fresh focused and project-canonical checks support the reported result. Report
exact observed outcomes, skipped or failed checks, residual risks, and any changed
documentation, automation, or release impact. Package publication remains a
separately authorized external operation and is not performed by this code workflow.
