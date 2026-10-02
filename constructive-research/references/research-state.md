# Research State

Use this reference only when research dependencies or material ownership must
survive the current response, or when multiple outputs consume one supported
source. A transient derivation, one-output explanation, or informal frontier does
not require a state artifact.

## Bind logical state to canonical material

The logical state is a bounded dependency view, not a mandatory directory tree.
An edge names the exact value consumed downstream; it grants no authority or work
order. Keep these roles distinct:

| Role | Default representation | Authority |
| --- | --- | --- |
| logical record or edge | entry/reference in an existing owner | dependency only |
| canonical owner | existing or admitted durable material | research fact/content |
| projection | view pinned to owner revision and boundary | no independent truth |
| generated output | transient unless independently admitted | result, not claim owner |
| cursor or audit | transient agent space; Git ignore does not make it confidential | no durable research authority |

Keep transient agent records distinct from reader-facing outputs.

Inventory only relevant papers, notes, derivations, data, plots, notebooks, and
programs with location, role, revision, and reliability. Reuse compatible
canonical owners, but do not treat an established layout as evidence that its
records are clear or usable. If a layout obscures ownership, scope, evidence, or
re-entry, identify the smallest useful repair. Reorganization of user material
still needs separate authority and a recoverable migration. Without that
authority, report the limitation and propose a repair; make in-place content or
navigation changes only when the task itself authorizes them. Preserving a layout
is not endorsing its quality.

A compact state entry carries only stable identity, canonical owner and revision,
exact exported value, consumer and purpose, applicable boundary or disposition,
and open obligation. This is a navigation and dependency record, not a second
narrative owner. Keep motivation, method, evidence, and interpretation with the
canonical claim, derivation, observation, computation, or exposition they
describe; link to them rather than copying them into an index. Where future
interpretation, review, or action depends on context, that canonical record must
make its purpose, relevant scope, decision-bearing process or evidence, supported
consequence, and limits recoverable without relying on the conversation. Preserve
a failed or abandoned step only when its reason changes interpretation, prevents
repeated work, or affects re-entry; do not turn this into a complete activity
diary. These are adequacy questions, not mandatory fields: omit what cannot
change interpretation, review, or future action. Claim contracts, evidence
records, computations, and prose stay with their own owners. Successive
conceptual revisions replace back edges; version control, not a parallel archive,
preserves obsolete tracked wording.

Choose record boundaries by coherent question, scope, evidence/status, and
reader or revision need—not by graph node, edge, or possible path. Keep distinct
claims or attempts together when they share a clear purpose and can be reviewed
without ambiguity; separate them when different scope, authority, evidence
status, consumer, or lifecycle would otherwise be conflated. A single large file
is not preferable merely because it minimizes file count, and a directory or file
per logical graph element is not preferable merely because it mirrors a DAG.
Represent dependencies with concise references or an index instead of copying
whole source material into a master record. Before adding files, test whether a
reader can locate the purpose, boundary, supporting path, disposition, and open
obligation; repair unclear ownership, headings, links, or record boundaries
before expanding the collection. Apply the physical admission rules below only
after the information is intelligible.

## Admit durable material

Prefer, in order:

1. update a compatible canonical owner;
2. add a compact binding or dependency edge to an existing entry point; or
3. create a tracked artifact only when durable content has a named consumer and an
   independent format, review, execution, authority, resource, or output lifecycle.

A logical type, status, version, large note, or desire for self-containment does
not admit a file. A new directory additionally needs a shared build/tool boundary,
distinct authority/security or resource lifecycle, or requested output collection.
Generated material remains transient unless exact bytes are requested, consumed,
evidential, or materially unsafe/costly to regenerate. Record its generator,
inputs, revision, and boundary without making it a second claim owner.

When the existing layout is adequate, preserve its established naming and
placement. When it is not, prefer a minimal, reversible improvement that preserves
canonical ownership and makes navigation and boundaries clearer; do not move,
rename, split, merge, or delete existing user material without separate authority
and a recovery plan. Otherwise name by stable domain capability or artifact role,
not workflow status or vague sequence. Use the shallowest placement that leaves
ownership clear; do not create empty directories or one file per logical record.

## Build and project the smallest durable view

Identify the capability, phenomenon, theorem, observable, prediction, or algorithm
that matters. Bind its live claims/inquiries, presumptions, contradictions,
constructions, canonical owners, exact dependency values, consumers, and open
bridges. A prospective method or unperformed computation remains an obligation and
cannot export a result.

Multiple outputs pin projections of one semantic owner:

```text
supported construction, claim, or disposition
  -> paper A projection
  -> paper B projection
  -> plot or dataset projection
```

Only explicit consumers become stale when the owner changes. Promote, compact, or
drop newly produced material according to the [research loop](research-loop.md),
but never interpret `drop` as permission to remove pre-existing user material.
Before pruning a durable entry, move every exported value to a surviving owner or
preserve its missing boundary explicitly.

Execution material follows [computation](computation.md); reader exposition follows
[research writing](research-writing.md). Neither output becomes a second owner of
the underlying research meaning.
