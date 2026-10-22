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
3. Keep governing choices settled: domain meaning, shared ownership, public
   boundaries, effects, compatibility, observable lifetime guarantees and cost
   commitments. `architecture-planning` owns these choices; its handoff supplies
   constraints and tradeoffs. Choose and revise private representations,
   synchronization and resource scopes here within those constraints; an absent
   plan is not an unresolved design. If construction would change a governing
   choice, use `architecture-planning` when available and settle it within the task's
   authority; otherwise expose the exact missing decision. Keep only affected code
   off an unsettled boundary. Reopen it if the diff contradicts its premises.

Workflow selection grants no additional authority for host mutation, external
integration, destructive operations, workflow execution, or publication.
A review- or verification-only request does not authorize implementation edits;
report findings unless the user also asked for fixes.
For authorized implementation, proceed within the requested scope without
inventing per-stage approval gates; pause for a material user-owned choice,
missing authority, or blocker.

Implement ordinary settled work directly. Prefer investigation that could change
the requested result or remove consequential coordination, relative to risk and
effort. Use actual dependency behavior to choose the construction and next
investment; adequate code can stay, without a cleanup quota or unrelated refactor.

Derive code names, comments, tests and observable output from domain meaning and
accepted project contracts. Use plans for constraints and execution order; their
stage labels and task identifiers remain coordination context unless the target
contract gives them meaning. Preserve existing compatibility names.

Before authorized doc edits, identify reader, purpose, exposure and destination.
Keep plans and scratch in task records; include context in durable docs only when
it serves that reader. Repository paths and ignore rules do not establish access
control or publication authority.

## Route by settled change

Select one primary route before loading specialized guidance:

| Condition | Route | Allowed result |
|---|---|---|
| user requests findings without edits | **Review** | evidence-backed report; no implementation mutation |
| contract is settled and code must change | **Implementation** | scoped source change and focused evidence |
| behavior is preserved while owners or topology change | **Refactor/migration** | compatible diff plus migration evidence |
| an existing diff or result needs checking | **Verification** | conformance and delivery findings; no unrequested redesign |

Routes can compose implementation followed by verification. An unresolved design,
stale governing context, or missing authority stops only the affected route; it
does not authorize an implicit architecture decision or broader tool use.

## Development loop

Enter at the earliest phase required by the request and available evidence. When
inheriting an existing diff, do not manufacture missing test-first or pre-change
history.

Implement the requested capability, using
[implementation normal form](references/implementation-normal-form.md) when flow,
ownership, failures, effects, resources, abstraction, compatibility, cost or topology
materially change. Its worked relationships guide construction; a routine file
edit alone does not trigger it. Use native mutation where one visible owner makes
it clear; linear/affine machinery fits genuinely single-use resources.

Use [feedback methods](references/feedback-methods.md) for construction uncertainty
and the next investment. Establish a baseline only when needed to interpret the
change. For an accepted numerical contract also read
[mathematics and numerics](references/mathematics-and-numerics.md); implementation
does not choose its domain, tolerance, solver policy or accuracy guarantee.

Load [simplification](references/simplification.md) for behavior-preserving
reduction, [structural migration](references/structural-migration.md) for module or
API moves, and [analytical migration](references/analytical-migration.md) for
dataframe/ML or reactive-notebook migration only when that work is in scope.

For user-facing interface changes, use
[interface content and layout](references/interface-content-and-layout.md) to
carry the accepted task flow, vocabulary and visual system into labels, grouping
and responsive reading order.

Inspect the actual diff using [conformance review](references/conformance-review.md)
within this feedback, then make the single completion decision through
[delivery verification](references/delivery-verification.md), reusing applicable
completed checks. These references add no separate review cycles. A governing
contradiction returns only its affected decision to Admission.

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

Completion requires the actual scope, no conformance blocker, and applicable
evidence for the changed claims under delivery verification. Report observed
results and remaining limits. Package publication is separately authorized.
