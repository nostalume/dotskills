# Conformance review

Review the actual final diff after implementation feedback and before delivery
verification. Planned pseudocode and predicted file shape are not evidence. Judge
the diff against the authorized contract, current architecture, repository rules,
and the nearest maintained analogues.

Apply the [implementation normal form](implementation-normal-form.md) when the
diff materially changes semantic flow, ownership, effects, failures, resources,
abstraction, compatibility, cost, or conceptual/physical topology. A file move or
routine edit alone is not a trigger. It consumes settled constraints; it does not
authorize a new architecture.

## Review map

Use the domain, authority, flow, failure, compatibility, resource, cost, and
topology criteria from [implementation normal form](implementation-normal-form.md)
only for claims the actual diff changes. Then confirm:

1. **Contract:** the authorized scope and settled constraints still hold.
2. **Project policy:** applicable instructions and maintained analogues support
   any style or structural rule treated as gating; taste alone is not a blocker.
3. **Economy:** no parallel authority, relay-only abstraction, speculative
   generality, compatibility residue without a consumer, or unrelated cleanup has
   entered the diff.
4. **Evidence:** each changed claim maps to feedback and final verification;
   documentation, automation, and release impact are stated.

## Findings and feedback

Classify each finding:

- **Blocker:** violates the accepted contract or invariant, duplicates authority,
  fragments an owner or inverts/hides a dependency/visibility boundary, hides an
  effect/failure, makes work or lifecycle materially unsafe/unbounded, breaks a
  supported consumer, lacks required evidence, or violates an evidenced
  repository gate.
- **Warning:** maintainability, cost, or consistency concern that does not currently
  violate an accepted claim; accept explicitly or correct it.
- **Note:** non-gating observation or follow-up outside the authorized scope.

Fix a local implementation defect and repeat the affected feedback. Reopen the
smallest architecture decision when the diff contradicts governing meaning,
ownership, topology, compatibility, lifecycle, or cost. Stop for user direction
when the only resolution materially changes the requested scope or policy.

The review is complete only when no blocker remains, warnings are resolved or
explicitly accepted, and every later edit has caused the affected review slice to
be repeated.
