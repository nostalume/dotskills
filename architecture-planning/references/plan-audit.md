# Plan Audit

Use this review only after creating or materially revising an architecture plan.
It tests whether a new implementer can act from the artifact and current repository
without hidden conversation. It does not re-decide settled owners or certify code
that has not been written.

## Establish the current baseline

Reinspect revision and dirty state, applicable instructions, named current paths,
public contracts, relevant tests/source, enforced tooling, and only matching
maintained analogues. Audit what the plan says, not what its author intended.

For each material decision, invoke [decision settlement](decision-settlement.md) and
only the category reference that owns the disputed claim. The audit supplies
adversarial falsification; it does not repeat settlement, topology, domain,
authority, lifecycle, compatibility, or cost guidance.

## Falsify the artifact

Check that:

- current observations, entailed consequences, user policy, proposals,
  contradictions, and unknowns retain their authority and revision;
- each decision has one owner, a clear status, and no hidden tradeoff;
- a goal has one canonical plan by default; stages are distinct outcomes with
  consumers, and tasks are executable dependency units. Keep them in one file
  unless a standalone handoff or separate lifecycle needs another file; dependencies
  are acyclic, and tasks inherit rather than restate governing decisions;
- interaction mode matches authority: review-only leaves no artifact; planning
  returns only the requested plan or a clear blocker/report and stops; end-to-end
  implementation proceeds only when authorized. No plan/stage/task creates
  authority;
- proposed delivery units are not inferred from stage count: each standalone
  candidate has one reviewer-verifiable claim, remains useful and revertible if
  later work stops, and has no hidden predecessor; characterization-only evidence
  travels with its owning change unless it protects an independently durable
  contract;
- every applicable input, output, effect, resource/lifecycle, failure/recovery,
  caller, compatibility surface, cutover, and removal gate needed for execution is
  available from the plan or its named owner;
- minimum behavior and completion are observable without prescribing speculative
  abstractions, pseudocode, helpers, or file layout;
- feedback matches the claim—behavior, characterization/mutation, proof, benchmark,
  static tooling, artifact inspection, or bounded exploration—and named checks are
  runnable in the stated environment;
- topology and style constraints have semantic or project evidence rather than
  file-size, prefix, fashion, or personal preference; and
- literal implementation would add no parallel authority, relay-only layer,
  repeated interpretation, speculative compatibility, hidden effect, or unrelated
  cleanup.

## Run the smallest adversarial mutations

Ask which relevant single change could expose ambiguity: another implementer's
interpretation, a failure or cancellation edge, a new caller, an invalidated
premise, a changed workload or user policy, missing lifecycle/compatibility detail,
a nondominant alternative, or removal of a plan/stage/task artifact. Confirm only
the dependent decision's status, scope, or evidence changes.

In particular, contrast same-goal stages that share a consumer (one plan file), a
stage requiring standalone handoff (split only if its consumer needs a separate
artifact), several commands sharing an owner/check (one task), review-only versus
planning (no artifact versus requested plan), and planning versus explicitly
authorized end-to-end work (stop versus handoff). These cases must not vary merely
because the request says “stage,” “task,” or “loop.”

Review-only work leaves no artifact. A plan needs suitable local placement and
must stay separate from reader-facing docs; Git ignore is not confidentiality or
publication control. Do not change ignore policy merely to store it. Planning
detail cannot stand in for actual-diff conformance, which remains with
`software-development`. Parallel local branches alone do not justify a public
dependent-review chain; repository policy, hosting, contributor authority, and the
final diff govern that choice.

## Reconcile findings

Record each finding at its smallest owner with scope, evidence, violated
constraint, correction, and severity:

- **Blocker:** contradiction, missing/duplicated authority, hidden input/effect/
  dependency, unapproved tradeoff, unverifiable outcome, broken compatibility, or
  enforced-policy violation.
- **Warning:** evidenced feasibility, maintainability, or consistency risk that
  does not make execution ambiguous or incorrect.
- **Note:** optional preference or separately scoped improvement.

Correct the smallest owner and re-audit only affected dependents. A production task
is ready when no blocker remains, warnings have dispositions, governing decisions
are settled, predecessors landed, and remaining unknowns cannot change it. A
bounded exploration instead needs settled authority, bounds, evidence,
termination, and discard/reframe behavior.

For high-risk work, use fresh-context independent review only when available and
authorized; provide raw evidence rather than the intended conclusion. Report when
that check was unavailable—self-review cannot establish independent reliability.
