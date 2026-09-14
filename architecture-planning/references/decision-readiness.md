# Decision Readiness and Stability

Use this protocol before turning an architecture, system, boundary, or API idea
into a resolution, ready task, or implementation handoff. It solely owns closure,
behavioral specificity, comparison, maturity, stability, and replacement. Domain,
effects, representation, topology, contracts, resources, cost, and mathematics
remain with their selected lenses.

This is a reasoning protocol, not a required scorecard, decision log, schema, or
claim that the whole repository can be understood exhaustively.

## Close the material decision cone

Start from the operation being decided and follow each boundary whose state could
change the choice. One input-to-output path is initial evidence; add materially
distinct callers, success/failure and recovery, compatibility, lifecycle,
concurrency, workload, authority, or effect edges only while they remain decision-
sensitive. Boundary-sufficient comprehension stops at observably irrelevant edges.

Classify a material premise as:

- **observed:** supported by revision-scoped project or authoritative external
  evidence;
- **entailed:** derived from named premises with a falsifier;
- **user policy:** an explicit user-owned choice with stated scope;
- **proposal:** a possible design not yet selected; or
- **unknown/contradiction:** missing or incompatible information plus the owner or
  observation that could resolve it.

An unknown blocks only decisions it can change: owner, public behavior, lifecycle,
compatibility, topology, workload acceptance, stage order, or required evidence.
Inspect project-owned facts rather than asking the user to reconstruct them. When
neither inspection nor user-owned policy can close an unknown, keep the affected
work exploratory or blocked instead of supplying a conventional architecture.

## Require behavioral specificity without premature syntax

A proposed system or API may leave private representation and exact syntax open,
but it must close every applicable operation's caller/use conditions; admitted
inputs and outputs; identity, ordering, invariants, and state owner; errors,
cancellation, timeout, partial results, retry/idempotency; authorization and
effects; resource lifetime, cleanup, and recovery; promised concurrency behavior;
compatibility/migration/removal; limiting workload and budget; and falsifying
observations.

Do not use a method signature, service, manager, facade, store, queue, protocol, or
detailed module sketch to conceal missing semantics. Conversely, do not decide
implementation details that cannot affect an architectural contract.

## Compare only material alternatives

Freeze hard constraints, contextual objectives, and acceptance evidence first.
Include the incumbent when changing an existing system, then add only materially
distinct viable alternatives. Reject hard-constraint violations without scoring.

Compare the dimensions that can change selection: correctness and failure;
authority; ergonomics for each affected actor and operation; conceptual owners,
states, translations, and dependencies; operational deployment/observation/
recovery burden; efficiency against a named workload and budget; compatibility and
migration cost; change locality, reversibility, and option value; and evidence
strength or blind spots. “Simple,” “clean,” “ergonomic,” “scalable,” and
“efficient” are incomplete without the affected structure, actor, workload, or
observation. Avoid weighted totals that manufacture commensurability.

Select an evidence-dominant candidate when one exists. Otherwise expose the one
material tradeoff to its owner rather than oscillating among equally incomplete
proposals.

## Assign the smallest honest maturity

- **Exploratory:** a material premise is unknown; only bounded inspection or an
  experiment with explicit authority, limits, termination, and discard/reframe
  outcome may be ready.
- **Candidate:** a projection is specific and falsifiable, but selection or one
  material premise remains open.
- **Settled:** the material cone and hard constraints are closed, comparison is
  complete, and evidence or an owner-approved tradeoff selects the resolution.
- **Invalidated:** new evidence contradicts a relied-upon premise; dependent
  decisions and ready work reopen.

Maturity belongs to the smallest decision. An unrelated unknown does not demote a
closed one; a settled subdecision does not settle the whole architecture.
Conversational agreement confirms a clearly presented user policy, not project
facts or an incompletely specified proposal.

## Stabilize and replace

A settled decision retains relied-upon premises, resolution, material rejected
alternatives, accepted tradeoffs, falsifiers, and reopen conditions. Replace it
only when authoritative evidence invalidates a premise, the user changes an owned
policy, implementation/integration/cost evidence violates an acceptance boundary,
or another candidate dominates under already accepted criteria.

A newly mentioned or fluent alternative is not a replacement trigger. When a
trigger qualifies, expose:

```text
previous decision and maturity
  -> changed evidence or policy
  -> affected premise and dependent decisions
  -> new resolution and maturity
  -> unchanged invariants
  -> plan delta and renewed evidence
```

Remove stale downstream guidance, while retaining enough replacement rationale to
prevent silent swing. Report the delta when it changes a previously presented
recommendation or plan.

## Falsify readiness

Change one input at a time: add/remove a caller; change one invariant, workload,
compatibility promise, or user policy; withhold a failure/lifecycle contract;
strengthen only user enthusiasm; add a nondominant alternative; or contradict one
premise with implementation evidence. Only dependent maturity, selection, scope,
or evidence may change.

Hard gate: no material unknown is hidden by a name or implementation detail; no
candidate settles without cone closure and material comparison; no recommendation
changes without a qualifying trigger and explicit delta; and no plan presents
exploratory architecture as ready production work.
