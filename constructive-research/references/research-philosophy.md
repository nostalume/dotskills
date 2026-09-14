# Research Philosophy

Use this reference for mathematical or physical derivation, construction,
compression, and reconstruction. Obstruction-driven construction is conditional:
descriptive inquiry, measurement, replication, literature synthesis, and accepted
result exposition do not need to invent an obstruction.

## Expose presumptions through derivation

Treat intuition as provisional formalization. Identify the phenomenon, typed
objects, relations, invariants, approximations, and plausible operations it
presumes. Derive consequences or failures, then revise only the premises that the
evidence reaches.

For every consequential claim or equation, expose:

```text
typed inputs and domain
  -> map, composition, quotient, substitution, variation, limit, or algorithm
  -> common target and explicit evaluation, witness, or certificate
  -> preserved or changed semantic content
  -> assumptions and failure boundary
```

An equation must arise from its operation rather than appear first and acquire an
interpretation afterward. A definition does not establish existence, uniqueness,
equivalence, or invariance. A theorem contract may bridge a step only when its
exact hypotheses, output, semantic role, and boundary match.

Prefer invariant, quotient, symmetry-adapted, normal-form, spectral, or
variational reasoning when it shortens or strengthens the complete route. Use
components when they are the observable representation, no structural reduction
is known, or a small independent check needs them; return the conclusion to its
invariant meaning.

## Construct from an obstruction when construction is the goal

When the inquiry asks why an object is necessary or seeks a reusable mathematical
operation, construct it from the capability it must supply:

```text
required capability
  -> cheapest typed candidate
  -> explicit failed equality, ambiguity, residual, or obstruction
  -> additional structure forced by that failure
  -> constructed object and operations
  -> witness, consequence, and refusal boundary
```

Do not introduce machinery whose necessity carries the argument without exposing
that necessity. When a foundation cannot reasonably be derived locally, state an
exact theorem contract. A finished formula without a generative origin remains an
ansatz or admitted theorem input, not an internally constructed object.

A construction is reusable only when it retains an operation for new admissible
inputs:

```text
Construct(data, capability, resource budget)
  -> generated object and reusable operations
  -> correctness or recovery certificates
  -> explicit failure or refusal
```

The interface is semantic and need not be software. Its input must not encode the
expected answer. Distinguish regression on known input, transfer to a structurally
new admissible input, and downstream use against the complete baseline route.
Regression alone verifies; transfer alone does not establish computational gain.

## Distinguish kinds of improvement

```text
reformulation   same objects and information in another representation
compression     less information or work for a named observable
reconstruction  different primitive objects or dynamics with controlled recovery
```

An invertible change may improve sparsity, conditioning, locality, or recursion
without being a new theory. A quotient is useful only relative to distinctions a
named observable cannot see. Judge construction, solution, and recovery cost
together.

A reconstructed theory must recover the earlier successful regime through a
specified bridge and controlled error, and produce a discriminating consequence
outside it. Failed approximations, proliferating repairs, singular behavior, or
collective structure can motivate reconstruction; none proves it. Separate
kinematics from dynamics, classification from realization, convention from
invariant, symmetry from selected dynamics, and exact statements from
approximations.

Finite derivation stays adjacent to the argument. Select
[computation](computation.md) only when execution must produce a required result or
carry inferential weight; a proof or construction does not imply code.
