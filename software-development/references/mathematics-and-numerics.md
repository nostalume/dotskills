# Mathematics and numerics

Use when implementing an accepted mathematical or numerical contract. Preserve
its domain, laws, dimensions, accuracy, and validity limits; do not choose a new
domain policy, tolerance, solver guarantee, or mathematical claim here. If one of
those choices can change behavior or architecture and remains unsettled, stop and
report that decision.

## Preserve the accepted claim

- State only the input/output domains, units, orientation, ranges, boundary cases,
  and refusal conditions that affect this implementation.
- Distinguish mathematical guarantees from what finite machine representations,
  types, tests, and solvers actually establish. A type cannot prove unbounded
  arithmetic or a theorem beyond its construction boundary.
- Keep domain meaning, representation, and numerical approximation distinct when
  they have different owners or validity limits.
- Identify laws that can falsify the implementation—such as identity,
  composition, conservation, dimensional, orientation, endpoint, or degeneracy
  laws. Do not enumerate laws irrelevant to the accepted contract.

## Bound numerical behavior

- Respect finite ranges, precision, rounding, overflow/underflow, cancellation,
  and accumulation error where they can affect the result.
- Normalize fragile local computations only when the accepted contract permits
  it, and restore dimensions consistently. Do not hide scale faults with a global
  tolerance or silent clipping.
- Keep structural rank/sparsity, residual, conditioning, forward or backward
  error, and sign evidence distinct. One does not establish another without an
  applicable theorem.
- Apply tolerances only when their source, scale, units, and acceptance meaning
  are settled. Diagnostics do not silently choose domain policy.
- Make solver assumptions, supported inputs, accuracy claims, refusal/failure
  states, and caller-visible outcomes match the accepted contract.

## Falsify the implementation

Test laws over representative, boundary, degenerate, orientation, and scale cases
when applicable. Examples and type checks do not establish a general theorem.
Separate proof obligations from runtime and solver evidence. Use
[feedback methods](feedback-methods.md) to select the cheapest evidence that can
falsify each mathematical or numerical claim. Benchmark only after correctness
obligations pass, against an accepted workload and budget.

Hard gate: the implementation preserves the accepted mathematical claim and its
validity boundary; numerical behavior and refusal states are explicit wherever
they affect callers, and each claimed guarantee has evidence appropriate to that
claim.
