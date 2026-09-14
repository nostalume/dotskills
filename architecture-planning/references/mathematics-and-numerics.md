# Mathematics and numerics

Use this lens only to project accepted mathematical domains, laws, dimensions,
orientation, scale, structure, conditioning, or solver policy into software
architecture. General runtime admission belongs to representation. When the
mathematical claim, derivation, or evidence itself remains unknown, use
[constructive research](../../constructive-research/SKILL.md) and return the exact
accepted claim and validity boundary before settling dependent architecture.

## Claims and domains

- Classify a claim only as far as the distinction changes representation or
  evidence: static, finite, combinatorial, algebraic, metric, or numerical.
- State the accepted domain, codomain, units, orientation, scale, capabilities,
  boundary cases, and refusal conditions that affect callers.
- Let types encode only relationships established at their construction boundary.
  Do not claim unbounded arithmetic, runtime identity, or mathematical evidence the
  language cannot prove.
- Separate mathematical proof obligations from type-checker, runtime, and solver
  evidence; name how each claim can be falsified.

## Structures and laws

- Keep representation, topology, geometry, algebra, duality, discretization, and
  numerical policy distinct when they have different owners or validity domains.
- Name every applicable identity, symmetry, composition, conservation, invariance,
  sign/orientation, dimensional, endpoint, and degeneracy law before selecting a
  representation or algorithm.
- Test accepted laws across representative, boundary, degenerate, orientation, and
  scale cases. A passing example or type check does not establish a general law.

## Scale and solvers

- State physical dimensions and expected scaling before implementation. Normalize
  fragile local computation deliberately and restore dimensions exactly; do not
  hide scale faults with a global tolerance or silent clipping.
- Separate structural rank or sparsity, residual, conditioning, forward error, and
  sign evidence. One does not imply another unless the accepted theorem says so.
- Make solver capabilities, failure/refusal states, accuracy claims, and caller
  policy explicit. Diagnostics never silently choose domain policy.
- Benchmark representative structure and scale only after correctness laws pass.
  Route material time, memory, retention, or recomputation choices to
  [cost and scale](cost-and-scale.md).

Hard gate: dependent architecture cites an accepted mathematical claim and exact
validity boundary; domains, units, laws, degeneracy, scale, solver evidence, and
refusal behavior are explicit wherever they can change the design.
