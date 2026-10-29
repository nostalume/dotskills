# Executable Research Computation

Use this reference only after symbolic, numerical, combinatorial, simulation,
data, or plotting execution must produce a requested result or bear inferential
weight because of scale, repetition, dependencies, nondeterminism, hardware, or a
required executable certificate. Ordinary finite derivation and bounded
calculation follow
[research-philosophy.md](research-philosophy.md). Reading this reference does not
by itself admit execution, a file, directory, notebook, or project.

## Admit execution

Identify what execution must produce: a requested observable or artifact, a
discriminating result, an independent check, or an error/cost boundary. Select the
least effectful adequate operation. A derivation, matched theorem contract,
admitted source or observation may already close the research obligation; code
availability or a more elaborate artifact adds no evidential force.

Before choosing a tool, state the result classes that would change the claim or
satisfy the request. A successful run establishes its result only under the
declared semantic, arithmetic, environment and domain conditions; it does not
establish a general theorem, model meaning or wider applicability.

## Organize execution around its use

A bounded one-off calculation can return a compact result, witness and boundary
to the existing argument, with execution scratch transient. Retain source or
outputs when a real replay, verification or reuse needs them; use
[research state](research-state.md) to choose their material boundaries.

Reuse compatible projects, environments and execution paths. Describe how the
needed commands exchange inputs and outputs, including units, schemas and
revisions that affect the research result. A Julia solver and Python plotter can
retain their native environments and entry points while sharing one research
directory; several commands in one package can serve different consumers.
Reproducibility depends on those paths and bindings, not a unique project, lock
file or runner.

Extract shared implementation or a common interface when repeated use actually
needs the same operation. Keep separate environments or projects where runtime,
protected data, hardware, distribution or independent maintenance warrants them.
Judge the split by its concrete dependencies and maintenance consequences; a
logical role, language or desire for self-containment alone supplies no reason.
Record the relevant owner, environment/configuration, supported commands, resource
and refusal bounds, and generated-output policy with the retained work.

## Choose the smallest substrate

Choose tools from the required operations and validity properties: coefficient
domain, symbolic equality, numerical behavior and resource bounds. Apply the
existing project's execution policy where that project owns the work, rather than
choosing a substrate from the first probe's language.

Use maintained packages for commodity rational arithmetic, matrix operations,
elimination, nullspaces, tensor canonicalization, quadrature, eigensolvers, data
transforms, and plotting. Retain a custom kernel only when coefficient domain,
rewrite orientation, canonical form, zero policy, termination, or resource refusal
is itself the research object. A CAS supplies execution, not semantic meaning;
unrestricted simplification or undecided symbolic equality is not a proof.

Prefer invariant or symmetry-adapted reductions before large expansion. Bound
time, memory, precision, seeds/repetitions, hardware, and output volume as relevant;
refuse work whose declared boundary cannot be enforced or observed.

## Canonical run and result

Bind the scientific question and admitted inputs to the operation actually run,
its observable or expected result, and its validity/refusal conditions. Input
references carry the revisions or digests needed to distinguish them. The
execution project owns runtime and dependency behavior, not the research claim.
Use the existing command, function or notebook interface that exposes this path.

Return the compact result with the witness/certificate or error evidence its use
requires. Make relevant tool/environment revisions, precision, seeds/repetitions,
instability and output identity recoverable. State incomplete, failed or refused
execution explicitly. Exact results replay under the request's declared mathematical
equivalence; approximate or stochastic results declare tolerances and accepted
variation. Byte identity is a separate requirement when exact bytes matter.

## Probe, certificate, and tool roles

- A **probe** discriminates a candidate and may disappear after its consequence
  is retained.
- A **certificate** reproducibly checks a result and stays bound to that result.
- A **tool** serves an independent consumer through an input/output, error,
  provenance and refusal contract.

These roles can use existing files and execution paths. Share code for demonstrated
common semantics; an independent check may need a different implementation.
A tool may be checked by a certificate but does not derive production authority
from that certificate or its tests.

## Retain execution material

Keep the source, dependency/configuration records, commands and small fixtures
needed for retained results. Caches, raw traces, logs and regenerable intermediates
remain ignored or transient unless their bytes have an admitted consumer or
evidential role. A notebook can expose an existing implementation rather than
duplicate it. Preserve user material when retiring owned scratch.

For a necessary migration, characterize the old result, port one usable semantic
slice, compare the result under its exact equivalence or declared tolerance and
failure behavior, then retire the replaced adapter only after its consumers have
moved. Reorganization is subject to the state reference's authority and recovery
requirements.

## Test computational leverage

When claiming computational leverage, compare complete routes on the same
requested result and required quality:

```text
(model/dynamics, preparation, observable, required accuracy and semantics)
  -> baseline route and complete cost
  -> proposed reduction and construction cost
  -> same-observable equality or controlled error
  -> recovery cost and failure boundary
```

Include decision-sensitive learning, representation, discovery/construction of
the reduced object, execution, verification, repair, and recovery of the requested
observable. Semantic compression may offer no cheaper computation; an invertible
reformulation may still gain locality, sparsity, conditioning, or recursion.
Compare observed transformation depth, time/memory, symbolic growth, conditioning,
reusable intermediates, assumptions, and recovery cost without pricing away
correctness or semantic preservation. Representation constrains admissible
channels but does not determine dynamics, preparation, or observables. State the
model class, accuracy, resource scale, and refusal rather than promising a
universal solver. This comparison establishes effective leverage only; it does
not decide whether a concept is explanatory or deductively productive.
