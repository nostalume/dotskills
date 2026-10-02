# Delivery verification

Close evidence over the actual final change. Bind every result to scope, command,
environment, revision or files, time, observed outcome, and limits. Development
feedback explains how implementation was guided; it is an input, not a substitute
for fresh final evidence.

## Invariants

- The final diff and accepted contracts determine the checks.
- Evidence is fresh after the last relevant edit.
- Every changed behavior, law, cost, structure, or effect maps to suitable focused
  or integration evidence.
- Persistent tests and operational acceptance remain distinct evidence classes.
- Produced artifacts are inspected, not merely created.
- Claims never exceed what was run and observed; blocked, failed, or skipped checks
  remain explicit in the report.

## Scope closure

Let the actual final diff—not a plan's stage count—determine what must be verified.
Keep independent claims reviewable and expose real code dependencies, but do not
infer publication or merge policy from development order. This reference closes
local evidence; external review, merge, and publication mechanics require separate
authority and current project rules.

## Closure

1. Freeze intended scope and inspect status, final diff, affected platforms,
   contracts, and conformance findings.
2. Map each changed claim or artifact to the evidence that must still hold after
   the last edit.
3. Run focused falsification checks, then relevant formatting, lint, type, static,
   dependency, and security checks.
4. Run applicable project-canonical checks for the changed scope (build, test, or
   package checks as relevant) from stable state.
5. When the change can produce process, filesystem, network, or host effects,
   verify them only in authorized clean disposable scope; post-observe outcomes and
   residue.
6. Inspect schemas, files, package contents, logs, hashes, or rendered output when
   the change produces them.
7. Record exact commands, exit codes, salient output, skipped checks, limits, and
   residual risks.

Prefer project-declared runners. Keep ad hoc verification under a task-scoped
temporary root, preserve its source inputs, and use native path forms for native
tools. A verifier script is evidence only when its source, inputs, command, and
result are retained.

Completion requires final-scope identity, no conformance blocker, fresh focused
and canonical evidence, artifact inspection where relevant, bounded effects, and
claims matching observed results. Do not substitute old CI, pre-edit tests,
plausible output, a merely started job, or manufactured RED-GREEN history.
