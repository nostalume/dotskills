# Representation and flow

Use this lens only to decide what values cross boundaries and how they are
admitted, transformed, selected, and evidenced. It owns data shape and semantic
flow, not state/effect authority, public compatibility, resource lifetime,
computational budget, or implementation syntax.

## Smallest complete representation

Choose the smallest representation that preserves the complete contract. Judge
simplicity by the concepts, boundaries, and transformations a reader must track,
not word or line count. Remove a layer or field only when its meaning, authority,
failure behavior, provenance, and recovery obligations remain explicit in another
owner.

Before adding an abstraction, identify the distinction or repeated transformation
it owns. Before merging representations, verify that meaning, contracts, and
lifecycles agree. Preserve necessary uncertainty and exact syntax in admitted
values; a short design that hides a dependency is incomplete, not simpler.

## Typed admission

- Prefer constructing an admitted type over check-then-reconstruct code.
- Decode unavoidable wire syntax once and invoke the schema/type constructor at
  the boundary. Pass only admitted values downstream.
- Encode alternatives as tagged variants and select once. Do not redispatch
  through nulls, strings, dictionaries, reflection, or repeated runtime-shape
  checks.
- Contain an unavoidable untyped edge in one adapter that returns a typed result.
- A dependency may replace interpretation only while schema authority,
  compatibility, dependency cost, and diagnostics remain explicit.
- Reject invalid or ambiguous construction with stable diagnostics; name the
  admitted type, selected variant, and next consumer.
- When runtime identity matters, bind it once during construction and carry it in
  the admitted value.
- When another owner requires single or at-most-one use, represent that admitted
  cardinality with native ownership/typestate or a contained explicit state. This
  lens chooses the encoding; [resources and recovery](resources-and-recovery.md)
  owns the lifecycle requirement.

## Semantic flow

- Give each transformation one admitted input and one explicit output or failure.
  A boundary exists only when it changes data, evidence, capability, or an owned
  state.
- Make variant selection, transformations, effects, and terminal handoff
  semantically ordered and locally attributable. Preserve errors, cancellation,
  and resource transfer across every edge.
- Share downstream flow only when input, output, failure, authority, lifecycle,
  and compatibility contracts agree.
- Route material repeated computation, copying, retention, or streaming choices to
  [cost and scale](cost-and-scale.md).

The settled flow constrains implementation behavior, not its preferred syntax.
Methods, functions, pipelines, recursion, iteration, local mutation, tail calls,
and handler shape belong to
[software development](../../software-development/SKILL.md) once they preserve the
accepted owners and transitions.

## Preserve evidence

- Preserve grain, schema, source identity, clocks, provenance, uncertainty,
  authority, and completeness through conversion.
- Keep failed, unavailable, uncertain, partial, stale, mismatched, changed, and
  nothing-found states distinct. Incomplete evidence cannot authorize a complete
  result.
- Bind an observation to the relevant source/subject identity, region or interval,
  operation, parameters, time, raw result, normalization, status, and diagnostics
  only where they affect the claim.
- Never promote a projection or interpretation to a stronger evidence class
  without an owner and an observable admission rule.
- Sync and async routes obey the same admission law; any mutation consuming
  evidence receives its admitted identity and completeness explicitly.

Hard gate: raw input is admitted once into explicit variants; each transformation
has an owned semantic purpose and failure; provenance and incomplete states survive
conversion; and selected evidence can falsify the admitted output contract.
