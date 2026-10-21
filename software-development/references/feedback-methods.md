# Feedback methods

Choose feedback that could change a consequential construction choice. Connect
the requested result to actual consumers and dependencies; a stand-in cannot
establish behavior it assumes. Use native input anchors and observations when
available, honoring later user steering. Let findings change the construction or
next investment; reopen governing contradictions through Admission. Stop when
further evidence would not change the decision, and reuse checks for delivery.

## Selection

| Claim | Development feedback | Distinguishing evidence |
| --- | --- | --- |
| Settled observable behavior at a stable seam | RED-GREEN-refactor | Intended RED, focused GREEN, refactor confirmation |
| Existing behavior under refactor | Reuse regression evidence; characterize uncovered behavior | Accepted baseline and focused evidence for changed obligations; probe a representative fault when sensitivity is uncertain |
| Domain or mathematical law | Law/property tests, derivation, or proof obligation | Positive, negative, boundary, and adversarial cases as applicable |
| Settled implementation flow, failure, ownership or topology | Applicable counterfactual inspection and focused probes | Inspect the changed obligation; inject a relevant fault when propagation, cleanup or sensitivity needs evidence, rather than exercising unrelated mutations |
| Cost or scale | Benchmark, profile, or counters against a budget | Reproducible baseline, workload, repetitions, result, and noise limits |
| Structural or style policy | Formatter, linter, type, dependency, or architecture tool | Applicable configuration/instruction and fresh tool result |
| External effect | Approved disposable integration with post-observation | Exact target, pre/post state, receipt, cleanup, and residue check |
| Uncertain domain or API | Bounded exploration | Discard or reframe the exploration, then settle or reopen the design before production implementation |

Combine methods only when the change makes different kinds of claims. Do not use a
large test matrix to compensate for an undefined contract. Reuse project-native
commands and fixtures; add a small helper only for observed execution friction,
kept with its project or task consumer.

## RED-GREEN-refactor

Use this protocol only after one domain behavior, public or durable boundary,
fixture, expected result/effect, and failure are settled.

1. Write the smallest test through the stable boundary.
2. Run it and confirm the failure is the intended missing or wrong behavior. A
   compile, import, fixture, or environment failure is not RED.
3. Implement the minimum coherent behavior and obtain focused GREEN.
4. Improve names, ownership, flow, and duplication while continuously green.
5. Add edge and failure cases required by the contract and rerun neighboring
   checks after the last edit.

Tests observe public behavior, domain laws, or durable logical invariants—not
private call inventory. Prefer deterministic fixtures and explicit clocks or
randomness. Mock external boundaries rather than the implementation under test;
real effects belong in separately authorized disposable integration tests.

Do not claim TDD without the observed intended RED, focused GREEN, refactor
confirmation, required edge cases, and fresh focused evidence. Do not manufacture
a test-first history for existing behavior.

## Characterization and mutation sensitivity

For behavior-preserving work, establish the relevant accepted baseline before
edits when it is needed to interpret the result; existing adequate evidence may
supply it. Add a representative semantic fault probe when a consequential behavior
is unprotected or the selected check's sensitivity is uncertain, then restore the
baseline. A protected local cleanup need not add tests or mutation machinery solely
for ceremony. Do not pretend existing behavior was developed test-first.

For a code-shape claim, choose the applicable counterfactual from
[implementation normal form](implementation-normal-form.md). Use
[conformance review](conformance-review.md) on the actual diff within that feedback.

## Laws, cost, structure, and effects

- Derive law/property cases from named invariants and preserve tolerances,
  provenance, and failure domains. Example tests do not replace a proof obligation
  when the contract requires one.
- For cost claims, name representative and limiting workloads, environment,
  warmup, repetitions, variance, and the acceptance budget. Reject semantic or
  recovery regressions hidden by a faster metric.
- Run structural/style tools only when relevant project configuration or task
  requirements select them; final findings and gating status belong to
  [conformance review](conformance-review.md).
- For effects, separate deterministic decisions from adapters. Use unique
  disposable scope, bounded timeouts, post-observation, cleanup, and explicit
  approval for real mutation.
