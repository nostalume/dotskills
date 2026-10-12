# Conformance review

Review the actual final diff after implementation feedback and before delivery
verification. Planned pseudocode and predicted file shape are not evidence. Judge
the diff against the authorized contract, current architecture, repository rules,
and the nearest maintained analogues.

Use the [entry's development-loop trigger](../SKILL.md#development-loop) to select
[implementation normal form](implementation-normal-form.md); review does not
create architecture or authorize implementation edits.

## Review map

Apply the selected normal-form criteria only to claims the actual diff changes.
Then confirm:

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

For an authorized fix, repair the local defect and repeat affected feedback;
otherwise report it. For a governing contradiction, use entry Admission to reopen
the smallest decision. A resolution changing requested scope or policy needs user
direction, not an implicit implementation choice.

The review is complete only when no blocker remains, warnings are resolved or
explicitly accepted, and every later edit has caused the affected review slice to
be repeated.
